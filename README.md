# Install Arch Linux with Hyprland

## 1. Create a Bootable USB

1. **[Download](https://archlinux.org/download/) the Arch Linux ISO**
   
2. **Create a bootable USB drive**  
   Replace `sdX` with your USB device (e.g., `/dev/sda`):
   ```bash
   $ sudo dd if="/home/user/Downloads/archlinux-2025.01.01-x86_64.iso" of="/dev/sda" status="progress" conv="fsync"
   ```

---

## 2. Start installation

1. **Connect to Wi-Fi (if needed)**

   - Use `iwctl` to connect to a wireless network if necessary.  
   - Refer to the [IWD Arch Wiki](https://wiki.archlinux.org/title/Iwd) for more details.  

2. **Start the Installer**

   Launch the Arch Linux installer.
   ```bash
   $ archinstall
   ```

---

## 3. Configuration

1. **Disk Configuration**

   - Select the **ext4** filesystem.  

2. **Bootloader**

   - Choose **GRUB** as the bootloader.  

3. **Profile**

   - Set the installation type to **Desktop**.  
   - Choose **Hyprland** as the desktop environment.  
   - Use **[polkit](https://wiki.archlinux.org/title/Polkit)** for access policy management.  

4. **Graphics Drivers**

   - Use open-source drivers for Intel GPUs.  
   - Use proprietary drivers for NVIDIA GPUs.  

5. **Display Manager (Greeter)**

   - Select **SSDM** as the display manager.  

6. **Audio**

   - Use **PipeWire** for audio.  

7. **Network**

   - Select **NetworkManager** for network management.  

8. **Additional Packages**

   Recommended packages:
   ```
   git firefox hyprpaper hyprlock waybar neovim fish telegram-desktop ttf-font-awesome otf-font-awesome ttf-jetbrains-mono pkgfile ttf-dejavu powerline-fonts inetutils fastfetch
   ```

9. **Optional Repositories**

   - Enable the **multilib** repository to support 32-bit applications by updating the configuration file.  

---

## 4. Other

1. **Connect to WiFi**  
   Use `nmcli` to connect to a wireless network.
   ```bash
   $ nmcli device wifi connect <SSID> --ask
   ```

2. **Set Configuration**  
   Clone and apply your configurations from the repository:
   
   [GitHub - bygagaup/configs](https://github.com/bygagaup/configs)

3. **Install Paru**  
   Follow the instructions on the official Paru repository:

   [GitHub - Morganamilo/paru](https://github.com/Morganamilo/paru)

4. **Install Required Packages**  
   Use paru to install the following packages:
   ```bash
   $ paru -S hyprlock hyprshot
   ```

5. **Change Default Shell**  
   Change your default shell to `fish`:
   ```bash
   $ chsh -s /usr/bin/fish
   ```

6. **Update the System**  
   Update all packages to their latest versions:
   ```bash
   pacman -Syu
   ```
