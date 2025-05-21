belarus@Roblox:~$ export GITHUB_USERNAME=HeinrichBelarus
belarus@Roblox:~$ cd ${GITHUB_USERNAME}/workspace
belarus@Roblox:~/HeinrichBelarus/workspace$ pushd .
~/HeinrichBelarus/workspace ~/HeinrichBelarus/workspace
belarus@Roblox:~/HeinrichBelarus/workspace$ source scripts/activate
belarus@Roblox:~/HeinrichBelarus/workspace$ git clone https://github.com/${GITHUB_USERNAME}/lab02.git projects/lab03
Cloning into 'projects/lab03'...
remote: Enumerating objects: 3008, done.
remote: Counting objects: 100% (3008/3008), done.
remote: Compressing objects: 100% (2306/2306), done.
remote: Total 3008 (delta 525), reused 2997 (delta 521), pack-reused 0 (from 0)
Receiving objects: 100% (3008/3008), 13.51 MiB | 12.57 MiB/s, done.
Resolving deltas: 100% (525/525), done.
belarus@Roblox:~/HeinrichBelarus/workspace$ cd projects/lab03
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git remote remove origin
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab03.git
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ g++ -std=c++11 -I./include -c sources/print.cpp
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ ls print.o
print.o
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ nm print.o | grep print
0000000000000000 T _Z5printRKNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEEERSo
000000000000002a T _Z5printRKNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEEERSt14basic_ofstreamIcS2_E
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ ar rvs print.a print.o
ar: creating print.a
a - print.o
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ file print.a
print.a: current ar archive
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ g++ -std=c++11 -I./include -c examples/example1.cpp
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ ls example1.o
example1.o
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ g++ example1.o print.a -o example1
/usr/bin/ld: /usr/lib/gcc/x86_64-linux-gnu/13/../../../x86_64-linux-gnu/Scrt1.o: in function `_start':
(.text+0x1b): undefined reference to `main'
collect2: error: ld returned 1 exit status
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ g++ -std=c++11 -I./include -c sources/print.cpp -o print.o
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ ar rcs print.a print.o
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ g++ -std=c++11 -I./include -c examples/example1.cpp -o example1.0
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ g++ example1.0 print.a -o example1
/usr/bin/ld: /usr/lib/gcc/x86_64-linux-gnu/13/../../../x86_64-linux-gnu/Scrt1.o: in function `_start':
(.text+0x1b): undefined reference to `main'
collect2: error: ld returned 1 exit status
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ g++ example1.0 print.a -o example1
/usr/bin/ld: /usr/lib/gcc/x86_64-linux-gnu/13/../../../x86_64-linux-gnu/Scrt1.o: in function `_start':
(.text+0x1b): undefined reference to `main'
collect2: error: ld returned 1 exit status
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ ./example1
bash: ./example1: No such file or directory
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ g++ -std=c++11 -I./include examples/example1.cpp sources/print.cpp -o example1
/usr/bin/ld: /usr/lib/gcc/x86_64-linux-gnu/13/../../../x86_64-linux-gnu/Scrt1.o: in function `_start':
(.text+0x1b): undefined reference to `main'
collect2: error: ld returned 1 exit status
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ nano print.a
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ nano example1.cpp
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git checkout examples/example1.cpp
Updated 0 paths from the index
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git ls-files examples/example1.cpp
examples/example1.cpp
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git branch -a
* master
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git checkout master
Already on 'master'
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ nano example1.cpp
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ g++ -std=c++11 -I./include examples/example1.cpp sources/print.cpp -o example1
/usr/bin/ld: /usr/lib/gcc/x86_64-linux-gnu/13/../../../x86_64-linux-gnu/Scrt1.o: in function `_start':
(.text+0x1b): undefined reference to `main'
collect2: error: ld returned 1 exit status
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ ls -l examples/example1.cpp
-rw-rw-r-- 1 belarus belarus 0 May 21 00:35 examples/example1.cpp
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cat examples/example1.cpp
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ nano examples/example1.cpp
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cat examples/example1.cpp
#include <iostream>
int main(){
std::cout<<"Hello, world"<<std::endl;
}
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ g++ -std=c++11 -I./include examples/example1.cpp sources/print.cpp -o example1
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ ./example1
Hello, world
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ ls example1.o
example1.o
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ g++ example1.o print.a -o example1
/usr/bin/ld: /usr/lib/gcc/x86_64-linux-gnu/13/../../../x86_64-linux-gnu/Scrt1.o: in function `_start':
(.text+0x1b): undefined reference to `main'
collect2: error: ld returned 1 exit status
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$  ./example1 && echo
bash: ./example1: No such file or directory
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ ./example1
bash: ./example1: No such file or directory
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ g++ -std=c++11 -I./include examples/example1.cpp sources/print.cpp -o example1
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ ./example1
Hello, world
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ ./example1
Hello, world
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ ./example1 && echo
Hello, world

belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ g++ -std=c++11 -I./include -c examples/example2.cpp
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ nm example2.o
0000000000000000 V DW.ref.__gxx_personality_v0
                 U __gxx_personality_v0
0000000000000000 T main
                 U __stack_chk_fail
                 U _Unwind_Resume
                 U _Z5printRKNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEEERSt14basic_ofstreamIcS2_E
                 U _ZNSt14basic_ofstreamIcSt11char_traitsIcEEC1EPKcSt13_Ios_Openmode
                 U _ZNSt14basic_ofstreamIcSt11char_traitsIcEED1Ev
0000000000000000 W _ZNSt15__new_allocatorIcED1Ev
0000000000000000 W _ZNSt15__new_allocatorIcED2Ev
0000000000000000 n _ZNSt15__new_allocatorIcED5Ev
                 U _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEEC1EPKcRKS3_
                 U _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEED1Ev
                 U _ZSt21ios_base_library_initv
0000000000000000 r _ZStL19piecewise_construct
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ g++ example2.o print.a -o example2
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ ./example2
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cat log.txt && echo
hello
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ $ rm -rf example1.o example2.o print.o
$: command not found
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ rm -rf example1.o example2.o print.o
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ rm -rf print.a
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ rm -rf example1 example2
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ rm -rf log.txt
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cat > CMakeLists.txt <<EOF
cmake_minimum_required(VERSION 3.4)
project(print)
EOF
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cat >> CMakeLists.txt <<EOF
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
EOF
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cat >> CMakeLists.txt <<EOF
add_library(print STATIC \${CMAKE_CURRENT_SOURCE_DIR}/sources/print.cpp)
EOF
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cat >> CMakeLists.txt <<EOF
include_directories(\${CMAKE_CURRENT_SOURCE_DIR}/include)
EOF
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cmake -H. -B_build
Command 'cmake' not found, but can be installed with:
sudo snap install cmake  # version 4.0.2, or
sudo apt  install cmake  # version 3.27.8-1build1
See 'snap info cmake' for additional versions.
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ sudo apt install cmake
[sudo] password for belarus: 
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  cmake-data libjsoncpp25 librhash0
Suggested packages:
  cmake-doc cmake-format elpa-cmake-mode ninja-build
The following NEW packages will be installed:
  cmake cmake-data libjsoncpp25 librhash0
