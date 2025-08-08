# Multi-RGB-D Cameras and Inertial Dataset (with Hyundai Motor Group)

**A comprehensive collection of time-synchronized RGB-D with IMU and LiDAR recordings captured by four Intel RealSense D455 cameras, a MicroStrain GX5-25 IMU, and an Ouster-64 LiDAR. Covering 360° non-overlapping views and diverse indoor/outdoor scenarios, this dataset enables research on confidence-driven multi-camera odometry, depth fusion, and scale-consistent VIO/SLAM.**

<sup>Created in collaboration with Hyundai Motor Group and released alongside our RA-L 2025 paper below.</sup>


<div align="center">

<h2>The More The Better? Confidence-Driven Residual Weighting and Depth Fusion for Multi-RGB-D Inertial Odometry</h2>

[**Seungsang Yun**](#) · [**Jaeho Shin**](#) · [**Jaekwang Cha**](#) · [**Ayoung Kim**](#*)

<sup>Seoul National University / Hyundai Motor Group Robotics Lab</sup>

**RA-L 2025 (to appear at ICRA 2025)**

[[`Paper PDF`](https://arxiv.org/abs/xxxxx)] [[`Project Video`](https://youtu.be/xxxxxxxx)] [[`BibTeX`](#citation)]

<img src="figures/main1.png" width="500">
<img src="figures/main2.png" width="480">

</div>

---




## 1. Dataset Features
* **Synchronized multi-sensor suite** – four hardware-triggered Intel RealSense D455 RGB-D cameras and a IMU
* **360° non-overlapping coverage** – front, back, left, and right views enable true multi-camera VO/VIO/SLAM research  
* **Challenging scenarios** – sequences include strong glare, low-light, texture-less walls, and dynamic occlusion in both indoor and outdoor environments  
* **Complete calibration package** – intrinsics, extrinsics, and camera-to-IMU SE3 transforms provided  
* **Research-ready formats** – ROS bag files, ground truth



## 2. Sensor Suite

<p align="center">
  <img src="figures/sensor_system.png" width="60%" alt="Sensor suite diagram">
</p>

| Component | Model | Rate | Notes |
|-----------|-------|------|-------|
| **RGB-D cameras (×4)** | Intel RealSense D455 | 640 × 360 @ 30 Hz | Front / Left / Right / Back (non-overlapping FOV) |
| **IMU** | MicroStrain 3DM-GX5-25 | 100 Hz | Hardware-synchronized to cameras |
| **LiDAR** | Ouster-64 | 10 Hz | Provides ground-truth via LiDAR-Inertial SLAM |

---

## 3. Sensor Synchronization

<p align="center">
  <img src="figures/rqt.png" width="90%" alt="ROS rqt_plot showing camera sync">
</p>
<p align="center"><sub><em>rqt_plot screenshot confirming sub-millisecond timestamp alignment across the four RGB-D camera topics.</em></sub></p>

All images and depth frames are hardware-triggered.


## 4. Sequences
| ID         | Length        | Challenges (✓)                               | Dataset |
|------------|---------------|----------------------------------------------|---------|
| `indoor`   | 100 m / 104 s | corridor, moderate texture                  | [link](https://drive.google.com/file/d/1MD2zmZHPLW_h_ONGBlc0HLY_2cVlbXYY/view?usp=drive_link) |
| `indoor2`  |  69 m / 159 s | spacious indoor, occlusion ✓                | [link](https://drive.google.com/file/d/11RcQbHpIhMuoP6TgFiVBIgByrNC5rhe0/view?usp=drive_link) |
| `glare`    |  45 m / 155 s | strong sunlight glare ✓                     | [link](https://drive.google.com/file/d/1ylb_0hbAf5sT-TQ_eUID4nAHQw7wPhRe/view?usp=drive_link) |
| `txl`      |  68 m / 150 s | texture-less walls ✓ glare ✓ dark ✓         | [link](https://drive.google.com/file/d/1FvlKwXq3G0CIpHw0hlqjLOmNkvrGJI1p/view?usp=drive_link) |
| `occ`      |  67 m / 146 s | front-camera occlusion ✓                    | [link](https://drive.google.com/file/d/1EiEpvv4hF2UT27MViXXgsQWq4u4SN_ps/view?usp=drive_link) |
| `dark`     |  73 m / 169 s | low light, large rotations ✓ texture-less ✓ | [link](https://drive.google.com/file/d/17RmePdUHBrZfHKipVJ0AJ7hp3bsrU79a/view?usp=drive_link) |
| **Calibration**  | –             | intrinsics & extrinsics               | [link](https://drive.google.com/file/d/1cK73j_JzyYdibqS_YILAjq_acHM0JYke/view?usp=drive_link) |
| **Ground truth**| –             | LiDAR-IMU SLAM trajectories (tum foramt)| [link](https://drive.google.com/file/d/1bQqDPedCUnpDyaIooqLUek4Sh8zu3D78/view?usp=drive_link) |


---
## 5. Example of Multi-camera images

#### Sequence. Indoor #1
![Indoor #1 – LiDAR projected](figures/indr.png)

#### Sequence. Indoor #2
![Indoor #2 – LiDAR projected](figures/indr2.png)

#### Sequence. Glare
![Glare scene – LiDAR projected](figures/glare.png)

#### Sequence. Texture-less
![Texture-less scene – LiDAR projected](figures/txl.png)

#### Sequence. Occlusion
![Occlusion scene – LiDAR projected](figures/occ.png)

#### Sequence. Dark
![Low-light scene – LiDAR projected](figures/dark.png)



## 6. Multi-cameras and LiDAR Calibration examples

![Indoor #2 – projected cloud](figures/cam_lidar/indr2.png)
![Indoor #1 – projected cloud](figures/cam_lidar/indr.png)
![Glare scene – projected cloud](figures/cam_lidar/glare.png)

## 7. Citation


If you use this dataset, please cite our RA-L 2025 paper:

```bibtex
@article{yun2025multicam,
  title   = {The More The Better? Confidence-Driven Residual Weighting and Depth Fusion for Multi-RGB-D Inertial Odometry},
  author  = {Yun, Seungsang and Shin, Jaeho and Cha, Jaekwang and Kim, Ayoung},
  journal = {IEEE Robotics and Automation Letters},
  year    = {2025},
  volume  = {TBD},
  number  = {TBD},
  pages   = {TBD},
  doi     = {TBD}
}

```

## 8. Contact
For any questions or issues, please contact **Seungsang Yun** at <seungsang@snu.ac.kr>.

## 9. Acknowledgement
We are deeply grateful to Hyundai Motor Group for their close collaboration and generous support throughout this project.

<p align="center">
  <a href="https://www.hyundaimotorgroup.com">
  <img src="figures/rpm.png"    width="130" alt="RPM Robotics Lab">
  <img src="figures/snu.png"    width="180" alt="Seoul National University">&nbsp;&nbsp;&nbsp;
  <img src="figures/hyundai.svg" width="260" alt="Hyundai Motor Group">
</p>
