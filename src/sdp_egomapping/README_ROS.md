#**SDP_egomapping**

This package allows a robot to create an egocentric map,
projecting a depthimage provided by the camera into laserscans.
This perceived infomation is merged with the laserscans
readings. This readings are converted into an egocentric map.

* Maintainer status: in development.
* Maintainer: SDP Team <Hochschule Bonn Rhein Sieg>
* Source:  git <https://github.com/oarriaga/SDP_SoSe2016.git>

##Dependencies.

1. deptimage_to_laserscans
 Takes a depth image and generates a 2D laser scan representation.
* **Source**: <http://wiki.ros.org/depthimage_to_laserscan> 

* Subscribed Topics.
  * image (sensor_msgs/Image).
Input image. 
For distorted image, this topic should be remapped to image_rect. 

  * camera_info (sensor_msgs/CameraInfo.
Camera info for the associated image. 
The topic will be subscribed to from the same namespace as image.

* Parameters

  * scan_height (int, default: 1 pixel)
    * The number of pixels rows to use to generate the laserscan.
    * For each column, the scan will return the minimum value for those pixels centered vertically in the image.

  * scan_time (double, default: 1/30.0Hz (0.033s))
    * Time between scans (seconds). Typically, 1.0/frame_rate. This value is not easily calculated from consquetive messages, and is thus left to the user to set correctly.

  * range_min (double, default: 0.45m)
    * The minimum ranges to return in meters. Ranges less than this will be output as -Inf.

  * range_max (double, default: 10.0m)
    * The maximum ranges to return in meters. Ranges greater than this will be output as +Inf.

  * output_frame_id (str, default: camera_depth_frame)
    * The frame id of the laser scan. For point clouds coming from an "optical" frame with Z forward, this value should be set to the corresponding frame with X forward and Z up.


2. cob_scan_unifier
  * This node is part of cob_driver package, however there is not
repository specified to cob_scan_unifier.
  * **cob_driver Source:** <http://wiki.ros.org/cob_driver>

* Subscribed Topics.
  * /tf [tf2_msgs/TFMessage]
  * /tf_static [tf2_msgs/TFMessage]
  * /clock [rosgraph_msgs/Clock]

* Parameters
  * input_scans
   .* String with containst the laserscans topic name that are wanted to be unified.
  * loop_rate
    * Not specified.


3. gmapping ????

