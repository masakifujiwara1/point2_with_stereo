# point2_with_stereo
## 準備
必要パッケージ
~~~
$ git clone https://github.com/masakifujiwara1/point2_with_stereo.git
$ git clone https://github.com/masakifujiwara1/turtlebot3.git
$ git clone https://github.com/ros-perception/image_pipeline.git
~~~
## 使い方
worldの立ち上げ
~~~
$ roslaunch point2_with_stereo stereo_camera_sim.launch
~~~
stereo_image_proc関連
~~~
$ ROS_NAMESPACE=stereo rosrun stereo_image_proc stereo_image_proc
$ rosrun image_view image_view image:=/stereo/left/image_rect_color
$ rosrun image_view stereo_view stereo:=/stereo image:=image_rect_color
$ rosrun tf static_transform_publisher 0 0 0 0 3.14 1.1 base_link camera_rgb_optical_left_frame 50
~~~
rvizで可視化
~~~
$ rviz
~~~
Global Options/Fixed Frameをbase_linkにする

## youtube
https://youtu.be/fZ6kFHBXVJM