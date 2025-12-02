# GDC Setup - Initial Server Setup

*Hands-On Lab: Building the second availability zone infrastructure*

---

## Lab Overview

This lab documents the initial setup of Dell PowerEdge servers at the Georgia Data Center (GDC) site, establishing the foundation for a distributed, fault-tolerant AI infrastructure.

---

## December 2024 Progress

**Current Status:** Building second availability zone

**Hardware:**
- 2x Dell PowerEdge servers
- Network connectivity to primary site via WireGuard VPN

**Objectives:**
1. RHEL 9 installation and base configuration
2. Network configuration for site-to-site connectivity
3. Storage preparation for OpenStack deployment
4. Security hardening and initial monitoring setup

---

## Lab Steps

### Phase 1: Base Installation
- [ ] RHEL 9 installation
- [ ] Initial network configuration
- [ ] User account setup
- [ ] SSH key-based authentication

### Phase 2: Network Configuration
- [ ] WireGuard VPN tunnel to primary site
- [ ] Internal network configuration
- [ ] Firewall rules configuration

### Phase 3: Storage Preparation
- [ ] Disk partitioning strategy
- [ ] LVM setup for flexibility
- [ ] Storage pools for OpenStack

### Phase 4: Security & Monitoring
- [ ] SELinux configuration
- [ ] Firewall hardening
- [ ] Basic monitoring (Prometheus node exporter)

---

## Real-World Context

This setup is part of building a distributed AI infrastructure across two sites:
- **Primary Site:** 3-node OpenShift cluster (operational)
- **Secondary Site (GDC):** OpenStack compute nodes (in progress)

The goal is fault-tolerant infrastructure for AI workloads supporting HBCU education.

---

## Detailed Documentation Coming Soon

Step-by-step procedures, configuration files, and troubleshooting notes will be added as the deployment progresses.

---

*Last Updated: December 2024*
