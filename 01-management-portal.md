# Processing videos using the Management Portal #

## Prerequisites ##

In order to complete this lab, you will need a Windows Azure account.

## Creating a new Media Services account ##

Log in to the [Windows Azure Management Portal](https://manage.windowsazure.com) and select "Media Services" from the left.

Click on the button labeled + NEW:

![](images/01-create-media-service.png)

A dialog for creating a new Media Service pops up:

![](images/02-create-media-service.png)

Choose a unique name and a region for your Media Service. For the storage account, you may either create a new account or use an existing one.

Finish this step by clicking on Create Media Service.

The actual creation of a Media Service will take a while. Once it has completed, the Media Service will appear in your list:

![](images/03-media-service-ready.png)

You can now access your Media Service by clicking on its name.

## Uploading a video ##

Open the Media Service you just created by clicking on its name in the Media Services list. You will see the Media Service Quick Start screen. Click on the Upload button at the bottom of the screen:

![](images/04-media-service-quickstart.png)

A dialog for uploading a media file pops up:

![](images/05-upload-media.png)

Because uploading a large file takes a long time, we recommend that you use a small, local media file for this hands-on lab.

### Uploading a local file ###

If you have a media file that is smaller than 200 MB in size, you can use the From Local option. Browse for the file on your local computer, select it and give it a name:

![](images/06a-accept-local-upload.png)

Click on the check mark to begin the upload.

### Uploading a file from a storage account ###

If your media file is larger than 200 MB in size, you will have to upload it to a storage account first. In order to do that, you will need a client application such as [Azure Storage Explorer](http://azurestorageexplorer.codeplex.com/downloads/get/160100). 

Once the file is in a storage account, click the From Storage button.

A dialog for selecting a media file from a storage account pops up. Navigate to the file you wish to use, select it and click Open:

![](images/06-upload-from-storage.png)

You will be taken back to the previous dialog. Add a name for your media file and click on the check mark to begin uploading the media file to your Media Service:

![](images/07-accept-upload.png)

The upload process will take a while, depending on the size of your media file and whether you uploaded a local file or a file located in a storage account.

Once the upload is completed, your new Media Asset will appear on the Content tab of your Media Service:

![](images/08-content-after-upload.png)

## Encoding a video for Smooth Streaming ##

Go to the Content tab of your Media Service and select the Media Asset you uploaded in the previous step. Click on the Encode button in the bottom toolbar:

![](images/09-encode.png)

A dialog for selecting an encoding preset and a name for the resulting Media Asset pops up:

![](images/10-start-encode.png)

Type in a name for the resulting Media Asset and click on the check mark.

Once the encoder job has started, go to the Jobs tab to view the status of the encoder job:

![](images/11-encoding-started.png)

The encoding job will take a while depending on the length and quality of your media asset and your selected encoding preset. A HD quality 10 minute video encoded with the Playback on PC/Mac (via Flash/Silverlight) preset takes approximately 20 minutes to encode.

## Publishing and playback ##

Once the encoding job has finished, go to the Content tab and select the new Media Asset. 
Click on Publish in the bottom toolbar and then click Yes in the confirmation box that pops up.

Click on Play in the bottom toolbar to test the playback.

![](images/12-playback.png)

That's it, you're done with the first hands-on lab! In the next part we will upload and encode a video asset using the Media Services API.