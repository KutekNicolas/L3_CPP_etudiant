cmake_minimum_required( VERSION 3.0 )
project( TP_CPP )
set( CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -Wall -Wextra" )
set( CMAKE_BUILD_TYPE Debug )

find_package( PkgConfig REQUIRED )
pkg_check_modules( PKG REQUIRED gtkmm-2.4 cpputest )
include_directories( ${PKG_INCLUDE_DIRS} )

add_executable( main_bibliotheque.out src/main_bibliotheque.cpp src/Livre.cpp src/Bibliotheque.cpp)
target_link_libraries( main_bibliotheque.out ${PKG_LIBRARIES} )

add_executable( main_test.out src/main_test.cpp 
   src/Bibliotheque_test.cpp
   src/Livre_test.cpp
   src/Livre.cpp
   src/Bibliotheque.cpp)
target_link_libraries( main_test.out ${PKG_LIBRARIES} )

