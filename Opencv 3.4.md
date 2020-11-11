#Opencv 3.4 with CUDA on Windows

#### Requirements

* Visual Studio 2013 (can not sovle the error of compiling on VS2017)

* CMake

    : download[https://cmake.org/download/]
    
* OpenCV-3.4

    : download[https://opencv.org/releases/]
    
    : modules[https://github.com/opencv/opencv_contrib/releases]
    
    : use same version Opencv and Opencv-contrib

* Eigen

    : download[http://eigen.tuxfamily.org/index.php?title=Main_Page]
    
* (Options) CUDA

    : driver[https://www.nvidia.co.kr/Download/index.aspx?lang=kr]
    
    : CUDA[https://developer.nvidia.com/cuda-toolkit-archive] (test on 8.0 and 10.0)
    
    : cudnn[https://developer.nvidia.com/rdp/cudnn-archive] (need login)
    
    : set environment variable on your PC 
    
        [variable] |                                    [value]
        
        CUDA_PATH  |  /path/to/CUDA(ex] C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0)
    
* (Options} GStreamer

    : download[https://gstreamer.freedesktop.org/download/]
    
    : download runtime and development
    
    : set environment variable on your PC 
    
        [variable] |              [value]
        
                   | /path/to/GStreamer/bin
        
           Path    | /path/to/GStreamer/lib
         
                   | /path/to/GStreamer/lib/gstreamer-1.0
    
#### CMake Configure

* Reference[https://m.blog.naver.com/PostView.nhn?blogId=msm2570&logNo=221333488789&proxyReferer=https:%2F%2Fwww.google.com%2F]

1. search "TEST" and off all

2. search "eigen" and set /path/to/eigen on "EIGEN_INCLUDE_PATH"

3. search "extra" and set /path/to/opencv_contrib/modules on "OPENCV_EXTRA_MODULES_PATH"

4. search "python" and off all

5. search "install" and change "CMAKE_INSTALL_PREFIX" if you want

6. search "package" and off "BUILD_PACKAGE"

7. search "example" and check if you want to get sample code

8. turn off the "WITH_1394", "WITH_VTX", "WITH_MATLAB", and "WITH_LAPACK"

    : about configuration-WITH[https://ipcvhomme.tistory.com/11]

9. (Options) turn on the "WITH_CUDA" and check your CUDA version

    : after CUDA 8.0, don't support "nvcuvid". you don't care

    : if you don't use, turn off the "WITH_CUDA", "WITH_CUBLAS", "WITH_CUFFT", and "WITH_NVCUVID"
    
10. (Options) turn on the "WITH_GSTREAMER" and check your GSTREAMER path

11. search "world" and turn on "BUILD_opencv_world"

12. click the "Configuration" and "Generate". if the success done, you can open project

    : if the fail done, click [File]->[Delete Cache] and retry
