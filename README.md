# Awesome-Cloud-Storage-Snapshot-Management

## Top Cloud Storage Snapshot Management Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Point-in-Time Copies, Snapshot Orchestration & Cyber-Resilient Recovery*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Cloud Storage Snapshot Management**. These tools help organizations create, schedule, retain, and restore point-in-time copies of storage volumes across on-premises arrays, cloud block storage, and hybrid environments—covering crash-consistent snapshots, application-consistent orchestration, and immutable recovery points for ransomware resilience.

**Examples** include NetApp Snapshot, AWS EBS Snapshots, Azure Backup Snapshots, Google Cloud Persistent Disk Snapshots, Druva, Veeam, Rubrik, Dell EMC Unity Snapshots, HPE Nimble Snapshots, Nutanix Prism, and Pure Storage FlashRecover (the category leaders).

**Open-source emphasis**: This section highlights every major active project for self-hosted snapshot-based backup, open-source volume management, and community-driven data protection—ideal for system administrators, platform engineers, and organizations seeking transparent, vendor-neutral snapshot orchestration without per-array licensing.

Contributions welcome! Open an PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-products)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

| Product | Description | Pricing (Starting Tier) | Free Tier / Trial Limits |
|---------|-------------|-------------------------|--------------------------|
| **[NetApp Snapshot](https://www.netapp.com/)** | Foundational snapshot technology built into ONTAP. Uses WAFL pointer manipulation to create space-efficient point-in-time copies. Cloud Volumes ONTAP (CVO) extends snapshot management to AWS, Azure, and GCP. | Cloud Volumes ONTAP PAYG starts at ~$0.062/TiB-hour ($45/TiB-month); on-prem ONTAP bundled with hardware/system licenses | Freemium tier free indefinitely up to 500 GiB; 30-day free trial on cloud marketplaces |
| **[AWS EBS Snapshots](https://aws.amazon.com/ebs/snapshots/)** | Incremental block-level snapshots of EBS volumes. Standard tier for regular access; Archive tier for long-term retention (90+ days). Data Lifecycle Manager (DLM) automates snapshot creation and retention at no additional fee. | Standard: $0.05/GB-month; Archive: $0.0125/GB-month | **AWS Free Tier**: 1 GB of EBS snapshot storage per month (12 months free for new accounts) |
| **[Azure Backup Snapshots](https://azure.microsoft.com/en-us/products/backup/)** | Instant disk snapshots integrated with Azure Backup for VMs and SAP HANA. Enhanced policy stores snapshots in Recovery Services Vault with immutability, soft delete, and cross-region restore. | Protected instance fee starts at $5/month (instances ≤ 50 GB) + snapshot storage at $0.05/GB-month (LRS) | **Azure Free Account**: $200 free credit valid for 30 days + 55+ services free for 12 months |
| **[Google Cloud Persistent Disk Snapshots](https://cloud.google.com/compute/docs/disks/create-snapshots)** | Incremental, compressed snapshots of Persistent Disk and Hyperdisk. Standard tier for active recovery; Archive tier for 90-day minimum long-term retention. Billed on actual compressed differential bytes. | Standard: ~$0.05/GiB-month; Archive: ~$0.019/GiB-month (plus $0.019/GiB retrieval fee) | **GCP Free Tier**: 5 GB-months of persistent disk snapshot storage per month (free forever in eligible US regions) |
| **[Druva](https://www.druva.com/)** | Fully hosted SaaS data protection with automated snapshot management across VMware, Hyper-V, Nutanix AHV, and AWS/Azure cloud workloads with air-gapped immutable backups. | AWS Marketplace / Phoenix Business tier starts at ~$450/TB annual commitment (~$37.50/TB-month after global deduplication) | 30-day full-featured free trial with cloud storage allocation |
| **[Veeam Backup & Replication](https://www.veeam.com/)** | Storage snapshot orchestration and backup across major arrays and cloud volumes. Backup from Storage Snapshots minimizes VM stun and IO impact. | Veeam Data Platform Essentials starts at $95/workload-year ($7.92/workload-month, sold in 5-instance packs) | **Community Edition**: 100% free forever for up to 10 workloads (VMs, cloud instances, or physical servers) |
| **[Rubrik Security Cloud](https://www.rubrik.com/)** | SLA-driven snapshot orchestration with immutable retention, automated ransomware quarantine, anomaly detection, and declarative policy management via Terraform. | Entry-level enterprise subscriptions start at ~$50,000/year (Foundation tier; median contracts ~$154,000/year for ~100 workloads/FETB) | 30-day proof-of-concept (PoC) free trial for SaaS workloads (e.g. M365/cloud data protection) |
| **[Dell EMC Unity Snapshots](https://www.dell.com/)** | Unified snapshots for NAS and SAN on Dell Unity and UnityVSA virtual arrays. Supports point-in-time read-only or read-write snapshots with automated expiration and replication. | UnityVSA Professional Edition subscription starts at ~$450 to $560/year for 10 TB capacity tier | **UnityVSA Community Edition**: 100% free forever up to 4 TB usable capacity (for lab/test/dev) |
| **[HPE Nimble Storage Snapshots](https://www.hpe.com/)** | Redirect-on-write volume snapshots and multi-volume consistency groups integrated into HPE GreenLake for Block Storage and OpenStack Cinder. | HPE Alletra / Nimble entry hardware/GreenLake subscriptions start at ~$25,000 to $30,000 for base configurations; GreenLake Block Storage starting at custom baseline reserve commits | 90-day free evaluation subscription for HPE GreenLake cloud-managed storage and data services |
| **[Nutanix Prism Snapshots](https://www.nutanix.com/)** | Granular VM and volume snapshots in Prism Central featuring Secure Snapshots (WORM immutability) and Approval Policies for protection against unauthorized deletion. | Nutanix Cloud Infrastructure (NCI) Starter edition starts at ~$330/core-year (or Pay-As-You-Go on NC2 cloud clusters at ~$0.10/core-hour) | **Nutanix Community Edition (CE)**: 100% free forever on non-production hardware; 30-day free trial on Nutanix Cloud Clusters (NC2) |
| **[Pure Storage FlashRecover](https://www.purestorage.com/)** | Joint all-flash snapshot and rapid DR solution (Pure FlashBlade/FlashArray + Cohesity DataProtect) with immutable SafeMode snapshots and sub-minute recovery points. | Pure FlashArray entry configurations start at ~$30,000 to $40,000 (hardware + 3-year support), or Evergreen//One storage-as-a-service starting at 50 TiB reserve commit | 30-day proof-of-concept (PoC) evaluation via Pure Storage and authorized channel partners |

## Open-Source GitHub Projects

| Project | Star Badge | Description |
|---------|------------|-------------|
| **[Restic](https://github.com/restic/restic)** | [![Stars](https://img.shields.io/github/stars/restic/restic?style=social&color=white)](https://github.com/restic/restic/stargazers) | Fast, secure, deduplicated backup tool with snapshot-based versioning. Supports S3, B2, Azure, GCS, SFTP, and local storage. Every snapshot is independently restorable; incremental runs only store changes . |
| **[Kopia](https://github.com/kopia/kopia)** | [![Stars](https://img.shields.io/github/stars/kopia/kopia?style=social&color=white)](https://github.com/kopia/kopia/stargazers) | Cross-platform backup tool with snapshot-based versioning, deduplication, and end-to-end encryption. Supports S3, B2, Azure Blob, GCS, WebDAV, and SFTP. Includes KopiaUI for scheduling and policy management . |
| **[BorgBackup](https://github.com/borgbackup/borg)** | [![Stars](https://img.shields.io/github/stars/borgbackup/borg?style=social&color=white)](https://github.com/borgbackup/borg/stargazers) | Deduplicating backup tool with point-in-time archive snapshots. Supports local, SSH, and cloud storage backends. Mature and battle-tested for Linux environments. |

### Additional Strong Open-Source Options

| Project | Star Badge | Description |
|---------|------------|-------------|
| **[Velero](https://github.com/vmware-tanzu/velero)** | [![Stars](https://img.shields.io/github/stars/vmware-tanzu/velero?style=social&color=white)](https://github.com/vmware-tanzu/velero/stargazers) | Kubernetes backup and restore with volume snapshot support. Integrates with cloud provider snapshot APIs (EBS, Azure Disk, GCE PD) for persistent volume protection. |
| **[K10 (Kasten)](https://github.com/kastenhq/k10)** | [![Stars](https://img.shields.io/github/stars/kastenhq/k10?style=social&color=white)](https://github.com/kastenhq/k10/stargazers) | Kubernetes-native backup with snapshot orchestration. Application-consistent snapshots via CSI volume snapshots and cloud provider integration. |

**Frameworks for building custom systems**: Combine **Restic** or **Kopia** for encrypted, snapshot-based backup to object storage, **Velero** for Kubernetes volume snapshot orchestration, and **BorgBackup** for legacy Linux workload protection—creating a fully self-hosted snapshot management stack without per-array licensing.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Snapshot management tools require broad access to storage APIs and volume metadata; enforce least-privilege IAM roles and audit snapshot deletion events.
- Snapshot pricing varies significantly by tier (Standard vs Archive) and retention duration; EBS Archive and GCP Archive offer substantial savings for infrequently accessed snapshots but add retrieval fees [citation:3][citation:5]. Self-hosted open-source tools require capacity planning and off-site replication to protect against primary storage loss.

---

**Made for system administrators, platform engineers, backup architects, and organizations building resilient storage infrastructure.**  
Let's make cloud storage snapshot management more open, automated, and cost-transparent.
