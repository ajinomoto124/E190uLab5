# E190uLab5
## Lab5 Write-Up
#### Introduction:
This lab was an introduction to OpenCV and Cuda on the Jetson TK1

#### Design & Testing Methodology:
I adopted the hand detection algorithm we were given to work a little more consistently.  This code was written using the C implementation of OpenCV.  Initially the hand detection did not work very well and picked up the door in the room as the "hand" a large amount of the time.  After going into GIMP and checking some HSV values, I was able to modify the color range that the program detected as a "hand" so it was able to pickup my hand more often. After lowering the number of fingers the program checked down to 4 instead of 5, it improved the accuracy considerably.  I added some printf statements that checked whether the hand y position had changed by a value of 15 in either direction to detect up and down movement.  Once I was satisfied with the program's ability to detect vertical hand movement, I set about to implement the functions on the gpu.  To do this, I first had to convert the C specific OpenCV code to its equivalent C++ version.  Then it was just a matter of calling the cv functions on the gpu.

Here are some screenshots that show the program displaying whether the hand moved up, down, or stayed stationary.
![alt-text](https://github.com/ajinomoto124/E190uLab5-6/blob/master/Screenshot%20from%202015-03-12%2016_26_35.png)
![alt-text](https://github.com/ajinomoto124/E190uLab5-6/blob/master/Screenshot%20from%202015-03-12%2016_26_53.png)

#### Results and Discussion
Modifying the hand detection program to consistently detect hands was a fairly successful venture.  However, I ran into difficulty when porting my code from C to C++ and then onto the GPU.  I was able to edit the Makefile to use a cpp version of my c file but my code was unable to compile on the gpu/C++ version so I was forced to revert to an earlier C version.

#### Conclusions
Time spend on lab: about 10 hours.
It was a little unclear to me as to whether we were supposed to start with the OpenCV samples or the hand detection code we were initially given.  I did not realize until it was too late that I would have to convert code in C++ in order to use the GPU processes and I spent a large amount of time trying and failing at doing so.
