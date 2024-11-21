# **P4 Network Programming: From Hub to L2 Switch**

Welcome to the **P4 Hub to L2 Switch** repository! This repository contains starter code for a simple network device written in P4. Currently, the device behaves as a **hub**, broadcasting all incoming packets to all connected ports. 

Your task is to transform this hub into an **L2 switch** that forwards packets based on a **static MAC address table**. The table will be pre-populated by the control plane when the switch is initialized.

---

## **What You’ll Learn**
By completing this task, you will:
- Understand the difference between **hub** and **L2 switch** behavior.
- Learn how to use **P4 tables** for exact-match lookups.
- Gain hands-on experience programming network devices with **P4**.

---

## **Task Description**

### **Hub Behavior (Current State)**:
The provided `hub.p4` program:
- **Broadcasts** every packet it receives to all ports except the ingress port.
- Does not inspect or process packet headers.

### **L2 Switch Behavior (Your Goal)**:
Modify `hub.p4` to implement an **L2 switch** with the following behavior:
1. **MAC Address Table**:
   - Create a table that maps destination MAC addresses to specific egress ports.
   - This table will be pre-populated by the control plane.
2. **Forwarding Logic**:
   - For packets with a **known destination MAC**, forward them to the corresponding port.
   - For packets with an **unknown destination MAC**, broadcast them to all ports except the ingress port.
