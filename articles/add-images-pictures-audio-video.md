<properties
	pageTitle="Upload images, take a picture, play an audio and video file in PowerApps Studio | Microsoft Azure"
	description="Use PowerApps Studio to add images, audio, video, microphone, and pen features to your app"
	services=""
	documentationCenter=""
	authors="MandiOhlinger"
	manager="dwrede"
	editor=""/>

<tags
   ms.service="powerapps"
   ms.devlang="na"
   ms.topic="article"
   ms.tgt_pltfrm="na"
   ms.workload="na" 
   ms.date="10/27/2015"
   ms.author="mandia"/>

# Using the image, picture, audio, and video multimedia options

In PowerApps Studio, there are several multimedia options available. You can use these options to do various things, including: 

- Upload images to your app
- Take pictures using the camera on your mobile device
- Import audio and play it within your app
- Add a video and play it within your app
- Use the microphone on your mobile device to make a recording
- Use a pen on a tablet to create a sketch or a drawing

This topic shows you how to do add these multimedia options to your app in PowerApps Studio. 

> [AZURE.TIP] New to PowerApps? Curious about what we're talking about? Go to [PowerApps](http://www.kratosapps.com).

### Prerequisites

- Install [PowerApps Studio](http://aka.ms/powerappsinstall). Create a new app or open an existing app in PowerApps. The following multimedia options are available within your app:  
![][19] 
- To familiarize yourself with configuring controls in PowerApps, step through the [configure a control](get-started-test-drive.md#configure-a-control).


## Upload an image or add a picture
In your PowerApps app, you can add an image and add a picture. Use the **Image** option to add a stationary picture when creating your app, like a company logo. If you're creating a travel app, you can add pictures of exotic travel destinations, city skylines, and common attractions. If you're creating a pet adoption app, you can add pictures of the animals available for adoption. 

Use the **Picture** option to give your app users the ability to upload pictures. If you have an insurance app, users can upload pictures of the items they want to insure, like a car or a motorcycle. If you have a dating app, users can upload pictures of themselves.

This section lists the steps to add an Image and Picture controls to your app.

#### Add an image 
1. On the **Insert** tab, select **Image**:  
![][2]  
2. On the **Content** tab, select **Image**, and then select **Add an image file**.
3. Browse and select the file that you want to use, and then select **Open**. The image you selected appears in the control you added:  
![][3]  

####  Add a picture
1. On the **Insert** tab, select **Media**, and then select **Add Picture**:  
![][20]  
2. Preview your app: ![][1]. The picture control automatically adds an **Add Picture** button. When you select it, an explorer window opens. Select your picture and select **Open**.  
	The picture is displayed in the control you added. 


## Take a picture using the camera control
Take multiple pictures with the camera on your computer or mobile device. Then, show the pictures in an image gallery. These steps use the camera on your computer. To follow these steps, start the camera on your computer or mobile device. 

1. On the **Home** tab, select **New Screen**.
2. On the **Insert** tab, select **Media**, and then select **Camera**:  
![][4]  
3. Select **Allow** if prompted. Rename the control to **MyCamera**:  
![][5]  
If your camera is enabled, it shows a live image of wherever it's pointed, which may be you. Smile.

4. Set the **OnSelect** property of **MyCamera** to the following function:  
```Collect(MyImages, {SinglePicture:MyCamera!Photo})```  

	![][6]  
When you click the camera, a picture is taken, and saved to a collection named **MyImages**; which we'll show you shortly. 

5. On the **Insert** tab, select **Gallery**, and then select the vertical **Image Only** gallery:  
![][7]  
You can easily resize the image gallery by clicking-and-dragging the corner. This control also has a scroll bar. 
5. Resize the image gallery until you see three images in the gallery. Select the second image. This puts a grey border around the entire control:  
![][8]  
	Set its **Items** property to MyImages:  
	![][9]  
6. Preview your app: ![][1]. To take pictures, select **MyCamera** multiple times. Each picture that you take is shown in the gallery. Press the **Esc** key to go back to the app designer. 
7. Select the first image in the gallery. Set its **OnSelect** property to the following function:  
```Remove(MyImages, ThisItem)```

8. Preview your app: ![][1]. Select any image in the gallery. The image you select is now removed. Press the **Esc** key to go back to the app designer.

> [AZURE.NOTE] 
> - When you create a collection, you can see what's in your collection by going to the **File** tab, and then select **Collections**.  
> - When you select the first item in the gallery, any changes you make apply to everything in the gallery. In this example, we selected the first image in the gallery and updated it's **OnSelect** property. This means that the changes you make apply to all images in the gallery.  
> - If you close the app, you'll lose the images that you've collected. If you want to keep them, go to the **File** tab, select **Save**.


## Add audio and play it in your app
Configure an audio control to play a file in any format that Internet Explorer supports, including the audio portion of a video file. For example, you can use a .wma file. If you don't have an audio recording, you can create your own using the **Sound Recorder** or **Voice Recorder** apps in Windows. Search for **Sound Recorder** or **Voice Recorder** to open it.

1. On the **Home** tab, select **New Screen**.
2. On the **Insert** tab, select **Media**, and then select **Audio**:  
![][10]  
3. On the **Content** tab, select **Media**, and then select **Add an audio**.
4. Browse for the audio file that you want to play. Select **Open**. The **Media** property of the audio control is set to the name of the file that you added. Select the play button near the left side of the audio control:  
![][11]  

	The file plays. You can also use the audio control to play sounds that you record using the **Microphone** control (also on the **Insert** tab > **Media**).

## Add video and play it in your app
Configure a video control to play a file in any format that Internet Explorer supports. For example, you can use a .wmv file. If you don't have a video, you can create your own using the video recording feature of your webcam.

1. On the **Home** tab, select **New Screen**.
1. On the **Insert** tab, select **Media**, and then select **Video**:  
![][12]  
2. On the **Content** tab, select **Media**, and then select **Add a video**.
3. Browse for the file that you want to play. Select **Open**. The **Media** property is set to the name of the file that you added. Select the play button in the center of the control to watch your video:  
![][13]  


#### Play a YouTube video
You can also play videos from external sources, including YouTube. 

Select the video control. Set its **Media** property to the URL of the video you want to show. For example, set it to the following video on the Microsoft YouTube channel:  
[https://www.youtube.com/watch?v=tGGCHmb9bro](https://www.youtube.com/watch?v=tGGCHmb9bro)  
![][14]


**Note** Use double quotation marks around the URL.

Preview your app: ![][1]. Select the play button and watch the video:  
![][15]  

To return to the app designer, press the **Esc** key.


## Use the microphone to make recordings and play them in your app
Using the microphone to create recordings, and show these recordings in a gallery. 

1. On the **Home** tab, select **New Screen**.
1. On the **Insert** tab, select **Text**, select **Input Text**, and rename the new control **Description**:  
![][21]  
2. On the **Insert** tab, select **Media**, and select **Microphone**. If prompted for permissions, select **Allow**.
3. Rename the control to **MyMicrophone**, and set its **OnStop** property to the following function:  
```Collect(Interviews, {Recordings:MyMicrophone!Audio, Notes:Description!Text})```  

	![][16]  
	By using this function, you create a collection named **Interviews**, which contains a column named **Recordings** and a column named **Notes**. Each row contains a sound file that you create by using the microphone and any text that the Input Text control contains when you stop recording.

4. On the **Insert** tab, select **Gallery**, and under **Custom Galleries**, select **Portrait**. Set the Portrait gallery's **Items** property to **Interviews**.
5. Select the first item in the gallery, select the **Insert** tab, select **Media**, and then select **Audio**.
6. Set the **Media** property for the audio control to ```ThisItem!Recordings```.  
	**Note** You can save visual space by shrinking the audio control so that only the play button appears.
7. Add a label to the first item in that gallery, and set the label's **Text** property to  ```ThisItem!Notes```. Your gallery control looks similar to the following:  
![][17]
8. Preview your app: ![][1]. Type a phrase in the Description box, and then select **MyMicrophone** to start recording. When done recording, select **MyMicrophone** again to stop recording.

	Your description appears in the first item of the gallery, and your recording plays if you click the play button in the audio control.

	Type something else in the **Description** box, and make another recording. Repeat as many times as you want. Each description and recording appears in the gallery.

Press the **Esc** key to return to the app designer.

## Use the pen to write or draw directly within the app
Create multiple drawings (or simulate a whiteboard), and show the results in a gallery.

1. On the **Home** tab, select **New Screen**.
1. On the **Insert** tab, select **Text**, select **Pen**, and then rename the new  pen control to **Sketches**. 
2. On the **Pen** tab, select **Show Controls**:  
![][18]  
	Confirm that ```ShowControls``` is equal to ```true``` in the Function Bar. 
3. Add a button, set its **Text** property to ```Add``` and set its **OnSelect** property to the following function:  
```Collect(Creativity, {Captures:Sketches!Image})```
4. On the **Insert** tab, select **Gallery**, and select the vertical **Image Only** gallery. Shrink the width of the gallery to show three items. 
5. Set the gallery's **Items** property to ```Creativity```.  
> [AZURE.NOTE] At anytime, you can resize and move the controls. 
6. Preview (![][1]) to see what you created. 

	Draw or write something in **Sketches**, and then select the **Add** button. The contents of the pen control appear in the first item of the gallery.

	Select the clear button (with the "x") in Sketches, write or draw something else in it, and then select the **Add** button again. The contents of the pen control appear in the second item in the gallery.

Repeat these steps as many times as you like. Press the **Esc** key to return to the designer. 

You can also convert written text to typed text:

1. Add a label, and set its **Text** property to ```Sketches!RecognizedText```.
2. Preview your app: ![][1]. Write a word in the pen control. The label shows the word as typed text.

## Tips and Tricks
- In the **File** tab > **Media**, you can also upload images, videos, and audio files. When you add one of these controls to your app, set the **Media** property to the name of the file. For example, you uploaded an audio file named MySuperAudio.wmv. In your app, set the **Media** property of the Audio control to ```MySuperAudio```.
- At anytime, you can select the preview button (![][1]) to see what you created and test it.
- When designing your app, you can resize the controls and move them around using click-and-drag.
- Press **ESC** to close the preview window.
- **Save** your work using the **File** menu, or press **Ctrl** + **S**.


## What you learned

In this topic, you:

- Learned the difference between adding an image control and adding a picture control to your app. 
- Added single images and used the Camera control to take pictures. You used Excel-like functions to create a collection to display the pictures you took. 
- Used the Audio and Video control to add sound and videos to your app, including playing a YouTube video. 
- Additional multimedia options, including the Microphone and Pen controls, are available to make recordings, and write text directly in the app. 


[1]: ./media/add-images-pictures-audio-video/preview.png
[2]: ./media/add-images-pictures-audio-video/insertimage.png
[3]: ./media/add-images-pictures-audio-video/imagecontrol.png
[4]: ./media/add-images-pictures-audio-video/camera.png
[5]: ./media/add-images-pictures-audio-video/renamecamera.png
[6]: ./media/add-images-pictures-audio-video/onselectfunction.png
[7]: ./media/add-images-pictures-audio-video/verticalimage.png
[8]: ./media/add-images-pictures-audio-video/threeitems.png
[9]: ./media/add-images-pictures-audio-video/itemsmyimages.png
[10]: ./media/add-images-pictures-audio-video/audio.png
[11]: ./media/add-images-pictures-audio-video/audiorecording.png
[12]: ./media/add-images-pictures-audio-video/video.png
[13]: ./media/add-images-pictures-audio-video/videorecording.png
[14]: ./media/add-images-pictures-audio-video/youtubemedia.png
[15]: ./media/add-images-pictures-audio-video/youtubevideo.png
[16]: ./media/add-images-pictures-audio-video/microphoneonstop.png
[17]: ./media/add-images-pictures-audio-video/gallery.png
[18]: ./media/add-images-pictures-audio-video/pentab.png
[19]: ./media/add-images-pictures-audio-video/allmedia.png
[20]: ./media/add-images-pictures-audio-video/addpicture.png
[21]: ./media/add-images-pictures-audio-video/renameinputtext.png