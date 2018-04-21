# Script generated with Bloom
pkgdesc="ROS - Track the output of the leg_detector to indicate the velocity of person."
url='http://ros.org/wiki/people_velocity_tracker'

pkgname='ros-kinetic-people-velocity-tracker'
pkgver='1.0.10_2'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-easy-markers'
'ros-kinetic-geometry-msgs'
'ros-kinetic-kalman-filter'
'ros-kinetic-people-msgs'
'ros-kinetic-roslib'
'ros-kinetic-rospy'
)

depends=('ros-kinetic-easy-markers'
'ros-kinetic-geometry-msgs'
'ros-kinetic-kalman-filter'
'ros-kinetic-leg-detector'
'ros-kinetic-people-msgs'
'ros-kinetic-roslib'
'ros-kinetic-rospy'
)

conflicts=()
replaces=()

_dir=people_velocity_tracker
source=()
md5sums=()

prepare() {
    cp -R $startdir/people_velocity_tracker $srcdir/people_velocity_tracker
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

