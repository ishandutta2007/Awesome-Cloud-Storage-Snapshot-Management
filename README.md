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

| Product | Description | Pricing (Starting) | Free Tier / Trial Limits |
|---------|-------------|-------------------|--------------------------|
| **[NetApp Snapshot](https://www.netapp.com/)** | Foundational snapshot technology built into ONTAP. Uses WAFL pointer manipulation to create read-only, space-efficient point-in-time copies with no performance impact. Supports up to 1,023 snapshots per volume; creation typically takes less than one second regardless of volume size . | Included with NetApp ONTAP systems (hardware/software licensing required) | No free tier; evaluation via NetApp sales |
| **[AWS EBS Snapshots](https://aws.amazon.com/ebs/snapshots/)** | Incremental block-level snapshots of EBS volumes. Standard tier for frequent access; Archive tier for long-term retention (90+ days) at significantly lower cost. Data Lifecycle Manager (DLM) automates snapshot creation and retention at no additional charge . | Standard: $0.05/GB-month; Archive: $0.0125/GB-month (up to 75% lower) [citation:3] | **AWS Free Tier**: limited snapshot storage for new accounts (varies by region) |
| **[Azure Backup Snapshots](https://azure.microsoft.com/en-us/products/backup/)** | Disk snapshots integrated into Azure Backup for VMs and SAP HANA. Managed disk snapshots combined with HANA snapshot commands for instant backup/restore. Enhanced policy (preview) stores snapshots in Recovery Services Vault with immutability and soft delete . | Snapshot storage billed per GB; Vault storage billed separately | **Azure Free Account**: $200 credit for 30 days |
| **[Google Cloud Persistent Disk Snapshots](https://cloud.google.com/compute/docs/disks/create-snapshots)** | Incremental, compressed snapshots of Persistent Disk and Hyperdisk. Standard tier for regular access; Archive tier for long-term retention with 90-day minimum. Billed on actual compressed snapshot size, not provisioned disk size . | Standard: ~$0.05/GiB-month; Archive: ~$0.019/GiB-month (plus retrieval fee) [citation:5] | **$300 free credits** for new Google Cloud customers (90 days) |
| **[Druva](https://www.druva.com/)** | SaaS data protection with snapshot management across VMware, Hyper-V, Nutanix AHV, and cloud workloads. Features incremental-forever backups, unlimited restore points, air-gapped immutable backups, and Threat Watch for scanning snapshots for indicators of compromise . | Quote-only (per TB/month after deduplication) | No free tier; trial via sales |
| **[Veeam Backup & Replication](https://www.veeam.com/)** | Snapshot orchestration across supported storage arrays. Backup from Storage Snapshots reduces production impact; Snapshot Orchestration creates periodic storage snapshots; restore from snapshots is up to 10x faster . | Quote-only (per-workload VUL licensing) | **Community Edition**: free for up to 10 workloads |
| **[Rubrik Security Cloud](https://www.rubrik.com/)** | SLA-driven snapshot management with immutable retention, anomaly detection, and orchestrated recovery. Terraform provider supports declarative snapshot policies with configurable frequency, retention, and replication targets . | Quote-only (enterprise contract) | No free tier; trial via sales |
| **[Dell EMC Unity Snapshots](https://www.dell.com/)** | Unified snapshots for NAS and SAN on Unity XT arrays. Included in UnityVSA Community Edition (free up to 4TB for test/dev). Professional Edition subscription adds support and higher capacity . | Community Edition: free (4TB, test/dev); Professional: subscription per capacity tier [citation:7] | **Community Edition**: free up to 4TB for test/dev environments |
| **[HPE Nimble Storage Snapshots](https://www.hpe.com/)** | Volume snapshots and consistency group snapshots integrated with OpenStack Cinder. Supports volume revert to snapshot, consistency group snapshots, and replication . | Included with Nimble/Alletra array licensing | No free tier; evaluation via HPE |
| **[Nutanix Prism Snapshots](https://www.nutanix.com/)** | VM snapshots via Prism Central with Secure Snapshots and Approval Policies for deletion protection. Requires policy engine (Calm/Self-Service) and NCM licensing for immutability features . | Included with NCI licensing; advanced features require NCM | No free tier; evaluation via Nutanix |
| **[Pure Storage FlashRecover](https://www.purestorage.com/)** | Integrated replication, snapshot, and policy management. Data reduction-aware snapshots and replication reduce bandwidth for DR. Protection Policies unify local and remote data protection management . | Included with Purity software on FlashArray systems | No free tier; evaluation via Pure Storage |

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
