# Web Playback #

This lab is a starting point for exploring Media Services. There is no predefined goal -- take the project for a quick spin and play around. 

It consists of an ASP.NET MVC web application that lists and provides a player for the media assets that have [On Demand Origin Locators](http://msdn.microsoft.com/en-us/library/windowsazure/hh974308.aspx) associated with them -- that is, assets which are available for streaming from within your Media Service.

## Getting the source ##

The sources for this project are at [https://github.com/rytmis/bootcamp-video-library](https://github.com/rytmis/bootcamp-video-library). 

Once you download and build the project, you will need to provide your Media Services credentials for the application. The parameters are named AccountName and AccountKey, and they can be set in:

+ Web.config
+ ServiceConfiguration.environmentname.cscfg
+ Web Role Configuration Settings in the Management Portal (for deployed applications)

Once you configure the settings and run the application, it will display your published On Demand Origin Locators as a list. Clicking on a list item will load the files contained within that publishing endpoint. The primary Smooth Streaming file will contain a link to the Smooth Streaming manifest. Clicking on the link will open the stream in a Flash-based media player.