0 upgraded, 4 newly installed, 0 to remove and 111 not upgraded.
Need to get 13.6 MB of archives.
After this operation, 49.1 MB of additional disk space will be used.
Do you want to continue? [Y/n] Y
Get:1 http://ru.archive.ubuntu.com/ubuntu noble/main amd64 libjsoncpp25 amd64 1.9.5-6build1 [82.8 kB]
Get:2 http://ru.archive.ubuntu.com/ubuntu noble/main amd64 librhash0 amd64 1.4.3-3build1 [129 kB]
Get:3 http://ru.archive.ubuntu.com/ubuntu noble/main amd64 cmake-data all 3.28.3-1build7 [2,155 kB]
Get:4 http://ru.archive.ubuntu.com/ubuntu noble/main amd64 cmake amd64 3.28.3-1build7 [11.2 MB]
Fetched 13.6 MB in 0s (29.5 MB/s)     
Selecting previously unselected package libjsoncpp25:amd64.
(Reading database ... 169455 files and directories currently installed.)
Preparing to unpack .../libjsoncpp25_1.9.5-6build1_amd64.deb ...
Unpacking libjsoncpp25:amd64 (1.9.5-6build1) ...
Selecting previously unselected package librhash0:amd64.
Preparing to unpack .../librhash0_1.4.3-3build1_amd64.deb ...
Unpacking librhash0:amd64 (1.4.3-3build1) ...
Selecting previously unselected package cmake-data.
Preparing to unpack .../cmake-data_3.28.3-1build7_all.deb ...
Unpacking cmake-data (3.28.3-1build7) ...
Selecting previously unselected package cmake.
Preparing to unpack .../cmake_3.28.3-1build7_amd64.deb ...
Unpacking cmake (3.28.3-1build7) ...
Setting up libjsoncpp25:amd64 (1.9.5-6build1) ...
Setting up librhash0:amd64 (1.4.3-3build1) ...
Setting up cmake-data (3.28.3-1build7) ...
Setting up cmake (3.28.3-1build7) ...
Processing triggers for man-db (2.12.0-4build2) ...
Processing triggers for libc-bin (2.39-0ubuntu8.4) ...
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cmake -H. -B_build
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- The C compiler identification is GNU 13.3.0
-- The CXX compiler identification is GNU 13.3.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: /usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Configuring done (0.3s)
-- Generating done (0.0s)
-- Build files have been written to: /home/belarus/HeinrichBelarus/workspace/projects/lab03/_build
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cmake --build _build
[ 50%] Building CXX object CMakeFiles/print.dir/sources/print.cpp.o
[100%] Linking CXX static library libprint.a
[100%] Built target print
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cat >> CMakeLists.txt <<EOF

add_executable(example1 \${CMAKE_CURRENT_SOURCE_DIR}/examples/example1.cpp)
add_executable(example2 \${CMAKE_CURRENT_SOURCE_DIR}/examples/example2.cpp)
EOF
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cat >> CMakeLists.txt <<EOF

target_link_libraries(example1 print)
target_link_libraries(example2 print)
EOF
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cmake --build _build
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- Configuring done (0.0s)
-- Generating done (0.0s)
-- Build files have been written to: /home/belarus/HeinrichBelarus/workspace/projects/lab03/_build
[ 33%] Built target print
[ 50%] Building CXX object CMakeFiles/example1.dir/examples/example1.cpp.o
[ 66%] Linking CXX executable example1
[ 66%] Built target example1
[ 83%] Building CXX object CMakeFiles/example2.dir/examples/example2.cpp.o
[100%] Linking CXX executable example2
[100%] Built target example2
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cmake --build _build --target print
[100%] Built target print
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cmake --build _build --target example1
[ 50%] Built target print
[100%] Built target example1
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cmake --build _build --target example2
[ 50%] Built target print
[100%] Built target example2
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ ls -la _build/libprint.a
-rw-rw-r-- 1 belarus belarus 2246 May 21 00:59 _build/libprint.a
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ _build/example1 && echo
hello
Hello, world

Command 'hello' not found, but can be installed with:
sudo snap install hello              # version 2.10, or
sudo apt  install hello              # version 2.10-3
sudo apt  install hello-traditional  # version 2.10-6
See 'snap info hello' for additional versions.
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ _build/example2
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cat log.txt && echo
hello
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ rm -rf log.txt
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git clone https://github.com/tp-labs/lab03 tmp
Cloning into 'tmp'...
remote: Enumerating objects: 91, done.
remote: Counting objects: 100% (30/30), done.
remote: Compressing objects: 100% (9/9), done.
remote: Total 91 (delta 23), reused 21 (delta 21), pack-reused 61 (from 1)
Receiving objects: 100% (91/91), 1.02 MiB | 3.94 MiB/s, done.
Resolving deltas: 100% (41/41), done.
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ mv -f tmp/CMakeLists.txt .
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ rm -rf tmp
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cat CMakeLists.txt
cmake_minimum_required(VERSION 3.4)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

