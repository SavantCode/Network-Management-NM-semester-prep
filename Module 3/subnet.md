Absolutely! Let’s make a **structured, detailed, and exam-ready explanation** of **Subnet Address** and **Subnet Mask** with examples.

---

# **Subnet Address and Subnet Mask**

---

## **1. Subnet Address**

**Definition:**
A **Subnet Address** is the **network portion of an IP address after subnetting**. It identifies a **specific subnet within a larger network**.

* It helps routers and devices determine **which subnet a host belongs to**.
* The **host portion** in the subnet address is always set to **0**.

> **In simple words:** Subnet Address is like the **name of a neighborhood** in a city. Every house (host) belongs to a neighborhood (subnet).

---

### **Example of Subnet Address**

Suppose we have a network:

```
IP Address: 192.168.1.0
Default Subnet Mask: 255.255.255.0 (/24)
```

* If we divide this network into **4 subnets**, we borrow **2 bits** from the host portion:

  * New subnet mask: **255.255.255.192 (/26)**

Now, subnet addresses are:

1. **192.168.1.0 /26** → Hosts: 192.168.1.1 – 192.168.1.62
2. **192.168.1.64 /26** → Hosts: 192.168.1.65 – 192.168.1.126
3. **192.168.1.128 /26** → Hosts: 192.168.1.129 – 192.168.1.190
4. **192.168.1.192 /26** → Hosts: 192.168.1.193 – 192.168.1.254

> Notice: The subnet address itself always ends with **all host bits as 0**.

---

## **2. Subnet Mask**

**Definition:**
A **Subnet Mask** is a **32-bit number** that separates the **network portion** and the **host portion** of an IP address.

* Determines **which part of an IP address refers to the network and which part refers to the host**.
* Represented in **dotted decimal** (255.255.255.0) or **CIDR notation** (/24).

> **In simple words:** Subnet Mask is like a **boundary line** that tells which part of the address is the neighborhood (network/subnet) and which part is the house (host).

---

### **How Subnet Mask Works**

* Bits set to **1** → Network/Subnet portion
* Bits set to **0** → Host portion

**Example 1:** Default Class C Network

```
IP Address: 192.168.1.10
Subnet Mask: 255.255.255.0 (/24)
```

* Network bits: 192.168.1 → Network
* Host bits: 10 → Host within network

**Example 2:** Subnetting Class C into 4 subnets

```
IP Address: 192.168.1.10
Subnet Mask: 255.255.255.192 (/26)
```

* Network bits: 192.168.1 + 2 borrowed bits → 4 subnets
* Host bits: Remaining 6 bits → 62 usable hosts per subnet

---

## **3. Relationship Between Subnet Address and Subnet Mask**

* **Subnet Mask defines the boundary** between network and host.
* **Subnet Address is the network portion obtained after applying the subnet mask** to any host IP in that subnet.

**Example:**

```
IP: 192.168.1.70
Subnet Mask: 255.255.255.192 (/26)
```

* Convert IP to binary: 11000000.10101000.00000001.01000110
* Apply subnet mask: 11111111.11111111.11111111.11000000
* Resulting subnet address (binary AND): 11000000.10101000.00000001.01000000 → **192.168.1.64**

> So, **192.168.1.64 /26** is the subnet address to which 192.168.1.70 belongs.

---

## **4. Summary Table**

| Concept            | Definition                                                   | Example                               |
| ------------------ | ------------------------------------------------------------ | ------------------------------------- |
| **Subnet Address** | Network portion of IP after subnetting. Identifies a subnet. | 192.168.1.64 /26                      |
| **Subnet Mask**    | 32-bit number separating network and host portions.          | 255.255.255.192 (/26)                 |
| **Relationship**   | Mask defines network/host, subnet address is the result.     | IP 192.168.1.70 → Subnet 192.168.1.64 |

---

💡 **Exam Tip:**

* Always remember: **Subnet address = host bits set to 0**
* Use **binary AND** between IP and subnet mask to calculate the subnet.
* Learn both **dotted decimal** and **CIDR notation**.

---

If you want, I can **draw a clear block diagram showing IP, subnet mask, and subnet address visually** for easy exam understanding.

Do you want me to make that diagram?


Sure! Here's a **simple, clear, and exam-friendly table differentiating Subnet Address and Subnet Mask**:

| **Feature**         | **Subnet Address**                                                | **Subnet Mask**                                                               |
| ------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| **Definition**      | Identifies a specific subnet within a network.                    | Defines which part of an IP address is network/subnet and which part is host. |
| **Purpose**         | Shows the network portion of an IP address after subnetting.      | Separates network bits from host bits in an IP address.                       |
| **Representation**  | Always ends with host bits as 0. Example: 192.168.1.64 (/26)      | 32-bit number in dotted decimal or CIDR. Example: 255.255.255.192 (/26)       |
| **Calculation**     | Obtained by applying subnet mask on IP (binary AND operation).    | Predefined or calculated to divide a network into subnets.                    |
| **Role in Routing** | Used by routers to identify the network/subnet a host belongs to. | Used by devices to determine network boundary and valid hosts.                |
| **Example**         | 192.168.1.64 (/26)                                                | 255.255.255.192 (/26)                                                         |

---

If you want, I can also **make a tiny diagram showing an IP, subnet mask, and subnet address** in one visual for quick understanding and exams.

Do you want me to make that diagram?
