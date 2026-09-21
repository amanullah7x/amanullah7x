# Amanullah Naseer

**Computer & Software Engineer | Autonomous Systems, Edge AI & Robotics Telemetry**  
Rawalpindi, Pakistan • [LinkedIn](https://linkedin.com/in/amanullah7x) • [Email](mailto:anaseer.ce41ceme@ce.ceme.edu.pk) • [Portfolio](https://amanullah7x.github.io)

---

### Core Focus

I engineer high-reliability software architectures operating at the boundary of low-level hardware constraints and high-throughput real-time telemetry:
* **Autonomous UAV Systems:** PX4/ArduPilot configuration, companion computer integration, offboard visual servoing, and digital-twin simulation (NVIDIA Isaac Sim + ROS2).
* **Edge Computer Vision:** Quantizing, benchmarking, and deploying detection (YOLOv8/v11) and multi-object tracking (BoT-SORT/ByteTrack) pipelines onto NVIDIA Jetson AGX Orin & embedded NPUs.
* **Ground Control Software:** Developing low-latency desktop/web GCS interfaces handling high-rate (50+ Hz) telemetry feeds without UI event loop starvation.

---

### Technical Toolkit

| Domain | Technologies & Frameworks |
|---|---|
| **Languages & Core** | Python, C# (.NET), TypeScript, C++17/20, Bash |
| **Robotics & Simulation** | ROS/ROS2 Humble, Gazebo, Isaac Sim 4.0+, ArduPilot, PX4, MAVLink, Mission Planner |
| **Edge AI & Computer Vision** | TensorRT, YOLOv8 / YOLOv11, MobileNet, BoT-SORT, ByteTrack, OpenCV, Coral EdgeTPU |
| **Networking & Telemetry** | ZeroMQ (ZMQ), MQTT, WebSockets, HTTP/HTTPS, Protobuf, Serial UART |
| **Frontend & Systems UI** | PyQt6, React.js, Next.js, Electron.js, Node.js, Tailwind CSS |
| **Embedded & Compute Hardware** | NVIDIA Jetson AGX Orin, Raspberry Pi 5, Pixhawk 6C/6X, ESP32, Rockchip RK3588 |

---

### Featured Architectures & Repositories

#### 🛰️ [Autonomous UAV Digital Twin (PX4 + Isaac Sim + ROS2)](https://github.com/amanullah7x/uav-isaac-sim-digital-twin)
A software-in-the-loop (SITL) environment coupling NVIDIA Isaac Sim with PX4 flight stacks and offboard visual servoing via ROS2 Humble.
* Integrated bi-directional MAVLink bridges streaming synthetic camera frames and 50 Hz IMU/state telemetry to companion tracking nodes.
* Closed the control loop with offboard velocity vector commands, validating terminal guidance and autonomous waypoint tracking in simulation prior to physical flight.

#### 🎯 [Jetson Edge Multi-Object Tracking Pipeline](https://github.com/amanullah7x/edge-vision-tracking-jetson)
A deterministic deployment pipeline for real-time target detection and multi-object tracking on resource-constrained compute modules (Jetson AGX Orin).
* Benchmark-tested FP32 vs. FP16 vs. INT8 quantized YOLO variants with BoT-SORT to balance inference latency (<22ms) and tracking continuity under high-speed motion.
* Architected hardware-accelerated GStreamer pipelines (NVMM zero-copy memory) to eliminate frame ingestion jitter.

#### 🎛️ [High-Throughput Desktop Ground Control Station (PyQt6 / .NET)](https://github.com/amanullah7x/pyqt-uav-ground-station)
A modular ground station interface designed to consume high-frequency drone telemetry without starving the UI thread.
* Decoupled raw telemetry ingestion (50–60 Hz) into dedicated background worker threads (`QThread`) over ZeroMQ pub/sub.
* Built a thread-safe circular ring buffer aggregated at 20 Hz for instrument and map rendering, with dedicated zero-latency bypass queues for critical flight safety interrupts.

---

### Engineering Approach
* **Hardware-Software Decoupling:** Isolating data transport, neural inference loops, and UI rendering into distinct execution domains to guarantee deterministic real-time behavior.
* **Simulation-First Validation:** Validating flight controllers, state estimators, and vision pipelines in physics-accurate digital twins before running field hardware tests.
* **Production-Grade Tooling:** Prioritizing native performance, clean IPC, low memory allocation, and maintainable documentation over brittle dependency graphs.
