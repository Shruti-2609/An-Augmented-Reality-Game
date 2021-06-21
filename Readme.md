An Augmented Reality Game

This project uses OpenCV, a hand tracking model and a physics engine. 
To create our simple augmented reality game, we detect the hand points then define those points and also a few balls as bodies for Pymunk.

I have used four python libraries in this project which are Mediapipe, Numpy, Pymunk and OpenCV.
To install these libraries we use "pip Packages" and we can simply type the following commands:-
~ pip install pymunk
~ pip install mediapipe
~ pip install numpy
~ pip install cv2

This project is made in three steps:
1. To find the position of hands I used a Hand Tracking Model
2. To handle the collision of balls and hands I used a physics engine
3. I gave the output of the hand tracking model to the physics engine to see the final results

By using Pymunk library, I defined the space module for mentioning gravity to be used in physics engine.
Then, I have defined 100 balls of radius 12 units each as dynamic bodies by using a method 'enumerate()', along with their mass and moments as required in the physics engine to identify them. I have also defined their shape uniformly.

I have defined Fingers as kinematic bodies used in the physics engine. The finger's radius are taken to be 20 units each. 
There are seven different colours of balls defined in the next step in line 30.

I am using the hands module of mediapipe library as mp_hands. The hands module creates a 21 points based localization of your hand. What this means is that if you supply a hand image to this module, it will return a 21 point vector showing the coordinates of 21 important landmarks present on your hand.

To read the video from webcam I have used OpenCV library.
Some terms used in this project which we need to know are as follows:-
max_num_hands: The number of hands that you want Mediapipe to detect. Mediapipe will return an array of hands and each element of the array (or a hand) would in turn have its 21 landmark points.
min_detection_confidence, min_tracking_confidence: When the Mediapipe is first started, it detects the hands. After that, it tries to track the hands as detecting is more time-consuming than tracking. If the tracking confidence goes down the specified-value then again it switches back to detection. Here, their values are 0.7 each.

Then the traced coordinates are converted into integral coordinates. And the velocity of the balls are increased by multiplying them with 14.0
We can obtain the velocity vector by subtracting the previous position from the current position vector. 

From physics engine, we will get the position of balls in integral form and draw them.

I am using a fixed time step as it is highly needed. Doing so will increase the efficiency of the contact persistence, requiring an order of magnitude fewer iterations to resolve the collisions in the usual case.

The function imshow() displays an image in the specified window.
The function waitKey waits for a key event infinitely or for delay milliseconds, when it is positive.

I am so glad to complete this interesting game project. 
I was inspired by Amirabbas Asadi.
