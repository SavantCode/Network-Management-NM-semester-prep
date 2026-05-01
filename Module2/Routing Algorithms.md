```md
# 📘 IP Routing Algorithms (Detailed Explanation)

---

## 🔹 Introduction

IP routing is the process of selecting the best path for sending packets from a source to a destination across an interconnected network (internet). Routers use routing algorithms to decide the next hop for each packet based on routing tables and network conditions.

---

## 🔹 Types of IP Routing Algorithms

IP routing algorithms are mainly classified into:

- Distance Vector Routing Algorithm  
- Link State Routing Algorithm  
- Path Vector Routing Algorithm  
- Hybrid Routing Algorithm  

---

## 🔹 1. Distance Vector Routing Algorithm

### 📌 Concept

In Distance Vector Routing, each router shares its routing table with its immediate neighbors only.

It is based on:

- Distance (hop count, cost)  
- Direction (next hop router)  

---

### 📌 Working

- Each router maintains a routing table  
- Periodically shares it with neighbors  
- Receives updates and recalculates best path using Bellman-Ford algorithm  
- Updates its routing table  

---

### 📌 Formula (Bellman-Ford principle)

Cost to destination = Cost to neighbor + Cost from neighbor to destination  

---

### 📌 Example Protocols

- RIP (Routing Information Protocol)  

---

### 📌 Advantages

- Simple to implement  
- Low computational overhead  

---

### 📌 Disadvantages

- Slow convergence  
- Routing loops  
- Count-to-infinity problem  

---

## 🔹 2. Link State Routing Algorithm

### 📌 Concept

Each router builds a complete map of the network topology instead of just sharing with neighbors.

---

### 📌 Working Steps

- Discover neighbors  
- Measure cost to neighbors  
- Create Link State Packet (LSP)  
- Flood LSP to all routers  
- Each router builds full topology map  
- Use Dijkstra’s shortest path algorithm to compute best route  

---

### 📌 Example Protocols

- OSPF (Open Shortest Path First)  
- IS-IS  

---

### 📌 Advantages

- Fast convergence  
- No routing loops  
- More accurate routing  

---

### 📌 Disadvantages

- High memory usage  
- Complex computation  
- Requires more CPU power  

---

## 🔹 3. Path Vector Routing Algorithm

### 📌 Concept

Path Vector Routing stores the entire path information to the destination.

---

### 📌 Working

Each router maintains a list of:

- Destination network  
- Complete path (sequence of AS or routers)  

When update is received, router checks:

- Loop prevention  
- Path validity  

---

### 📌 Example Protocol

- BGP (Border Gateway Protocol)  

---

### 📌 Advantages

- Prevents routing loops  
- Suitable for large networks (Internet backbone)  

---

### 📌 Disadvantages

- Slower updates  
- Complex path management  

---

## 🔹 4. Hybrid Routing Algorithm

### 📌 Concept

Hybrid routing combines features of:

- Distance Vector  
- Link State  

---

### 📌 Working

- Uses distance vector for simplicity  
- Uses link state for faster convergence  
- Optimized decision making  

---

### 📌 Example Protocol

- EIGRP (Enhanced Interior Gateway Routing Protocol)  

---

### 📌 Advantages

- Fast and efficient  
- Reduced routing loops  
- Scalable  

---

### 📌 Disadvantages

- More complex than basic algorithms  
- Requires more configuration  

---

## 🔹 Comparison Table

| Algorithm         | Approach              | Speed | Complexity   | Example |
|------------------|----------------------|-------|--------------|---------|
| Distance Vector  | Neighbour sharing    | Slow  | Low          | RIP     |
| Link State       | Full topology        | Fast  | High         | OSPF    |
| Path Vector      | Full path info       | Medium| Medium       | BGP     |
| Hybrid           | Combined approach    | Fast  | Medium-High  | EIGRP   |

---

## 📌 Conclusion

IP routing algorithms are essential for efficient packet delivery in the Internet. Different algorithms are used based on network size and requirements:

- Small networks → Distance Vector  
- Large enterprise networks → Link State  
- Internet backbone → Path Vector  
- Optimized networks → Hybrid  
```
