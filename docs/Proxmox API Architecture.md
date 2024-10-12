# Proxmox Virtual Environment (PVE) API Architecture

Upon starting this project, I was interested in researching the underlying
architecture of Proxmox's API. Until this point, I was only familiar with
Proxmox through its web GUI and some broader automation tools, such as Packer,
Terraform, and Ansible. It was fascinating to see that the Proxmox API is
largely written via Perl.

## Proxmox User Manual Documentation

Proxmox's documentation provides an [API Viewer](https://pve.proxmox.com/pve-docs/api-viewer/index.html#/version) for exploring the various API
endpoints available.

The PVE API itself is comprised of multiple components:

- [PVE API Daemon](https://pve.proxmox.com/pve-docs/pvedaemon.8.html)
  - Internal API daemon
  - Listens on 127.0.0.1:85
  - Runs as root user

- [PVE API Proxy](https://pve.proxmox.com/pve-docs/pveproxy.8.html)

  - Daemon that externally exposes the PVE API
  - Initially has very limited permissions
  - Forwards requests to the PVE API Daemon
  - Listens on 0.0.0.0:8006 and [::]:8006 for TCP connections
  - Runs as www-data user

- [PVE Status Daemon](https://pve.proxmox.com/pve-docs/pvestatd.8.html)
  - Queries the status of VMs, storages, and containers
  - Sends results to all PVE Cluster nodes

- [PVE Scheduler Daemon](https://pve.proxmox.com/pve-docs/pvescheduler.8.html)
  - Manages scheduled jobs

- [PVE Shell
  Interface](https://pve.proxmox.com/pve-docs/pve-admin-guide.html#_shell_interface_for_the_proxmox_ve_api)
  - Provides a shell interface for the Proxmox API

## Source Code

[Proxmox's Git catalog](https://git.proxmox.com/) provides the source code for
the PVE API:

- [The perl API client library](https://git.proxmox.com/?p=pve-apiclient.git)

- [The Proxmox VE Management API and Web
  UI](https://git.proxmox.com/?p=pve-manager.git)

## 