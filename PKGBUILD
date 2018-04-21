# Script generated with Bloom
pkgdesc="ROS - Saturation in the Null Space (SNS) Inverse Kinematic Library. SNS is a real-time Cartesian IK solver for uses the redundancy in the supplied kinematic chain for collision avoidance, joint motion optimization, or additional task objectives or soft constraints."
url='http://ros.org/wiki/sns_ikl'

pkgname='ros-kinetic-sns-ik-lib'
pkgver='0.2.3_1'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('eigen3'
'ros-kinetic-catkin'
'ros-kinetic-kdl-parser'
'ros-kinetic-orocos-kdl'
'ros-kinetic-roscpp'
'ros-kinetic-std-msgs'
)

depends=('ros-kinetic-orocos-kdl'
'ros-kinetic-roscpp'
'ros-kinetic-std-msgs'
)

conflicts=()
replaces=()

_dir=sns_ik_lib
source=()
md5sums=()

prepare() {
    cp -R $startdir/sns_ik_lib $srcdir/sns_ik_lib
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

