# lidar_superres_dockerfile

# LiDAR Super Resolution

This repository contains the code and instructions to run the LiDAR Super Resolution project using Docker and ROS. Follow the steps below to build the Docker image, run the necessary scripts, and visualize the results in RViz.

## Prerequisites

- Docker installed on your system
- A ROS bag file or a robot that publishes to the `/velodyne_points` topic

## Building the Docker Image

1. Clone the repository:
   ```bash
   git clone https://github.com/macunaimaa/lidar_super_resolution_formiga.git
   cd lidar_super_resolution_formiga
2. Build the Docker image:
    ```bash
    docker build -t lidar_super_resolution .
3. Running the Docker Container
Run the Docker container using the run.sh script. Ensure you provide the correct parameters for your environment:
    ```bash
    ./run.sh
4. Launching the ROS Nodes
Inside the Docker container, launch the visualization nodes:
    ```bash
    roslaunch lidar_super_resolution visualize.launch
## Running the Inference Script
5. Navigate to the scripts directory:
    ```bash
    cd /home/ros_packages/src/lidar_super_resolution/scripts

6. Run the inference script while a ROS bag or your robot is running. The script will listen to the /velodyne_points topic by default:
    ```bash
    python inference.py

If you need to change the topic, modify the inference.py file accordingly.

## Visualizing the Results  

Open RViz to visualize the results. Ensure that you have configured RViz to display the appropriate topics.
  
The inference script inference.py listens to the /velodyne_points topic. If you want to change this topic, edit the inference.py file and update the topic name.
Ensure that your ROS environment is correctly set up and that the required ROS packages are installed.