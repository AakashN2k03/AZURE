# ☁️ Cloud Computing Notes

**Virtualization · Regions · Availability Zones · High Availability · Fault Tolerance · Disaster Recovery · Load Balancing**

---

## 1. Virtualization

### Definition

Virtualization is a technology that allows us to create **multiple virtual computers (Virtual Machines) on a single physical computer/server**.

### Why Do We Need Virtualization?

**Without Virtualization**

```
1 Physical Server
       ↓
1 Application
```

A lot of CPU, RAM, and storage may remain unused.

**With Virtualization**

```
        Physical Server
               ↓
           Hypervisor
               ↓
      ┌────────┼────────┐
      ↓        ↓        ↓
     VM1      VM2      VM3
      ↓        ↓        ↓
    App A    App B    App C
```

One physical server can run multiple Virtual Machines (VMs).

---

## 2. Important Terms

### Physical Machine

The actual physical computer/server containing resources such as:

- CPU
- RAM
- Storage
- Network interfaces

### Virtual Machine (VM)

A Virtual Machine is a **software-based computer** that runs on a physical machine.

A VM behaves like an independent computer and can have its own:

- Operating System
- CPU
- RAM
- Storage
- Applications

### Hypervisor

A Hypervisor is **software that creates and manages Virtual Machines**.

It manages the physical server's resources and allocates them to different VMs.

```
Physical Server
       ↓
   Hypervisor
       ↓
 ┌─────┼─────┐
 ↓     ↓     ↓
VM1   VM2   VM3
```

---

## 3. Virtualization Example

Suppose a physical server has:

- **16 CPU Cores**
- **64 GB RAM**

A hypervisor can allocate these resources among multiple VMs:

| Virtual Machine | CPU | RAM |
|---|---|---|
| VM1 | 4 cores | 16 GB |
| VM2 | 4 cores | 16 GB |
| VM3 | 8 cores | 32 GB |

The VMs share the resources of the same physical server while operating as separate virtual computers.

---

## 4. Advantages of Virtualization

- ✅ Better utilization of hardware
- ✅ Reduces infrastructure cost
- ✅ Multiple VMs can run on one physical server
- ✅ Provides isolation between VMs
- ✅ Easy to create and remove VMs
- ✅ Makes scaling easier
- ✅ Allows different operating systems and applications to run on the same physical server

---

## 5. Virtualization and Cloud Computing

Cloud providers such as **Microsoft Azure**, **AWS**, and **Google Cloud** use virtualization extensively.

```
Physical Servers
       ↓
   Hypervisors
       ↓
 Virtual Machines
       ↓
 Cloud Customers
```

When a customer creates a cloud Virtual Machine, the cloud provider uses its underlying physical infrastructure to provide the requested virtual resources.

> 💡 **Easy Definition to Remember**
>
> **Virtualization = Using software to divide one physical computer into multiple virtual computers.**

---

## 6. Region

### Definition

A **Region** is a geographical location where a cloud provider has cloud infrastructure and data centers.

Cloud providers have regions around the world so customers can choose where their applications and data are hosted.

### Examples

- Central India
- South India
- East US
- West Europe

A region can contain multiple Availability Zones.

```
             Cloud Provider
                   ↓
                Region
                   ↓
       ┌───────────┼───────────┐
       ↓           ↓           ↓
    Zone 1      Zone 2      Zone 3
```

> 🔑 **Key Point**
>
> Region = A geographical location containing cloud infrastructure.

---

## 7. Availability Zone (AZ)

### Definition

An **Availability Zone (AZ)** is an isolated location within a cloud region, designed with independent infrastructure such as **power, cooling, and networking**.

A region can contain multiple Availability Zones.

```
                Region
       ┌──────────┼──────────┐
       ↓          ↓          ↓
    Zone 1     Zone 2     Zone 3
      🏢         🏢         🏢
```

### Why Use Availability Zones?

Availability Zones help provide:

- High Availability
- Fault Tolerance
- Disaster Resilience

### Example

Suppose an application is deployed across multiple zones:

```
              Region
                 ↓
       ┌─────────┼─────────┐
       ↓         ↓         ↓
    Zone 1    Zone 2    Zone 3
       ❌        ✅        ✅
```

If Zone 1 has a problem, the application can continue running from the other zones — **assuming the application has been designed and deployed for multi-zone operation**.

> 🔑 **Key Point**
>
> Availability Zone = An isolated location inside a region that helps protect applications from failures in another zone.

---

## 8. High Availability (HA)

### Definition

**High Availability** means designing a system to remain available for most of the time, even if some components fail.

### Main Goal

Minimize downtime.

### Example

Suppose an application is running on two servers:

```
              Load Balancer
                    ↓
          ┌─────────┴─────────┐
          ↓                   ↓
      Server 1            Server 2
          ↓                   ↓
             Application
```

If Server 1 fails:

```
              Load Balancer
                    ↓
                Server 1 ❌
                    ↓
                Server 2 ✅
                    ↓
             Application
```

Traffic can be redirected to Server 2.

There may be a **small interruption** while the system detects the failure and performs the failover.

> 🔑 **Key Point**
>
> High Availability = Recover quickly when something fails.

---

## 9. Fault Tolerance (FT)

### Definition

**Fault Tolerance** means designing a system so that it can continue operating when a component fails, with **little or no interruption**.

### Main Goal

Continue working despite failure.

### Example

```
        Server 1 ✅
             │
             ├────→ Application
             │
        Server 2 ✅
```

If Server 1 fails:

```
        Server 1 ❌

        Server 2 ✅
             ↓
      Application continues
```

The system is designed to tolerate the failure **without requiring a noticeable recovery period**.

> 🔑 **Key Point**
>
> Fault Tolerance = Keep running even when something fails.

---

## 10. High Availability vs Fault Tolerance

Both High Availability and Fault Tolerance aim to keep an application available, but they have different goals.

| Feature | High Availability | Fault Tolerance |
|---|---|---|
| **Main Goal** | Minimize downtime | Continue operating despite failure |
| **Failure Handling** | Failover to another resource | Continue with little or no interruption |
| **Downtime** | Small downtime may occur | Ideally zero or nearly zero |
| **Approach** | Recover quickly | Tolerate the failure |
| **Cost** | Usually lower | Usually higher |
| **Redundancy** | Uses redundant resources | Often requires more extensive redundancy |


## 1. Disaster Recovery (DR)

### Definition

Disaster Recovery is the process of restoring applications, data, and systems after a major failure or disaster.

### Examples of Disasters

- Data center failure
- Natural disaster
- Cyberattack
- Hardware/software failure
- Data loss

### Basic Flow

```
Disaster
   ↓
Backup / Secondary System
   ↓
Recovery
   ↓
Application Running
```

### Important Concepts

**Backup**

A copy of data stored separately so it can be restored.

**RTO (Recovery Time Objective)**

How quickly the system should be restored.

> RTO = How much downtime can we tolerate?

**RPO (Recovery Point Objective)**

How much data loss is acceptable.

> RPO = How much data can we afford to lose?

### Key Point

> Disaster Recovery = Recover the system after a major disaster.

---

## 2. Load Balancing

### Definition

Load Balancing is the process of distributing incoming traffic across multiple servers.

### Basic Flow

```
             Users
               ↓
         Load Balancer
               ↓
      ┌────────┼────────┐
      ↓        ↓        ↓
   Server 1 Server 2 Server 3
```

### Why Use Load Balancing?

- Distributes traffic
- Prevents server overload
- Improves performance
- Improves availability
- Can redirect traffic if a server fails
