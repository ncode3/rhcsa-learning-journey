# RHCSA Learning Journey

*Certification prep meets production infrastructure — documenting the path to Red Hat Certified System Administrator.*

## About This Journey

This isn't just exam prep. It's hands-on learning through building real infrastructure:

- **Building:** Distributed data center with OpenShift, OpenStack, and KVM
- **Learning:** RHCSA fundamentals through production deployments
- **Teaching:** Creating curriculum for HBCU students

Every concept here has been applied to real systems at the [Atlanta AI & Robotics Initiative](https://atlanta-robotics.org).

---

## Current Progress

### December 2025: Building Second Availability Zone

**This Week's Focus:**
- Site-to-site VPN configuration (WireGuard)
- OpenStack deployment on secondary site
- Multi-site OpenShift architecture planning

**Infrastructure Context:**
- Primary site: 3-node OpenShift cluster (operational)
- Secondary site: 2 Dell PowerEdge servers (building now)
- Goal: Distributed, fault-tolerant AI infrastructure

---

## Real-World Application: SAMMO Fight IQ

**Production AI deployment demonstrating RHCSA skills in action.**

SAMMO Fight IQ is an AI-powered boxing coach analyzing sparring footage using computer vision (MediaPipe) and providing personalized coaching feedback.

**Why This Tests RHCSA Skills:**

Every RHCSA exam objective was applied deploying this production application:

| RHCSA Objective | SAMMO Fight IQ Application |
|-----------------|----------------------------|
| Understand and use essential tools | Debugged container logs with journalctl, grep, awk |
| Operate running systems | Managed OpenShift nodes, maintained uptime during reboots |
| Configure local storage | Created LVMs for container registry, configured PVCs for video storage |
| Create and configure file systems | Set up NFS exports for persistent storage across nodes |
| Deploy, configure, and maintain systems | Deployed multi-container app, automated updates |
| Manage users and groups | Created service accounts, configured RBAC for deployments |
| Manage security | SELinux contexts for containers, firewall rules for ingress |
| Manage containers | Built images, deployed to OpenShift, managed pod lifecycle |

**Production Metrics:**
- **Frames Processed:** 14,895 (full sparring session analysis)
- **Infrastructure:** OpenShift on KVM/bare metal
- **Storage:** NFS persistent volumes (100GB)
- **Uptime:** 99.5%
- **Cost:** $0 cloud fees (vs $1,500/month AWS equivalent)

**The Learning Path:**

Traditional approach: "Read about LVM, do practice lab, move on"

My approach: "SAMMO container registry ran out of space at 2 AM. Extended LVM online without downtime while application kept running. Now I REALLY understand LVM."

Real failures. Real troubleshooting. Real skills.

---

## Learning Path

### Phase 1: Linux Fundamentals ✅
- [x] File system navigation and management
- [x] User and group administration
- [x] Permissions and ownership
- [x] Process management
- [x] Package management (dnf/yum)

### Phase 2: System Administration (Current)
- [x] Storage management (LVM, partitioning)
- [x] Network configuration
- [ ] Firewall configuration (firewalld)
- [ ] SELinux management
- [ ] Systemd services

### Phase 3: Virtualization & Containers
- [x] KVM hypervisor setup
- [ ] Virtual machine management
- [ ] Container basics (podman)
- [ ] OpenShift fundamentals

### Phase 4: Advanced Topics
- [ ] Ansible automation
- [ ] Shell scripting
- [ ] Troubleshooting
- [ ] Performance tuning

---

## Hands-On Labs

Real infrastructure work documented for learning:

### GDC Setup Series
- [Initial server setup](hands-on-labs/gdc-setup.md)
- [KVM hypervisor configuration](hands-on-labs/kvm-config.md)
- [Network architecture](hands-on-labs/network-setup.md)

### OpenStack Deployment
- [Controller node setup](hands-on-labs/openstack-controller.md)
- [Compute node configuration](hands-on-labs/openstack-compute.md)
- [Networking (Neutron)](hands-on-labs/openstack-networking.md)

### OpenShift on Bare Metal
- [Prerequisites and planning](hands-on-labs/openshift-prereqs.md)
- [Installation walkthrough](hands-on-labs/openshift-install.md)
- [Post-install configuration](hands-on-labs/openshift-config.md)

### SAMMO Fight IQ (Production Deployment)
**Status:** Live on Dave's GDC infrastructure
**Stack:** Python/FastAPI backend, React frontend, MediaPipe pose detection
**Infrastructure:** OpenShift on bare metal (KVM virtualization)
**Complexity Level:** Production-grade multi-container AI application
**Learning Value:** Every RHCSA objective tested in real deployment

[Full deployment guide](docs/sammo-deployment.md)

---

## Study Notes

### RHCSA Exam Objectives
- [Understand and use essential tools](notes/essential-tools.md)
- [Create simple shell scripts](notes/shell-scripting.md)
- [Operate running systems](notes/running-systems.md)
- [Configure local storage](notes/local-storage.md)
- [Create and configure file systems](notes/file-systems.md)
- [Deploy, configure, and maintain systems](notes/system-maintenance.md)
- [Manage basic networking](notes/networking.md)
- [Manage users and groups](notes/users-groups.md)
- [Manage security](notes/security.md)
- [Manage containers](notes/containers.md)

---

## The Context

### Why RHCSA?

Building production AI infrastructure requires solid Linux fundamentals. This certification provides:

- **Credibility:** Industry-recognized validation
- **Foundation:** Skills needed for OpenShift, OpenStack, and beyond
- **Teaching:** Ability to train HBCU students on enterprise Linux

### The Bigger Picture

This learning journey feeds into the [African AI Cloud](https://github.com/ncode3/african-ai-cloud) project:

- **Learn:** Master Linux administration
- **Build:** Deploy production infrastructure
- **Teach:** Train the next generation of engineers
- **Scale:** Replicate model across HBCUs and eventually Africa

---

## Resources

### Official Documentation
- [Red Hat RHCSA Exam Objectives](https://www.redhat.com/en/services/training/ex200-red-hat-certified-system-administrator-rhcsa-exam)
- [RHEL 9 Documentation](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/9)

### Books & Courses
- *RHCSA Red Hat Enterprise Linux 9* by Sander van Vugt
- Red Hat Learning Subscription

### Practice Environments
- Home lab (KVM on Dell PowerEdge)
- Red Hat Developer Subscription (free RHEL)

---

## Weekly Updates

Documenting progress every Friday:

| Week | Focus | Status |
|------|-------|--------|
| Dec 2, 2025 | Second AZ setup, WireGuard VPN | In Progress |
| Nov 25, 2025 | OpenStack planning | Complete |
| Nov 18, 2025 | Primary site optimization | Complete |

---

## Connect

- **Project:** [African AI Cloud](https://github.com/ncode3/african-ai-cloud)
- **Organization:** [Atlanta AI & Robotics Initiative](https://atlanta-robotics.org)
- **LinkedIn:** [Nolan Code](https://linkedin.com/in/nolanscode)

---

*"The expert in anything was once a beginner."* — Helen Hayes

Learning in public. Building for impact.

---

*Last Updated: December 2025*
