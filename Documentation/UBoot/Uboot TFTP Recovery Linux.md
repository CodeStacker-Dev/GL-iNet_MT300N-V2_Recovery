
# Guide: TFTP Recovery for GL.iNet MT300N-V2 on Linux

This guide explains how to recover or flash Uboot on your GL.iNet MT300N-V2 router using the TFTP method in a Linux environment. This method is ideal if the web-based recovery mode is inaccessible or you prefer command-line tools.

---

## Requirements:
1. **Hardware:**
   - GL.iNet MT300N-V2 router
   - Ethernet cable
   - Power supply for the router

2. **Software:**
   - TFTP server (`tftp-hpa` or equivalent)
   - Network tools like `ifconfig` or `ip`

3. **Files:**
   - The Uboot file (`uboot.bin`) from this repository.

---

## Step 1: Prepare the Environment

### 1.1 Install TFTP Server
Install a TFTP server on your Linux machine:
```bash
sudo apt update
sudo apt install tftp-hpa
```

### 1.2 Download the Uboot File
Clone the repository and locate the Uboot file:
```bash
git clone https://github.com/CodeStacker-Dev/GL-iNet_MT300N-V2_Factory.git
cd GL-iNet_MT300N-V2_Factory
```

### 1.3 Move Uboot File to TFTP Directory
Copy the `uboot.bin` file to your TFTP server’s root directory:
```bash
sudo cp uboot.bin /var/lib/tftpboot/
```

---

## Step 2: Configure the Network

### 2.1 Set a Static IP
Set your Ethernet adapter to a static IP:
```bash
sudo ip addr add 192.168.1.2/24 dev eth0
sudo ip link set eth0 up
```
Replace `eth0` with your Ethernet interface name (use `ip link` to find it).

### 2.2 Verify Connectivity
Test connectivity with the router:
```bash
ping 192.168.1.1
```

---

## Step 3: Enter Uboot Recovery Mode

1. **Power Off the Router**:
   - Unplug the router’s power supply.

2. **Enter Recovery Mode**:
   - Hold the **reset button** on the router.
   - While holding the reset button, power the router back on.
   - Continue holding the button for **10 seconds** until the router is in recovery mode.

---

## Step 4: Flash Uboot Using TFTP

1. **Initiate the Transfer**:
   From your Linux terminal, use TFTP to push the `uboot.bin` file to the router:
   ```bash
   tftp 192.168.1.1
   ```
   Inside the TFTP shell, run:
   ```bash
   put uboot.bin
   ```

2. **Wait for the Process to Complete**:
   - The router will automatically reboot after the Uboot file is successfully flashed.

---

## Step 5: Verify the Installation

1. Reboot the router if it hasn’t already.
2. Test the Uboot environment by accessing `http://192.168.1.1` in a browser or repeating the recovery mode entry process.

---

## Troubleshooting:
- **No Response from the Router**:
  - Verify the Ethernet connection.
  - Check the router’s recovery mode status.
  - Recheck your static IP configuration.

- **TFTP Transfer Fails**:
  - Ensure the `uboot.bin` file is in the correct TFTP root directory.
  - Restart the TFTP server:
    ```bash
    sudo systemctl restart tftpd-hpa
    ```

---

This concludes the **TFTP Recovery Guide for Linux Users**. Follow other guides in this repository for alternative recovery methods like web-based recovery or CH341A.
