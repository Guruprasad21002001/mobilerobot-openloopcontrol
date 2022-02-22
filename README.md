# MobileRobot-Openloopcontrol
## Aim:

To develop a python control code to move the mobilerobot along the predefined path.

## Equipments Required:
1. RoboMaster EP core
2. Python 3.7

## Procedure:

Step 1:
Use from robomaster import robot.

Step 2:
Choose the x,y,z - axis movement distance(meters).

Step 3:
Give ep_chassis.move to move straight.

Step 4:
Give time.sleep() for a break.

Step 5:
Give ep_chassis.drive_speed to have a circular movement.

## Program:
```
from robomaster import robot
import time
from robomaster import camera

if _name_ == '_main_':
    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    ep_chassis = ep_robot.chassis

    ep_led = ep_robot.led

    ep_camera = ep_robot.camera

    '''
    x = x-axis movement distance,( meters) [-5,5]
    y = y-axis movement distance,( meters) [-5,5]
    z = rotation about z axis ( degree)[-180,180]
    xy_speed = xy axis movement speed,( unit meter/second) [0.5,2]
    '''
  

    print("Camera streaming started...")
    ep_camera.start_video_stream(display=True, resolution=camera.STREAM_360P)   

    ep_chassis.move(x=1.5, y=0, z=0, xy_speed=0.75).wait_for_completed()

    ep_led.set_led(comp="all",r=255,g=0,b=0,effect="on")   
    time.sleep(2)

    ep_chassis.move(x=0, y=0, z=-90, xy_speed=0.75).wait_for_completed()
    
    ep_chassis.move(x=0.5, y=0, z=0, xy_speed=0.75).wait_for_completed()
    
    ep_chassis.move(x=0, y=0, z=-90, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=1.5, y=0, z=0, xy_speed=0.75).wait_for_completed()

    ep_led.set_led(comp="all",r=0,g=0,b=255,effect="on")   
    time.sleep(2)

    ep_chassis.move(x=0, y=0, z=90, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=0.5, y=0, z=0, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=0, y=0, z=90, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=1.5, y=0, z=0, xy_speed=0.75).wait_for_completed()

    ep_led.set_led(comp="all",r=0,g=255,b=0,effect="on")   
    time.sleep(2)

    ep_camera.stop_video_stream()
    print("Stopped video streaming...")

    ep_robot.close()
```

## MobileRobot Movement Image:

![robo](./img/robomaster.png)

## MobileRobot Movement Video:

Upload your video in Youtube and paste your video-id here

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/YOUTUBE_VIDEO_ID_HERE/0.jpg)]

(YOUTUBE LINK: https://youtu.be/64UekdmDQmU)

## Result:
Thus the python program code is developed to move the mobilerobot in the predefined path.

```
Mobile Robotics Laboratory
Department of Artificial Intelligence and Data Science/ Machine Learning
Saveetha Engineering College
```
