# 🌐 Distance Vector Routing Protocol Simulation

A lightweight and interactive simulation of the **Distance Vector Routing Protocol** based on the **Bellman-Ford Algorithm**.

This project demonstrates how routers in a computer network discover optimal paths to different destinations by exchanging **distance vectors with their neighboring routers**. The simulation continues iteratively until the routing tables reach a stable state, known as **convergence**.

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Objectives](#-objectives)
- [Key Features](#-key-features)
- [Concepts Covered](#-concepts-covered)
- [How Distance Vector Routing Works](#-how-distance-vector-routing-works)
- [Bellman-Ford Equation](#-bellman-ford-equation)
- [Example Network](#-example-network)
- [Routing Table Updates](#-routing-table-updates)
- [Count-to-Infinity Problem](#-count-to-infinity-problem)
- [Split Horizon](#-split-horizon)
- [Project Structure](#-project-structure)
- [Requirements](#-requirements)
- [Installation](#-installation)
- [Usage](#-usage)
- [Input Format](#-input-format)
- [Sample Workflow](#-sample-workflow)
- [Algorithm](#-algorithm)
- [Time Complexity](#-time-complexity)
- [Applications](#-applications)
- [Limitations](#-limitations)
- [Future Enhancements](#-future-enhancements)
- [Learning Outcomes](#-learning-outcomes)
- [Contributing](#-contributing)
- [License](#-license)

---

# 📖 Overview

**Distance Vector Routing** is a routing protocol in which every router maintains a routing table containing the best-known distance to each destination and the next hop used to reach that destination.

Routers do not have complete knowledge of the entire network initially. Instead, each router communicates with its **direct neighbors** and exchanges information about the destinations it knows.

Using the **Bellman-Ford algorithm**, routers repeatedly update their routing tables whenever a shorter path is discovered.

The process continues until no further improvements can be made.

### Basic Process

```text
Initialize Routing Tables
          ↓
Exchange Distance Vectors
          ↓
Calculate New Shortest Paths
          ↓
Update Routing Tables
          ↓
Exchange Updated Vectors
          ↓
      Convergence?
       ↙       ↘
     No         Yes
     ↓           ↓
  Repeat      Finish
