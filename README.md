# CodeClauseInternship_FacialEmotionsDetection

### Facial emotion detection using ​artificial intelligence (​AI) involves analyzing facial expressions from images or videos to determine an individual's emotional state. This is achieved through the use of AI algorithms that are trained to recognize different facial features and patterns associated with various emotions such as happiness, sadness, anger, surprise, fear, disgust, and contempt.

![image](https://github.com/pavankalyanchittala/CodeClauseInternship_FacialEmotionsDetection/assets/117903644/3ef8bff3-7f46-4684-9d2a-80deafd0f51f)


#### The provided code implements face emotion detection using the '​DeepFace' library and the '​CascadeClassifier' class from ​OpenCV. Let's break down the code and understand how it works.

Importing Necessary Packages: The code begins by importing the necessary packages, including 'cv2' for OpenCV and 'DeepFace' for face attribute analysis.

Initializing the Cascade Classifier: The 'CascadeClassifier' class is initialized with the path to the XML file ('haarcascade_frontalface_default.xml'), which contains a pre-trained model for detecting faces.

Capturing Video: The 'cap' object is created using 'cv2.VideoCapture(0)', which captures video frames from the default camera. The number (0) can be changed to capture video from a specific camera source or a video file.

Processing Video Frames: Inside the while loop, the 'cap.read()' function captures each frame from the video. The video frame is then converted to grayscale using 'cv2.cvtColor(frame,0)'.

Detecting Faces: The 'classifier.detectMultiScale(frame,1.3,5)' function detects faces in the frame using the pre-trained face detection model. It returns the coordinates and dimensions of the bounding box for each detected face.

Analyzing Emotions: The 'DeepFace.analyze(frame, actions=("emotion",), enforce_detection=False)' function is used to analyze the emotions of each detected face in the frame. It returns a dictionary ('response') containing the emotion predictions with their corresponding percentages of accuracy.

Extracting Dominant Emotion: The dominant emotion is extracted from the 'response' dictionary using 'emotionPredPer['dominant_emotion']'. This represents the emotion with the highest probability.

Displaying Text on Frame: Text is displayed on the video frame using 'cv2.putText()'. The first call to 'cv2.putText()' displays a message to press 'q' to quit. The second call displays the dominant emotion on the frame using the coordinates of the bounding box.

Drawing Rectangle: A rectangle is drawn on the frame using 'cv2.rectangle()'. The rectangle surrounds the detected face and is drawn using the coordinates and dimensions obtained from the face detection.

Showing Video Frame: The processed frame is displayed using 'cv2.imshow()'. This shows the video frame with the text and rectangle overlay.

Exiting the Loop: The while loop continues until the user presses the 'q' key. This is detected by the 'cv2.waitKey(1) & 0xff ==ord('q')' condition. Pressing 'q' breaks the loop and the program ends.

Overall, the code captures video frames, detects faces, analyzes the emotions of the detected faces, and displays the dominant emotion on the video frame in real-time.
