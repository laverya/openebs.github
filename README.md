# openEBS

[![OpenEBS Social Banner](../../website/public/images/png/openebs_github_main_banner_HERO_1.png)](https://www.openebs.io/)

# [openebs.io](https://www.openebs.io/)
OpenEBS is a free openesource Stateful Persistent Data Storage platform for Kubernetes.<BR>
We are CNCF member project, with a large global community of K8s Datastorage users.<BR>
<BR>
Our project team was an early pioneering inventor of K8s Container Native Storage services. We concieved the vision of a K8s Stateful Persistent data platform that is tightly integrated and embeded natively into the core of K8s.<BR>
<BR>
We have designd and built an innovative ultra High-performance Enterprise grade Block-mode storage Hyper-converged Data Fabric that augments the core storage services of K8s with Stateful Persistence, Enterprise Data mgmt, SSD/NVMe optomized I/O services,
Replicated Data volumes, Thin Provisioning, Snapshot and Clones; and many other critical data storage services that don't come in K8s out-of-the-box.<BR>
<BR>
Building an Enterprise Data Storage platform is complex, and areas of the Data & I/O stack could be considerd 'Rocket science'. Our global team comes from many areas of the data storage industry and our project is sponsored by many innovative data storage companies within the industry, as well as many amazing individuals. Coding, contribuing, brainstorming ideas to the project are all welcome.<BR>
<BR>
<BR>
## Project structure
As a project, OpenEBS has kept up a steady pace of evolution in order to keep in alignment with K8s advancment overall and with the rapid changing pace of technologies, hardware and software innovations in the data stroage industry. The proejct is divided into 2 main areas:<BR>
| ID  | Edition name  |
|-----|---------------|
|  1  |  Legacy       |
|  2  |  Standard     |
<BR>

## LEGACY
LEGACY consists of a traditional Data-Engines that we experimented with early on. These Data-Engines have a number of opensoruce techologies embeded inside them, and are a great intro into the world of simple K8s storage services. LEGACY helped us learn, iterate and develop our core storage K8s strategy, as well as decern how users want & need to interact with K8s storage services. LEGACY also helped to reveal key areas where K8s is lacking in storage/datastore services and what areas of K8s we could optomize; and how we can provide the best value into the K8s storage layers.<BR>
<BR>
There are 3 main Data-Engines in LEGACY:<BR>
| ID  | Data-Eegines      | Embeded tech stack   | Status                           |
|-----|-------------------|----------------------|----------------------------------|
|  1  |  Jiva             | iSCSI                | We plan to sunset LEGACY in 2024 |
|  2  |  cStor            | Open ZFS             | We plan to sunset LEGACY in 2024 |
|  2  |  NFS Provisioner  | NFS userspace server | We plan to sunset LEGACY in 2024 |
<BR>

## STANDARD
**STANDARD** is our Ultra modern Datastore stack that is strongly aligned with the cutting edge direction of storage use-cases in the K8s industry. It is designed to faciliate modern K8s datastore archiectures, key K8s I/O patterns, K8s data access methods, K8s data use-cases and where K8s Datastore applications are heading.
* STANDARD is optomized for NVMe and SSD Flash and integrates ultra modern extremme high performance storage technologies at its core...
    * It uses the High performance [SPDK](https://spdk.io) storage stack - (SPDK is an opensource NVMe project initiated by INTEL)
    * The hyper modern [IO_Uring](https://github.com/axboe/liburing) Linux Kernel Async polling-mode I/O Interface - (fastest kernel I/O mode possible)
    * Native abilties for RDMA and Zero-Copy I/O
    * NVMe-oF TCP Block storage Hyper-converged data fabric
    * Block layer volume replication
    * Logical volumes and Diskpool based data managment
    * a Native high peformance Blobstore
    * Native Block layer Thin provisoning
    * Native Block layer Snapshtos and Clones
 <BR>	

There are 2 Data-Engines within the 'STANDARD' Edition:
| ID  | Data-Eegines       | Type of data services                                  |
|-----|--------------------|--------------------------------------------------------|
|  1  |  **Mayastor**      | Replicated data volumes (a Cluster wide Data fabric)   |
|     | &nbsp;             |                                                        |
|  2  |  **Local-PV**      | Non-replicated node local data volumes                 |
|     |  LVM Local-PV      | for tight integration with LVM datastor deployments    |
|     |  ZFS Local-PV      | for tight integration with ZFS datastor deployments    |
|     |  Local-PV-HostPath | for integration with local node hostpath (/mnt/fs1)    |
|     |  Device Local-PV   | for integration with explicit device paths (/dev/sdb)  |
|     |  Local-PV-Device   | for integration with NDM managed devices               |
|     |  RawFile-Device    | for integration with Soft Luns devices on a filesystem |

<BR>
Note: Our Roadmap plans to provide a new K8s Local-PV entity called Hyper-Local-PV.<BR>
This new innovative K8s volume type allows High performance Maystor block storage devices to be deployed and accessed as Local Non-replicated Local-PV's and inherrit all the Enterprise Data Mgmt capabilities of Maystor Replciaetd farbic voluems (while operating in non-replciated node local mode). Please see the roadmap for details.
