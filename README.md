# Air Doodling/Note Taking With GCP(VisionAI), OpenCV and Evernote API
This project is made using a service from Google Cloud Platform and packages like cv2 and Evernote API.  

## What does it do?
The script has three main features:
1. Use cv2 to detect and track the movement of a color specified.  
2. Take the doodle made drawn on the canvas by the user and translate into a string using Vision AI by GCP.  
3. Append all th text/image to a note and upload the note to Evernote.  
  

## Detailed Working
### cv2
Webcam is used to capture frames.  
Color detection is done using cv2 and a mask is applied to narrow down on the roi.  
Erosion reduces the impurities present in the mask and dilation further restores the eroded main mask.  
The coordinates of the color being tracked are stored and are projected onto a canvas.  

### GCP  
VisionAPI is a free service upto first 1000 requests.  
VisionAPI has a use case of handwriting detection.  
The handwritten words drawn on canvas are saved and an image/png and a request is made to the API.
The API returns a string which is then concatenated body of previous requests/responses.  
[Docs](https://cloud.google.com/vision/?hl=en_US)

### Evernote API
There are two options for storing notes.  
1. Text  
2. Doodle/Drawing  

The text uses GCP to convert while the image is uploaded directly by generating a MD5 checksum of the same.
The API initializes client, welcomes the user and lists the notebooks.  
The user can then select the type of note (Text, Drawing)  
Finally the appropriate syntax of creating a new note is used and the request is sent.  
[Docs](https://dev.evernote.com/doc/articles/core_concepts.php)

### Demo
Doodling hello faizan
![Screenshot (111)](https://user-images.githubusercontent.com/52961945/127783199-78b98ef3-e93c-4699-96b2-6d2948e93555.png)  
![Screenshot (112)](https://user-images.githubusercontent.com/52961945/127783200-9f035f2d-4352-451a-95c8-3f44ab01800e.png)  
As Save and Exit option is selected makeNote function is called and an attempt is made to create a new note.  
In the image below we see that the note was successfully created
![Screenshot (113)](https://user-images.githubusercontent.com/52961945/127783208-5ee2fa45-e4fa-462d-848e-222b902b23c7.png)  
  
Made an error as confused i for r in faizan.
