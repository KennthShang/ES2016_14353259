# 谷歌Cartographer学习-快速安装测试
本文基本安装过程按照该[博客](http://wiki.ros.org/jade/Installation/Ubuntu)操作
## 安装所有依赖项
如下，需要安装3个软件包，ceres solver、cartographer和cartographer_ros    
`sudo apt-get install -y google-mock libboost-all-dev  libeigen3-dev `
`libgflags-devlibgoogle-glog-dev liblua5.2-dev libprotobuf-dev`
`libsuitesparse-dev libwebp-dev ninja-build protobuf-compiler python-sphinx`  
`ros-indigo-tf2-eigen libatlas-base-dev libsuitesparse-dev liblapack-dev`
<img src = "/img/1.png" />
## 安装过程
1. 首先ceres solver，选择的版本是1.11,路径随意
`git clone https://github.com/hitcm/ceres-solver-1.11.0.git`
<img src = "/img/2.png" />
`cd ceres-solver-1.11.0/build`（这里注意需要自己先创建build文件夹，后续部分一样）
<img src = "/img/3.png" />
`cmake ..`
`make –j`（这里可以选择不加-j，加-j表示cpu同时处理全部文件）
`sudo make install`
<img src = "/img/5.png" />
2. 然后安装 cartographer,路径随意     
`git clone https://github.com/hitcm/cartographer.git` 
<img src = "/img/6.png" />   
`cd cartographer/build`    
`cmake .. -G Ninja `
<img src = "/img/7.png" />  
`ninja`
<img src = "/img/4.png" />
`ninja test`
`sudo ninja install`
<img src = "/img/8.png" />  
3. 安装cartographer_ros   
下载到catkin_ws下面的src文件夹下面   
`git clone https://github.com/hitcm/cartographer_ros.git`   
然后到catkin_ws下面运行catkin_make即可
4. 数据下载测试    
将下载好的文件放入虚拟机的文件夹中然后执行如下指令即可
`roslaunch cartographer_ros demo_backpack_2d.launch bag_filename:=${HOME}/Downloads/cartographer_paper_deutsches_museum.bag`
<img src = "/img/11.png" />  

### 至此所有的安装过程就结束了
