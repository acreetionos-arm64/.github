# Welcome to AcreetionOS ARM64

We're porting AcreetionOS (a Cinnamon-focused Arch Linux distribution) to ARM64 architecture. This means getting it running on devices like Raspberry Pi 5, Pine64 boards, and other ARM-based hardware.

## What's This Project About?

If you've used Ubuntu, Fedora, or Arch Linux on your laptop or desktop, you know those typically run on x86_64 processors (Intel/AMD). We're adapting AcreetionOS to work on ARM64 processors instead - the chips that power Raspberry Pis, many single-board computers, and increasingly, even laptops and servers.

## How Is This Project Organized?

We use a **multi-repository structure** with Git submodules. Think of it like having separate workspaces for different parts of the project:

- **`iso-builder`** - Takes the archiso build system and converts it from x86_64 to ARM64
- **`custom-packages`** - Handles AcreetionOS-specific stuff (branding, installer configuration)
- **`arm64-toolchain`** - Cross-compilation tools (building ARM64 software on your x86_64 machine)
- **`hardware-support`** - Device-specific firmware and configurations
- **`boot-systems`** - Bootloader setup for ARM64 hardware
- **`package-builder`** - Scripts for compiling ARM64 packages
- **`testing-infrastructure`** - Automated testing and validation
- **`documentation`** - Technical guides and architecture documents
- **`upstream-sync`** - Coordination with the original AcreetionOS project
- **`releases`** - Where finished ISO files live

Each repository focuses on one thing. This keeps work organized and prevents confusion.

## I Want to Help - Where Do I Start?

Great! Here's how to get oriented:

### 1. Check the Project Board
Visit our [GitHub Project Board](https://github.com/orgs/acreetionos-arm64/projects/2) to see what's being worked on and what's available.

### 2. Understand Our Tracking System
We use something called **Work Breakdown Structure (WBS)** - just a fancy way of saying "organized numbering for tasks." Issues look like this:

- `M1.1.1` - Validate x86_64 build baseline
- `M1.2.1` - Setup ARM64 cross-compilation toolchain
- `M2.6.2` - Implement U-Boot configuration

Breaking it down:
- `M1` = Milestone 1 (Foundation & Infrastructure)
- `M2` = Milestone 2 (Core ARM64 Implementation)
- The middle number = which repository (1=iso-builder, 2=arm64-toolchain, etc.)
- The last number = specific task within that repository

### 3. Look for Issues Tagged for Contributors
We label issues with:
- **`good-first-issue`** - Approachable for newcomers
- **`documentation`** - Writing guides, improving clarity
- **`complexity:low`** - Straightforward tasks that don't require deep expertise

### 4. Don't Know Linux Development? That's OK
Start with:
- Documentation improvements (fixing typos, clarifying instructions)
- Testing on hardware you own (Raspberry Pi, etc.)
- Packaging and branding tasks
- Reporting bugs or confusing instructions

You'll learn as you go. That's part of the point.

## How Dependencies Work

Some tasks need others finished first. For example:
- You can't test ARM64 builds before you have cross-compilation tools set up
- You can't customize the installer before you have a bootable ISO

Check the issue's description for "**Dependencies**" - if it says `M1.1.1`, that means issue M1.1.1 needs completion first.

## Getting the Code

```bash
# Clone everything (this project uses Git submodules)
git clone --recursive https://github.com/acreetionos-arm64/workspace.git
cd workspace

# If you already cloned without --recursive, initialize submodules:
git submodule update --init --recursive
```

## Working on a Specific Part

```bash
# Navigate to the repository you want to work on
cd iso-builder

# Make your changes
# (edit files, test, commit locally)

# Push to your fork or create a pull request
```

When you're done, update the main workspace to reference your changes (we can help with this if it's confusing).

## What If I Get Stuck?

- **Open an issue** describing what you tried and where you got stuck
- **Ask questions in existing issues** - we'd rather clarify than have you spin your wheels
- **Check the documentation repository** for guides on specific topics

## Project Philosophy

This is a **learning project with no deadlines**. We're targeting 18-36 months for completion, but there's zero pressure. Work happens when people are motivated and have time.

**Quality over speed.** It's better to ask questions and do it right than rush and break things.

## What Skills Are Useful Here?

You don't need all of these - pick what matches your interests:

- **Linux basics** - command line, file systems, package management
- **ARM architecture** - understanding ARM64 hardware differences
- **Build systems** - archiso, makefiles, PKGBUILD files
- **Bootloaders** - U-Boot, UEFI for ARM
- **Cross-compilation** - building software for a different architecture
- **Testing/QA** - running builds in QEMU or on real hardware
- **Documentation** - explaining technical concepts clearly
- **Project management** - tracking issues, organizing workflows

## Key Resources

- **[Main Workspace README](https://github.com/acreetionos-arm64/workspace)** - Technical overview
- **[Project Board](https://github.com/orgs/acreetionos-arm64/projects/2)** - Current tasks and progress
- **[Development Roadmap](https://github.com/acreetionos-arm64/documentation/blob/main/ROADMAP.md)** - Complete milestone breakdown
- **[CONTRIBUTING.md](CONTRIBUTING.md)** - Contribution guidelines (if present)

## Current Status

**Milestone 1 (M1)** is ready to start. We have 16 foundation tasks to complete before moving to Milestone 2 (core ARM64 implementation with 13 tasks).

Right now, the immediate next steps are:
1. Validating the x86_64 baseline build works (M1.1.1)
2. Setting up ARM64 cross-compilation tools (M1.2.1)
3. Researching ARM64 architecture specifics (M1.3.x tasks)

## Who's Behind This?

**Project Lead**: John Junkins ([@macjunkins](https://github.com/macjunkins))

This is an independent project that builds on the excellent work of the AcreetionOS team. We're doing this to learn, to expand hardware support, and to contribute back to the broader Arch Linux ARM ecosystem.

---

**Questions?** Open an issue or start a discussion. We're here to help you contribute successfully.
