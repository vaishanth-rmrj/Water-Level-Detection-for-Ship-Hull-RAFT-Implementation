# Water Level Detection for Ship Hull

## Introduction
This repository contains the source code and paper for a project aimed at detecting water levels in the hull of a ship. The project was a collaboration between five team members: Vaishanth Ramaraj, Sri Sai Charan V, Pranav Limbekar, Yash Kulkarni, and Jerry Pittman, Jr. The goal of this project was to create a tool that could detect water levels in real-time, thereby helping to prevent water ingress and potential damage to the ship.

## Algorithm
The algorithm used in this project is called RAFT (Recurrent All Pairs Field Transforms for Optical Flow)(https://arxiv.org/pdf/2003.12039.pdf). It was proposed in ECCV 2020 by Zachary Teed and Jia Deng. The RAFT algorithm is a state-of-the-art method for optical flow estimation, and it was adapted for use in this project to detect water levels in a ship's hull.

## Software Requirements
The code has been tested on a computer with PyTorch 1.6, Cuda 10.1, and CPU. To set up the environment, run the following commands in a conda prompt:
```
conda create --name raft
conda activate raft
conda install pytorch=1.6.0 torchvision=0.7.0 cudatoolkit=10.1 matplotlib tensorboard scipy opencv -c pytorch
```

## Running the Code
To run the code on a video of a ship's hull to detect water levels, use the following commands:

```
python main.py
```

If you do not have a GPU, you will need to comment out line 20 and uncomment line 23 before running the code:

```
# device = torch.device("cuda" if torch.cuda.is_available() else "cpu")
device = "cpu"
```

Training a CNN
To train a CNN for the task of water level detection, use the following command:

```
python cnn_training.py
```

Hardware Implementation with Raspberry Pi
The code for the hardware implementation using a Raspberry Pi can be run with the following command:

```
python3 waterdetection.py
```

Unfortunately, due to the limited processing power of the Raspberry Pi, the water levels in the video may not be accurately detected. Water level detection is a computationally intensive task, particularly when there is flow involved.

Final Output Video
The final output video from the project can be found in this Google Drive folder(https://drive.google.com/drive/folders/1S9JEo39-vkEtpP1TtJBmfUNx4ZZ1hCPv?usp=sharing).

Conclusion
In conclusion, the Water Level Detection for Ship Hull project aimed to develop a tool for detecting water levels in real-time in a ship's hull. The RAFT algorithm was adapted for this task, and the code was implemented on both a computer and a Raspberry Pi. While the hardware implementation was limited by the processing power of the Raspberry Pi, the code run on a computer was able to accurately detect water levels in a video of a ship's hull.

