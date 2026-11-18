# Home Assistant Operating System (armv7 Legacy Support)

> [!IMPORTANT]
> **Project Status: Work in Progress (WIP)**  
> This repository is a pinned fork of the official [Home Assistant Operating System](https://github.com/home-assistant/operating-system/releases/tag/16.3) at version **16.3**—the final release with official **armv7 architecture** support.
> 
> - **OS Base (`home-assistant-os-armv7`):** Pinned & ready at v16.3.
> - **Core Dependency ([`home-assistant-core-armv7`](https://github.com/roteRakete66/home-assistant-core-armv7)):** *Currently WIP* – full end-to-end OS builds depend on finalizing the matching armv7 Core fork.
> - **Add-ons:** Already functional and ready to use on existing armv7 Home Assistant setups (see below).

### 📦 Compatible Add-ons
I have curated a collection of Home Assistant Add-ons specifically for armv7 users. These have been forked and pinned to versions that remain compatible with this OS version:
👉 **[Home Assistant Add-ons for armv7](https://github.com/stars/roteRakete66/lists/home-assistant-add-ons-for-armv7)**

**Is something missing?** If you need a specific add-on that isn't listed, feel free to start a [discussion](https://github.com/roteRakete66/home-assistant-os-armv7/discussions/new?category=ideas) or open an [issue](https://github.com/roteRakete66/home-assistant-os-armv7/issues/new?template=custom.md), and I will do my best to add a compatible version as soon as possible.

---

# Home Assistant Operating System

Home Assistant Operating System (formerly HassOS) is a Linux based operating system optimized to host [Home Assistant](https://www.home-assistant.io) and its [Add-ons](https://www.home-assistant.io/addons/).

Home Assistant Operating System uses Docker as its container engine. By default it deploys the Home Assistant Supervisor as a container. Home Assistant Supervisor in turn uses the Docker container engine to control Home Assistant Core and Add-Ons in separate containers. Home Assistant Operating System is **not** based on a regular Linux distribution like Ubuntu. It is built using [Buildroot](https://buildroot.org/) and it is optimized to run Home Assistant. It targets single board compute (SBC) devices like the Raspberry Pi or ODROID but also supports x86-64 systems with UEFI.

[![Home Assistant - A project from the Open Home Foundation](https://www.openhomefoundation.org/badges/home-assistant.png)](https://www.openhomefoundation.org/)

## Features

- Lightweight and memory-efficient
- Minimized I/O
- Over The Air (OTA) updates
- Offline updates
- Modular using Docker container engine

## Supported hardware

The list of supported hardware is defined by [ADR-0015](https://github.com/home-assistant/architecture/blob/master/adr/0015-home-assistant-os.md).
Every new hardware addition must meet at least requirements defined in [ADR-0017](https://github.com/home-assistant/architecture/blob/master/adr/0017-hardware-screening-os.md) and pass through an architecture design proposal.

For documentation explaining details of the individual supported boards, see [Board support](https://developers.home-assistant.io/docs/operating-system/boards/overview) section of the Home Assistant Developer Docs.

## Getting Started

If you just want to use Home Assistant the official [getting started guide](https://www.home-assistant.io/getting-started/) and [installation instructions](https://www.home-assistant.io/hassio/installation/) take you through how to download Home Assistant Operating System and get it running on your machine.

If you're interested in finding out more about Home Assistant Operating System and how it works read on...

## Development

If you don't have experience with embedded systems, Buildroot or the build process for Linux distributions it is recommended to read up on these topics first (e.g. [Bootlin](https://bootlin.com/docs/) has excellent resources).

The Home Assistant Operating System documentation can be found on the [Home Assistant Developer Docs website](https://developers.home-assistant.io/docs/operating-system).

### Components

- **Bootloader:**
  - [GRUB](https://www.gnu.org/software/grub/) for devices that support UEFI
  - [U-Boot](https://www.denx.de/wiki/U-Boot) for devices that don't support UEFI
- **Operating System:**
  - [Buildroot](https://buildroot.org/) LTS Linux
- **File Systems:**
  - [SquashFS](https://www.kernel.org/doc/Documentation/filesystems/squashfs.txt) for read-only file systems (using LZ4 compression)
  - [ZRAM](https://www.kernel.org/doc/Documentation/blockdev/zram.txt) for `/tmp`, `/var` and swap (using LZ4 compression)
- **Container Platform:**
  - [Docker Engine](https://docs.docker.com/engine/) for running Home Assistant components in containers
- **Updates:**
  - [RAUC](https://rauc.io/) for Over The Air (OTA) and USB updates
- **Security:**
  - [AppArmor](https://apparmor.net/) Linux kernel security module

### Development builds

The Development build GitHub Action Workflow is a manually triggered workflow which creates Home Assistant OS development builds. The development builds are available at [https://os-artifacts.home-assistant.io/index.html](https://os-artifacts.home-assistant.io/index.html).
