# download 
    mkdir -P ~/catkin_imu/src 

    cd ~/catkin_imu/src

    git clone git@github.com:yanjingang/yesense_ros1.git

# conf
    cd ~/catkin_imu

    find src/yesense_imu/ -type f |xargs grep -w "sensor/imu" --color -n # 需要改到配置文件里

# build
    catkin_make -DCATKIN_WHITELIST_PACKAGES=yesense_imu

# run
    source devel/setup.bash

    roslaunch yesense_imu yesense_ahrs.launch

# topic
    rostopic list

    rostopic hz /sensor/imu/data

        average rate: 199.175 HZ
    
    rostopic echo /sensor/imu/data

