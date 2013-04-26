# Web Playback #

This lab is a starting point for exploring Media Services.

It consists of an ASP.NET MVC web application that lists and provides a player for the media assets that have [On Demand Origin Locators](http://msdn.microsoft.com/en-us/library/windowsazure/hh974308.aspx) associated with them -- that is, assets which are available for streaming from within your Media Service.

One way of creating an On Demand Origin Locator for a video is to publish a Smooth Streaming or HLS video from within the Management Portal.

This application does not support playing HLS videos, so in order to test it, you will need a published Smooth Streaming video asset.

## Getting the source ##

The sources for this project are at [https://github.com/rytmis/bootcamp-video-library](https://github.com/rytmis/bootcamp-video-library). 

Once you download and build the project, you will need to provide your Media Services credentials for the application. The parameters are named AccountName and AccountKey, and they can be set in:

+ Web.config
+ ServiceConfiguration.environmentname.cscfg
+ Web Role Configuration Settings in the Management Portal (for deployed applications)

Once you configure the settings and run the application, it will display your published On Demand Origin Locators as a list. Clicking on a list item will load the files contained within that publishing endpoint. The primary Smooth Streaming file will contain a link to the Smooth Streaming manifest. Clicking on the link will open the stream in a Flash-based media player.

## Ideas to pursue ##

Since the bare-bones implementation only lists videos with On Demand Origin Locators, an obvious next step would be to add a view that lists videos *without* them, providing a way to publish video assets for viewing from within the library. To do that, you will probably need to look at:

> mediaContext.Locators.CreateLocator(LocatorType, IAsset, IAssetPolicy)

Note that On Demand Origin Locators are only useful for Smooth Streaming and HLS assets. If you wish to publish a regular video file (for instance, a standalone MP4), you should create an SAS locator for it.