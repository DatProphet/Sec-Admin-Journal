# 🔐 Azure Environment Setup for Hosting Security Apps and VMs (Beginner Friendly)

This guide walks you through how to set up an environment in Azure to host your security apps, tools, and virtual machines (VMs), all protected by a Web Application Firewall (WAF). It’s written in simple steps for Azure beginners.

---

## ⚙️ PHASE 1: Set Up Your Azure Environment

1. **Create an Azure Account:**
   - Visit: [https://azure.microsoft.com](https://azure.microsoft.com)
   - Sign up or log in.
   - Choose the free plan if available.

2. **Access the Azure Portal:**
   - Go to [https://portal.azure.com](https://portal.azure.com)

---

## 🗂️ PHASE 2: Create a Resource Group

1. In the Azure Portal, click **“Resource groups”** on the left.
2. Click **“+ Create”**
3. Fill out:
   - **Name**: `SecurityEnvRG`
   - **Region**: e.g., `East US`, `Canada Central`
4. Click **Review + Create**, then **Create**

---

## 🌐 PHASE 3: Set Up a Virtual Network (VNet)

1. Search **"Virtual Network"**, click **+ Create**
2. Use:
   - **Name**: `SecurityVNet`
   - **Region**: same as your resource group
3. Leave IP ranges as default unless you need to customize
4. Click **Review + Create**, then **Create**

---

## 💻 PHASE 4: Create a Virtual Machine (VM)

1. Search for **"Virtual Machines"**, click **+ Create**
2. Fill in:
   - **Name**: `SecurityVM01`
   - **Image**: Windows Server 2022 or Ubuntu
   - **Size**: Start small (e.g., B2s)
   - **Username/Password**: Create credentials
3. **Networking**:
   - Choose **SecurityVNet**
   - Select **Allow selected ports** → RDP or SSH
4. Click **Review + Create**, then **Create**

---

## 🔒 PHASE 5: Configure Web Application Firewall (WAF)

1. Search for **“Application Gateway”**, click **+ Create**
2. Fill in:
   - **Name**: `SecurityAppGateway`
   - **Tier**: WAF V2
   - **Region**: same as VM
3. **Frontend IP**: Choose **Public** (for external access)
4. **Backend Pool**: Add your VM’s private IP
5. **Routing Rules**: Set listener on port 80/443 and link to backend pool
6. **WAF Policy**:
   - Set to **Prevention mode**
   - Use OWASP default rules

Click **Review + Create**, then **Create**

---

## ✅ Final Tips

- Use **NSGs** for basic traffic control
- Use **Azure Bastion** to access VMs securely (optional)
- Install your tools (e.g., Wazuh, OpenVAS) on your VM

You're now ready to build a secure environment in Azure!
