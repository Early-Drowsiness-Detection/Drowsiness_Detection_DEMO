# Drowsiness Detection DEMO

### This repository contains the official implementation of our research paper: 
[Feasibility Study on Contactless Feature Analysis for Early Drowsiness Detection in Driving Scenarios](https://doi.org/10.3390/electronics14040662) <br/>

<br/>
This is a demo program for drowsiness detection using facial features and physiological signals. <br/>
<br/>

While our research explores multi-class drowsiness detection, this demo focuses on a **simplified binary classification** using **XGBoost** to distinguish between drowsy and alert states.  


## 🎥 Demonstration Videos

| Alert State Detection | Drowsy State Detection |
|------------------------|----------------------|
| [![Alert](http://img.youtube.com/vi/vGg1ZLzEVkQ/0.jpg)](https://youtu.be/vGg1ZLzEVkQ) | [![Drowsy](http://img.youtube.com/vi/XYcVI3s64IA/0.jpg)](https://youtu.be/XYcVI3s64IA) |



## 📌 Key Features

- **Facial Landmark Detection**: Extracting eye aspect ratio (EAR), mouth aspect ratio (MAR), eyebrow width (EBW), and eyebrow height (EBH).
- **Remote Photoplethysmography (PPG) Signal Processing**: Estimating heart rate and LF/HF ratio from facial videos.
- **Machine Learning Model**: Using **XGBoost** for binary classification (Drowsy or Alert).

This demo program implements our approach using `OpenCV`, `Mediapipe`.

## 🛠 Usage

**To run the drowsiness detection system:**
   ```bash
   python main.py
   ```
   
**To run with custom parameters, use:**
  ```bash
  python main.py --use_ppg True --use_detect True --scale_factor 1.5 --use_saved_calibration False --save_calibration True --calibration_path 'calibration/user.json' --saved_calibration_path 'calibration/user.json'
  ```
#### Command-line Arguments

| Argument | Type | Default | Description |
|----------|------|---------|-------------|
| `--use_ppg` | Bool | `True` | Enable or disable PPG processing |
| `--use_detect` | Bool | `True` | Enable or disable landmark detection |
| `--scale_factor` | Float | `1.5` | Set the window scale factor |
| `--use_saved_calibration` | Bool | `False` | Load previously saved calibration data |
| `--save_calibration` | Bool | `True` | Save newly computed calibration data |
| `--calibration_path` | String | `'calibration/user.json'` | Path to save calibration data |
| `--saved_calibration_path` | String | `'calibration/user.json'` | Path to load calibration data |

> **Note:** During the first **30 seconds**, the system will perform calibration. Please maintain a neutral state during this period.

   
