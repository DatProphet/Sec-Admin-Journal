# 🛡️ Azure VM Deployment Report – `KaliPrime`

## 👤 Contact Information
- **Name:**  
- **Email:**
- **Phone:** 

---

## 🔧 Basics
| Key | Value |
|-----|-------|
| **Subscription** |  |
| **Resource Group** | SecurityEnvRG |
| **VM Name** | KaliPrime |
| **Region** | East US |
| **Availability Zone** | 1 |
| **Zone Option** | Self-selected |
| **Security Type** | Standard |

---

## 💻 VM Configuration
| Key | Value |
|-----|-------|
| **Image** | Kali 2024.3 - Gen2 |
| **Architecture** | x64 |
| **Size** | Standard D4as v5 (4 vCPUs, 16 GiB RAM) |
| **Hibernation Enabled** | No |

---

## 🔐 Authentication
| Key | Value |
|-----|-------|
| **Type** | SSH Public Key |
| **Username** | KaliSec |
| **Key Format** | RSA |
| **Key Pair Name** | KaliPrime_key |

---

## 💰 Pricing Options
| Key | Value |
|-----|-------|
| **Azure Spot Instance** | No |

---

## 💾 Disk Settings
| Key | Value |
|-----|-------|
| **OS Disk Size** | Image default |
| **OS Disk Type** | Premium SSD LRS |
| **Managed Disks** | Yes |
| **Delete OS Disk with VM** | Enabled |
| **Ephemeral OS Disk** | No |

---

## 🌐 Networking
| Key | Value |
|-----|-------|
| **Virtual Network** | SecurityVNet |
| **Subnet** | default (10.1.0.0/24) |
| **Public IP** | KaliPrime_IP (new) |
| **NSG** | SecurityEnv-nsg |
| **Accelerated Networking** | Off |
| **Behind Load Balancer** | No |
| **Delete Public IP & NIC on Delete** | Enabled |

---

## 🛠️ Management
| Key | Value |
|-----|-------|
| **Defender for Cloud** | Basic (Free) |
| **System Assigned Identity** | Off |
| **Login with Microsoft Entra ID** | Off |
| **Auto-shutdown** | Off |
| **Periodic Assessment** | Off |
| **Hotpatch Enabled** | Off |
| **Patch Orchestration** | Image Default |

---

## 📈 Monitoring
| Key | Value |
|-----|-------|
| **Alerts** | Off |
| **Boot Diagnostics** | On |
| **Guest Diagnostics** | Off |
| **App Health Monitoring** | Off |

---

## ⚙️ Advanced Settings
| Key | Value |
|-----|-------|
| **Extensions** | None |
| **VM Applications** | None |
| **Cloud Init** | No |
| **User Data** | No |
| **Disk Controller** | SCSI |
| **Proximity Placement Group** | None |
| **Capacity Reservation Group** | None |

---

## 🏷️ Tags
```text
CreatedBy: jmorgan@globalwarranty.com (Auto-shutdown schedule)
CreatedBy: jmorgan@globalwarranty.com (Availability set)
CreatedBy: jmorgan@globalwarranty.com (Disk)
CreatedBy: jmorgan@globalwarranty.com (Network interface)
CreatedBy: jmorgan@globalwarranty.com (Network security group)
CreatedBy: jmorgan@globalwarranty.com (Public IP address)
CreatedBy: jmorgan@globalwarranty.com (Recovery Services vault)
CreatedBy: jmorgan@globalwarranty.com (SQL Virtual Machine)
CreatedBy: jmorgan@globalwarranty.com (SSH key)
CreatedBy: jmorgan@globalwarranty.com (Storage account)
CreatedBy: jmorgan@globalwarranty.com (Virtual machine)
CreatedBy: jmorgan@globalwarranty.com (Virtual machine extension)
CreatedBy: jmorgan@globalwarranty.com (Virtual network)
