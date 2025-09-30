# Xkyrage's Top 5 Bootloaders

## 🧠 My Top 5 Favorite Bootloaders

This repository showcases my favorite Linux bootloaders — tools that initialize and load operating systems.  
Each section includes a short description and simple installation steps (for Arch Linux and general Linux systems).

---

## 1. 🐧 GRUB (GNU GRand Unified Bootloader)

**Description:**  
The most widely used bootloader across Linux distributions. It supports multiple OSes, themes, and recovery tools.

### 🔧 Installation (Arch Linux)
```
bash
sudo pacman -S grub os-prober
sudo grub-install --target=x86_64-efi --efi-directory=/boot --bootloader-id=GRUB
sudo grub-mkconfig -o /boot/grub/grub.cfg
```

2. 🚀 systemd-boot

Description:
A lightweight EFI boot manager that integrates tightly with systemd. Ideal for minimalist and Arch-based setups.

🔧 Installation
```
bootctl --path=/boot install
```
Then edit `/boot/loader/entries/arch.conf:`

```
title   Arch Linux
linux   /vmlinuz-linux
initrd  /initramfs-linux.img
options root=/dev/sdX2 rw
```

3. ⚙️ rEFInd

Description:
A beautiful and user-friendly EFI boot manager with graphical menu, auto-detection, and theme support.
🔧 Installation
```
yay -S refind
sudo refind-install
```
To refresh entries:
```
sudo refind-mkrlconf
```
4. 🌀 Limine

Description:
A modern, fast, and lightweight bootloader supporting BIOS and UEFI. Commonly used in OS development and custom kernels.

🔧 Installation
```
yay -S limine
sudo limine-install /dev/sdX
```

4. 🌀 Limine

Description:
A modern, fast, and lightweight bootloader supporting BIOS and UEFI. Commonly used in OS development and custom kernels.

🔧 Installation
```
yay -S limine
sudo limine-install /dev/sdX
```
For UEFI:
```
sudo cp /usr/share/limine/limine.efi /boot/EFI/BOOT/BOOTX64.EFI
```

🧩 Notes

For EFI systems, ensure /boot is mounted before installing.

Use efibootmgr to verify entries:
```
sudo efibootmgr
```

