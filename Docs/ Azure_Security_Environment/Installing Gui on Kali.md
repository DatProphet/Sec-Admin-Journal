Here’s your instruction guide in **GitHub-ready Markdown format** for installing a GUI on Kali Linux and enabling RDP access on an Azure-hosted VM:

```markdown
# 🖥️ Install XFCE GUI and Enable RDP on Kali Linux (Azure VM)

This guide will walk you through installing a lightweight GUI on Kali Linux and enabling RDP access so you can connect using a Remote Desktop client.

---

## ✅ Prerequisites
- A running **Kali Linux VM** in Azure (e.g., `KaliPrime`)
- **SSH access** to the VM
- Azure NSG rule allowing **TCP port 3389** (explained below)

---

## 🧱 Step 1: Update the System and Install XFCE Desktop
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install kali-desktop-xfce -y
```

---

## 🛠️ Step 2: Install and Configure XRDP
```bash
sudo apt install xrdp -y
sudo systemctl enable xrdp
sudo systemctl start xrdp
sudo adduser xrdp ssl-cert
echo "startxfce4" > ~/.xsession
```

---

## 🌐 Step 3: Allow RDP Traffic in Azure

1. Go to the [Azure Portal](https://portal.azure.com)
2. Navigate to your **VM** → **Networking**
3. Under **Inbound port rules**, click **+ Add inbound port rule**
4. Configure as follows:

| Setting        | Value                 |
|----------------|-----------------------|
| **Port**       | 3389                  |
| **Protocol**   | TCP                   |
| **Source**     | Your IP or Any        |
| **Action**     | Allow                 |
| **Priority**   | (e.g., 1000)          |
| **Name**       | Allow-RDP             |

---

## 🔁 Step 4: Reboot the VM
```bash
sudo reboot
```

---

## 💻 Step 5: Connect Using RDP

- Open **Remote Desktop Connection** (on Windows) or any RDP client
- Connect to your **public IP** or **DNS name**
- Use:
  - **Username:** KaliSec (or your configured username)
  - **Password:** The password set for your user

---

## 📌 Notes
- Ensure the NSG doesn't block RDP (port 3389).
- If using a private IP, make sure you're connected via VPN or Azure Bastion.

---

> _Tested on Kali Linux 2024.3 - Gen2 running on Azure D4as v5 instance._
```

Let me know if you'd like this saved into a `.md` file or added as part of a `docs/` folder structure for a GitHub repository.
