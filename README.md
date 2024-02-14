# 34763 - Autonomous Marine Robotics

### Navigate to the Docker folder inside the cloned repository:

```bash
cd 34763-autonomous-marine-robotics/docker/noetic-minimum

```

### Running the Docker Container:

To run the Docker container and access it through VNC, execute the following command:

```bash
docker run -p 6080:80 --shm-size=512m ros_34763_v_1
```

### Accessing VNC via Web Browser:

Once the Docker container is running, you can access the VNC server through your web browser using the following URL:

[http://127.0.0.1:6080/](http://127.0.0.1:6080/)


## Spawn a Bluerov2 on Gazebo

Open terminal and do:

```bash
roslaunch bluerov2_gazebo start_pid_demo.launch
```
=======

