# 🛠️ Setup
[![OS](https://img.shields.io/badge/OS-Ubuntu%2024.04%20LTS-orange?logo=ubuntu)](https://releases.ubuntu.com/noble/)
[![Terminal](https://img.shields.io/badge/🖥️-Windows%20Terminal-4D4D4D?logo=windows)](https://github.com/microsoft/terminal)
[![WSL2](https://img.shields.io/badge/🐧WSL2-Enabled-blue?logo=windows)](https://learn.microsoft.com/en-us/windows/wsl/)
[![Fonts](https://img.shields.io/badge/🔤Font-Hack%20Nerd%20Font-96231A?logo=nerdfonts)](https://github.com/ryanoasis/nerd-fonts)
[![Shell](https://img.shields.io/badge/🐟Shell-Fish-4C9141?logo=fish)](https://fishshell.com/)
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
- [Ubuntu 24.04 LTS (Noble Numbat)](https://releases.ubuntu.com/noble/)

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

---


## Ansible
For having multiple [Ansible versions](https://docs.ansible.com/ansible/latest/reference_appendices/release_and_maintenance.html), I prefer working with [python virtual environments](https://docs.python.org/3/library/venv.html).\
You can adapt or use your own requirements files. Here is an example with python3.12 (shipped with the Ubuntu 24.04) and Ansible 11 (core 2.18).

```bash
sudo apt install python3.12-venv
mkdir -p ~/python_venv/Ansible2.18
python3 -m venv ~/python_venv/Ansible2.18/
source ~/python_venv/Ansible2.18/bin/activate
pip install -r ansible2.18_requirements.txt
```

We will later use fish shell, in that case source file to activate is **activate.fish**.

## Installation
You can modify your sudoers configuration file to avoid providing the become password or use **--ask-become-pass** option. You can also use **--tags** to run specific parts of the setup.

Available tags:
- packages
- fish_config

```bash
ansible-playbook setup.yml
```

## Shell setup

- [fish shell](https://github.com/fish-shell/fish-shell)
- [fisher](https://github.com/jorgebucaran/fisher) - Plugin manager for fish
- [tide](https://github.com/IlanCosman/tide) - Prompt fish theme
- [z](https://github.com/jethrokuan/z) - Directory jumper
- [eza](https://github.com/eza-community/eza) with [fish-exa](https://github.com/gazorby/fish-exa) - Modern ls replacement
