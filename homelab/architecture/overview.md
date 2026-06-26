# Homelab Architecture Overview

## Purpose

This document provides a simple overview of the current homelab architecture. The environment is used for Linux administration, virtualization, networking, remote access, and infrastructure documentation practice.

## Core Components

| Component | Role |
| --- | --- |
| MacBook | Primary control system for administration, documentation, Git, browser access, and SSH sessions. |
| Airtel Router | Main home network gateway providing local network connectivity. |
| Proxmox Host | Virtualization host used to run Ubuntu Server virtual machines. |
| VM100 | Ubuntu Server virtual machine running on the Proxmox host. |
| VM101 | Ubuntu Server virtual machine running on the Proxmox host. |
| Lenovo Server | Bare metal Ubuntu Server system connected to the local network. |
| Tailscale | Secure private overlay network for remote access to lab systems. |
| SSH | Primary management method for accessing Linux servers and virtual machines. |

## Architecture Diagram

```text
                              Tailscale
                         Secure Remote Access
                                  |
                                  v
MacBook Control System ---- SSH / Web ---- Airtel Router
                                      |
                                      |---- Proxmox Host
                                      |        |
                                      |        |---- VM100 Ubuntu Server
                                      |        |
                                      |        |---- VM101 Ubuntu Server
                                      |
                                      |---- Lenovo Bare Metal Ubuntu Server
```

## Access Model

The MacBook is the primary administration endpoint. From the MacBook, lab systems are managed over SSH on the local network or through Tailscale when remote access is required.

The Airtel router provides the base local network. Proxmox hosts the virtualized Ubuntu Server workloads, while the Lenovo server runs Ubuntu Server directly on bare metal.
