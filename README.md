# Distance Vector Routing Protocol Simulation

A lightweight implementation and visual simulation of the **Distance Vector Routing Algorithm** using the **Bellman-Ford Algorithm**. This project simulates how network routers continuously update their routing tables through iterative exchanges with immediate neighbors until convergence is achieved.

---

## Key Features

- **Iterative Bellman-Ford Implementation**: Computes the shortest path from each node to all other nodes across the topology.
- **Dynamic Routing Table Updates**: Displays real-time updates as routers exchange distance vectors.
- **Count-to-Infinity & Split Horizon Handling**: Demonstrates routing loop challenges and techniques used to prevent them.
- **Custom Topology Input**: Supports node and edge additions via adjacency matrices or direct configuration files.

---

## How It Works

Distance Vector Routing relies on the **Bellman-Ford equation**:

$$D_x(y) = \min_v \{ c(x, v) + D_v(y) \}$$

Where:
- $D_x(y)$ is the estimated cost from router $x$ to router $y$.
- $c(x, v)$ is the direct cost between router $x$ and neighbor $v$.
- $D_v(y)$ is neighbor $v$'s cost estimate to reach router $y$.

1. **Initialization**: Each router initializes its routing table with direct link costs to immediate neighbors ($\infty$ for non-neighbors).
2. **Exchange**: Routers periodically send their distance vectors to direct neighbors.
3. **Update**: Upon receiving a vector, a router recomputes its table. If a cheaper path is discovered, the table updates and triggers a new broadcast.
4. **Convergence**: The exchange continues until no router updates its routing table.

## Project Structure

```text
.
├── src/
│   ├── main.py          # Main execution script / simulation engine
│   ├── router.py        # Router node representation and vector logic
│   └── network.py       # Graph network topology manager
├── data/
│   └── topology.txt     # Input matrix/graph configuration
├── README.md            # Project documentation
└── requirements.txt     # Python dependencies (if applicable)
