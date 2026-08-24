# Scalability and Elasticity

## 1. Scalability

### Definition

**Scalability is the ability of a system to handle an increasing workload by adding or upgrading resources.**

### Example

Your application has:

```text
100 Users
   ↓
1 Server
```

Now the number of users increases to 1,000:

```text
1,000 Users
     ↓
Need more resources
     ↓
Add more Servers / CPU / RAM
```

### Types of Scalability

#### Vertical Scaling (Scale Up)

Increase the resources or power of an existing server.

```text
Server
4 CPU + 8 GB RAM
        ↓
     Scale Up
        ↓
8 CPU + 32 GB RAM
```

**Scale Up = Add more power to the existing server.**

---

#### Horizontal Scaling (Scale Out)

Add more servers to handle the workload.

```text
Before:

1 Server
```

```text
After:

Server 1 + Server 2 + Server 3
```

**Scale Out = Add more servers.**

### Key Point

> **Scalability = Ability to handle increased workload by adding or upgrading resources.**

---

## 2. Elasticity

### Definition

**Elasticity is the ability of a system to automatically add or remove resources based on the current workload or demand.**

### Example

#### Normal Traffic

```text
100 Users
   ↓
2 Servers
```

#### High Traffic

```text
10,000 Users
    ↓
Automatically add servers
    ↓
10 Servers
```

#### Traffic Decreases

```text
100 Users
   ↓
Automatically remove extra servers
   ↓
2 Servers
```

### Key Point

> **Elasticity = Automatically add or remove resources based on demand.**

---

# Scalability vs Elasticity

| Scalability                    | Elasticity                                      |
| ------------------------------ | ----------------------------------------------- |
| Handles increased workload     | Adjusts resources based on changing workload    |
| Can add or upgrade resources   | Automatically adds and removes resources        |
| Can be manual or automatic     | Typically automatic                             |
| Focuses on increasing capacity | Focuses on matching resources to current demand |

## Easy Way to Remember

> **Scalability = Long-term growth 📈**

> **Elasticity = Current/real-time demand 🔄.**
