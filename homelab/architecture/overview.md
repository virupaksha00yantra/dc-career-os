# Home Lab Architecture Overview

## Purpose

This document explains the current architecture of my home lab used for learning data center operations, Linux administration, networking, virtualization, and infrastructure documentation.

## Current Setup

| Component | Description |
|----------|-------------|
| MacBook | Main control system used for SSH, documentation, GitHub, and administration |
| Proxmox Host | Main virtualization server |
| VM100 | Ubuntu Server virtual machine |
| VM101 | Ubuntu Server virtual machine |
| Lenovo Laptop | Bare metal Ubuntu Server |
| Airtel Router | Main home network gateway |
| Tailscale | Secure remote access network |

## Network Overview

```text
MacBook
   |
   | SSH / Git / Browser
   |
Airtel Router
   |
   |---------------- Proxmox Host
   |                    |
   |                    |--- VM100 Ubuntu Server
   |                    |
   |                    |--- VM101 Ubuntu Server
   |
   |---------------- Lenovo Ubuntu Server

Tailscale is used for secure remote access to lab systems.
