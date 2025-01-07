
# Guide: TFTP Recovery for GL.iNet MT300N-V2 on Windows

This guide explains how to recover or flash Uboot on your GL.iNet MT300N-V2 router using the TFTP method in a Windows environment. This method is ideal if the web-based recovery mode is inaccessible or you prefer a more manual approach.

---

## Requirements:
1. **Hardware:**
   - GL.iNet MT300N-V2 router
   - Ethernet cable
   - Power supply for the router

2. **Software:**
   - TFTP server (e.g., TFTPD64)
   - Command Prompt (built into Windows)

3. **Files:**
   - The Uboot file (`uboot.bin`) from this repository.

---

## Step 1: Install and Configure the TFTP Server

### 1.1 Download and Install TFTPD64
1. Download the TFTP server software from [TFTPD64 Official Website](https://tftpd64.jounin.net/tftpd32.html).
2. Install the software and launch it.

### 1.2 Configure the TFTP Server
1. In TFTPD64, set the **current directory** to where the `uboot.bin` file is located.
2. Note the IP address of your computer as shown in the software.

---

## Step 2: Prepare the Environment

### 2.1 Download the Uboot File
Clone the repository and locate the Uboot file:
```cmd
git clone https://github.com/CodeStacker-Dev/GL-iNet_MT300N-V2_Factory.git
cd GL-iNet_MT300N-V2_Factory
```
Copy the `uboot.bin` file to the directory configured in TFTPD64.

### 2.2 Set a Static IP
1. Open **Network and Sharing Center** > **Change Adapter Settings**.
2. Right-click your Ethernet connection and select **Properties**.
3. Double-click **Internet Protocol Version 4 (TCP/IPv4)**.
4. Set:
   - **IP Address**: `192.168.1.2`
   - **Subnet Mask**: `255.255.255.0`
   - Leave the rest blank.

---

## Step 3: Enter Uboot Recovery Mode

1. **Power Off the Router**:
   - Unplug the router’s power supply.

2. **Enter Recovery Mode**:
   - Hold the **reset button** on the router.
   - While holding the reset button, power the router back on.
   - Continue holding the button for *5* seconds** until the router is in recovery mode.

---

## Step 4: Flash Uboot Using TFTP

1. **Start the TFTP Transfer**:
   - Ensure the TFTP server is running (TFTPD64).
   - Open Command Prompt and execute:
     ```cmd
     tftp -i 192.168.1.1 put uboot.bin
     ```

2. **Wait for the Transfer to Complete**:
   - TFTPD64 will display a log of the transfer.
   - The router will automatically reboot once the transfer is successful.

---

## Step 5: Verify the Installation

1. Reboot the router if it hasn’t already.
2. Test the Uboot environment by accessing `http://192.168.1.1` in a browser or repeating the recovery mode entry process.

---

## Troubleshooting:
- **TFTP Transfer Fails**:
  - Verify that TFTPD64 is running and correctly configured.
  - Ensure the `uboot.bin` file is in the correct directory.
  - Recheck your static IP settings.

- **No Response from the Router**:
  - Verify the Ethernet connection.
  - Confirm the router is in recovery mode.

---
