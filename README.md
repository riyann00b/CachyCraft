# 🐧 CachyCraft  

<div align="center">
  
  [![Arch Linux](https://img.shields.io/badge/Arch_Linux-1793D1?style=for-the-badge&logo=arch-linux&logoColor=white)](https://archlinux.org)
  [![CachyOS](https://img.shields.io/badge/CachyOS-00AEEF?style=for-the-badge&logo=linux&logoColor=white)](https://cachyos.org)
  [![Btrfs](https://img.shields.io/badge/Btrfs-53B9E0?style=for-the-badge&logo=linux&logoColor=white)](https://btrfs.readthedocs.io)
  [![Productivity](https://img.shields.io/badge/Productivity-FF9800?style=for-the-badge&logo=todoist&logoColor=white)](#)
  [![Developer Friendly](https://img.shields.io/badge/Developer_Friendly-2ECC71?style=for-the-badge&logo=visualstudiocode&logoColor=white)](#)
  
</div>

**CachyCraft** is a curated post-installation guide for [CachyOS](https://cachyos.org), crafted to help you set up a fast, productive, and beautiful Linux environment.  
It includes essential apps, developer tools, system configurations, and maintenance tips — all in one place — so you can transform a fresh CachyOS install into a fully customized daily driver with ease.  

✨ Whether you’re a developer, a power user, or just exploring CachyOS, this guide will help you craft the perfect workflow.  

![CheatSheet](https://github.com/riyann00b/CachyCraft/blob/main/fisherman-toolkit.md)

---

## 📑 Table of Contents

- [🚀 Tech Stack & Tools](#-tech-stack--tools)
    
- [📦 Package Management](#-package-management)
    
- [🖥️ Essential Applications](#%EF%B8%8F-essential-applications)
    
    - [🔤 Terminal — Ghostty](#-terminal--ghostty)
        
    - [🌐 Browser — Zen](#-browser--zen)
        
    - [📝 Productivity — Kuro, Betterbird, Obsidian](#-productivity---kuro-betterbird-obsidian)
        
    - [🎬 Media — VLC, OBS Studio, Telegram](#-media---vlc-obs-studio-telegram)
        
    - [💻 Dev Tools — Neovim, VS Code, JetBrains, Android Tools](#-dev-tools---neovim-vs-code-jetbrains-android-tools)
        
    - [🐳 Docker & Container Tools (Docker Engine, Docker Desktop, Compose)](#-docker--container-tools)
        
    - [💾 Btrfs & Snapshots](#-btrfs--snapshots)
        
- [🎨 System Configuration](#-system-configuration)
    
    - [🖼️ GRUB Theme Customization (with GRUB Customizer)](#%EF%B8%8F-grub-theme-customization)
        
    - [⚡ Starship Prompt (with font installer)](#-starship-prompt)
        
    - [🌸 GNOME Extensions (ArcMenu and co.)](#-gnome-extensions)
        
    - [📂 Access Root in GNOME Files (admin://, bookmarks, desktop shortcut)](#-access-root-in-gnome-files)
        
- [🐟 Fish Shell Essentials](#-fish-shell-essentials)
    
- [🧹 System Maintenance & Cleanup](#-system-maintenance--cleanup)
    
- [💡 Pro Tips](#-pro-tips)
    
- [📖 Resources](#-resources)
    

---

## 🚀 Tech Stack & Tools

![Ghostty](https://img.shields.io/badge/Ghostty-000000?style=for-the-badge&logo=gnometerminal&logoColor=white) ![Zen Browser](https://img.shields.io/badge/Zen%20Browser-4CAF50?style=for-the-badge&logo=firefoxbrowser&logoColor=white) ![Neovim](https://img.shields.io/badge/Neovim-57A143?style=for-the-badge&logo=neovim&logoColor=white) ![VS Code](https://img.shields.io/badge/VS%20Code-0078D4?style=for-the-badge&logo=visualstudiocode&logoColor=white) ![Betterbird](https://img.shields.io/badge/Betterbird-FF7139?style=for-the-badge&logo=thunderbird&logoColor=white) ![VLC](https://img.shields.io/badge/VLC%20Media%20Player-FF8800?style=for-the-badge&logo=vlcmediaplayer&logoColor=white) ![OBS Studio](https://img.shields.io/badge/OBS%20Studio-302E31?style=for-the-badge&logo=obsstudio&logoColor=white) ![Telegram](https://img.shields.io/badge/Telegram-26A5E4?style=for-the-badge&logo=telegram&logoColor=white) ![Obsidian](https://img.shields.io/badge/Obsidian-483699?style=for-the-badge&logo=obsidian&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white) ![Btrfs](https://img.shields.io/badge/Btrfs-003366?style=for-the-badge&logo=linux&logoColor=white)

---

## 📦 Package Management

Install apps via:

- **Pacman** → official repos
    
- **Yay** → AUR helper
    
- **Flatpak** → sandboxed apps from Flathub
    

Enable Flatpak:

```bash
sudo pacman -S flatpak
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

---

## 🖥️ Essential Applications

### 🔤 Terminal — Ghostty

A fast, GPU-accelerated modern terminal.

```bash
sudo pacman -S ghostty  # Stable version
yay -S ghostty-git       # AUR (latest)
```

### 🌐 Browser — Zen

Privacy-focused, modern browsing experience.

```bash
flatpak install flathub app.zen_browser.zen
flatpak run app.zen_browser.zen
```

### 📝 Productivity — Kuro, Betterbird, Obsidian

- **Kuro**: Sleek MS To-Do client.
    
    ```bash
    yay -S kuro-appimage
    ```
    
- **Betterbird**: Enhanced Thunderbird fork.
    
    ```bash
    yay -S betterbird-bin
    ```
    
- **Obsidian**: Markdown wiki and notes.
    
    ```bash
    flatpak install flathub md.obsidian.Obsidian
    ```
    

### 🎬 Media — VLC, OBS Studio, Telegram

- **VLC**: Universal media player.
    
    ```bash
    flatpak install flathub org.videolan.VLC
    ```
    
- **OBS Studio**: Recording/streaming tool.
    
    ```bash
    flatpak install flathub com.obsproject.Studio
    ```
    
- **Telegram**: Secure messaging.
    
    ```bash
    flatpak install flathub org.telegram.desktop
    ```
    

### 💻 Dev Tools — Neovim, VS Code, JetBrains, Android Tools

- **Neovim**: Lightweight extensible editor.
    
    ```bash
    yay -S neovim
    ```
    
- **VS Code**: Feature-rich IDE.
    
    ```bash
    yay -S visual-studio-code-bin
    ```
    
- **JetBrains Toolbox**: Manage IDEs.  
    [Download Toolbox](https://www.jetbrains.com/toolbox-app/)
    
- **Android Tools**: `adb`, `fastboot` etc.
    
    ```bash
    sudo pacman -S android-tools
    ```
    

### 🐳 Docker & Container Tools

Docker lets you run containers for development, databases, and deployment workflows. On Arch-based distros, **Docker Desktop** is now officially supported.

#### 📥 Install Docker Desktop

1. **Install Docker client binary**
    

```bash
wget https://download.docker.com/linux/static/stable/x86_64/docker-28.4.0.tgz -qO- | tar xvfz - docker/docker --strip-components=1
sudo mv ./docker /usr/local/bin
```

2. **Download latest Arch package**  
    Go to [Docker Desktop Release Notes](https://docs.docker.com/desktop/release-notes/) and download the latest `.pkg.tar.zst` file.
    
3. **Install the package**
    

```bash
sudo pacman -U ./docker-desktop-x86_64.pkg.tar.zst
```

By default, Docker Desktop installs to `/opt/docker-desktop`.

---

#### ▶️ Launch Docker Desktop

- From GNOME/KDE, open **Docker Desktop** from your apps menu.
    
- Accept the subscription terms when prompted.
    

Or start it manually:

```bash
systemctl --user start docker-desktop
```

Enable auto-start on login:

```bash
systemctl --user enable docker-desktop
```

Stop Docker Desktop:

```bash
systemctl --user stop docker-desktop
```

---

#### 🔄 Updating Docker Desktop

1. Download the **latest Arch package** from [Docker Desktop Release Notes](https://docs.docker.com/desktop/release-notes/).
    
2. Install the update:
    

```bash
sudo pacman -U ./docker-desktop-x86_64.pkg.tar.zst
```

The installer updates:

- **Docker Compose V2**
    
- **Docker CLI** (with cloud integration)
    

---

#### ✅ Verify installation

```bash
docker --version
docker compose version
docker version
```

---

### 🐳 Docker Cleanup
```bash
# Clean up unused Docker objects
docker system prune -af

# Remove unused volumes
docker volume prune -f

# Remove unused networks
docker network prune -f

# Remove dangling images
docker image prune -f
```
---

### 🗃️ Database — MariaDB

For robust, high-performance database management, MariaDB is the default choice for Arch Linux and CachyOS. It serves as a powerful, open-source, and community-driven replacement for MySQL.

#### Why MariaDB over MySQL?

MariaDB originated as a fork of MySQL, created by its original developers to ensure it remained free and open-source. Here’s why it’s often preferred:

-   **Truly Open-Source**: MariaDB is fully GPL licensed and driven by its community and the MariaDB Foundation, whereas MySQL's open-source Community Edition is managed by Oracle, with many advanced features reserved for the Enterprise version.
-   **Better Performance**: MariaDB often demonstrates superior performance thanks to its enhanced query optimizer and additional storage engines like Aria and ColumnStore, which are designed for speed and analytics.
-   **More Features**: It includes modern features like system-versioned tables, Oracle compatibility syntax, and invisible columns that aren't available in MySQL Community Edition.
-   **Drop-in Replacement**: For most use cases, you can switch from MySQL to MariaDB without any code changes. It maintains backward compatibility and uses the same client protocols, ports, and tools.

#### 📦 Installation on CachyOS

1.  **Install the MariaDB package:**  
    MariaDB is the default implementation on Arch-based systems.

    ```bash
    sudo pacman -S mariadb
    ```

2.  **Initialize the data directory:**  
    This command sets up the necessary system tables and database structure.

    ```bash
    sudo mariadb-install-db --user=mysql --basedir=/usr --datadir=/var/lib/mysql
    ```

3.  **Start and enable the MariaDB service:**  
    This ensures the database server runs automatically on boot.

    ```bash
    sudo systemctl start mariadb
    sudo systemctl enable mariadb
    ```

4.  **Secure your installation (Highly Recommended):**  
    Run the security script to set a root password, remove anonymous users, disallow remote root login, and clean up the test database.

    ```bash
    sudo mariadb-secure-installation
    ```

    Follow the on-screen prompts to secure your new database server. You're now ready to create databases and users!

[User Guide and cheatsheet](https://github.com/riyann00b/CachyCraft/blob/main/MariaDB%20Crafter's%20Guide.md)

---

### 💾 Btrfs & Snapshots

**What is Btrfs?**  
A modern Linux filesystem with **copy-on-write**, **checksums**, and **snapshots**.

**Why Snapshots Matter:**

- Roll back updates if something breaks.
    
- Recover from system crashes.
    
- Save disk space with incremental backups.

**Install tools:**

```bash
yay -S btrfs-assistant grub-btrfs snapper
```

**Create a snapshot before updates:**

```bash
sudo snapper -c root create -d "Before system update"
```

**List snapshots:**

```bash
snapper -c root list
```

**Restore snapshot:**

```bash
sudo snapper -c root undochange <SNAPSHOT_ID>..0
```

With `grub-btrfs`, snapshots appear in your boot menu for easy rollback.

Btrfs Snapshot Management

```bash
# List all snapshots
sudo btrfs subvolume list / | grep -i snapshot

# Delete snapshots older than 30 days (keep last 5)
sudo snapper -c root list | awk 'NR>1 && $5 ~ /pre|post/ && $6 ~ /^[0-9]{4}-[0-9]{2}-[0-9]{2}/ {print $2}' | tail -n +6 | xargs -I{} sudo snapper -c root delete {}

# Clean up snapper configuration
sudo snapper -c root cleanup number
```


---
## 🎨 System Configuration

### 🖼️ GRUB Theme Customization

**GRUB Customizer** is a GUI to change bootloader settings, OS order, and themes.

```bash
yay -S grub-customizer
```

**Add a Theme:**

1. Download from [GNOME-Look GRUB Themes](https://www.gnome-look.org/browse?cat=109&ord=latest).
    
2. Extract theme into `/boot/grub/themes/`.
    
3. Open **Grub Customizer → Preferences → Theme tab**.
    
4. Select your theme, save, then update GRUB:
    
    ```bash
    sudo grub-mkconfig -o /boot/grub/grub.cfg
    ```
    

📖 [GRUB Customizer Docs](https://launchpad.net/grub-customizer)

---

### ⚡ Starship Prompt

**What is Starship?**  
A fast, customizable shell prompt that shows git status, package versions, and more.

**Install Starship:**

```bash
sudo pacman -S starship
```

**Install required fonts (FiraCode Nerd Font):**

```bash
sudo pacman -S ttf-firacode-nerd
```

**Or install via Starship itself:**

```bash
starship prompt install-fonts
```

**Enable in Fish:**

```fish
starship init fish | source
```

Apply preset:

```bash
starship preset gruvbox-rainbow -o ~/.config/starship.toml
```

---

### 🌸 GNOME Extensions

Enhance GNOME with these extensions:

- **AppIndicator and KStatusNotifierItem Support** → system tray icons
    
- **ArcMenu** → Windows-style start menu
    
- **Compiz Effects (Magic Lamp, Window Effects)** → eye candy animations
    
- **Desktop Icons NG (DING)** → desktop icon support
    
- **GSConnect** → Android device integration
  - if you are unable to locate your device do this

    ```bash
    sudo pacman -S ufw
    ```

    ```bash
    sudo ufw enable
    ```

    ```bash
    sudo ufw allow 1714:1764/udp
    sudo ufw allow 1714:1764/tcp
    ```
    
- **Vitals** → system resource monitoring in top bar
    
- **User Themes** → apply shell themes
    
- **Media Controls** → control playback from panel
    

```bash
yay -S extension-manager gnome-tweaks
```


### 📂 Access Root in GNOME Files

GNOME Files (Nautilus) uses **GVFS admin:// protocol** for root access.

**Open root folder:**

```bash
nautilus admin:///
```

**Create a shortcut:**

1. Open Nautilus → Press `Ctrl+D` on `admin:///`.
    
2. This bookmarks **Root (Admin)** in the sidebar.
    

**Create a desktop shortcut:**

```bash
nano ~/.local/share/applications/root-folder.desktop
```

Paste:

```ini
[Desktop Entry]
Name=Root File Manager
Exec=nautilus admin:///
Icon=folder
Terminal=false
Type=Application
```

Make executable:

```bash
chmod +x ~/.local/share/applications/root-folder.desktop
```

Now search “**Root File Manager**” in GNOME app grid.

---

## 🐟 Fish Shell Essentials

CachyOS comes with **Fish Shell** pre-configured with some aliases.  
Here are the most useful ones (no need to add manually unless you want to extend them):

- **File Management** → `ls`, `ll`, `la`, `lt` use `eza` for colorful listings with icons.
    
- **Navigation** → `..`, `...`, `....` quickly jump up directories.
    
- **System** → `update` runs mirror ranking + full system update, `grubup` updates GRUB.
    
- **Monitoring** → `psmem` sorts processes by memory, `jctl` shows system errors.
    
- **Package Management** → `cleanup` removes orphans, `big` shows largest packages, `gitpkg` counts `-git` packages.
    
Full list of alies ![Here](https://github.com/riyann00b/CachyCraft/blob/main/fisherman-toolkit.md)

---

## 🧹 System Maintenance

### 🔄 Regular Updates

```bash
sudo cachyos-rate-mirrors && sudo pacman -Syu
```

### 🧽 Cleanup Orphan Packages

```bash
sudo pacman -Rns $(pacman -Qtdq)
```

### 💾 Pacman Cache Cleanup

```bash
sudo pacman -Sc   # keep last 3 versions
sudo pacman -Scc  # clear ALL cache
```

### 🗑️ Journal Logs Cleanup

```bash
sudo journalctl --vacuum-time=7d
sudo journalctl --vacuum-size=500M
```

### 🧹 Full System Cleanup

```bash
# Remove orphan packages
sudo pacman -Rns $(pacman -Qtdq)

# Clear package cache
sudo pacman -Scc

# Clean journal logs
sudo journalctl --vacuum-time=7d

# Flatpak cleanup
flatpak uninstall --unused
flatpak remove --delete-data

# Clear system/user cache
sudo rm -rf /var/cache/*
rm -rf ~/.cache/*
```

---

## 💡 Pro Tips

* 🛡️ **Update weekly**: Run `update` to keep your system secure and optimized
* 📸 **Snapshot before upgrades**: Always create a snapshot before major updates:
  ```bash
  sudo snapper -c root create -d "Before update $(date +%Y%m%d)"
  ```
* 💾 **Check disk usage**: Use `big` to see which packages consume the most space
* 🎨 **Customize Starship**: Edit `~/.config/starship.toml` to tailor your prompt
* ⚡ **Faster boot**: Set `GRUB_TIMEOUT=3` in `/etc/default/grub` and run `grubup`
* 🐟 **Fish configuration**: Add custom functions to `~/.config/fish/functions/`
* 🔍 **Find large files**: Use `find / -xdev -type f -size +100M 2>/dev/null` to locate large files
* 📊 **Monitor system**: Use `htop` or `btop` for real-time system monitoring
* 🐳 **Docker management**: Regularly run `docker system prune` to clean up unused containers and images
* 📂 **Root access**: Use `admin://` in GNOME Files instead of running the entire file manager as root
---

## 📖 Resources

- [CachyOS Wiki](https://wiki.cachyos.org)
    
- [Arch Wiki](https://wiki.archlinux.org/)
    
- [Flathub](https://flathub.org/)
    
- [Starship Prompt](https://starship.rs/)
    
- [GRUB Customizer Docs](https://launchpad.net/grub-customizer)
    
- **Docker official guides:**
    
    - [Docker Engine Install](https://docs.docker.com/engine/install/) ([Docker Documentation](https://docs.docker.com/engine/install/?utm_source=chatgpt.com "Install Docker Engine"))
        
    - [Docker Desktop on Arch](https://docs.docker.com/desktop/setup/install/linux/archlinux/) ([Docker Documentation](https://docs.docker.com/desktop/setup/install/linux/archlinux/?utm_source=chatgpt.com "Install Docker Desktop on Arch-based distributions"))
        

---

> 📝 **Note:** This guide reflects my personal CachyOS setup.  
> Adapt it to your workflow — that’s the beauty of Arch-based systems.

_Last updated: **September 7, 2025**_

---


