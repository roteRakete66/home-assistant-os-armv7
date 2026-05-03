# Home Assistant Operating System (armv7 Legacy Support)

> [!IMPORTANT]
> **This is a fork of the official Home Assistant Operating System.**
> This repository is pinned to version **16.3**, which is the latest version that still provides official support for the **armv7 architecture**[cite: 3]. While these builds may still be available in the [official repository](https://github.com/home-assistant/operating-system/releases/tag/16.3) for now, this fork serves as a permanent home to ensure long-term availability for users on older hardware.

### 📦 Compatible Add-ons
I have curated a collection of Home Assistant Add-ons specifically for armv7 users. These have been forked and reverted to versions that remain compatible with this OS version:
👉 **[Home Assistant Add-ons for armv7](https://github.com/stars/roteRakete66/lists/home-assistant-add-ons-for-armv7)**

**Is something missing?** If you need a specific add-on that isn't listed, feel free to start a [discussion](https://github.com/roteRakete66/home-assistant-os-armv7/discussions/new?category=ideas) or open an [issue](https://github.com/roteRakete66/home-assistant-os-armv7/issues/new?template=custom.md), and I will do my best to add a compatible version as soon as possible.

---

# Home Assistant Operating System

Home Assistant Operating System (formerly HassOS) is a Linux based operating system optimized to host [Home Assistant](https://www.home-assistant.io) and its [Add-ons](https://www.home-assistant.io/addons/)[cite: 3].

Home Assistant Operating System uses Docker as its container engine[cite: 3]. By default it deploys the Home Assistant Supervisor as a container[cite: 3]. Home Assistant Supervisor in turn uses the Docker container engine to control Home Assistant Core and Add-Ons in separate containers[cite: 3]. Home Assistant Operating System is **not** based on a regular Linux distribution like Ubuntu[cite: 3]. It is built using [Buildroot](https://buildroot.org/) and it is optimized to run Home Assistant[cite: 3]. It targets single board compute (SBC) devices like the Raspberry Pi or ODROID but also supports x86-64 systems with UEFI[cite: 3].

[![Home Assistant - A project from the Open Home Foundation](https://www.openhomefoundation.org/badges/home-assistant.png)](https://www.openhomefoundation.org/)

## Features

- Lightweight and memory-efficient[cite: 3]
- Minimized I/O[cite: 3]
- Over The Air (OTA) updates[cite: 3]
- Offline updates[cite: 3]
- Modular using Docker container engine[cite: 3]

## Supported hardware

The list of supported hardware is defined by [ADR-0015](https://github.com/home-assistant/architecture/blob/master/adr/0015-home-assistant-os.md)[cite: 3].
Every new hardware addition must meet at least requirements defined in [ADR-0017](https://github.com/home-assistant/architecture/blob/master/adr/0017-hardware-screening-os.md) and pass through an architecture design proposal[cite: 3].

For documentation explaining details of the individual supported boards, see [Board support](https://developers.home-assistant.io/docs/operating-system/boards/overview) section of the Home Assistant Developer Docs[cite: 3].

## Getting Started

If you just want to use Home Assistant the official [getting started guide](https://www.home-assistant.io/getting-started/) and [installation instructions](https://www.home-assistant.io/hassio/installation/) take you through how to download Home Assistant Operating System and get it running on your machine[cite: 3].

If you're interested in finding out more about Home Assistant Operating System and how it works read on...[cite: 3]

## Development

If you don't have experience with embedded systems, Buildroot or the build process for Linux distributions it is recommended to read up on these topics first (e.g. [Bootlin](https://bootlin.com/docs/) has excellent resources)[cite: 3].

The Home Assistant Operating System documentation can be found on the [Home Assistant Developer Docs website](https://developers.home-assistant.io/docs/operating-system)[cite: 3].

### Components

- **Bootloader:**[cite: 3]
  - [GRUB](https://www.gnu.org/software/grub/) for devices that support UEFI[cite: 3]
  - [U-Boot](https://www.denx.de/wiki/U-Boot) for devices that don't support UEFI[cite: 3]
- **Operating System:**[cite: 3]
  - [Buildroot](https://buildroot.org/) LTS Linux[cite: 3]
- **File Systems:**[cite: 3]
  - [SquashFS](https://www.kernel.org/doc/Documentation/filesystems/squashfs.txt) for read-only file systems (using LZ4 compression)[cite: 3]
  - [ZRAM](https://www.kernel.org/doc/Documentation/blockdev/zram.txt) for `/tmp`, `/var` and swap (using LZ4 compression)[cite: 3]
- **Container Platform:**[cite: 3]
  - [Docker Engine](https://docs.docker.com/engine/) for running Home Assistant components in containers[cite: 3]
- **Updates:**[cite: 3]
  - [RAUC](https://rauc.io/) for Over The Air (OTA) and USB updates[cite: 3]
- **Security:**[cite: 3]
  - [AppArmor](https://apparmor.net/) Linux kernel security module[cite: 3]

### Development builds

The Development build GitHub Action Workflow is a manually triggered workflow which creates Home Assistant OS development builds[cite: 3]. The development builds are available at [https://os-artifacts.home-assistant.io/index.html](https://os-artifacts.home-assistant.io/index.html)[cite: 3].

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

The Development build GitHub Action Workflow is a manually triggered workflow
which creates Home Assistant OS development builds. The development builds are
available at [https://os-artifacts.home-assistant.io/index.html](https://os-artifacts.home-assistant.io/index.html).
