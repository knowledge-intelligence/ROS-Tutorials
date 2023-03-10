# ROS2 Yolov5 Docker Tutorial


## (Install ROS2 Foxy)
$ wget https://raw.githubusercontent.com/knowledge-intelligence/ROS-Tutorials/master/install_ros2_foxy.sh && chmod 755 ./install_ros2_foxy.sh && ./install_ros2_foxy.sh


## (Install Docker)
$ wget https://raw.githubusercontent.com/knowledge-intelligence/ROS-Tutorials/master/install_docker.sh && chmod 755 ./install_docker.sh && ./install_docker.sh


## (git clone)
$ git clone https://github.com/knowledge-intelligence/ROS-Tutorials.git -b main


## (Docker Build)
$ sudo docker build . -t yolov5 <br>
$ sudo docker build -f Dockerfile_CPU . -t yolov5_cpu

## (Docker Run)
$ sudo docker run -it yolov5 --name yolov5_docker <br>
$ sudo docker run -it --entrypoint /bin/bash yolov5_cpu -c "source /opt/ros/foxy/setup.bash && source ./install/setup.bash && export ROS_DOMAIN_ID=2 && ros2 run ros2_yolov5_docker ros2_yolov5_docker_node" --name yolov5_docker
[참고] https://www.daleseo.com/docker-run/


## (Out_Docker Build)
$ cd ~/ROS-Tutorials/ROS2_Yolov5_Docker/Out_Docker/ <br>
$ colcon build --symlink-install


## (Webcam Check)
$ sudo apt install v4l-utils <br>
$ v4l2-ctl --list-devices


## (Run Out_Docker Nodes - Publisher)
$ source ~/ROS-Tutorials/ROS2_Yolov5_Docker/Out_Docker/install/setup.bash <br>
$ ros2 run ros2_yolov5 img_publisher


## (Run Out_Docker Nodes - Subscriber)
$ source ~/ROS-Tutorials/ROS2_Yolov5_Docker/Out_Docker/install/setup.bash <br>
$ ros2 run ros2_yolov5 img_subscriber


## (Docker Images/ps list)

## (remove all containers)
$ sudo docker images list <br>
$ sudo docker ps <br>

## (To run a disposable new container / run it without --rm for no disposable)
(--rm 옵션, 일회성으로 실행) <br>
$ docker run --rm -it --entrypoint bash \<image-name-or-id\>

## (to enter a running container)
(-it 컨테이너를 종료하지 않고, 터미널의 입력을 계속해서 컨테이너로 전달하기 위해서 사용) <br>
$ docker exec -it \<container-name-or-id\> bash

