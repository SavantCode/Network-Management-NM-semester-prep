Absolutely! Let’s create a **clear, detailed, and exam-ready explanation of CIDR (Classless Inter-Domain Routing)** with examples, so you can write a **perfect answer for university exams**.

---

# **CIDR (Classless Inter-Domain Routing)**

---

### **1. Definition**

**CIDR (Classless Inter-Domain Routing)** is a method for **allocating IP addresses and routing IP packets** more efficiently than the traditional classful IP addressing (Class A, B, C).

* Introduced in **1993** to overcome the limitations of classful addressing.
* Allows **variable-length subnet masks (VLSM)** so networks can be divided into smaller or larger blocks based on need.
* Helps **reduce the wastage of IP addresses** and **simplify routing tables**.

> **In simple words:** CIDR allows you to assign IP addresses in flexible blocks instead of fixed classes (A, B, C), saving addresses and making routing more efficient.

---

### **2. CIDR Notation**

CIDR uses the **slash notation** to indicate the network prefix:

[
\text{IP Address / Prefix Length}
]

* **IP Address:** The network or host address (e.g., 192.168.1.0)
* **Prefix Length (/n):** Number of bits used for the network portion
* Example:

  * `192.168.1.0/24` → First 24 bits are network bits, last 8 bits are host bits
  * `10.0.0.0/8` → First 8 bits are network bits, last 24 bits are host bits

**CIDR removes the concept of class A/B/C**, so you can create networks of any size.

---

### **3. How CIDR Works**

1. **Assign IP Addresses Efficiently**

   * Instead of allocating a full Class C (256 addresses) for a small network of 50 hosts, CIDR allows you to assign a **smaller block** like `/26` (64 addresses).

2. **Combine Multiple Networks (Supernetting)**

   * CIDR allows multiple small networks to be grouped together into a **single larger network** to reduce routing table entries.

3. **Flexible Subnetting**

   * You can divide a large network into smaller subnets of any size based on requirements, avoiding wasted IP addresses.

---

### **4. CIDR Example 1: Subnetting**

Suppose you have **192.168.1.0/24** network and need **4 subnets**.

* Total host bits = 32 – 24 = 8 bits → 2^8 = 256 addresses
* For 4 subnets, borrow 2 bits from host portion → new prefix = 24 + 2 = 26

**Subnets:**

| Subnet | Network Address  | Broadcast Address | Hosts |
| ------ | ---------------- | ----------------- | ----- |
| 1      | 192.168.1.0/26   | 192.168.1.63      | 62    |
| 2      | 192.168.1.64/26  | 192.168.1.127     | 62    |
| 3      | 192.168.1.128/26 | 192.168.1.191     | 62    |
| 4      | 192.168.1.192/26 | 192.168.1.255     | 62    |

* **Each subnet has 64 IP addresses**, 2 are reserved (network & broadcast), leaving 62 usable hosts.

> Using CIDR, we efficiently divide a network without wasting addresses.

---

### **5. CIDR Example 2: Supernetting**

Suppose you have **4 contiguous Class C networks**:

```
192.168.0.0/24
192.168.1.0/24
192.168.2.0/24
192.168.3.0/24
```

* Instead of advertising 4 separate routes, we can combine them using **CIDR /22**:

```
192.168.0.0/22 → Covers 192.168.0.0 – 192.168.3.255
```

* This **reduces the number of routes in routing tables**, improving router efficiency.

---

### **6. Benefits of CIDR**

1. **Efficient IP Address Utilization**

   * No wastage of IP addresses like in classful addressing.

2. **Reduces Routing Table Size**

   * Aggregates multiple routes into a single route using **supernetting**.

3. **Supports Variable-Length Subnet Masks (VLSM)**

   * Flexible subnetting based on host requirements.

4. **Scalable for Large Networks and ISPs**

   * Simplifies global routing on the internet.

---

### **7. CIDR vs Classful Addressing**

| Feature                | Classful Addressing            | CIDR                             |
| ---------------------- | ------------------------------ | -------------------------------- |
| **Subnetting**         | Fixed sizes (Class A/B/C)      | Flexible (VLSM)                  |
| **Routing Table Size** | Larger due to multiple entries | Smaller due to route aggregation |
| **IP Wastage**         | Often wastes IP addresses      | Efficient use of IP addresses    |
| **Notation**           | 192.168.1.0 (implied class)    | 192.168.1.0/24 (explicit prefix) |
| **Scalability**        | Limited                        | Highly scalable                  |

---

### **8. Summary**

* **CIDR** allows **flexible IP addressing** and efficient routing.
* **Subnetting** splits networks into smaller blocks for better utilization.
* **Supernetting** combines networks into larger blocks to simplify routing.
* CIDR is essential for **modern networks** and **Internet routing**, reducing wasted IP addresses and routing table size.

---

### **Exam Tip:**

1. Always mention **CIDR notation (/n)** and explain how the prefix determines network and host bits.
2. Give a **subnetting example** showing network, broadcast, and host addresses.
3. If possible, show **supernetting** for route aggregation to impress examiners.

---

If you want, I can **also draw a simple CIDR diagram** showing **subnetting and supernetting visually**, which is perfect for **exam diagrams**.

Do you want me to make that diagram?
