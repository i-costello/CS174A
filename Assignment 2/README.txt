Ian Costello
CS 174A Project 2

Controls:

Move with WASD to line up your shot.
Shoot the ball with Space
Reload the ball with Enter


Animations:

I used Math.sin for most animations. For the animation that starts when the ball is thrown, I plug a time offset (from when the spacebar is pressed to the current animation time) into the position equation (x = x0 + vt + at^2).

The people who jump and wave their arms have more than three levels of hierarchy.


Game objective:

The objective of the game is to shoot two of the five balls into cups; the player can move slightly right, left, forward, and back then to fire. The trajectory of the ball and player starting position are preset to hit the middle cup.


Custom shapes:

I created the custom “Cup” shape, “Disk” shape, and “TableLeg” shape. From a combination of these and with the provided sphere and cube shapes, I created people named Brad, Tad, and Fratboy McChad as antagonists. I varied the scaling of their components for diversity. It would have been trivial to move most of my lengthy display code into separate functions for efficiency, but due to time constraints, I had to leave my code very sloppy. Regardless, these shapes are defined and used in my index.html file.

The Cup shape was the most difficult to create; using the Windmill shape as a basis, I created a number of strips surrounding the shape’s origin, and extending upward and outward given two radii (RadA and RadB). I repurposed this same code from creating the TableLeg shape, which is simply a “cup” with the radii equal. I close the tops and bottoms of these shapes with either disks or spheres depending on the application.


look_at():

I used look_at() when graphics.state.game_state is 1 (i.e. during the “Replay”). I use it to follow the path of a ball, which I spawn above the cup the player hit in game_state 0. The eye vector is a point near the cups, the at vector is the ball’s position minus the eye’s, and the up vector is a reordered projection of the at vector, which is always perpendicular to it.



Limitations:

There are a few bugs I did not have time to fix, such as the character’s unlimited movement and miscalculating the ball’s position relative to given cups occasionally. Otherwise, the gameplay seems robust. I also hoped to loop the audio and decrease its volume, but I believe its inclusion as-is is preferable to silence. Finally, I intended to implement a reset function to restart the game without reloading the page. I plan to revisit and correct these bugs at the end of this quarter.
