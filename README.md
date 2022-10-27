## Capture Video from Camera

Generally, we have to capture live stream with camera. OpenCV provides a very simple interface to this. Let’s capture a video from the camera (I am using the in-built webcam of my laptop), convert it into grayscale video and display it.

To capture a video, you need to create a VideoCapture object. Its argument can be either the device index or the name of a video file. 

Device index is just the number to specify which camera. Normally one camera will be connected (as in my case). So I simply pass 0 (or -1). *You can select the second camera by passing 1 and so on. After that, you can capture frame-by-frame. 


At the end, don’t forget to release the capture.

## Playing Video from file

It is same as capturing from Camera, just change camera index with video file name.

Also while displaying the frame, use appropriate time for cv2.waitKey().

If it is too less, video will be very fast and if it is too high, video will be slow (Well, that is how you can display videos in slow motion).

25 milliseconds will be OK in normal cases.

## Saving a Video

We capture a video, process it frame-by-frame and we want to save that video.

This time we create a VideoWriter object. We should specify the output file name (eg: output.avi). Then we should specify the FourCC code (details in next paragraph). Then number of frames per second (fps) and frame size should be passed. And last one is isColor flag. If it is True, encoder expect color frame, otherwise it works with grayscale frame.

FourCC is a 4-byte code used to specify the video codec. The list of available codes can be found in fourcc.org. It is platform dependent.



