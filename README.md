# 🧠 Brain-Controlled Wheelchair using EEG and Bluetooth

## Overview
This project implements a **brain-controlled wheelchair system** using EEG signals from a NeuroSky MindWave headset. The system translates brain activity (attention levels and eye blinks) into movement commands, which are transmitted via Bluetooth to a Raspberry Pi controlling the wheelchair motors.

It demonstrates a real-world application of **brain-computer interface (BCI)** technology integrated with embedded systems and mobile applications.

---

## 🎯 Objective
- Enable wheelchair movement using brain signals
- Process EEG data in real time
- Detect attention levels and eye blink patterns
- Translate signals into motor control commands

---

## 🏗️ System Architecture

1. **EEG Headset (NeuroSky MindWave)**
   - Captures brain signals (attention, meditation, blink)

2. **Android Application**
   - Processes EEG signals using NeuroSky SDK
   - Detects:
     - Attention level
     - Eye blinks (including double blink)
   - Sends commands via Bluetooth

3. **Raspberry Pi**
   - Acts as Bluetooth server
   - Receives commands from Android device
   - Controls motors via GPIO pins

4. **Motor Driver + Wheelchair**
   - Executes movement commands:
     - Forward
     - Right turn
     - Stop

---

## ⚙️ Key Features

### 🧠 Attention-Based Movement
- If attention level exceeds threshold → wheelchair moves forward

### 👁️ Blink Detection
- Single blink → signal detected
- Double blink → triggers directional control (e.g., right turn)

### 📡 Bluetooth Communication
- Android acts as client
- Raspberry Pi acts as server (RFCOMM socket)

### 🎛️ Motor Control
- GPIO pins control motor direction and enable signals
- Differential motor control for movement

---

## 🔄 Workflow

1. EEG headset streams brain signals to Android device  
2. Android app processes signals using NeuroSky SDK  
3. Commands are generated:
   - Numeric values → attention levels  
   - "DOUBLE_BLINK" → directional control  
4. Commands sent via Bluetooth  
5. Raspberry Pi receives commands and drives motors  

---

## 🛠️ Tech Stack

### Hardware
- NeuroSky MindWave EEG Headset  
- Raspberry Pi  
- Motor Driver Module  
- Wheelchair platform  

### Software
- Python (Raspberry Pi control logic)
- Java (Android application)
- NeuroSky SDK
- Bluetooth (RFCOMM communication)
- RPi.GPIO
