# Object-Tracking
Rugved taskphase

Necessary libraries (cv2,numpy,time) are imported.
cap is an instance of the VideoCapture class, it is assigned a method 'read()' which returns two return_parametres
a "boolean value" and the "frame"(the video is composed of frames which are read and acted upon one at a time)
The loop runs until the ret gets a value false which indicates the end of video or some unexpected corruption in the videofile.

hsv stores the frames in the 'HSV' colour channel. This is needed as an input parameter to create a mask around the ball.
A mask is created around the ball according to the min and max range of HSV values given as a NUMPY array .

Next we detect countours in the mask(which in my case was just one ... a single ball), store the largest contour .
'M' is a dictionary which stores the values of intensities of the coordinates which is used to calculate the centre of the ball.
(This can be thought in parallel lines with finding the centroid of a figure where M['m10'] represents the summation of x_cord masses while M[m01] represents the weighted value for the y coordinates.
which are divided by M[m00] which would give us the centroid ) 

A circle is then drawn with suitable choice of radius and is displayed through the cv2.circle() in sync with the running video.


NOTE:
The lower and upper boundn values are taken by approximation by seeing the variation in the same.
