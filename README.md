# face_detection
This face detection lgorithm uses haarcascade_frontalface_default.xml

1. Cascade Classifier loads the XML file name 'hi.xml'. This file contains neccessary information about detecting the faces 

2. b: Initialises a video capture objec to capture video  from the default camera (index 0)

3. while True: Continually captures faces from the camera and perform face detection

5. c_rec, d_image: D_image reads the frame from the video object b where as c_rec is boolean indicating twhether the fram has been successfully read

6. Then we convert captured frame BGR(Blue Green Red) to gray scale

7. Gray Scale images simplify the processing

8. f = a.detectMultiScale(e, 1.3, 6): Detects faces in the grayscale image using the detectMultiScale method of the cascade classifier a.

9. for (x1, y1, w1, h1) in f:: Iterates over each rectangle in the list f, where (x1, y1) are the coordinates of the top-left corner of the rectangle, w1 is the width, and h1 is the height.

10. 'cv2.rectangle(d_image, (x1, y1), (x1 + w1, y1 + h1), (255, 0, 0)): Draws a rectangle around the detected face on the original BGR color image d_image. The rectangle is drawn using the coordinates (x1, y1) of the top-left corner and the calculated width w1 and height h1. The color of the rectangle is specified as (255, 0, 0), which represents blue in BGR format.

11. 'cv2.imshow('img', d_image): Displays the modified image with rectangles drawn around the detected faces. The window is titled "img".

12. h = cv2.waitKey(40) & 0xff: Waits for a key press for 40 milliseconds. If a key is pressed, its ASCII value is stored in h

13. if h == 27: # 27 is the ASCII code for the escape key: Checks if the ASCII value of the pressed key is 27, which corresponds to the escape key. If so, it breaks out of the loop.

14. b.release(): Releases the video capture object, releasing the camera resource.

15. cv2.destroyAllWindows(): Closes all OpenCV windows. This function is called after exiting the loop to close the window displaying the captured video stream.