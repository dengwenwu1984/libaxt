cmake_minimum_required(VERSION 2.6)

include(ReMake)

remake_project(
  libaxt
  VERSION 0.1
  RELEASE alpha
  SUMMARY "Driver library for the Ibeo Alasca XT laser scanner."
  AUTHOR "Sascha Kolski"
  AUTHOR "Ralf Kaestner"
  CONTACT "ralf.kaestner@gmail.com"
  HOME "http://github.com/kralf/libaxt"
  LICENSE "GNU Lesser General Public License (LGPL)"
  PREFIX axt-
  INSTALL /usr
)

remake_doc(
  html
)

remake_pack_deb(
)
remake_pack_deb(
  COMPONENT dev
  DESCRIPTION "development headers"
  DEPENDS libaxt
)
remake_pack_deb(
  ARCH all
  COMPONENT doc
  DESCRIPTION "documentation"
)

remake_distribute_deb(
  DISTRIBUTION lucid
  SECTION libs
  UPLOAD ppa:kralf/asl
  DEPENDS tulibs-dev libcpc-dev remake doxygen
  PASS CMAKE_BUILD_TYPE LIBCAN_GIT_REVISION
)
remake_distribute_deb(
  DISTRIBUTION precise
  SECTION libs
  UPLOAD ppa:kralf/asl
  DEPENDS tulibs-dev libcpc-dev remake doxygen
  PASS CMAKE_BUILD_TYPE LIBCAN_GIT_REVISION
)
