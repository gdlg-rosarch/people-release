# Script generated with Bloom
pkgdesc="ROS - Face detection in images."
url='http://ros.org/wiki/face_detector'

pkgname='ros-kinetic-face-detector'
pkgver='1.0.10_2'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-actionlib'
'ros-kinetic-actionlib-msgs'
'ros-kinetic-catkin'
'ros-kinetic-cv-bridge'
'ros-kinetic-geometry-msgs'
'ros-kinetic-image-geometry'
'ros-kinetic-image-transport'
'ros-kinetic-message-generation'
'ros-kinetic-people-msgs'
'ros-kinetic-rosbag'
'ros-kinetic-roscpp'
'ros-kinetic-roslib'
'ros-kinetic-rospy'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
'ros-kinetic-stereo-msgs'
'ros-kinetic-tf'
)

depends=('ros-kinetic-actionlib'
'ros-kinetic-actionlib-msgs'
'ros-kinetic-cv-bridge'
'ros-kinetic-dynamic-reconfigure'
'ros-kinetic-geometry-msgs'
'ros-kinetic-image-geometry'
'ros-kinetic-image-transport'
'ros-kinetic-message-runtime'
'ros-kinetic-openni-launch'
'ros-kinetic-people-msgs'
'ros-kinetic-rosbag'
'ros-kinetic-roscpp'
'ros-kinetic-roslib'
'ros-kinetic-rospy'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
'ros-kinetic-stereo-msgs'
'ros-kinetic-tf'
)

conflicts=()
replaces=()

_dir=face_detector
source=()
md5sums=()

prepare() {
    cp -R $startdir/face_detector $srcdir/face_detector
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

