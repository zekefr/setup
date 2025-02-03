# Setup
My setup as a SRE/DevOps Engineer.

Using:
- [Windows Terminal](https://github.com/microsoft/terminal)
- [WSL2](https://learn.microsoft.com/en-us/windows/wsl/)
- [Ubuntu 24.04 LTS (Noble Numbat)](https://releases.ubuntu.com/noble/)

## WSL2
Follow [How to install Linux on Windows with WSL](https://learn.microsoft.com/en-us/windows/wsl/install)

## Windows Terminal
Follow [Installing and running Windows Terminal](https://github.com/microsoft/terminal?tab=readme-ov-file#installing-and-running-windows-terminal)\
Windows terminal [settings](windows-terminal/settings.json)\
**Warning**: Don’t blindly copy the settings.json / adapt yours!

## Fonts
Using [Hack Nerd Fonts](https://github.com/ryanoasis/nerd-fonts)

For windows installation:
- install [Scoop](https://github.com/ScoopInstaller/Scoop)
- follow [Option 3: Unofficial Chocolatey or Scoop Repositories](https://github.com/ryanoasis/nerd-fonts?tab=readme-ov-file#option-3-unofficial-chocolatey-or-scoop-repositories)

## Ansible
For having multiple [Ansible versions](https://docs.ansible.com/ansible/latest/reference_appendices/release_and_maintenance.html), I prefer working with [python virtual environments](https://docs.python.org/3/library/venv.html).\
You can adapt or use your own requirements files. Here is an example with python3.12 (shipped with the Ubuntu 24.04) and Ansible 11 (core 2.18).

```bash
sudo apt install python3.12-venv
mkdir ~/python_venv/Ansible2.18
python3 -m venv ~/python_venv/Ansible2.18/
source ~/python_venv/Ansible2.18/bin/activate
pip install -r ansible2.18_requirements.txt
```

We will later use fish shell, in that case source file to activate is **activate.fish**.

## Shell setup

- [fish shell](https://github.com/fish-shell/fish-shell)
- [fisher](https://github.com/jorgebucaran/fisher) - Plugin manager for fish
- [tide](https://github.com/IlanCosman/tide) - Prompt fish theme
- [z](https://github.com/jethrokuan/z) - Directory jumper
- [eza](https://github.com/eza-community/eza) with [fish-exa](https://github.com/gazorby/fish-exa) - Modern ls replacement
