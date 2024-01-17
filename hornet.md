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
  - Nodes
  - Messages
  - Parameters
  - Standard

---
# Agenda
- Migration Process
  - Home <--> Field
  - Work Method

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
### Setup Definition
- Ubuntu22
- RosHumble
- DDS Vendor

---
### Nodes
- as small as possible
- 

---
### Messages
- as many as needed
- use standard msgs

---
### Parameters

---
### Standard
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