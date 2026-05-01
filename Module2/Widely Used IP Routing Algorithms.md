# 📘 Most Widely Used IP Routing Algorithms (Detailed and Clear Explanation)

---

## 🔹 Introduction

In the Internet, data is sent in the form of packets from one device to another. To make this possible, routers must decide the best path for each packet. This process is called IP routing, and it is done using routing algorithms.

Although many routing algorithms exist in theory, in real-world networks only a few are widely used. The most important and commonly used ones today are:

- Link State Routing (used inside networks)  
- Path Vector Routing (used across the Internet)  

These two algorithms together form the backbone of modern Internet routing.

---

## 🔷 1. Link State Routing (Most used inside networks)

### 🔹 Where it is used

Link State Routing is mainly used within organizations, data centers, and ISP internal networks. It is the most efficient method for internal routing because it provides fast and accurate route calculation.

It is implemented using the routing protocol:

- Open Shortest Path First (OSPF)

---

### 🔹 Basic Idea

In Link State Routing, every router tries to build a complete map of the entire network topology. Instead of relying only on neighbors, each router knows how every other router in the network is connected.

Once the full map is available, the router calculates the best path using a shortest path algorithm.

---

### 🔹 Step-by-step Working

#### 1. Discovering neighbors

Each router first identifies the routers directly connected to it. This helps it understand its immediate surroundings.

---

#### 2. Measuring link cost

Each connection between routers is assigned a cost value. This cost may depend on:

- bandwidth (higher is better, lower cost)  
- delay  
- congestion  
- reliability  

---

#### 3. Creating Link State Packet (LSP)

Each router creates a packet called a Link State Packet, which contains:

- router ID  
- list of neighbors  
- cost of each link  

---

#### 4. Flooding the network

The LSP is sent (flooded) to all routers in the network. This ensures every router receives the same information.

---

#### 5. Building topology database

After receiving LSPs from all routers, each router builds a complete network graph (topology map).

---

#### 6. Finding best path

Each router applies Dijkstra’s Shortest Path Algorithm to calculate the shortest and most efficient path to every destination.

---

### 🔹 Advantages

- Very fast convergence (quick update after network changes)  
- No routing loops  
- Accurate routing decisions  
- Works well in large enterprise networks  

---

### 🔹 Disadvantages

- Requires more memory (stores full network map)  
- Higher CPU usage (due to complex calculations)  
- More complex to configure than simpler protocols  

---

### 🔹 Why it is widely used?

It is used internally because it provides fast, reliable, and loop-free routing, which is essential for modern enterprise and ISP networks.

---

## 🔷 2. Path Vector Routing (Most used on Internet backbone)

### 🔹 Where it is used

Path Vector Routing is used for communication between different networks (called Autonomous Systems or AS). It is the routing method used across the global Internet.

It is implemented using:

- Border Gateway Protocol (BGP)

---

### 🔹 Basic Idea

Unlike Link State Routing, Path Vector Routing does not try to find the shortest path based on cost. Instead, it focuses on:

- the full path taken by the packet (sequence of networks)  
- routing policies defined by ISPs  
- loop prevention  

Each route carries complete path information.

---

### 🔹 Step-by-step Working

#### 1. Route advertisement

Each router (or ISP) advertises available routes to its neighboring networks.

---

#### 2. Path information exchange

Each routing update contains:

- destination network  
- complete path of Autonomous Systems (AS path)  

Example:

Network A → AS1 → AS2 → AS3 → Destination  

---

#### 3. Loop prevention

If a router sees its own AS number in the path, it rejects the route. This prevents routing loops.

---

#### 4. Policy-based selection

Instead of choosing the shortest path, routers consider:

- ISP policies  
- business agreements  
- path reliability  
- AS path length  

---

#### 5. Best path selection

The router selects the best route based on rules, not just distance.

---

### 🔹 Advantages

- Prevents routing loops effectively  
- Highly scalable for Internet-level routing  
- Supports policy-based routing (very important for ISPs)  
- Suitable for inter-network communication  

---

### 🔹 Disadvantages

- Slower convergence compared to internal routing protocols  
- Complex configuration  
- Not optimized for speed, but for control and stability  

---

### 🔹 Why it is widely used?

It is used because the Internet is made up of thousands of independent networks (ISPs). These networks need control over routing decisions, not just shortest paths. BGP provides this control.

---

## 🔷 Final Summary

In modern IP networks:

### ✔ Inside networks (LAN, enterprise, ISP internal):
- Link State Routing (OSPF) is used  
- Focus: speed, accuracy, shortest path  

---

### ✔ Between networks (Internet backbone):
- Path Vector Routing (BGP) is used  
- Focus: policy control, scalability, loop prevention  

---

## 📌 Conclusion

The most widely used IP routing algorithms are not just based on shortest path, but on the requirement of the network environment. Link State Routing ensures fast and efficient internal communication, while Path Vector Routing ensures stable and controlled global Internet routing.