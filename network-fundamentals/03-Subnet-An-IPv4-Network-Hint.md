### CCNA - Network fundamentals : Subnet An IPv4 Network

_Topics: subnetting, stactic routing_

#### Topology

![topology](./03-Subnet-An6IPv4-Network-Topology.png)

#### Instructions :

1. Subnet 192.168.99.0/24 for LAN Servers (4 hosts). Assign IPs to Server1 and R2 G0/0/1.

2. Subnet 10.0.0.0/24 for the R1-R2 link. Assign IPs to R1 G0/0/0 and R2 G0/0/0.

3. Configure static routes so R1 can reach Server1.

4. Subnet 10.188.70.0/20 for Office LAN (33 hosts). Assign IPs to R1 G0/0/1, PC1, PC13, and PC28.

5. Configure static routes so PC1 can reach Server1. Vice versa. Verify with simulation mode from PC1 to Server1.

#### Hint 0: Activate Router Interfaces

By default, all router interfaces are administratively down. You need to activate them.

**Commands:**

```

# show ip int br

# int range G0/0-1

# no shutdown

```

---

#### Hint 1: Subnetting for LAN Servers (Question 1)

To subnet the 192.168.99.0/24 network for LAN Servers (4 hosts):

Use the formula **2^n - 2 ≥ number_of_hosts** to determine how many host bits you need.

**What to calculate:**

- How many host bits do you need for 4 hosts?
- What subnet mask (in CIDR notation) does this give you?
- What is the network address, first usable IP, last usable IP, and broadcast address?

**Remember:**

- First usable IP = Network address + 1
- Last usable IP = Broadcast address - 1

**▶️ Tutorial:** [Subnetting - Sunny Classroom](https://www.youtube.com/watch?v=ecCuyq-Wprc)

---

#### Hint 2: Point-to-Point Subnetting (Question 2)

Subnet the 10.0.0.0/24 network for the point-to-point connection between R1 and R2.

**What you need:**

- 2 usable hosts
- Find the most efficient CIDR for a point-to-point link

---

#### Hint 3: Configure Static Routing (Question 3)

To allow R1 to reach Server1, you need to add a static route.

**Think about:**

- What is the destination network?
- What is the next-hop IP address from R1's perspective?

**▶️ Tutorial:** [Static Routing - Jeremy's IT Lab](https://www.youtube.com/watch?v=YCv4-_sMvYE&t)

---

#### Hint 4: Layer 2 Mode on Multilayer Switch (Question 4)

For Office LAN Single Network, ensure that the Multilayer Switch operates in Layer 2 mode only.

**Command:**

```

# no ip routing

```

---

#### Hint 5: Subnetting for Office LAN (Question 4)

Subnet the 10.188.70.0/20 for the entire Office LAN (33 hosts).

**What to find:**

- How many host bits for 33 hosts?
- The appropriate CIDR

**Note:** Don't confuse /20 (the given block) with the subnet you'll create from it.

---

#### Hint 6: Static Routes for Office-to-Server (Question 5)

For PC1 to reach Server1, you need static routes on BOTH routers:

- R1 needs a route to 192.168.99.0/X
- R2 needs a route to 10.188.70.0/X

#### Hint 7: Simulation Mode (Question 5)

Perform a simulation mode to see the life of a packet from PC1 to Server1. Observe the path taken by the packets and explain each hop.

**▶️ Tutorial:** [Packet Tracer Simulation Mode - Jeremy's IT Lab](https://www.youtube.com/watch?v=bfsEqDeHbpI)

---

#### Acknowledgments

This lab was created using inspiration and knowledge from the following sources:

#### Lab Structure

- Boson NetSim Lab Guide - Professional lab format and presentation style  
  [Boson NetSim CCNA 200-301 Labs](https://netsim.boson.com/labs/200-301)

#### Network Architecture

- **Network Academy** - Three-tier architecture concepts  
  [Three-Tier Architecture](https://www.networkacademy.io/ccna/network-fundamentals/three-tier-architecture)

#### Technical Content

- **Jeremy's IT Lab** - Subnetting (VLSM) concepts and practice  
  [Day 15 Lab - Subnetting (VLSM)](https://www.youtube.com/watch?v=Rn_E1Qv8--I)

#### Original Contributions

- Architecture firm business scenario
- Multi-site topology (Office + Servers)
- 33-host office network segmentation

---

Lab Starter and Solution Files in :

**Download:** [GitHub Repository](https://github.com/dineproject/ccna-labs/networkfundamentals)
**Download:** [Google drive](https://drive.google.com/drive/u/1/folders/1u8mwEXy5HasH5t5agzvljvLu-BLnvoeF)

---
