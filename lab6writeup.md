# E190uLab6
## Lab6 Write-Up
#### Introduction:
The goal of this lab was to use our motion detection from lab 5 as a control scheme in a game of Pong.

#### Design & Testing Methodology:
We were given a Python implementation of Pong as a reference.  Rather than piping code from C to Python I decided to use the cv objects to draw Pong on top of the video display of the hand detection.  Instead of programming an opponent as typical in pong, I simply created a "goal" on the opposite side of the player that the player can score points in.  The score is added to when the player hits the ball in the goal and subtracted from when the player misses the ball and lets it hit the wall behind the player.  In addition to the up and down movement being controlled by the player's hand moving up and down, if the player moves a certain amount to the right, the ball is sped up.  Similarly, if the player moves the same distance to the left, the ball slows down to half speed.

#### Results and Discussion
The implementation of Pong using OpenCV objects worked out surprisingly well. While the motion controls don't work perfectly with the game, they do work consistently enough to make the game playable.

#### Conclusions
Time spend on lab: about 8 hours.
I was unclear as to whether we were supposed to use the Python implementation of the game we were given or not.  Thus, I spent a long time trying to get my C code to work with the Python code when the easier solution was to just add pong to the hand detection code from the beginning.
