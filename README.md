# rust_kafka_on_windows

Running apache kafka on local windows machine 
Prerequistes: 
1] JDK (https://www.oracle.com/in/java/technologies/downloads/)
2] APACHE KAKFA (https://kafka.apache.org/downloads)
3] Visual Studio Code install with : C++ CMake tools for windows (use visual studion installer)  (required by 4th dependency)
4] OPENSSL Intsallation in local machine 
  clone https://github.com/Microsoft/vcpkg
  open directory where you've cloned vcpkg
  run ./bootstrap-vcpkg.bat
  run ./vcpkg.exe install openssl-windows:x64-windows
  run ./vcpkg.exe install openssl:x64-windows-static
  run ./vcpkg.exe integrate install
  set environment variable - VCPKGRS_DYNAMIC=1
5] RUST 
