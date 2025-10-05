# Autonomous Line Following and Obstacle Avoidance Robot
This project implements a fully autonomous mobile robot using ROS 2 that can follow a yellow line, detect obstacles, and navigate through tunnels and turns.
It uses computer vision for line detection, laser scanning for obstacle avoidance, and a finite state machine for decision making.

## Features
Line Following: Detects and follows a yellow line using a camera feed.    
Obstacle Avoidance: Detects and avoids obstacles using LIDAR (LaserScan data).  
Wall Following: Switches to wall-following behavior when the line is lost.  
Tunnel Entry/Exit Detection: Detects a tunnel sign and triggers tunnel navigation.  
PID Control: Smooth steering and speed adjustment using a tuned PID controller.  
Multi-threaded Execution: Runs multiple callbacks (vision, LIDAR, control) concurrently.  

## How It Works
#### 1. Image Processing:
- Converts camera images to HSV color space.  
- Detects yellow areas representing the line.  
- Calculates the line’s offset (error) from the image center.
#### 2. PID Control:  
- Uses the calculated error to adjust the robot’s angular velocity for smoother steering.
#### 3. Obstacle Detection:  
- Uses front LIDAR ranges to check for obstacles.  
- Switches states when an obstacle or wall is detected.
#### 4. Decision Logic:  
- The robot transitions between states based on vision and LIDAR feedback.

## Demo
https://github.com/user-attachments/assets/e4e1aad0-0d9d-4a98-b5c2-47c119969236  

## Future Improvements  
- Add left wall following for smoother navigation in tight spaces.  
- Integrate AI based perception to detect lines, signs, and obstacles more reliably under varying light conditions.  
- Use Behavior Trees (BTs) instead of a traditional state machine for clearer, modular decision making.  
  - BTs make it easier to add or modify tasks without breaking existing logic.  



