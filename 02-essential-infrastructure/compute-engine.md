# Compute Engine

- Infrastructure as a Service (IaaS)
- Offers predefined or custom virtual machine types. We can chose these:
    - vCPU (cores) and Memory (RAM)
    - Storage:
        - Zonal or regional persistent HDD or SSD
        - Local SSD
        - Cloud Storage
    - Networking
    - OS: Linux or Windows
- A vCPU is equal to 1 hardware hyper-thread. The CPU will affect the network throughput (2GBits/sec for each vCPU core - except for instances with 2 or 4 vCPU where we receive 10GBit/sec bandwidth)

## Accessing VMs

- The creator of the VM has full root access
- On Linux, the creator has SSH access. Access can be granted to other users
- On Windows, the creator use the cloud console to create an username and password. These can be used for Remote Desktop Access (RDP) connectivity

## Instance States

- States are as follows:
    - Provisioning
    - Staging: IP Addresses are acquired, system image is booted
    - Running: pre-configured startup scripts are running at the startup
    - Stopping: pre-configured shutdown scripts will run
    - Terminated
- The shutdown process of an instance is about 90 seconds. Shutdown scripts should run during this period

## Manage Updates for a Fleet of VMs

- With GCP we can easily manage patches of our instances
- We can use Patch Management to apply patches across a fleet of instances
- OS patch management service has 2 main components:
    - Patch compliance reporting
    - Patch deployment (patch jobs which apply patches)

## Charges for Stopped Instances

- When a VM is terminated, we do not pay for CPU and memory resources
- We are charged for attached disks a allocated IP addresses

## Compute Options

- When we create a VM we can set the following configurations:
    - Machine family: curated set of processor and HW configurations optimized for specific workloads
        - Machine series
            - Machine type: predefined or custom types (we specify the CPU and memory)
- They are 4 types of machine families:
    - General-purpose:
        - Best price-performance
        - Suited for day-to-day computing a low cost
        - Series: E2 (contains shared-core machine types as well), N2, N2D, N1 (balanced price/performance, N2 - intel, N2D - AMD), Tau T2D (AMD Epyc processors, best performance/cost for scale-out workloads)
    - Compute-optimized:
        - Best compute performance for the price
        - Series: C2 (ultra-high performance, for compute-intensive performance), C2D (suited for high-performance computing, has the highest cache per core)
    - Memory-optimized:
        - Ideal for workloads with high memory usage (4TB - 12TB)
        - Series: M1, M2 (lowest cost per memory usage)
    - Accelerator-optimized:
        - Ideal for workloads requiring GPU computing (CUDA)
        - Series: A2 (offers nVidia GPU computing)
- If none of these machines are perfect for our workloads, we can create custom machine types
- Custom machine types may cost more than choosing a predefined options

## Compute Engine Pricing

- GCP offers per-second billing with a minimum of 1 minute for compute instances
- Each vCPU and each GB of memory is billed separately
- Discounts (discount types cannot be combined):
    - Sustained used: automatic discounts for running specific instances resources for a longer period of time (up to 30% for entire month usage)
    - Committed use (1 - 3 year, up to 60% discount)
    - Preemtible VMs

## Compute Engine Roles

- To create Compute Engine resources in a project, users must be team members on the project or a specific resource and have appropriate permissions to perform specific tasks. Users can be associated with projects as follows:
    - Individual users
    - A Google group
    - A G Suite domain
    - A service account
- Once a user or set of users is added to a project, we can assign permissions by granting roles to the user or set of users
- Compute Engine predefined roles:
    - **Compute Engine Admin Users**: with this role have full control over Compute Engine instances
    - **Compute Engine Network Admin Users**: with this role can create, modify, and delete most networking resources, and it provides read-only access to firewall rules and SSL certifications. This role does not give the user permission to create or alter instances
    - **Compute Engine Security Admin Users**: with this role can create, modify, and delete SSL certificates and firewall rules
    - **Compute Engine Viewer Users**: with this role can get and list Compute Engine resources but cannot read data from those resources

## Preemptible VMs

- Instances, which we can create run at a lower cost (up to 80%)
- These VMs might be terminated at any time by Google cloud
- There is no charge if the instance is terminated in the first minute
- They can live at most 24 hours
- There is a 30 seconds termination warning, but there is no guarantee that the termination script will run successfully
- There are no live migrations and no automatic restarts for preemptible VMs
- We can create monitoring and load-balancers to start up preemptible instances

## Sole-tenant Nodes

