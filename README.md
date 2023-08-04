# cocos2ddemo
Testing and learning with Cocos2dx

# Install Cocos2dx and CocosCLI
Follow the basic [Linux Instructions](https://docs.cocos2d-x.org/cocos2d-x/v4/en/installation/Linux.html) with a few deviations from the guide to get it to run well on modern linux environments or even more specically for Fedora/Nobara support.
- Dependencies: `sudo dnf install g++ python2.7 openssl-devel cmake libXxf86vm libXxf86vm-devel glew-devel  glib2 glib2-devel gdk-pixbuf2 gdk-pixbuf2-devel libXmu-devel libX11-devel glfw glfw-devel mesa-libGL mesa-libGL-devel gtk3-devel xorg-x11-server-devel sqlite-devel libcurl-devel fontconfig-devel libpng libpng-devel libzip libzip-devel libXi-devel gl2ps gl2ps-devel mesa-libGL-devel mesa-libGL`
- From Cocoas root replace chipmunk prebuild lib with the one downloaded [here](https://github.com/cocos2d/cocos2d-x/files/4272227/libchipmunk7.0.1.zip). Replace at path <cocos-root>/cocos2d/external/chipmunk/prebuild/linux/64-bit/ibchipmunk.a - https://github.com/cocos2d/cocos2d-x/issues/20471
- Add the following line to CMakeLists.txt `set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -no-pie -fexceptions -std=c++11 -Wno-deprecated-declarations -Wno-reorder")` https://github.com/cocos2d/cocos2d-x-docs/commit/dbecfd91a06946deb08ae918bcdb0235c0f84fab
- `mkdir -p build/linux-build`
- `cmake ../..`
- `make -j <num cores>`
- `cd <cocos-root>/cocos2d/python2.7 setup.py` to add binaries and envars to path