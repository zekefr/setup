# 🛠️ Setup
[![OS](https://img.shields.io/badge/OS-Ubuntu%2024.04%20LTS-orange?logo=ubuntu)](https://releases.ubuntu.com/noble/)
[![Terminal](https://img.shields.io/badge/🖥️-Windows%20Terminal-4D4D4D?logo=windows)](https://github.com/microsoft/terminal)
[![WSL2](https://img.shields.io/badge/🐧-WSL2%20Enabled-blue?logo=windows)](https://learn.microsoft.com/en-us/windows/wsl/)
[![Shell](https://img.shields.io/badge/🐟-Fish%20Shell-4C9141?logo=fish)](https://fishshell.com/)
[![Font](https://img.shields.io/badge/🔤-Hack%20Nerd%20Font-96231A?logo=nerdfonts)](https://github.com/ryanoasis/nerd-fonts)
[![Automation](https://img.shields.io/badge/Ansible-Role-000000?logo=ansible)](https://www.ansible.com/)

My personal WSL2 setup as an SRE/DevOps Engineer, automated with **Ansible**.

---

## ✅ Prerequisites
Before running the Ansible role, set up the following on your Windows machine:

### 🐧 WSL2
Follow the official guide:
👉 [How to install Linux on Windows with WSL](https://learn.microsoft.com/en-us/windows/wsl/install)

Using:
- [WSL2](https://learn.microsoft.com/en-us/windows/wsl/)
- [Ubuntu 25.04 (Plucky Puffin)](https://releases.ubuntu.com/plucky/)

### 🖥️ Windows Terminal
Install instructions:
👉 [Installing and running Windows Terminal](https://github.com/microsoft/terminal?tab=readme-ov-file#installing-and-running-windows-terminal)

Optional customization:
- Check out my [settings.json](windows-terminal/settings.json)

⚠️ **Warning:** Don’t blindly copy the settings — adapt to your own preferences!

### 🔤 Fonts
Using [Hack Nerd Fonts](https://github.com/ryanoasis/nerd-fonts)

For Windows installation:
1. Install [Scoop](https://github.com/ScoopInstaller/Scoop)
2. Follow 👉 [Option 3: Unofficial Chocolatey or Scoop Repositories](https://github.com/ryanoasis/nerd-fonts?tab=readme-ov-file#option-3-unofficial-chocolatey-or-scoop-repositories)

### ⚙️ Ansible
This setup uses [Ansible](https://www.ansible.com/) to automate environment configuration.
To keep it clean and easily manage multiple Ansible versions, use [UV](https://docs.astral.sh/uv/) inside the cloned repo.
I am using Python 3.13 (shipped with Ubuntu 25.04) and Ansible 12 (core 2.19).

#### Steps

Clone this repository first:

```bash
git clone https://github.com/zekefr/setup.git
cd setup
```

Install UV and Ansible:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
uv sync
source .venv/bin/activate
```

We will later use fish shell, in that case source file to activate is **activate.fish**.

---

## 🚀 Usage
You can run the full playbook to configure your environment:

```bash
ansible-playbook setup.yml
```

If your `sudo` requires a password, either:
- Modify your sudoers configuration to skip asking for it
- Or use the `--ask-become-pass` option

```bash
ansible-playbook setup.yml --ask-become-pass
```

You can also run only specific parts of the setup using **--tags**.

Available tags:
- `packages`
- `fish_config`

For example, to only install packages:

```bash
ansible-playbook setup.yml --tags packages
```

---

## 📦 What’s Installed and Configured
This Ansible setup will automatically install and configure the following:

- **Linux packages**
  Essential tools and utilities to get your environment ready.

- **Fish shell with tide and plugins**
  Preferred interactive shell with useful plugins via Fisher.
  - [fish shell](https://github.com/fish-shell/fish-shell)
  - [fisher](https://github.com/jorgebucaran/fisher) - Plugin manager for fish
  - [tide](https://github.com/IlanCosman/tide) - Prompt fish theme
  - [z](https://github.com/jethrokuan/z) - Directory jumper
  - [eza](https://github.com/eza-community/eza) with [fish-exa](https://github.com/gazorby/fish-exa) - Modern ls replacement
