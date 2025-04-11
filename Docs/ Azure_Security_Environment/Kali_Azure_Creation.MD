# 🔐 Azure Secure Environment Setup – Revised Procedure

This procedure outlines the revised steps we followed to create a secure environment in Azure with a Kali Linux VM and Web Application Firewall (WAF) protection.

---

## ⚙️ STEP 1: Create the Resource Group
- **Name:** `SecurityEnvRG`
- **Region:** `East US`
- Use this group to organize all related resources (VM, VNet, NSG, IP, Gateway, etc.)

---

## 🌐 STEP 2: Create the Virtual Network
- **Name:** `SecurityVNet`
- **Address Space:** `10.1.0.0/16`
- **Subnet 1 (VM Subnet):**  
  - **Name:** `default`  
  - **Range:** `10.1.0.0/24`
- **Subnet 2 (Gateway Subnet):**  
  - **Name:** `SecAppGatewaySubnet`  
  - **Range:** `10.1.1.0/24`

---

## 🖥️ STEP 3: Deploy the Virtual Machine
- **Name:** `KaliPrime`
- **Image:** Kali Linux 2025.1a - Gen2
- **Size:** Standard D4as v5 (4 vCPUs, 16 GiB)
- **Auth Type:** SSH Public Key (RSA)
- **Username:** `KaliSec`
- **Public IP Name:** `KaliPrime-ip`
- **NIC NSG:** `SecurityEnv-nsg`
- **OS Disk:** Premium SSD LRS
- **Availability Zone:** 1
- **Boot Diagnostics:** Enabled
- **Auto-shutdown:** Disabled

---

## 🌐 STEP 4: Create the Application Gateway (WAF V2)
- **Name:** `SecurityAppGateway`
- **Tier:** WAF V2
- **Frontend IP:** Public (Auto-generated: `172.214.29.197`)
- **Frontend Listener:** `Kali-Listener`
- **Backend Pool:** `SecurityBackendPool`  
  - Target: Private IP of `KaliPrime`
- **Routing Rule:** `Kali-Listener` (HTTP, port 80)

---

## 🔍 STEP 5: Configure Health Probe
- **Name:** `basic-probe`
- **Protocol:** HTTP
- **Path:** `/`
- **Port:** 80
- **Interval:** 30s
- **Unhealthy Threshold:** 3

---

## ⚙️ STEP 6: HTTP Settings (Backend Communication)
- **Name:** `http-setting-basic`
- **Port:** 80
- **Protocol:** HTTP
- **Timeout:** 20s
- **Custom Health Probe:** `basic-probe`

---

## 🧠 STEP 7: Validate & Deploy
- Review all configurations
- Click **"Create"** to deploy all resources
- Monitor deployment from the **Notifications** section

---

## ✅ POST-DEPLOYMENT CHECK
- Confirm access via `http://<public-ip>` (e.g., `http://172.214.29.197`)
- Check **Application Gateway > Backend Health** for green (healthy) status

---

Let me know if any adjustments are needed before exporting or publishing this.
