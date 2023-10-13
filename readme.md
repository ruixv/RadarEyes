# RadarEyes

> mmWave (millimeter-wave) pointcloud dataset and preprocessing code

RadarEyes is a unique dataset sourced from the paper ["DREAM-PCD: Deep Reconstruction and Enhancement of mmWave Radar Pointcloud"](https://arxiv.org/abs/2309.15374).

## Dataset Introduction

RadarEyes is a large-scale dataset focusing on indoor mmWave radar pointcloud. It consists of aligned horizontally placed mmWave radar, vertically placed mmWave radar, LiDAR, and tracking cameras, capturing **120,000** frames of incoherent mmWave radar and **1,200,000** frames of coherent mmWave radar, along with corresponding poses and LiDAR pointcloud.

## Dataset Implementation

![RadarEyes](https://img-blog.csdnimg.cn/a568c502207a48eb89a9504ebe16b350.png)


Our sensor platform, as shown above, is built on a remotely controllable vehicle and equipped with four sensors:

**Two orthogonally placed mmWave radars:** Both are Texas Instruments AWR1843BOOST-EVM paired with a DCA1000-EVM for raw data capture. Each radar board has 3 transmitting antennas and 4 receiving antennas, operating at 77-81 GHz. Notably, RadarEyes contains raw ADC data and the source code for loading and processing the ADC data, which can significantly facilitate related research.

**An 128-beam LiDAR:** LS-128 S2 1550nm [1], an automotive-grade hybrid solid-state LiDAR.

**Camera and IMU:** ZED 2i Camera [2], an integrated device for simultaneous localization and mapping featuring optical odometry and IMU. The frame rate is set to 30fps, and the localization accuracy is under 1% closed-loop drift under intended use conditions.

### Hardware Configuration

| Horizontal Radar | Vertical Radar | Lidar |
|-----------------|---------------|------|
| FMCW             | FMCW           | Pulse |
| 10              | 100            | 10    |
| $77.70-78.90GHz$ | $79.1-80.70GHz$ | $193THz$ |
| 3                | 3               | -    |
| 4                | 4               | -    |
| 0.12             | 0.09375         | Lidar |
| 15.99            | 12.0            | Lidar |
| $11.3^\circ$         | $45^\circ$          | $0.09^\circ$ |
| $\pm 50^\circ @6dB$    | $\pm 20^\circ @6dB$ | $\pm 60^\circ$ |
| $45^\circ$           | $11.3^\circ$        | $0.1^\circ$ |
| $\pm 20^\circ @6dB$   | $\pm 50^\circ @6dB$  | $\pm 12.5^\circ$ |
| $0.12 m/s$       | $0.55 m/s$       | -     |
| $7.63 m/s$        | $4.47 m/s$       | -     |

## How to access the dataset

The paper associated with this dataset is currently under review. Therefore, only a partial dataset is currently available.

To obtain the dataset, please sign the [agreement](datasetAgreement.pdf), scan and send it to gengruixu@mail.ustc.edu.cn. You will receive a notification email which includes the download links of the partial dataset in two days. The complete dataset will be made public once the paper is accepted.

### Preprocessing Code

We provide Python scripts for data handling, including data loading, preprocessing, and visualization. These scripts are bundled with the part of the dataset provided via the download links in the confirmation email.

## Citation

Please cite the following paper if this dataset is helpful to your research

```bibtex
@article{geng2023dreampcd,
  title={DREAM-PCD: Deep Reconstruction and Enhancement of mmWave Radar Pointcloud},
  author={Geng, Ruixu and Li, Yadong and Zhang, Dongheng and Wu, Jincheng and Gao, Yating and Hu, Yang and Chen, Yan},
  journal={arXiv preprint arXiv:2309.15374},
  year={2023},
  url={https://arxiv.org/abs/2309.15374},
  doi={10.48550/arXiv.2309.15374}
}
```


--- 

**References:**

1. [Leishen Lidar](https://www.leishen-lidar.com/tof/158)
2. [ZED 2i Camera](https://www.stereolabs.com/zed-2i/)


> Both the dataset and this README are currently being updated. Please stay tuned for updates on BaiduYun / OneDrive.

