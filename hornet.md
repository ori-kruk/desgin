---
title: Hornet desgin
description: ROS2
marp: true
# size: 16:9
paginate: true
theme: uncover

---
# Agenda
- Current System Design
  - State Machine
  - Mavlink Routing
- New System Architecture
  - General Design
  - Control Design

---
# Agenda
- Main Design Principles
  - Setup Definition
  - ROS
    - Nodes, Messages, Parameters
    - Echo System
    - DDS
  - Development Standard

---
# Agenda
- Migration Process
  - Home <--> Field
  - Work Method
  - On going migration

---
### State Machine
![image]()

---
### Mavlink Routing
![](images/pix_cc_gcs_block.drawio.png)

---
### General Design
![](images/general_design.drawio.png)

---
### Control Design
![](images/control.drawio.png)

---
### Design Zen
- Ros is only a way of implementation
  - Bridge can always be used as a legitimate solution
- "Don't invent the wheel..."
- Design must consider **Testability**
- System resources are limited (network, cpu, memory)
  
---
### Setup Definition
##### Hardware
- Rom Box III (Jetson Orin)
- [New Gimbal](https://gremsy.com/gremsy-introduces-two-axis-mio-gimbal-for-drone-developers)
- New Sensors:
  - temp, range, proximity, stereo (point cloud)
  
![bg 30%](images/two-axis_mio_gimbal.png)

---
### Setup Definition
##### Software
- Ubuntu LTS latest (22.04)
- ROS LTS latest (Humble)
- DDS Vendor (fast rtps / cyclonDDS)

---
### ROS verbs
- Nodes
- Topics and Messages
- Pub/Sub
- Service: RPC
- Action: long time service
- Parameters: config node behavior

### Nodes
- Units of work
- for example
  - camera capture
  - camera control
  - tracker
  - streaming
  - gpio control

---
### Messages
- Units of data
  - not mixing data that not from the same domain
- as many as needed
- use standard msgs

---
### Topic
- Declarative
- Namespace
- Try to use common name from community
  
---
---
### Echo System

---
### DDS

---
### Development Standard
-  deb (dependency)
-  docker
-  documentation (README.md)
-  test ?

---
### Migration Process
Field <--------------------------------> Home
![](images/domains.drawio.png)

---
### Work Method
- Describe each cube from "General Design" in ROS orientation
- Design each node
- Implementation
- Tests
- Integration

---
### On going migration
- Partial test on exist system
- Run as Payload