# Amanullah Naseer

**Computer & Software Engineer | Autonomous Systems, Edge AI & Robotics Telemetry**  
Rawalpindi, Pakistan • [LinkedIn](https://linkedin.com/in/amanullah7x) • [Email](mailto:anaseer.ce41ceme@ce.ceme.edu.pk) • [Portfolio Website](https://amanullah7x.github.io)

---

### Core Focus

I engineer high-reliability software architectures operating at the boundary of low-level hardware constraints and high-throughput real-time telemetry:
* **Autonomous UAV Systems:** PX4/ArduPilot configuration, companion computer integration (RPi 5 / Jetson AGX Orin), offboard visual servoing, and digital-twin simulation (NVIDIA Isaac Sim + ROS2).
* **Edge Computer Vision:** Quantizing, benchmarking, and deploying detection (**Custom RF-DETR Nano**, YOLOv8/v11) and multi-object tracking (BoT-SORT/ByteTrack) pipelines on embedded NPUs (Google Coral EdgeTPU, Rockchip RK3588, TensorRT).
* **Ground Control Software:** Developing low-latency desktop/web GCS interfaces in PyQt6 handling high-rate (50+ Hz) telemetry feeds without UI event loop starvation.
* **Payload & Sensor Integration:** Serial communication with BaseCam 3-axis gimbal controllers, ViewLink Pro camera C++ SDK integration, and Tailscale Meshnet RTSP video streaming across devices.

---

### Technical Toolkit

| Domain | Technologies & Frameworks |
|---|---|
| **Languages & Core** | Python, C# (.NET), TypeScript, C++17/20, Bash |
| **Robotics & Simulation** | ROS/ROS2 Humble, Gazebo, Isaac Sim 4.0+, ArduPilot, PX4, MAVLink, Mission Planner |
| **Edge AI & Computer Vision** | RF-DETR Nano, TensorRT, YOLOv8/v11, BoT-SORT, ByteTrack, OpenCV, Coral EdgeTPU |
| **Networking & Telemetry** | ZeroMQ (ZMQ), MQTT, Tailscale Meshnet, WebSockets, Protobuf, Serial UART |
| **Frontend & Systems UI** | PyQt6, React.js, Next.js, Electron.js, Node.js, Tailwind CSS |
| **Embedded & Compute Hardware** | NVIDIA Jetson AGX Orin, Raspberry Pi 5, Pixhawk 6C/6X, Dual MIPI-CSI Cams, ESP32 |

---

### Featured Architectures & Repositories

#### 🛰️ [Autonomous UAV Digital Twin (PX4 + Isaac Sim + ROS2)](https://github.com/amanullah7x/uav-isaac-sim-digital-twin)
A software-in-the-loop (SITL) environment on Ubuntu coupling NVIDIA Isaac Sim with PX4 flight stacks and offboard visual servoing via ROS2 Humble.
* Integrated bi-directional MAVLink bridges streaming synthetic camera frames and 50 Hz IMU/state telemetry to companion tracking nodes.
* Calculates real-time pixel offsets ($dx/dy$) to override manual control via MAVLink offboard velocity setpoints, validating terminal guidance prior to physical flight.

#### 🎯 [Jetson Edge Multi-Object Tracking Pipeline (RF-DETR Nano)](https://github.com/amanullah7x/edge-vision-tracking-jetson)
A deterministic deployment pipeline for real-time target detection and multi-object tracking on resource-constrained compute modules (Jetson AGX Orin).
* Trained a custom **RF-DETR Nano** model achieving **89.4% mAP@50, 86.8% precision, and 89.2% recall** for granular hierarchical sub-component detection (**Tank**, **Turret**, and **Track**).
* Implemented hardware-accelerated GStreamer pipelines (NVMM zero-copy memory) and TensorRT INT8 quantization to achieve sub-22ms inference latency.

#### 🎛️ [High-Throughput Desktop Ground Control Station (PyQt6 / .NET)](https://github.com/amanullah7x/pyqt-uav-ground-station)
A modular ground station interface designed to consume high-frequency drone telemetry without starving the UI thread.
* Decoupled raw telemetry ingestion (50–60 Hz) into dedicated background worker threads (`QThread`) over ZeroMQ pub/sub.
* Built a thread-safe circular ring buffer aggregated at 20 Hz for instrument and map rendering, with dedicated zero-latency bypass queues for critical flight safety interrupts.

---

### Advanced R&D Initiatives
* **Stereo Camera Depth Estimation:** Designing dual MIPI-CSI setups on Raspberry Pi 5 to calculate precise target distances and dimensions ($D = \frac{f B}{\delta}$) in real time, replacing heavy 500g LiDAR payloads with dual 25g camera modules.
* **Visual SLAM in GPS-Denied Environments:** Building real-time 3D mapping and autonomous path planning (SLAM3R) for tactical UAV operations in jammed or GPS-denied operational zones.
* **Vision-Language-Action (VLA) Robotics:** Exploring OpenVLA models for natural language and AR-assisted UAV direction.
