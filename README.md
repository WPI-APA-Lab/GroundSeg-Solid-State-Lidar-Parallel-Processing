# GroundSeg-Solid-State-Lidar-Parallel-Processing
ISICAS2024 TCAS-II
# LiDAR Mechanism
<img src="/figure/LiDAR mechanism.png" width="400">
The traditional mechanical LiDAR sensors, which require rotation to achieve a 360-degree field of view, often pose challenges in terms of size, cost, and reliability. These challenges have spurred the development of Solid-State LiDAR (SSL) systems, which are categorized into flash-based and scanning-based (semi-SSL) technologies, with the latter often employing Micro-Electro-Mechanical Systems (MEMS) mirrors to reduce mechanical components and enhance resolution.


# Parallel Processing Via Slice Number on Mechanical LiDAR
<img src="/figure/mechanical segment.png" width="800">
 Following spherical projection, we segment the LiDAR data frame according to horizontal angular ranges. This procedure involves dividing the range image into equal slices based on predetermined segments to assess the impact of slice size and number on ground segmentation performance. In our experiments, we segment the frame into up to five slices.
 
# Parallel Processing via Sub Frame on Solid-state LiDAR
<img src="/figure/ssl segment.png" width="400">
The initial input data was organized in a fixed structure, containing 78,750 points in a single column. Upon detailed analysis shown in Figure, we determined that this data frame was segmented into five uniform subframes, each comprising 15,750 points, as depicted in the accompanying figure. Notably, the points within the subframes were arranged in a zig-zag pattern. To rectify this, we reorganized the even rows and reconfigured each subframe into a 126x125 matrix. Given the data frame's natural division into five distinct parts, we implemented a five-slice parallel segmentation strategy. Each subframe underwent range-image-based ground segmentation to assess the method's efficacy and functionality under real-world conditions, as demonstrated in Figure.

# Data Collection

To assess the efficacy and compatibility of our parallel ground segmentation approach with solid-state LiDAR sensors, we established a LiDAR-Camera recording framework designed to capture real-world data. Utilizing a synchronized setup within the Robot Operating System (ROS) at approximately 10 Hz, we achieved coherent data collection between LiDAR and camera sensors. Sensor calibration was conducted using a [previously developed method](https://github.com/WPI-APA-Lab/Acrylic-Board-Lidar-Camera-Calibration) , which optimized the alignment and synchronization of data streams, thereby enhancing the accuracy of our real-world testing.

<img src="/figure/Data collection frame work.png" width="400">

The raw data collected show as follow:

<img src="/figure/data collection.png" width="400">

# Configurable Range-image-based FPGA Implementation
Our previous work has been published as an Example in Matlab 2023b. You could try it with HDL Coder and Vision HDL Toolbox. [Example](https://www.mathworks.com/help/visionhdl/ug/lidar-ground-segmentation.html) 

