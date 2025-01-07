
# Guide: Web-Based Uboot Recovery for GL.iNet MT300N-V2

This guide walks you through the process of recovering or flashing Uboot on your GL.iNet MT300N-V2 router using the web-based Uboot recovery interface. This method is straightforward and requires no additional hardware or software beyond your computer and router.

---

## Requirements

1. **Hardware:**
   - GL.iNet MT300N-V2 router
   - Ethernet cable
   - Power supply for the router

2. **Software:**
   - A modern web browser (e.g., Chrome, Firefox, Edge)

3. **Files:**
   - The Uboot file (`uboot.bin`) from this repository.

---

## Step 1: Prepare the Environment

1. **Download the Uboot File**:
   - Clone this repository to your computer:

     ```bash
     git clone https://github.com/CodeStacker-Dev/GL-iNet_MT300N-V2_Factory.git
     ```

   - Navigate to `GL-iNet_MT300N-V2_Factory/uboot/` directory and locate the `uboot.bin` size `192KiB` file.

2. **Set Up Your Network**:
   - Use an Ethernet cable to connect your computer directly to the router.
   - Disable Wi-Fi on your computer to avoid interference.

3. **Configure Static IP**:
   - Set your computer's Ethernet adapter to a static IP:
     - **IP Address**: `192.168.1.2`
     - **Subnet Mask**: `255.255.255.0`
     - **Gateway**: `Leave Blank`

---

## Step 2: Access the Web-Based Uboot Interface

1. **Power Off the Router**:
   - Unplug the power cable from the router.

2. **Enter Recovery Mode**:
   - Hold down the **reset button** on the router.
   - While holding the reset button, power the router back on.
   - Keep holding the reset button for **6 seconds** until the router enters Uboot recovery mode.

3. **Access the Interface**:
   - Open a web browser and navigate to `http://192.168.1.1/uboot.html`.
   - You should see the **Uboot recovery web interface**.

---

## Step 3: Flash the Uboot File

1. **Upload the Uboot File**:
   - In the Uboot recovery interface, locate the "Choose File" or "Browse" button.
   - Select the `uboot.bin` file you downloaded earlier.

2. **Flash the Uboot File**:
   - Click the **Upload** or **Flash** button.
   - Wait patiently for the flashing process to complete. This may take a few minutes.

3. **Reboot the Router**:
   - Once the flashing process is complete, reboot the router by unplugging and reconnecting the power cable.

---

## Step 4: Verify the Installation

1. Repeat step `2:2 ~ Enter Recovery Mode`.
2. After rebooting, access the router's Uboot web interface again by navigating to `http://192.168.1.1`.
3. Verify that the Uboot environment is functioning correctly.

---

## Troubleshooting

- If the Uboot web interface does not load:
  - Double-check your computer's static IP configuration.
  - Ensure the Ethernet cable is securely connected.
  - Try a different browser.
- If the upload fails:
  - Verify the integrity of the `uboot.bin` file.
  - Try using another method, such as TFTP or CH341A (guides available in this repository).
  
---
