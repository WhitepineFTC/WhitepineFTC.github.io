---
layout: post
title: Second Tournament
date: 2016-10-21
---

### Wednesday Meeting Recap

On Wednesday __some of our programmers__ got a great start: we now have a fully
updated Android Studio, we made changes in last years code to reflect some
changes in the way motors and motor controllers are handled in the code this
year, and we managed to compile the last years code in the new environment.
The compiled code successfully installed on the robot phone.

We then built a simple experimental robot circuit with two motors, two servos
and two touch sensors, and some of our programmers entered the configuration
into the phone.  The same programmers then updated our `Hardware` class to
reflect the new configuration.  Together we then wrote a simple opmode that
should spin motor 1 when touch sensor 1 is pressed, and motor 2 when touch
sensor 2 is pressed:

```java
package com.qualcomm.ftcrobotcontroller.opmodes;

import com.qualcomm.robotcore.eventloop.opmode.OpMode;
import com.qualcomm.robotcore.hardware.DcMotor;
import com.qualcomm.robotcore.hardware.TouchSensor;

public class TeamTest extends Hardware
{

    public TeamTest ()
    {

    }

    @Override public void loop ()
    {
        if (v_sensor_touch_1.isPressed())
        {
            v_motor_1.setPower(1);
        }
        else
        {
            v_motor_2.setPower(0);
        }

        if (v_sensor_touch_2.isPressed())
        {
            v_motor_2.setPower(1);
        }
        else
        {
            v_motor_2.setPower(0);
        }

    }
}
```

The code compiled and installed on the phone.  We did not get to test it,
because it turned out the driver phone still had the old version of the driver
app, and the two versions of apps refused to communicate to each other.  I have
since updated the app, and we will be testing the code today.

__The builders__ continued working on the robot, and also made a great
progress.  They now have both drive motors connected to a motor controller, and
the base is now nice and sturdy.  They are getting ready to work on the
particle picking mechanism.  I have seen some pretty cool looking designs for
that.

### Second Tournament Assignment

Great news: we have been accepted to a second qualifier tournament, on December
3 in Kettering!  That will give us an extra opportunity to apply all the stuff
we will learn during our first tournament on November 12 in Midland.  In
addition to that, it gives us an additional chance to advance to the state
tournament.

I am looking forward to see everybody in the afternoon!
