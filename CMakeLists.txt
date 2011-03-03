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
  HOME "http://aslforge.ethz.ch/projects/libaxt"
  LICENSE "GNU Lesser General Public License (LGPL)"
  PREFIX axt-
  INSTALL /usr
)

remake_doc(
  html
)

remake_pack_deb(
  libaxt
)
remake_pack_deb(
  COMPONENT dev
  DESCRIPTION "development headers"
  libaxt
)
remake_pack_deb(
  ARCH all
  COMPONENT doc
  DESCRIPTION "documentation"
)
