# New Features 

This is a list of the **new features** provided by PLVS: 
* **Line segment** detection, matching, triangulation and tracking. 
  - This capability can be enabled via the option `Line.on` in the yaml settings.
  - Removed some bugs and optimized parts of the adopted [line_descriptor](https://github.com/opencv/opencv_contrib/tree/4.x/modules/line_descriptor) OpenCV module. 
* Dense reconstruction with different **volumetric mapping methods**: *voxelgrid*, *octree_point*, *[octomap](https://github.com/OctoMap/octomap)*, *[fastfusion](https://github.com/tum-vision/fastfusion)*, *[chisel](https://github.com/personalrobotics/OpenChisel)*, *[voxblox](https://github.com/ethz-asl/voxblox)*.  
  - It can be enabled by using the option `PointCloudMapping.on` in the yaml settings and selecting your preferred method `PointCloudMapping.type` (see the comments in the yaml files). 
* **Incremental segmentation** with RGBD sensors and octree-based dense map. 
  - It can be enabled by using the option `Segmentation.on` in the yaml settings of the RGBD cameras (only working when `octree_point` is selected as volumetric mapping method). 
* **Augmented reality** with overlay of tracked features, built meshes and loaded 3D models. 
  - This viz can be enabled by using the button `AR Camera` in the viewer GUI. 
* Generated **sparse and dense maps** can be **saved** and **reloaded**. 
* Extraction of **ORB** keypoints via **CUDA**. 
  - This capability can be optionally activated by using the option `USE_CUDA` in [config.sh](./config.sh) 
* Different methods can be used with calibrated stereo cameras for estimating depth maps: *libelas*, *libsgm*, *opencv* (these methods may need more fine tuning).
  - Use the option `StereoDense.type` to select your preferred method in the yaml settings for stereo cameras. This will work with your stereo datasets when `PointCloudMapping.on` is set to 1.  
* Some parts of the original ORBSLAM code were improved or optimized.
* A **new version of g2o** is supported (*tags/20230223_git*). This can be enabled by setting the option `WITH_G2O_NEW` to `ON` in the main CMakeList.txt of PLVS. 
* **Smart pointers** to manage points and lines (WIP for keyframes).
* **MapOjbect**: Experimental representation for planar objects (WIP for PLVS II).
* C++17 support. 
* Many convenient scripts are provided for launching apps, benchmarking and monitoring the system.
  
**Note**: PLVS is an active project. The main *README* is under construction and will be updated soon with further information and details. Code improvements are coming soon. 


You can find further details and videos on this [page](https://www.luigifreda.com/research/plvs-an-open-source-rgb-d-and-stereo-slam-for-volumetric-reconstruction-and-3d-incremental-segmentation/) and in the following **document**:          
**[PLVS: A SLAM System with Points, Lines, Volumetric Mapping, and 3D Incremental Segmentation](https://arxiv.org/pdf/2309.10896.pdf)**         
*Luigi Freda* 
