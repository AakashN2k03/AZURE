# ☁️ What is Cloud Computing?

Cloud computing means using computing resources over the internet, on demand, instead of owning and managing everything on your own computer/server.

You rent instead of buy, and pay only for what you use.

These resources can include:

- 🖥️ Servers
- 💾 Storage
- 🗄️ Databases
- 🌐 Networking
- 🤖 AI/ML services
- 🔐 Security
- ⚙️ Applications

---

## ☁️ Types of Cloud

The three common **deployment models** — who owns the infrastructure, and who shares it:

1. Public Cloud
2. Private Cloud
3. Hybrid Cloud

---

### 1. 🌍 Public Cloud

The infrastructure is owned and managed by a cloud provider, and **multiple customers share it** (multi-tenant). Your workloads are kept isolated from other tenants by virtualization.

**Examples:** Microsoft Azure · Amazon Web Services (AWS) · Google Cloud

**Advantages**
- Low upfront cost — little money needed at the beginning
- Easy to scale up or down in minutes
- No need to buy physical servers
- Provider manages the infrastructure
- Pay only for what you use

**Watch out for:** less control over the underlying stack, data stored in the provider's data centre, and costs that can grow at large scale.

---

### 2. 🏢 Private Cloud

Cloud infrastructure **dedicated to one organization**. It is not shared with other organizations (single-tenant).

It can be hosted:
- Inside the company's own data center, or
- By a third-party provider, but reserved for that organization

**Why use private cloud?**
- Greater control
- Specific security requirements
- Custom configurations
- Regulatory/compliance requirements (banking, healthcare, government)

**But:** it needs more management, and generally costs more than public cloud. Capacity is limited to the hardware you own, so it is less elastic.

---

### 3. 🔄 Hybrid Cloud

**Hybrid cloud = public cloud + private cloud, connected together** so data and workloads can move between them.

**Common uses**
- Keep sensitive data private, run the public-facing app in the public cloud
- **Cloud bursting** — handle traffic spikes using public cloud capacity
- Use public cloud as a backup / disaster-recovery site
- Migrate off legacy systems gradually

**But:** you now manage two environments plus the network and identity between them — more complexity.

---

## 📊 Quick Comparison

| | Public | Private | Hybrid |
|---|---|---|---|
| Shared with others? | Yes | No | Partly |
| Upfront cost | Low | High | Medium |
| Control | Low | High | Medium |
| Scalability | Very high | Limited | High |

---
