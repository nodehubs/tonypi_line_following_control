# tonypi_line_following_control
# Function Introduction

This package controls the robot to automatically follow the line by receiving messages from the line detection node.

# Usage

## Preparations

1. Have a TonyPi robot, including the robot body, camera, and RDK suite, and ensure it runs normally.

## Install the Package

**1. Install the package**

After starting the robot, connect to the robot through terminal SSH or VNC, click the "One-click Deployment" button at the top right of this page, copy the following command to run on the RDK system to complete the installation of the relevant Node.

```bash
sudo apt update
sudo apt install -y tros-tonypi-line-following-control
```
**2. Run the Task Decomposition Function**

```shell
source /opt/tros/local_setup.bash

ros2 launch tonypi_line_following_control line_follower_control.launch.py
```

# Interface Description

## Topics

### Subscribed Topics

|Name  | Type                                  |  Description           |
|------| --------------------------------------| --------------------------------|
|line_center_detection	|ai_msgs::msg::PerceptionTargets	|Receives messages about the position of the line midpoint|

## Parameters
| Parameter Name             | Type       | Description  |
| --------------------- | ----------- | ----------------------------------------------------- |
| sub_topic	| string	| Name of the subscribed topic for receiving messages about the position of the line midpoint. Configure according to the actual published topic name. Default value is /line_center_detection|