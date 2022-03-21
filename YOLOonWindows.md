# Install YOLO on Windows

### How to compile on Windows (using `CMake`)

Requirements:

- MSVC: https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community
- CMake GUI: `Windows win64-x64 Installer`https://cmake.org/download/
- Download Darknet zip-archive with the latest commit and uncompress it: [master.zip](https://github.com/AlexeyAB/darknet/archive/master.zip)

install:
1. [Download Darknet zip-archive with the latest commit and uncompress it](https://github.com/AlexeyAB/darknet/archive/master.zip)
2. [Go to MSVC:](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community).This will download the MSVC Community edition setup exe file for you. Run it.
 Select the “Desktop development with C++” package as shown below and click on install.
3. [CMake GUI: Windows win64-x64 Installer](https://cmake.org/download/)  Select the installer for your system. 
4.  Install CUDA, cuDNN and OpenCV on the system.
    - [Download OpenCV latest release Windows] (https://opencv.org/releases/).Run the exe file, extract it to C drive and install it.
    - give the following paths in the path environment variable for your System variables 
      - C:\opencv\build\include
      - C:\opencv\build\x64\vc14\bin
      - C:\opencv\build\x64\vc14\lib
      - C:\opencv\build\x64\vc15\bin
      - C:\opencv\build\x64\vc15\lib
      - C:\opencv\build\bin

In Windows:

- Start (button) -> All programs -> CMake -> CMake (gui) ->

- [look at image](https://habrastorage.org/webt/pz/s1/uu/pzs1uu4heb7vflfcjqn-lxy-aqu.jpeg) In CMake: Enter input path to the darknet Source, and output path to the Binaries -> Configure (button) -> Optional platform for generator: `x64`  -> Finish -> Generate -> Open Project ->
  - note: disable CUDA if you do not have NVIDIA GPU. 

- in MS Visual Studio: Select: x64 and Release -> Build -> Build solution

- find the executable file `darknet.exe` in the output path to the binaries you specified

![x64 and Release](https://habrastorage.org/webt/ay/ty/f-/aytyf-8bufe7q-16yoecommlwys.jpeg)

Setup darknet directory:
- Before we can run the darknet.exe from the command prompt, you need to copy the pthreadVC2.dll from the darknet-master/3rdparty/pthreads/bin folder and place it alongside the darknet.exe file in the darknet-master main folder.
- [download the YOLOv4 weights file](https://github.com/AlexeyAB/darknet/releases/download/darknet_yolo_v3_optimal/yolov4.weights). put the weights file alongside the darknet.exe file in the darknet-master main folder.
#### How to use on the command line
- Yolo v4 COCO - **WebCam 0**: `darknet.exe detector demo cfg/coco.data cfg/yolov4.cfg yolov4.weights`


### View 
- https://github.com/AlexeyAB/darknet/blob/master/README.md
- https://techzizou.com/yolo-installation-on-windows-and-linux/#install_windows
