# DipGSeg++
***DipGSeg++*** is a two-stage progressive segmentation framework for LiDAR ground segmentation, designed to address the limitations of existing methods in handling abrupt elevation changes and ambiguous transition regions. Our method achieves efficient and accurate ground segmentation through coarse-to-fine collaborative optimization, demonstrating excellent terrain adaptability and generalization capabilities.

## 1. Project Features
* **Coarse-to-Fine Progressive Segmentation**

  Employs a hierarchical architecture that combines dynamic plane modeling and multimodal feature fusion to effectively overcome elevation variations and transitional terrain ambiguities in complex environments.

*  **Slope-Aware Dynamic Adaptation Mechanism**   

  Automatically adjusts plane constraints through real-time terrain inclination analysis, resolving key limitations of fixed-parameter methods and eliminating the need for manual threshold tuning.

* **Cross-Scene Generalization Capability**

  Extensively evaluated in both structured and unstructured terrains, setting a new reliability standard for autonomous driving systems without requiring scene-specific calibration.

* **High Performance and Accuracy**
## 2. Main Contributions
- **Hierarchical Coarse-to-Fine Segmentation Architecture**: Utilizes dynamic plane modeling for efficient ground candidate screening and multimodal spherical feature fusion for boundary refinement, effectively addressing elevation variations and transitional terrain ambiguities in complex environments.
- **Slope-Aware Dynamic Adaptation Mechanism**: Automatically adjusts plane constraints through real-time terrain inclination analysis, resolving key limitations of fixed-parameter methods and eliminating manual threshold tuning requirements.
- **Cross-Scene Generalizable Perception Capability**: Demonstrated via extensive evaluation in both structured and unstructured terrains, establishing a new state-of-the-art reliability standard for autonomous driving systems without scene-specific calibration.

## 3. Related Visualizations

### 3.1 Schematic Diagram of Point Cloud Preprocessing and Dynamic Parameter Tuning
![3](C:\Users\66494\Desktop\论文\图\3.jpg)
(a) Original point cloud. (b) Filtered point cloud. (c) Height-ordered candidate seed points.

### 3.2 Visualization of the Ground Plane Extraction Pipeline
![4](C:\Users\66494\Desktop\论文\图\4.jpg)
(a) Initial Seeds: Lowest points selected to initialize the ground model (green); (b) Iterative Process: Intermediate ground point refinement based on distance and normal updates (gray); (c) Final Fitting Result: Final ground points and estimated plane surface (red).

### 3.3 Schematic Diagram of Point Cloud Spherical Projection with Depth Image Restoration
![5](C:\Users\66494\Desktop\论文\图\5.jpg)
(a) Original depth map generated based on the spherical model, with obvious hollow areas. (b) Continuous depth map after applying the two-stage interpolation method for restoration, providing stable input for feature extraction.

### 3.4 Visualization of Multimodal Local Features
![6](C:\Users\66494\Desktop\论文\图\6.jpg)
From top to bottom: (a) Height standard deviation plot. (b) Horizontal edge intensity plot. (c) Vertical slope plot (d) Slope dispersion plot. High eigenvalue regions are highlighted in bright yellow, revealing significant feature differences between the ground and obstacles.

### 3.5 Schematic Diagram of the Morphological Optimization and Point Cloud Reverse Mapping Process
![7](C:\Users\66494\Desktop\论文\图\7.jpg)
From top to bottom: (a) Initial binary classification map; (b) Result after closed operation; (c) Result after open operation; (d) Final point cloud label mapping. Morphological operations effectively improve the coherence and labeling accuracy of the ground area.

## 4. How to Run

### 4.1 Environment Configuration
- **Operating System**: [Specific OS]
- **Python Version**: [Specific Python Version]
- **C++ Compiler**: [Specific C++ Compiler]

### 4.2 Dependencies
- **Python Packages**:
```bash
pip install numpy pandas
```

- C++ Packages

  - **OpenCV**: Install from [OpenCV Installation Guide](https://docs.opencv.org/4.x/d7/d9f/tutorial_linux_install.html).

  - **PCL**: Install via terminal:

    ```
    sudo apt install libpcl-dev
    ```

### 4.3 Compilation
```
mkdir -p ~/catkin_ws/src/
cd ~/catkin_ws/src/
git clone https://github.com/PKZD-JLL/DipGSegplus.git
cd .. && catkin_make
# Remember to source devel/setup.bash before running nodes
```



### 4.4 Dataset Preparation
- If you want to validate Dipgseg++ on a specific dataset, download the dataset and place it in the `~/your_dataset_path/` directory.

- Modify the `projection_parameter` file according to your dataset.

  

### 4.5 Execution Commands
```bash
source ~/catkin_ws/devel/setup.bash
roscore
roslaunch dipgsegplus demo.launch
```


## 5.Acknowledgement
The following works have provided significant inspiration and assistance in achieving good code style and performance. We thank the authors for their outstanding contributions!
1. [Related Work 1](https://github.com/some/repo1)

2. [Related Work 2](https://github.com/some/repo2)

   