option(BUILD_EXAMPLES "Build examples" OFF)

project(print)

add_library(print STATIC ${CMAKE_CURRENT_SOURCE_DIR}/sources/print.cpp)

target_include_directories(print PUBLIC
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
  $<INSTALL_INTERFACE:include>
)

if(BUILD_EXAMPLES)
  file(GLOB EXAMPLE_SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/examples/*.cpp")
  foreach(EXAMPLE_SOURCE ${EXAMPLE_SOURCES})
    get_filename_component(EXAMPLE_NAME ${EXAMPLE_SOURCE} NAME_WE)
    add_executable(${EXAMPLE_NAME} ${EXAMPLE_SOURCE})
    target_link_libraries(${EXAMPLE_NAME} print)
    install(TARGETS ${EXAMPLE_NAME}
      RUNTIME DESTINATION bin
    )
  endforeach(EXAMPLE_SOURCE ${EXAMPLE_SOURCES})
endif()

install(TARGETS print
    EXPORT print-config
    ARCHIVE DESTINATION lib
    LIBRARY DESTINATION lib
)

install(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/include/ DESTINATION include)
install(EXPORT print-config DESTINATION cmake)
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cmake -H. -B_build -DCMAKE_INSTALL_PREFIX=_install
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- Configuring done (0.0s)
-- Generating done (0.0s)
-- Build files have been written to: /home/belarus/HeinrichBelarus/workspace/projects/lab03/_build
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cmake --build _build --target install
[100%] Built target print
Install the project...
-- Install configuration: ""
-- Installing: /home/belarus/HeinrichBelarus/workspace/projects/lab03/_install/lib/libprint.a
-- Installing: /home/belarus/HeinrichBelarus/workspace/projects/lab03/_install/include
-- Installing: /home/belarus/HeinrichBelarus/workspace/projects/lab03/_install/include/print.hpp
-- Installing: /home/belarus/HeinrichBelarus/workspace/projects/lab03/_install/cmake/print-config.cmake
-- Installing: /home/belarus/HeinrichBelarus/workspace/projects/lab03/_install/cmake/print-config-noconfig.cmake
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ tree _install
Command 'tree' not found, but can be installed with:
sudo snap install tree  # version 2.1.3+pkg-5852, or
sudo apt  install tree  # version 2.1.1-2
See 'snap info tree' for additional versions.
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git add CMakeLists.txt
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git commit -m"added CMakeLists.txt"
[master 91aeb8a] added CMakeLists.txt
 1 file changed, 36 insertions(+)
 create mode 100644 CMakeLists.txt
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git push origin master
Username for 'https://github.com': HeinrichBelarus
Password for 'https://HeinrichBelarus@github.com': 
remote: Support for password authentication was removed on August 13, 2021.
remote: Please see https://docs.github.com/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
fatal: Authentication failed for 'https://github.com/HeinrichBelarus/lab03.git/'
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git remote set-url origin https://HeinrichBelarus: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@github.com/HeinrichBelarus/lab-02.git
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git push origin master
remote: Invalid username or password.
fatal: Authentication failed for 'https://github.com/HeinrichBelarus/lab-02.git/'
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git remote set-url origin https://HeinrichBelarus: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@github.com/HeinrichBelarus/lab03.git
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git push origin master
remote: Invalid username or password.
fatal: Authentication failed for 'https://github.com/HeinrichBelarus/lab03.git/'
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git remote set-url origin https://HeinrichBelarus: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@github.com/HeinrichBelarus/lab03.git
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git push origin master
Enumerating objects: 3011, done.
Counting objects: 100% (3011/3011), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2305/2305), done.
Writing objects: 100% (3011/3011), 13.51 MiB | 19.05 MiB/s, done.
Total 3011 (delta 526), reused 3007 (delta 525), pack-reused 0
remote: Resolving deltas: 100% (526/526), done.
remote: error: GH013: Repository rule violations found for refs/heads/master.
remote: 
remote: - GITHUB PUSH PROTECTION
remote:   —————————————————————————————————————————
remote:     Resolve the following violations before pushing again
remote: 
remote:     - Push cannot contain secrets
remote: 
remote:     
remote:      (?) Learn how to resolve a blocked push
remote:      https://docs.github.com/code-security/secret-scanning/working-with-secret-scanning-and-push-protection/working-with-push-protection-from-the-command-line#resolving-a-blocked-push
remote:     
remote:     
remote:       —— GitHub Personal Access Token ——————————————————————
remote:        locations:
remote:          - commit: 534e6a8e4aeb632314145e73df62046dd6a1325f
remote:            path: README.md:3
remote:     
remote:        (?) To push, remove secret from commit(s) or follow this URL to allow the secret.
remote:        https://github.com/HeinrichBelarus/lab03/security/secret-scanning/unblock-secret/2xNsPGONZCI3BoYabwi6Q9BHfGl
remote:     
remote:     
remote:       —— GitHub Personal Access Token ——————————————————————
remote:        locations:
remote:          - commit: 4a0053889bdc1aa4515087abcfba72199b9ed02c
remote:            path: reports/lab01/REPORT.md:6
remote:     
remote:        (?) To push, remove secret from commit(s) or follow this URL to allow the secret.
remote:        https://github.com/HeinrichBelarus/lab03/security/secret-scanning/unblock-secret/2xNsPFINibUXTaHqIZ7WvbDXB58
remote:     
remote: 
remote: 
To https://github.com/HeinrichBelarus/lab03.git
 ! [remote rejected] master -> master (push declined due to repository rule violations)
error: failed to push some refs to 'https://github.com/HeinrichBelarus/lab03.git'
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git config --local core.checkSecret false
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git push origin master
Enumerating objects: 3011, done.
Counting objects: 100% (3011/3011), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2305/2305), done.
Writing objects: 100% (3011/3011), 13.51 MiB | 15.44 MiB/s, done.
Total 3011 (delta 526), reused 3007 (delta 525), pack-reused 0
remote: Resolving deltas: 100% (526/526), done.
remote: error: GH013: Repository rule violations found for refs/heads/master.
remote: 
remote: - GITHUB PUSH PROTECTION
remote:   —————————————————————————————————————————
remote:     Resolve the following violations before pushing again
remote: 
remote:     - Push cannot contain secrets
remote: 
remote:     
remote:      (?) Learn how to resolve a blocked push
remote:      https://docs.github.com/code-security/secret-scanning/working-with-secret-scanning-and-push-protection/working-with-push-protection-from-the-command-line#resolving-a-blocked-push
remote:     
remote:     
remote:       —— GitHub Personal Access Token ——————————————————————
remote:        locations:
remote:          - commit: 534e6a8e4aeb632314145e73df62046dd6a1325f
remote:            path: README.md:3
remote:     
remote:        (?) To push, remove secret from commit(s) or follow this URL to allow the secret.
remote:        https://github.com/HeinrichBelarus/lab03/security/secret-scanning/unblock-secret/2xNsPGONZCI3BoYabwi6Q9BHfGl
remote:     
remote:     
remote:       —— GitHub Personal Access Token ——————————————————————
remote:        locations:
remote:          - commit: 4a0053889bdc1aa4515087abcfba72199b9ed02c
remote:            path: reports/lab01/REPORT.md:6
remote:     
remote:        (?) To push, remove secret from commit(s) or follow this URL to allow the secret.
remote:        https://github.com/HeinrichBelarus/lab03/security/secret-scanning/unblock-secret/2xNsPFINibUXTaHqIZ7WvbDXB58
remote:     
remote: 
remote: 
To https://github.com/HeinrichBelarus/lab03.git
 ! [remote rejected] master -> master (push declined due to repository rule violations)
error: failed to push some refs to 'https://github.com/HeinrichBelarus/lab03.git'
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git remote set-url origin https://github.com/HeinrichBelarus/lab03.git
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git push origin master
Username for 'https://github.com': HeinrichBelarus
Password for 'https://HeinrichBelarus@github.com': 
Enumerating objects: 3011, done.
Counting objects: 100% (3011/3011), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2305/2305), done.
Writing objects: 100% (3011/3011), 13.51 MiB | 17.94 MiB/s, done.
Total 3011 (delta 526), reused 3007 (delta 525), pack-reused 0
remote: Resolving deltas: 100% (526/526), done.
remote: error: GH013: Repository rule violations found for refs/heads/master.
remote: 
remote: - GITHUB PUSH PROTECTION
remote:   —————————————————————————————————————————
remote:     Resolve the following violations before pushing again
remote: 
remote:     - Push cannot contain secrets
remote: 
remote:     
remote:      (?) Learn how to resolve a blocked push
remote:      https://docs.github.com/code-security/secret-scanning/working-with-secret-scanning-and-push-protection/working-with-push-protection-from-the-command-line#resolving-a-blocked-push
remote:     
remote:     
remote:       —— GitHub Personal Access Token ——————————————————————
remote:        locations:
remote:          - commit: 534e6a8e4aeb632314145e73df62046dd6a1325f
remote:            path: README.md:3
remote:     
remote:        (?) To push, remove secret from commit(s) or follow this URL to allow the secret.
remote:        https://github.com/HeinrichBelarus/lab03/security/secret-scanning/unblock-secret/2xNsPGONZCI3BoYabwi6Q9BHfGl
remote:     
remote:     
remote:       —— GitHub Personal Access Token ——————————————————————
remote:        locations:
remote:          - commit: 4a0053889bdc1aa4515087abcfba72199b9ed02c
remote:            path: reports/lab01/REPORT.md:6
remote:     
remote:        (?) To push, remove secret from commit(s) or follow this URL to allow the secret.
remote:        https://github.com/HeinrichBelarus/lab03/security/secret-scanning/unblock-secret/2xNsPFINibUXTaHqIZ7WvbDXB58
remote:     
remote: 
remote: 
To https://github.com/HeinrichBelarus/lab03.git
 ! [remote rejected] master -> master (push declined due to repository rule violations)
error: failed to push some refs to 'https://github.com/HeinrichBelarus/lab03.git'
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cat ~/.ssh/id_rsa.pub
cat: /home/belarus/.ssh/id_rsa.pub: No such file or directory
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git push origin master
Username for 'https://github.com': HeinrichBelarus
Password for 'https://HeinrichBelarus@github.com': 
Enumerating objects: 3011, done.
Counting objects: 100% (3011/3011), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2305/2305), done.
Writing objects: 100% (3011/3011), 13.51 MiB | 15.42 MiB/s, done.
Total 3011 (delta 526), reused 3007 (delta 525), pack-reused 0
remote: Resolving deltas: 100% (526/526), done.
remote: error: GH013: Repository rule violations found for refs/heads/master.
remote: 
remote: - GITHUB PUSH PROTECTION
remote:   —————————————————————————————————————————
remote:     Resolve the following violations before pushing again
remote: 
remote:     - Push cannot contain secrets
remote: 
remote:     
remote:      (?) Learn how to resolve a blocked push
remote:      https://docs.github.com/code-security/secret-scanning/working-with-secret-scanning-and-push-protection/working-with-push-protection-from-the-command-line#resolving-a-blocked-push
remote:     
remote:     
remote:       —— GitHub Personal Access Token ——————————————————————
remote:        locations:
remote:          - commit: 4a0053889bdc1aa4515087abcfba72199b9ed02c
remote:            path: reports/lab01/REPORT.md:6
remote:     
remote:        (?) To push, remove secret from commit(s) or follow this URL to allow the secret.
remote:        https://github.com/HeinrichBelarus/lab03/security/secret-scanning/unblock-secret/2xNsPFINibUXTaHqIZ7WvbDXB58
remote:     
remote: 
remote: 
To https://github.com/HeinrichBelarus/lab03.git
 ! [remote rejected] master -> master (push declined due to repository rule violations)
error: failed to push some refs to 'https://github.com/HeinrichBelarus/lab03.git'
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git push origin master
Username for 'https://github.com': HeinrichBelarus
Password for 'https://HeinrichBelarus@github.com': 
remote: Support for password authentication was removed on August 13, 2021.
remote: Please see https://docs.github.com/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
fatal: Authentication failed for 'https://github.com/HeinrichBelarus/lab03.git/'
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git push origin master
Username for 'https://github.com': HeinrichBelarus
Password for 'https://HeinrichBelarus@github.com': 
Enumerating objects: 3011, done.
Counting objects: 100% (3011/3011), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2305/2305), done.
Writing objects: 100% (3011/3011), 13.51 MiB | 17.55 MiB/s, done.
Total 3011 (delta 526), reused 3007 (delta 525), pack-reused 0
remote: Resolving deltas: 100% (526/526), done.
remote: 
remote: Create a pull request for 'master' on GitHub by visiting:
remote:      https://github.com/HeinrichBelarus/lab03/pull/new/master
remote: 
To https://github.com/HeinrichBelarus/lab03.git
 * [new branch]      master -> master
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ export LAB_NUMBER=03
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER}
Cloning into 'tasks/lab03'...
remote: Enumerating objects: 91, done.
remote: Counting objects: 100% (30/30), done.
remote: Compressing objects: 100% (9/9), done.
remote: Total 91 (delta 23), reused 21 (delta 21), pack-reused 61 (from 1)
Receiving objects: 100% (91/91), 1.02 MiB | 3.99 MiB/s, done.
Resolving deltas: 100% (41/41), done.
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ mkdir reports/lab${LAB_NUMBER}
mkdir: cannot create directory ‘reports/lab03’: No such file or directory
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ mkdir reports/lab${LAB_NUMBER}
mkdir: cannot create directory ‘reports/lab03’: No such file or directory
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ mkdir reports/lab3
mkdir: cannot create directory ‘reports/lab3’: No such file or directory
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ mkdir reports/lab03
mkdir: cannot create directory ‘reports/lab03’: No such file or directory
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ mkdir reports/
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ mkdir reports/lab03
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ mkdir reports/lab${LAB_NUMBER}
mkdir: cannot create directory ‘reports/lab03’: File exists
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03$ cd reports/lab${LAB_NUMBER}
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03/reports/lab03$ edit REPORT.md
Command 'edit' not found, but can be installed with:
sudo apt install mailcap
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03/reports/lab03$ alias edit=nano
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03/reports/lab03$ edit REPORT.md
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03/reports/lab03$ gist REPORT.md
Error: Got Net::HTTPUnauthorized from gist: {"message":"Bad credentials","documentation_url":"https://docs.github.com/rest","status":"401"}
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03/reports/lab03$ gist --login
Requesting login parameters...
Please sign in at https://github.com/login/device
  and enter code: 96D2-3684
Success! https://github.com/settings/connections/applications/4f7ec0d4eab38e74384e
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03/reports/lab03$ gist --login
Requesting login parameters...
Please sign in at https://github.com/login/device
  and enter code: CFAE-0C9B
^[[ASuccess! https://github.com/settings/connections/applications/4f7ec0d4eab38e74384e
belarus@Roblox:~/HeinrichBelarus/workspace/projects/lab03/reports/lab03$ gist REPORT.md
https://gist.github.com/HeinrichBelarus/3d5d3b97161298c51ad9ba7c2fa07bdf
