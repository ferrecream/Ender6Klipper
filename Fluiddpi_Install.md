**Prerequisites:**

- **Hardware:**
  - Raspberry Pi (any model; Raspberry Pi Zero is a cost-effective choice).
  - MicroSD Card (high-speed recommended).
  - Power supply capable of delivering at least 2.5A.

- **Software:**
  - FluiddPi image: [Download from GitHub](https://github.com/cadriel/fluiddpi/releases).
  - Win32 Disk Imager: [Download here](https://sourceforge.net/projects/win32diskimager/).
  - Optional: PuTTY for SSH access: [Download here](https://www.putty.org/).

**Installation Steps:**

1. **Flash FluiddPi onto the SD Card:**
   - Download and unzip the latest FluiddPi image.
   - Install and open Win32 Disk Imager.
   - Select the unzipped `.img` file and your SD card's drive letter.
   - Click 'Write' to flash the image onto the SD card.

2. **Configure Wi-Fi (Optional):**
   - After flashing, open the `fluiddpi-wpa-supplicant.txt` file in the SD card's boot partition using a text editor like Notepad.
   - Uncomment lines 27 to 30 by removing the `#` at the beginning of each line.
   - Enter your Wi-Fi network's SSID and password:
     ```
     ssid="YourNetworkName"
     psk="YourNetworkPassword"
     ```
   - Save the file and safely eject the SD card.

3. **Set Up the Raspberry Pi:**
   - Insert the configured SD card into the Raspberry Pi.
   - Power on the Raspberry Pi.
   - Allow a few minutes for the initial boot process.

4. **Access the Fluidd Web Interface:**
   - Determine the Raspberry Pi's IP address:
     - On a Windows PC, open Command Prompt and execute:
       ```
       ping fluidd.local -4
       ```
     - Alternatively, check your router's connected devices list for the Raspberry Pi's IP.
   - Enter the IP address into a web browser to access the Fluidd interface.

5. **Install KIAUH (Klipper Installation And Update Helper):**
   - Use an SSH client like PuTTY to connect to the Raspberry Pi using its IP address.
   - Log in with the default credentials:
     ```
     Username: pi
     Password: raspberry
     ```
   - Execute the following commands:
     ```
     git clone https://github.com/th33xitus/kiauh.git
     cd kiauh
     chmod +x kiauh.sh scripts/*
     ./kiauh.sh
     ```
   - Follow the on-screen instructions in the KIAUH interface to install Klipper and other desired components.

