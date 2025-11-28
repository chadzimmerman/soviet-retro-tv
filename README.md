# Retro Soviet TV: A Nostalgic Broadcast Simulator (Fork of FieldStation42)

**Retro Soviet TV** is a community-driven fork of the original **FieldStation42** project, specialized to evoke the nostalgic television experience of the **late 1970s through the 1990s in the former Soviet Union.**

This fork is designed with **older ex-Soviet generations** and their families in mind, providing a unique blend of authentic retro functionality and curated multilingual content.

It maintains the core goals of simulating serial, time-locked broadcast TV while enhancing **cross-platform compatibility** (Mac, PC, WSL, and Linux VMs) and adding **user-friendly hardware integrations**.

-----

## ✨ Features & Philosophy

### A Nostalgic Focus 📺

The entire experience is tailored to replicate the aesthetic, schedule quirks, and broadcasting style of Soviet and early post-Soviet television.

### Duel Language Channels 🇷🇺 🇬🇧

The channel lineup is strategically split to appeal to two distinct audiences:

  * **Historical/Nostalgic:** Channels featuring classic Soviet-era programming, including news, shows, and films, often in **Russian**.
  * **Contemporary/International:** Channels featuring content appealing to younger generations or English-speaking users, designed to run alongside the retro broadcasts.

### Enhanced Usability for Older Generations

A core design goal is simple, tactile channel control. The project is specifically adapted for reliable use with **Air Mouse or generic USB remotes**, simplifying the channel-changing process without requiring complex web UIs or dedicated hardware.

### Cross-Platform & Accessibility

We ensure reliable installation and operation across various environments popular for emulation and hobby projects: **Mac, PC, WSL (Windows Subsystem for Linux), and native Linux VMs/Raspberry Pi**.

-----

## 🛠️ Project Status

### What We've Changed So Far

  * **Air Mouse / Generic Remote Integration:** Implemented robust and reliable mapping within the `remote_controller.py` script. This involved forcing the script to listen to the generic **AT translated set 2 keyboard** device (which air mice often emulate) and mapping non-standard Page Up (`104`) and Page Down (`109`) key codes to `channel_up_pressed()` and `channel_down_pressed()`.
  * **Improved Channel Management:** Debugged and validated the client-side remote logic to correctly handle single-digit channel inputs and multiple-digit timeouts.
  * **Permission Hardening:** Identified and fixed the requirement for `sudo` access, recommending the permanent fix of adding the user to the `input` group for production use on systems like the Raspberry Pi.

### What We Are Currently Working On

  * **Commercial Break Reliability:** Implementing the global configuration override for `COMMERCIAL_INTERVAL_MINUTES` to ensure the simulated **5-minute mid-content commercial breaks** function reliably across all schedules.
  * **Custom Content & Configuration:** Finalizing and sharing curated **Russian-language channel configurations** and **commercial break catalogs** to jump-start the authentic Soviet experience.
  * **Raspberry Pi Deployment:** Preparing the final setup and documentation for simple deployment onto a dedicated Raspberry Pi device.

-----

## 🚀 Quick Start

1.  **Clone the repository:**
       `bash    git clone https://github.com/YOUR_FORK_URL/RetroSovietTV.git    cd RetroSovietTV    `
2.  **Install dependencies:**
       `bash    ./install.sh    `
3.  **Add your own content:**
       - Place video files in the appropriate folders (see `catalog/` and `confs/examples/`).
4.  **Configure your stations:**
       - Copy an example config from `confs/examples` to `confs/` and edit as needed. **(Ensure your channel configs reflect the dual-language goals\!)**
5.  **Build catalogs and schedules:**
       `bash    python3 station_42.py --rebuild_catalog --schedule    `
6.  **Start the player:**
       `bash    python3 field_player.py    `
7.  **(Optional) Start the remote controller (after fixing permissions or using sudo):**
       `bash    python3 remote_controller.py    `

[Image of an older TV set displaying static or a test pattern]

For a full guide, see the [FieldStation42 Guide](https://github.com/shane-mason/FieldStation42/wiki).

-----

## 📚 Links & Resources

  - [FieldStation42 Guide (Wiki)](https://github.com/shane-mason/FieldStation42/wiki)
  - [API Reference](https://www.google.com/search?q=fs42/fs42_server/README.md)
  - [Discussions](https://github.com/shane-mason/FieldStation42/discussions)

