---
layout: post
title: Tournament is near!
date: 2016-10-28
---

### We don't have much time

The team is continuing the building process.  The Cannon now has a motor
attached, and most of the central electronic components are now on the robot.
There is still a lot of work that needs to be done, and the time is running
short: the first tournament is in two weeks!  There seem to be a lot of team
members that use the meeting time to play with water battles, throw the game
particles around, and distract others from doing work!  That really should not
be happening!  Everybody needs to figure out if they want to be on the robotics
team to do robotics, or if they want to join a bottle throwing team instead.

In the two weeks, you need to figure out how to attach The Cannon to the robot
in such a way that it will fit into the size limit, and how to collect the
particles and bring them up into The Cannon so they are ready for shooting.
The robot has to be fully wired, and we need some time to practice driving.

The programming team is currently waiting for the robot to be wired so they can
test their ideas for the driver controlled period.  In the mean time, we are
learning about some ideas that will be useful for the autonomous period.  We
work with processing, and on Friday we made the following program, that
implements a simple __state machine__:

```java
/**
 * Setup positin variables for x and y coordinates
 * Also setup "saved" versions to remember where did the last state change
 * happened.
 */

int y = 180;
int x = 320;
int saved_x = x;
int saved_y = y;

/*
* We use enum to keep track of states.  We have four states, one for each side
* of the square.  We start moving left.
*/

enum Direction {
  DOWN, UP, RIGHT, LEFT
}

Direction dir = Direction.LEFT;

// The statements in the setup() function
// execute once when the program begins
void setup() {
  size(640, 360);  // Size must be the first statement
  stroke(255);     // Set line drawing color to white
  frameRate(100);
}
// The statements in draw() are executed until the 
// program is stopped. Each statement is executed in 
// sequence and after the last line is read, the first 
// line is executed again.
void draw() { 
  background(0);   // Clear the screen with a black background

  ellipse(x,y,20,20);
  switch (dir) {
    case UP:
       if (dist(x,y,saved_x,saved_y)>=50) {
          dir = Direction.RIGHT;  // switch state to RIGHT
          saved_x = x;
          saved_y = y;
       } else {
          y = y - 1;
       }
       break;
    case DOWN:
       if (dist(x,y,saved_x,saved_y) >= 50) {
           dir = Direction.LEFT;  // switch state to LEFT
           saved_x = x;
           saved_y = y;
       } else {
           y = y + 1;
       }
       break;
    case LEFT:
       if (dist(x,y,saved_x,saved_y) >= 50) {
           dir = Direction.UP;  // switch state to UP
           saved_x = x;
           saved_y = y;
       } else {
           x = x - 1;
       }
       break;
    case RIGHT:
       if (dist(x,y,saved_x,saved_y) >= 50) {
           dir = Direction.DOWN;  // switch state to DOWN
           saved_x = x;
           saved_y = y;
       } else {
           x = x + 1;
       }
       break;
   }
}
```

The program draws a white circle on black background and then moves the circle
in a square pattern over and over again.  You can cut and paste this program
into a processing editor and experiment with it.  Can you turn the square on
its tip (like a diamond shape)? All you really need to do is change __both x
and y__ at the same time.  The rest will actually be almost the same, although
you may want to rename the states so they reflect the new directions.  It is
always a good idea to use descriptive names in your code, so when somebody
reads it they have better idea what is going on!
