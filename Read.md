# 34761 Robot Autonomy 

### Runnin the Docker Container
```bash
docker run -p 6080:80 --security-opt seccomp=unconfined --shm-size=512m tiryoh/ros2-desktop-vnc:humble
```

Once the Docker container is running, you can access the VNC server through your web browser using the following URL:

http://localhost:6080/


### Training 1

1. Run TurtleSim
```bash  
ros2 run turtlesim turtlesim_node 
```
2. Kill the turtle already in the simulator
```bash 
ros2 service call /kill turtlesim/srv/Kill "{name: 'turtle1'}"
```
3. Spawn a new turtle at position (6,3), remember to give it a unique name
```bash 
ros2 service call /spawn turtlesim/srv/Spawn "{x: 6.0, y: 3.0, theta: 0.0, name: 'my_turtle'}"
```
4. Control the turtle you spawned with the keyboards
```bash 
ros2 run turtlesim turtle_teleop_key
```
5. Record a rosbag of you moving the turtle around
```bash 
ros2 bag record -o /home/ubuntu/rosbag2_24_03_24 /turtle1/cmd_vel
```
6. Replay the rosbagand see the turtle replicate the movement you recorded
```bash 
ros2 bag play /home/ubuntu/rosbag2_24_03_24
```
7. Use an action message to control the turtle
```bash 
ros2 topic pub /my_turtle/cmd_vel geometry_msgs/msg/Twist "{linear: {x: 2.0, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: 1.8}}"
```

Extra useful 
Cleaning of trajectories:
```bash 
ros2 service call /clear std_srvs/srv/Empty "{}"

```


