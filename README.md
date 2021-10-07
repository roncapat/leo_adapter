# LeoRover adapter for common topics

This simple node:

- merges `/imu/accel` and `/imu/gyro` (`geometry_msgs/Vector3Stamped`) in `/leo_imu/data_raw` (`sensor_msgs/Imu`)
- merges `/wheel_odom` (`geometry_msgs/TwistStamped`) and `/wheel_pose` (`geometry_msgs/PoseStamped`) in `/leo_odom` (`nav_msgs/Odometry`)
- converts `/imu/mag` (`geometry_msgs/Vector3Stamped `) in `/leo_imu/mag` (`sensor_msgs/MagneticField`)

## Note on Odometry

Firmware 1.2.0 has a bug that will prevent this node to merge topics under `/leo_odom`.

See this [issue](https://github.com/LeoRover/leo_firmware/issues/4).

The solution is described in the issue itself: you have to recompile and flash the firmware by adding the missing code line.
