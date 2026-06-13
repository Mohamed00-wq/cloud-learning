# 🖥️ Debian Server VM on Arch Linux

## Overview
Set up a Debian VM using VirtualBox on Arch Linux, configured sudo user, verified internet, and connected via SSH.

## Steps

### 1. Create the VM
```bash
VBoxManage createvm --name "debian" --ostype "Debian13_64" --register
VBoxManage modifyvm "debian" --memory 2048 --vram 16 --ioapic on --boot1 dvd --boot2 disk --nic1 nat
VBoxManage createhd --filename "debian.vdi" --size 20480
```

### 2. User Configuration
```bash
su -
apt install sudo -y
usermod -aG sudo username
```

### 3. Test Internet
```bash
ping -c 3 8.8.8.8
ping -c 3 google.com
```

### 4. SSH Issue
```bash
ssh username@10.0.2.15  # ❌ Connection timed out
```
Root cause: VirtualBox NAT isolates the VM — host can't reach guest directly.

### 5. Fix — Port Forwarding
```bash
VBoxManage controlvm "debian" poweroff
VBoxManage modifyvm "debian" --natpf1 "ssh,tcp,,2222,,22"
VBoxManage startvm "debian"
```

### 6. Successful SSH
```bash
ssh username@127.0.0.1 -p 2222  # ✅ Success
```

## Key Takeaways
- NAT mode requires port forwarding for host-to-guest SSH
- `127.0.0.1` with custom port bypasses NAT isolation
- This mirrors how cloud VMs are accessed via SSH
