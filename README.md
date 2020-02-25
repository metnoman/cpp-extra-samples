# cpp-extra-samples

This repository contains  **C++** code samples for **Zivid**.

[![Build Status][ci-badge]][ci-url]

Check out our [tutorial on configuring and building these samples on Ubuntu](https://zivid.atlassian.net/wiki/spaces/ZividKB/pages/59441336/Configure+C+Samples+with+CMake+and+then+build+them+using+make+in+Ubuntu).

## Samples list

There are two main categories of samples: **Camera** and **Applications**. The samples in the **Camera** category focus only on how to use the camera. The samples in the **Applications** category use the output generated by the camera, such as the 3D point cloud, a 2D image or other data from the camera. These samples shows how the data from the camera can be used.

- **Camera**
  - **Basic** ([tutorial][BasicCaptureTutorial-url])
    - [**Capture**][Capture-url] - This example shows how to acquire images from the Zivid camera.
    - [**Capture2D**][Capture2D-url] - This example shows how to acquire only 2D images from the Zivid camera.
    - [**CaptureAssistant**][CaptureAssistant-url] - This example shows how to use Capture Assistant to acquire HDR images from the Zivid camera.
    - [**CaptureFromFile**][CaptureFromFile-url] - This example shows how to acquire HDR images from file. This example can be used without access to a physical camera.
    - [**CaptureHDR**][CaptureHDR-url] - This example shows how to acquire HDR images from the Zivid camera.
  - **InfoUtilOther**
    - [**CameraUserData**][CameraUserData-url] - This example shows how to store user data on the Zivid camera.
    - [**GetCameraIntrinsics**][GetCameraIntrinsics-url] - This example shows how to get camera intrinsics from the Zivid camera.

- **Applications**
  - **Basic**
    - **Visualization**
      - [**CaptureHDRLoop**][CaptureHDRLoop-url] - This example shows how to acquire HDR images from the Zivid camera in a loop (while actively changing some HDR settings).
      - [**CaptureFromFileVis3D**][CaptureFromFileVis3D-url] - This example shows how capture a Zivid point cloud from file, and visualize it.
      - [**CaptureVis3D**][CaptureVis3D-url] - This example shows how to capture a Zivid point cloud, and visualize it.
      - [**CaptureLiveVis3D**][CaptureLiveVis3D-url] - This example shows how to continuosly capture a Zivid point cloud, and visualize it.
      - [**CaptureWritePCLVis3D**][CaptureWritePCLVis3D-url] - This example shows how capture a Zivid point cloud, save it to a .PCD file format, and visualize it.
      - [**ReadPCLVis3D**][ReadPCLVis3D-url] - This example shows how to read a PCL point cloud and visualize it.
    - **FileFormats**
      - [**ReadIterateZDF**][ReadIterateZDF-url] - This example shows how to import and display a Zivid point cloud from a .ZDF file.
  - **Advanced**
    - [**HandEyeCalibration**][HandEyeCalibration-url]
      - [**HandEyeCalibration**][HandEyeCalibrationSample-url] - This samples shows how to perform a complete Hand Eye calibration
      - [**UtilizeEyeInHandCalibration**][UtilizeEyeInHandCalibration-url] - Transform a 3D point from camera frame to robot base frame using hand-eye calibration matrix.
      - [**PoseConversions**][PoseConversions-url] - Convert to/from Transformation Matrix (Rotation Matrix + Translation Vector)
    - [**Downsample**][Downsample-url]  - This example shows how to import a Zivid point cloud from a .ZDF file and downsample it.
      - **Dependencies:**
        - [Eigen](http://eigen.tuxfamily.org/) version 3.3.7 or newer
    - [**CaptureUndistortRGB**][CaptureUndistortRGB-url] - Use Zivid camera intrinsics to undistort an RGB image. This example will prompt the user for whether to capture a 2D or a 3D image. In both instances it will operate on a 2D image. However, in the 3D case it will extract 2D image from a ZDF point cloud. The 2D variant is faster.
      - **Dependencies:**
        - [OpenCV](https://opencv.org/) version 4.0.1 or newer
    - [**CreateDepthMap**][CreateDepthMap-url] - Import a ZDF point cloud and convert it to OpenCV format, then extract and visualize depth map.
      - **Dependencies:**
        - [OpenCV](https://opencv.org/) version 4.0.1 or newer

## Instructions

[**Install Zivid Software**](https://zivid.atlassian.net/wiki/spaces/ZividKB/pages/59080712/Zivid+Software+Installation).
Note: The version tested with Zivid cameras is 1.8.0.

### Windows

Launch the Command Prompt by pressing *Win + R* keys on the keyboard, then type cmd and press Enter.

Navigage to a location where you want to clone the repository, then run to following command:

```bash
git clone https://github.com/zivid/cpp-extra-samples
```

[comment]: <> (Choose a sample solution and configure it with CMake.)
[comment]: <> (Launch Visual Studio, open, build, and run the sample solution.)

Configure the sample solution with CMake, open it in Visual Studio, build it, run it. If you are uncertain about doing this, check out our tutorial for configuring [**C++ Extra Samples**](https://zivid.atlassian.net/wiki/spaces/ZividKB/pages/61472793/Configure+C+Extra+Samples+with+CMake+and+build+them+using+Visual+Studio+in+Windows) with CMake and building them using Visual Studio in Windows.

#### Ubuntu

Open the Terminal by pressing *Ctrl + Alt + T* keys on the keyboard.

Navigate to a location where you want to clone the repository, then run to following commands:

```bash
git clone https://github.com/zivid/cpp-extra-samples
cd cpp-extra-samples
```

Build the project:

```bash
mkdir build
cd build
cmake <options, see below> ..
make -j
```

Some of the samples depend on external libraries, in particular Eigen 3, OpenCV or PCL. If you don't want to install those, you can disable the samples depending on them by passing the following options, respectively, to `cmake`: `-DUSE_EIGEN3=OFF`, `-DUSE_OPENCV=OFF`, `-DUSEPCL=OFF`.

If you do want to use them:

- **Eigen 3**: Set `-DEIGEN3_INCLUDE_DIR=<path>` where `<path>` is the root directory of your Eigen3 installation (the folder containing Eigen/Core, Eigen/Dense etc.)
- **PCL** and **OpenCV**: If a recent enough version is installed on your system, these should just work. If not, set `-DPCL_DIR=<path>` / `-DOpenCV_DIR=<path>` where `<path>` is the directory containing `PCLConfig.cmake` and `OpenCVConfig.cmake`, respectively.

The samples can now be run from the `build` directory, for instance like this:

```bash
./ZDF2PLY
```

## Support

If you need assistance with using Zivid cameras, visit our [**Knowledge Base**](https://help.zivid.com/) or contact us at [customersuccess@zivid.com](mailto:customersuccess@zivid.com).

## Licence

Zivid Samples are distributed under the [BSD license](https://github.com/zivid/cpp-extra-samples/blob/master/LICENSE).

## Development

To run continuous integration locally, use [Docker](https://www.docker.com). With Docker installed, run this command:

```bash
docker run -it -v <unixy-repo-path>:/host -w /host/continuous-integration/linux ubuntu:18.04
```

Where `<unixy-repo-path>` is the unixy path to the repo on your computer. On Linux, use `$PWD` for this. On Windows you need to translate the windowsy path to a unixy one (e.g. `/c/Users/alice/Documents/cpp-extra-samples`).

Now run `./setup.sh` to install dependencies. Once setup has completed, you can run `./lint.sh && ./build.sh` repeatedly to check your code.

Tip: If your build hangs, try to increase the memory available to Docker.

[ci-badge]: https://img.shields.io/azure-devops/build/zivid-devops/5e76c4a5-26ad-4cbb-8ab5-b9588e1ed2b2/4
[ci-url]: https://dev.azure.com/zivid-devops/cpp-extra-samples/_build/latest?definitionId=4&branchName=master
[BasicCaptureTutorial-url]: https://github.com/zivid/cpp-extra-samples/blob/basic-capture-tutorial/source/Camera/Basic/CaptureTutorial.md
[Capture-url]: https://github.com/zivid/cpp-extra-samples/tree/master/source/Camera/Basic/Capture/Capture.cpp
[Capture2D-url]: https://github.com/zivid/cpp-extra-samples/tree/master/source/Camera/Basic/Capture2D/Capture2D.cpp
[CaptureAssistant-url]: https://github.com/zivid/cpp-extra-samples/tree/master/source/Camera/Basic/CaptureAssistant/CaptureAssistant.cpp
[CaptureFromFile-url]: https://github.com/zivid/cpp-extra-samples/tree/master/source/Camera/Basic/CaptureFromFile/CaptureFromFile.cpp
[CaptureHDR-url]: https://github.com/zivid/cpp-extra-samples/tree/master/source/Camera/Basic/CaptureHDR/CaptureHDR.cpp
[CameraUserData-url]: https://github.com/zivid/cpp-extra-samples/tree/master/source/Camera/InfoUtilOther/CameraUserData/CameraUserData.cpp
[GetCameraIntrinsics-url]: https://github.com/zivid/cpp-extra-samples/tree/source/master/Camera/InfoUtilOther/GetCameraIntrinsics/GetCameraIntrinsics.cpp
[CaptureHDRLoop-url]: https://github.com/zivid/cpp-extra-samples/tree/master/source/Applications/Basic/Visualization/CaptureHDRLoop/CaptureHDRLoop.cpp
[CaptureFromFileVis3D-url]: https://github.com/zivid/cpp-extra-samples/blob/master/source/Applications/Basic/Visualization/CaptureFromFileVis3D/CaptureFromFileVis3D.cpp
[CaptureVis3D-url]: https://github.com/zivid/cpp-extra-samples/blob/master/source/Applications/Basic/Visualization/CaptureVis3D/CaptureVis3D.cpp
[CaptureLiveVis3D-url]: https://github.com/zivid/cpp-extra-samples/blob/master/source/Applications/Basic/Visualization/CaptureLiveVis3D/CaptureLiveVis3D.cpp
[CaptureWritePCLVis3D-url]: https://github.com/zivid/cpp-extra-samples/blob/master/source/Applications/Basic/Visualization/CaptureWritePCLVis3D/CaptureWritePCLVis3D.cpp
[ReadPCLVis3D-url]: https://github.com/zivid/cpp-extra-samples/blob/master/source/Applications/Basic/Visualization/ReadPCLVis3D/ReadPCLVis3D.cpp
[ReadIterateZDF-url]: https://github.com/zivid/cpp-extra-samples/tree/master/source/Applications/Basic/FileFormats/ReadIterateZDF/ReadIterateZDF.cpp
[HandEyeCalibration-url]: https://github.com/zivid/cpp-extra-samples/tree/master/source/Applications/Advanced/HandEyeCalibration
[HandEyeCalibrationSample-url]: https://github.com/zivid/cpp-extra-samples/tree/master/source/Applications/Advanced/HandEyeCalibration/HandEyeCalibration/HandEyeCalibration.cpp
[UtilizeEyeInHandCalibration-url]: https://github.com/zivid/cpp-extra-samples/blob/master/source/Applications/Advanced/HandEyeCalibration/UtilizeEyeInHandCalibration/UtilizeEyeInHandCalibration.cpp
[PoseConversions-url]: https://github.com/zivid/cpp-extra-samples/blob/master/source/Applications/Advanced/HandEyeCalibration/PoseConversions/PoseConversions.cpp
[Downsample-url]: https://github.com/zivid/cpp-extra-samples/tree/master/source/Applications/Advanced/Downsample/Downsample.cpp
[CaptureUndistortRGB-url]: https://github.com/zivid/cpp-extra-samples/blob/master/source/Applications/Advanced/CaptureUndistortRGB/CaptureUndistortRGB.cpp
[CreateDepthMap-url]: https://github.com/zivid/cpp-extra-samples/blob/master/source/Applications/Advanced/CreateDepthMap/CreateDepthMap.cpp
