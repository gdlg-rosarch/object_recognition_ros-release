# Script generated with Bloom
pkgdesc="ROS - object_recognition_core contains tools to launch several recognition pipelines, train objects, store models ..."
url='wg-perception.github.io/object_recognition_ros'

pkgname='ros-kinetic-object-recognition-ros'
pkgver='0.3.7_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('boost'
'ros-kinetic-actionlib'
'ros-kinetic-catkin'
'ros-kinetic-cmake-modules'
'ros-kinetic-ecto'
'ros-kinetic-ecto-image-pipeline'
'ros-kinetic-ecto-ros'
'ros-kinetic-geometric-shapes'
'ros-kinetic-object-recognition-core'
'ros-kinetic-object-recognition-msgs'
'ros-kinetic-pluginlib'
'ros-kinetic-rostest'
'ros-kinetic-visualization-msgs'
)

depends=('boost'
'ros-kinetic-actionlib'
'ros-kinetic-ecto'
'ros-kinetic-ecto-image-pipeline'
'ros-kinetic-ecto-ros'
'ros-kinetic-geometric-shapes'
'ros-kinetic-object-recognition-core'
'ros-kinetic-object-recognition-msgs'
'ros-kinetic-pluginlib'
'ros-kinetic-rostopic'
)

conflicts=()
replaces=()

_dir=object_recognition_ros
source=()
md5sums=()

prepare() {
    cp -R $startdir/object_recognition_ros $srcdir/object_recognition_ros
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