- They are physical compute engine servers dedicated to host VM instances only for our VMs
- We can use sole-tenant nodes to keep our VMs physically separated from VMs in other projects, or to group your VMs together on the same host hardware
- Provides the ability to bring CPU-bound licenses to the cloud
- A Sole-tenant node is a physical Compute Engine server that is dedicated to hosting only your project's VMs
- The following types of workloads might benefit from using sole-tenant nodes:
    - Gaming workloads with performance requirements
    - Finance or healthcare workloads with security and compliance requirements
    - Windows workloads with licensing requirements
    - Machine learning, data processing, or image rendering workloads. For these workloads, consider reserving GPUs
    - Workloads requiring increased input/output operations per second (IOPS) and decreased latency, or workloads that use temporary storage in the form of caches, processing space, or low-value data. For these workloads, consider reserving local SSDs
- Node templates: 
    - Is a regional resource that defines the properties of each node in a node group
    - When we create a node group from a node template, the properties of the node template are immutably copied to each node in the node group

## Shielded VMs

- Offer verifiable integrity to VMs instances
- First offering in the Shielded Cloud initiative
- Offers virtual trusted platform module (vTPM)

## Confidential VMs

- Allow to encrypt data in use
- Encrypts data while it's being processed
- Confidential VMs are easy to use with no changes to code or performance compromises
- N2D Compute Engines VMs running on second generation AMD Epyc processors
- Provides high memory capacity, high throughput and supports parallel and compute heavy workloads

# Images

- When creating a VM, we can chose a boot disk image. These images contain:
    - Boot loader
    - Operating system
    - File system structure
    - Additional software
    - Other customizations
- We can select public or custom images
- We chose between Windows and Linux images. We can have premium images with additional cost
- Machine images: resource storing all configuration, metadata, permissions and data for one or more disks for a VM. Ideal resources for instance backups

## Disk Options

- Every VM comes with a single root persistent disk
- This image is bootable. It is durable, it can survive if the VM terminates
- There are different types of disks:
    - **Persistent disks**:
        - These are network storages appearing as block devices
        - They are attached to the VMs through the network interface
        - They are durable and bootable
        - We can create snapshots from them
        - Performance scales with size
        - They can be HDD (magnetic) or SSD options
        - They can be resized even when running an attached
        - They can be attached in read-only mode to multiple VMs
        - Zonal disks: efficient, reliable block storage
        - Regional disks: active-active replication across 2 zones in the same region
        - Disk types:
            - pd-standard (HDD)
            - pd-ssd
            - pd-balanced
            - pd-extreme (zonal only SSD)
        - By default compute engine encrypts all data persisted on disks
    - **Local SSD**:
        - They are physically attached to a VM
        - They are ephemeral
        - They offer very high IOPS number
        - We can attach at most 8 SSDs to one VM
        - Data on local SSDs can survive a restart but not a VM stop or a reset
    - **RAM disks**:
        - tmpfs
        - Faster than local disks, slower than RAM memory
        - They are very volatile, data is erased at stop or start
        - We can use persistent disks to back up RAM disk data
- Maximum persistent disks attachable to VMs:
    - Shared-core: max 16
    - Other: max 128

## Common Compute Engine Actions

- Metadata and scripts: 
    - Every instance stores data about itself on a metadata server
    - Example of metadata: external IP address
- Move an instance to a new zone:
    - We can move a VM even if it is terminated of it is a shielded VM
    - We can automate moving VMs if the move is inside a region
    - To move a VM we have to shutdown the VM, move it and restart it
    - If the VM is moved to another region, the following process should be applied:
        - Snapshot all persistent disks
        - Create new persistent disks in the destination zone and restore the snapshots
        - Assign static IP to the VM
        - Update references to VM
        - Delete the snapshots, original disks and the original VM
- Snapshots:
    - Stored in cloud storage, used to backup data and move VMs between regions
    - Snapshots can be used to transfer data between different disk types
    - Snapshots are **not available for local SSD**
    - Snapshots are incremental and automatically compressed
- Resize persistent disks:
    - Can be achieved even when a disk is attached to a running VM
    - We can increase disk size but not shrink it

## Instance Groups

- Instance groups are sets of VMs that are managed as a single entity
- Any gcloud or console command applied to an instance group is applied to all members of the instance group
- Google provides two types of instance groups: **managed** and **unmanaged**
- Managed Instance Groups:
    - Consist of groups of identical VMs
    - They are created using an instance template, which is a specification of a VM configuration, including machine type, boot disk image, zone, labels, and other properties of an instance
    - Managed instance groups can automatically scale the number of instances in a group and be used with load balancing
- Unmanaged groups should be used only when you need to work with different configurations within different VMs within the group
