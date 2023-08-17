# rust_kafka_on_windows

basic project to add elements to vector using kafka - code is reffered from blog : https://blog.logrocket.com/building-rust-microservices-apache-kafka/
Thanks to logrocket for simple and precise exmaple of apache kafka in rust.
You can follow it - only difference is tried building it on windows and it requires several other dependencies which are mentione below

Prerequistes: 
1. JDK (https://www.oracle.com/in/java/technologies/downloads/) (required by 2nd dependency)
2. APACHE KAKFA (https://kafka.apache.org/downloads) - follow here - https://www.geeksforgeeks.org/how-to-install-and-run-apache-kafka-on-windows/
3. Visual Studio Code install with : C++ CMake tools for windows (use visual studion installer)  (required by 4th dependency)
4. OPENSSL Intsallation in local machine 
  clone https://github.com/Microsoft/vcpkg
  open directory where you've cloned vcpkg
  run ./bootstrap-vcpkg.bat
  run ./vcpkg.exe install openssl-windows:x64-windows
  run ./vcpkg.exe install openssl:x64-windows-static
  run ./vcpkg.exe integrate install
  set environment variable - VCPKGRS_DYNAMIC=1
5. RUST 

after cloning the repo 
1. in project run cargo build and then cargo run 
2. open terminal to path where kafka is installed and run below commands
  .\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties (in new tab)
  .\bin\windows\kafka-server-start.bat .\config\server.properties (in new tab)
  .\bin\windows\kafka-topics.bat --create --topic texts --bootstrap-server localhost:9092
  .\bin\windows\kafka-topics.bat --create --topic actions --bootstrap-server localhost:9092
  .\bin\windows\kafka-console-consumer.bat --topic texts --from-beginning --bootstrap-server localhost:9092 (in new tab)
  .\bin\windows\kafka-console-producer.bat --topic actions --bootstrap-server localhost:9092 (in new tab)
      and write some actions like below :
      > { "action": "add", "value": "first text" }
      > { "action": "add", "value": "second text" }
      > { "action": "remove", "value": 1 }
      > { "action": "add", "value": "third text" }
