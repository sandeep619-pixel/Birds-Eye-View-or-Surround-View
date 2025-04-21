# Birds-Eye-View-or-Surround-View
Surround view or Birds eye view

 
 
 
Initial Concept
Describe the initial concept for your capstone project.
 
Bird’s eye view in computer vision refers to a perspective in which the scene or objects are viewed from directly above, resembling the view one would have if they were looking down from the sky onto the scene.
This perspective is often achieved using techniques such as camera calibration, geometric transformations, and image processing.
It is a useful representation for processing 3D point clouds.
The purpose of obtaining a bird’s eye view in computer vision is to gain a comprehensive understanding of the spatial layout and relationships between objects in a scene.
This perspective can be particularly useful in various applications, including object tracking and detection, navigation and mapping, environmental monitoring, etc.
 
1)Initial Concept
 ![image](https://github.com/user-attachments/assets/aa955a29-ff13-4585-8937-d52454ea3229)

 
 
From where did your idea come?
My Idea came from already existing surround view system in CARS equipped with High end autonomous driving capabilities where Computer vision Algorithms are applied to multiple images captured from multiple cameras.
I wanted to explore if I can just take one image and convert to a top view using Image processing techniques and Image stitching(Transformation and Homography)
 
 
What inspired you?
Inspiration came from the fact that availability of multiple cameras are limited and if one can convert to Birds eye view with just one image
 
What two (or more) computer vision concepts are you using in your project? 
I am using  
1.Image processing technique- Create a discrete representation from a continuous Gaussian function
2.Image warping technique - Warp the image to a bird's eye view
 
2)Methods
Describe the methods used in your capstone.
cv2.cvtColor: Converts an image from one color space to another.
cv2.GaussianBlur: Blurs the image to reduce noise and details.
cv2.Canny: Performs Canny edge detection.
cv2.HoughLines: Detects lines in the image using the Hough Line Transform.
np.linalg.solve: Solves a linear matrix equation to find the vanishing point.
cv2.getPerspectiveTransform: Calculates a perspective transform from four pairs of points.
cv2.warpPerspective: Applies a perspective transformation to an image.
cv2.imread: Loads an image from a file.
cv2.imshow: Displays an image in a window.
cv2.waitKey: Waits for a key event.
cv2.destroyAllWindows: Destroys all OpenCV windows.
•	What libraries, APIs, frameworks, tools were used?
Libraries used- OpenCV (cv2) Numpy & matplotlib
 
 
•	How and why did you use them?
OpenCV was used to load image, Converts an image from one color space to another, Blurs an image using a Gaussian filter, Applies the Canny edge detection algorithm, 
Detects lines in a binary image using the Hough Line Transform, Reads an image from a file
NumPy is a fundamental package for scientific computing with Python
 
 
•	Results
Describe your results.
Results are as shown below. As you can see images that span over a large tilt seem to work well with this approach. Images that are at 180 degrees to camera view cannot achieve a Birds eye view.
Reason for this is the algorithm looks for 4 spanning points that have large area.This doesn’t work well with images captured straight
 
Guiding Questions:
•	What worked well for you?

Images that span over a large tilt seem to work well with this approach.  Example- Road 
•	What didn’t work well for you?

Images that are at 180 degrees to camera view cannot achieve a Birds eye view. Example- Car
•	Did you have any unexpected negative or positive results? 
 
I thought the image of Lion would achieve birds eye view but failed.Reason for assumption is that this image has large area on the Ground
![image](https://github.com/user-attachments/assets/f89690d7-cb96-40ff-8e3c-4988b8ad3877)
![image](https://github.com/user-attachments/assets/5f4a232a-2660-4996-9f6b-b186aab02f96)

![image](https://github.com/user-attachments/assets/f45760bd-f461-4fec-bfbd-edbacf4ce60b)
![image](https://github.com/user-attachments/assets/3b9e9627-b6e8-4b79-b661-fa41199c4785)



 
 
 
 
 
 
 
 
4 Lessons Learned
Some lessons learned are 
Computing a Bird's eye view with a single image is difficult as there are no multiple views and largely relied upon Image Homography . With multiple images and stereo vision Bird's Eye view can be improved to a larger extent as this would actually give multi view prepective and distance of objects
Guiding Questions:
•	What were your primary take-home findings?
Computing a Bird's eye view with a single image is difficult as there are no multiple views and largely relied upon Image Homography
•	What would you do differently next time?
Next time my approach would be to capture multiple images and use camera calibration techniques to find both intrinsic and extrinsic parameters and stich images from multiple cameras. If this fails I will be generating 3D point clouds using Stereo Vision technique learned in Module 8

