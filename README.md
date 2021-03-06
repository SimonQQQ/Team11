# Communicating and Lane-Following Vehicle Swarm
https://github.com/DIT168-Group11/Team11.git

## Introduction
This project is a part of a collaboration between different teams in order to acheive communication between cars, and autonomous lane following.

## Description of folder layout

  ### Representation of the layout
  - src 
    - build
      - bin

  ### How the layout works
  - src is used for storing the source files for the application.
  - build contains all object files after the app is compiled.
  - bin will be autogenerated inside of build after building and will contain the binaries

## Cloning, Building and Testing the Project

### Cloning
Clone the file using git with fetching information from our githubpage using the link from our repository or download it from the github page as a .Zip file. 

### Building
Make sure that you have the [libcluon](https://github.com/chrberger/libcluon) dependency before trying to build the app.
Go to the build folder using terminal and use the `cmake ..` command and afterward run the `make` command.

### Testing
After you are done with the building, run the binary `./bin/carComm.messageFetch` open a new terminal in the build folder and run the binary `./bin/carComm.messageSend`. After doing so the `carComm.messageSend` binary will send 3 random generated number messages to the `carComm.messageFetch` binary. You can see the output in the terminal of both of the binaries and compare the messages.

## Package Software using Docker

### Install all dependencies into Docker container
apk update
apk --no-cache add ca-certificates cmake g++ make
apk add libcluon --no-cache --repository https://chrberger.github.io/libcluon/alpine/v3.7 --allow-untrusted

### Manually building with Docker
cd /path
mkdir build && cd build
cmake ..
make && make test
./helloworld 
It is an example above, you should rename the path and project according to your project, after above steps you should create a Dockerfile

### Running and Testing the build 
docker build -t myrepository/mydockerimage .
docker run --rm -ti --net=host myrepository/mydockerimage

### Saving Docker image
docker save myrepository/mydockerimage > myImage.tar
