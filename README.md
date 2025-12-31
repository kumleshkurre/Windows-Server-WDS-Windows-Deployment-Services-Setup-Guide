🖥️ Windows Server WDS (Windows Deployment Services) Setup Guide

This document explains step-by-step configuration of Windows Deployment Services (WDS) with DHCP for network-based Windows OS installation using PXE Boot. This guide is suitable for IT Support / System Administrator / CCNA-level learners.

📌 1. Install Required Roles & Features

Open Server Manager

Click Add Roles and Features

Click Next (3 times)

Select following roles:

✅ DHCP Server

✅ Windows Deployment Services (WDS)

Click Next (4 times)

Click Install

After installation completes, click Close

🌐 2. Configure Static IP Address on Server

Press Windows + R

Type ncpa.cpl → Press Enter

Right-click on Network Adapter → Properties

Select Internet Protocol Version 4 (TCP/IPv4) → Properties

Select Use the following IP address

IP Configuration:

IP Address: 10.0.0.1

Subnet Mask: 255.0.0.0

Click OK → Close

📡 3. DHCP Server Configuration

Open Server Manager

Go to Tools → DHCP

Expand your Server Name

Right-click IPv4 → New Scope

Click Next

Scope Details:

Scope Name: WDS

Start IP: 10.0.0.2

End IP: 10.0.0.100

Click Next (3 times)

Select No.I will configure these options later

Finish the wizard

Right-click scope (10.0.0.0) WDS → Activate

⚙️ 4. DHCP Advanced Settings for PXE

Right-click Scope (10.0.0.0) WDS → Properties

Go to Advanced tab

Tick:

✅ BOOTP

Click Apply → OK

🚀 5. Windows Deployment Services (WDS) Configuration

Open Server Manager

Go to Tools → Windows Deployment Services

Expand Servers

Right-click your Server Name → Configure Server

Click Next

Select:

☑️ Standalone Server

Create Special Partition and select storage path

Click Next

Select Respond to all client computers (known and unknown)

Click Next → Finish

📀 6. Add Boot & Install Images
➤ Add Install Image

Expand Install Images

Right-click → Add Install Image

Click Next

Browse and select install.wim

Click Next (3 times)

Click Finish

➤ Add Boot Image

Right-click Boot Images → Add Boot Image

Browse and select boot.wim

Click Next (3 times)

Click Finish

💻 7. Client-Side PXE Boot Configuration

Start Client Computer

Enter BIOS / UEFI Settings

Enable PXE Network Boot

Save and Restart

Press F12 for Network Boot

Select DHCP / PXE Boot

Loading files...

Enter Server Username & Password

Select Windows OS

Start Installation 🎉
