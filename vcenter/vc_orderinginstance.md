---

copyright:

  years:  2016, 2020

lastupdated: "2020-03-12"

keywords: vCenter Server order instance, order vCenter Server, order vCenter Server instance

subcollection: vmware-solutions


---

{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Ordering vCenter Server instances
{: #vc_orderinginstance}

To deploy a flexible and customizable VMware virtualized platform that best fits your workload needs, order a VMware vCenter Server instance.

For NSX-V, you can also add services, such as [Zerto](/docs/services/vmwaresolutions?topic=vmware-solutions-addingzertodr) for disaster recovery.

## Requirements for vCenter Server
{: #vc_orderinginstance-req}

Ensure that you completed the following tasks:
* You configured the {{site.data.keyword.cloud}} infrastructure credentials on the **Settings** page. For more information, see [Managing user accounts and settings](/docs/services/vmwaresolutions?topic=vmware-solutions-useraccount).
* You reviewed the information in [Requirements and planning for vCenter Server instances](/docs/services/vmwaresolutions?topic=vmware-solutions-vc_planning).
* You reviewed the instance and domain name format. The domain name and subdomain label are used to generate the user name and server names of the instance.

| Name        | Value Format |
|:------------|:------------ |
| Domain name | `<root_domain>` |  
| vCenter Server login user name | `<user_id>@<root_domain>` (Microsoft Active Directory user) or `administrator@vsphere.local` |
| vCenter Server (with embedded PSC) FQDN | `<instance_name>-vc.<root_domain>`. The maximum length is 50 characters. |
| Single Sign-On (SSO) site name | `<subdomain_label>` |
| Fully qualified ESXi server name | `<host_prefix><n>.<subdomain_label>.<root_domain>`, where `n` is the sequence of the ESXi server. The maximum length is 50 characters. |
{: caption="Table 1. Value format for instance and domain names" caption-side="top"}

Do not modify any values that are set during instance order or deployment. Doing so can make your instance unusable. For example, if public networking shuts down, if servers and Virtual Server Instances (VSIs) move behind a Vyatta mid-provision, or if the IBM CloudBuilder VSI stops or is deleted.
{:important}

## System settings
{: #vc_orderinginstance-sys-settings}

You must specify the following system settings when you order a vCenter Server instance.

### Instance configurations
{: #vc_orderinginstance-inst-config}

You can select **New Configuration** to specify settings for an instance and finally place the order or save the settings as a configuration template without placing an order.

You can also select a saved configuration template to further edit it, or to update it and then save it as a new configuration template.

### Instance name
{: #vc_orderinginstance-inst-name}

The instance name must meet the following requirements:
* Only lowercase alphabetic, numeric, and dash (-) characters are allowed.
* The instance name must start with a lowercase alphabetic character.
* The instance name must end with a lowercase alphabetic or numeric character.
* The maximum length of the instance name is 10 characters.
* The instance name must be unique within your account.

### Initial cluster name
{: #vc_orderinginstance-cluster-name}

The initial cluster name must meet the following requirements:
* Only lowercase alphabetic, numeric, and dash (-) characters are allowed.
* The cluster name must start with a lowercase alphabetic character.
* The cluster name must end with a lowercase alphabetic or numeric character.
* The maximum length of the cluster name is 30 characters.
* The cluster name must be unique within the vCenter Server instance.

### VMware vSphere version
{: #vc_orderinginstance-vsphere-license}

For NSX-V, select whether to order vSphere Enterprise Plus 6.7u2 or vSphere Enterprise Plus 6.5u3. 6.7u2 is available for only Skylake, Cascade Lake, and Broadwell {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}.

For NSX-T, only the vSphere Enterprise Plus 6.7u2 license is supported and it is selected by default.

### VMware NSX Network virtualization version
{: #vc_orderinginstance-nsx}

Select either **NSX-V** or **NSX-T**.

### Instance type
{: #vc_orderinginstance-primary-secondary}

Select whether to order a new primary instance or a secondary instance for an existing primary instance.

## Licensing settings
{: #vc_orderinginstance-licensing-settings}

### License options
{: #vc_orderinginstance-licensing-opt}

Specify the licensing options for the following VMware components in the instance:
* vCenter Server 6.5
* vSphere Enterprise Plus 6.5 (NSX-V only) or 6.7
* (NSX-V only) NSX Service Providers 6.4 (Base, Advanced, or Enterprise edition). The VMware HCX service requires either the NSX Advanced or NSX Enterprise edition license.
* (NSX-T only) NSX-T 2.5 (Base, Advanced, or Enterprise edition)

For Business Partner users, the vCenter Server license (Standard edition), the vSphere license (Enterprise Plus edition), and the NSX license are included and purchased on your behalf. However, you must specify the edition for the NSX license.

For users who are not Business Partners, you can use the IBM-provided VMware licenses for these components by selecting **Include with purchase**, or you can Bring Your Own License (BYOL) by selecting **I will provide** and entering your own license keys.

### Licensing notes
{: #vc_orderinginstance-licensing-notes}

* The minimum number of licenses for BYOL that are required depends on the number of CPUs per server and the number of servers in the order. The license choice for each VMware component applies to the base instance and to any ESXi servers that you add to the instance later. Ensure that your license supports future capacity expansion in your infrastructure.
* The minimum license editions are indicated on the user interface. If different component editions are supported, you can select the edition that you want. You are responsible to ensure that the license key provided is correct for each VMware component selected.
* For vSphere, a license charge is incurred at the time of order, but the license charge is then credited to your account.
* You can change any licenses that you provided by using the VMware vSphere Web Client after the instance deployment is completed.
* Support for the VMware components that you provide licenses is provided by VMware, not by IBM Support.

## Bare Metal Server settings
{: #vc_orderinginstance-bare-metal-settings}

Bare Metal settings are based on your data center selection and bare metal server configuration. When you size the capacity of your servers, consider your current requirements and include extra capacity to accommodate anticipated growth. For more information about sizing, see [Exporting VMware inventory](/docs/services/vmwaresolutions?topic=vmware-solutions-vmware-inventory-export).

For NSX-T, the Bare Metal Server settings must be specified for both the Management Cluster and the Workload Cluster.
{:note}

### Data Center Location
{: #vc_orderinginstance-dc-location}

Select the {{site.data.keyword.CloudDataCent_notm}} where the instance (for NSX-V) or the Management Cluster and the Workload Cluster (for NSX-T) are hosted.

### Skylake
{: #vc_orderinginstance-skylake}

When you select **Skylake**, you can choose the CPU and RAM combination for the Bare Metal Server according to your needs.

| CPU model | RAM options for NSX-V | RAM options for NSX-T |
|:--------- |:--------------------- |:--------------------- |
| Dual Intel Xeon Silver 4110 Processor / 16 cores total, 2.1 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB | 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 5120 Processor / 28 cores total, 2.2 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB | 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 6140 Processor / 36 cores total, 2.3 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB | 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
{: caption="Table 2. Options for Skylake {{site.data.keyword.baremetal_short}}" caption-side="top"}

### Cascade Lake
{: #vc_orderinginstance-cascade}

For the **Cascade Lake** setting, you have options for the **CPU Model** and **RAM**.

| CPU model | RAM options |
|:--------- |:----------- |
| Dual Intel Xeon Silver 4210 Processor / 20 cores total, 2.2 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 5218 Processor / 32 cores total, 2.3 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 6248 Processor / 40 cores total, 2.5 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Quad Intel Xeon Gold 6248 Processor[^vsphere] / 80 cores total, 2.5 GHz | 384 GB, 768 GB, 1.5 TB, 3 TB |
{: caption="Table 3. Options for Cascade Lake {{site.data.keyword.baremetal_short}}" caption-side="top"}
[^vsphere]: If you use vSAN storage, the 4-CPU Intel Cascade Lake server Quad Intel Xeon Gold 6248 does not currently support the High Performance Intel Optane option.

### SAP-certified
{: #vc_orderinginstance-sap}

When you select **SAP-certified**, you cannot alter the CPU or RAM settings.

Based on your requirements, select a Bare Metal Server configuration from the following table:

| CPU model | RAM options |
|:--------- |:----------- |
| Dual Intel Xeon Gold 5218 processor / 32 cores total, 2.3 GHz | 192 GB, 384 GB |
| Dual Intel Xeon Gold 6248 processor / 40 cores total, 2.5 GHz | 768 GB |
| Dual Intel Xeon Platinum 8280M processor / 56 cores total, 2.7 GHz | 1.5 TB, 3 TB |
| Dual Intel Xeon Gold 6140 processor / 36 cores total, 2.3 GHz | 192 GB, 384 GB, 768 GB |
| Dual Intel Xeon E5-2690 v4 processor / 28 cores total, 2.6 GHz | 512 GB |
| Quad Intel Xeon E7-8890 v4 processor / 96 cores total, 2.2 GHz | 1 TB, 2 TB, 4 TB |
{: caption="Table 4. Options for SAP-certified {{site.data.keyword.baremetal_short}}" caption-side="top"}

### Broadwell (NSX-V only)
{: #vc_orderinginstance-broadwell}

When you select **Broadwell**, you can choose the CPU and RAM combination for the Bare Metal Server according to your needs.

| CPU model | RAM options |
|:--------- |:----------- |
| Quad Intel Xeon E7-4820 v4 / 40 cores total, 2.0 GHz | 128 GB, 256 GB, 512 GB, 1 TB, 2 TB, 3 TB |
| Quad Intel Xeon E7-4850 v4 / 64 cores total, 2.1 GHz | 128 GB, 256 GB, 512 GB, 1 TB, 2 TB, 3 TB |
{: caption="Table 5. Options for Broadwell {{site.data.keyword.baremetal_short}}" caption-side="top"}

### Number of Bare Metal Servers
{: #vc_orderinginstance-bare-metal-number}

* All servers that you order have the same configuration.
* If you are planning to use vSAN storage, you can order 4 - 20 servers.
* If you are planning to use NFS storage, you can order 2 - 20 servers. However, for production workloads, a minimum of three servers is recommended. For more information, see [Is a two-node vCenter Server instance highly available?](/docs/services/vmwaresolutions?topic=vmware-solutions-faq#is-a-two-node-vcenter-server-instance-highly-available-)

## Storage settings
{: #vc_orderinginstance-storage-settings}

Storage settings are based on your selection of Bare Metal Server configuration and the storage type.

For deployed instances, you can add NFS storage shares to an existing NFS or vSAN cluster. For more information, see [Adding NFS storage to vCenter Server instances](/docs/services/vmwaresolutions?topic=vmware-solutions-vc_addingremovingservers#section-adding-nfs-storage-to-vcenter-server-instances).

### vSAN storage
{: #vc_orderinginstance-vsan-storage}

vSAN is available for the **Skylake**, **Cascade Lake**, and **Broadwell** Bare Metal configurations only. **Broadwell** is supported for NSX-V only.

#### Disk Type and Size for vSAN Capacity Disks
{: #vc_orderinginstance-vsan-storage-typesize-capdisks}

Select an option for the capacity disks that you need.

#### Number of vSAN Capacity Disks
{: #vc_orderinginstance-vsan-storage-number-capdisks}

Specify the number of capacity disks that you want to add.

If you want to add capacity disks over the limit of 10, check the **High Performance Intel Optane** box. This option provides two extra capacity disk bays for a total of 12 capacity disks and is useful for workloads that require less latency and higher IOPS throughput.

The **High Performance Intel Optane** option is available only for the Skylake and Cascade Lake CPU models. Currently, the 4-CPU Intel Cascade Lake server Quad Intel Xeon Gold 6248 is not supported for this option.
{:note}

#### Disk Size for vSAN Cache Disks
{: #vc_orderinginstance-vsan-storage-size-cachedisks}

Review the **Disk Size for vSAN Cache Disks** value. The value depends on whether you checked the **High Performance Intel Optane** box.

#### Number of vSAN Cache Disks
{: #vc_orderinginstance-vsan-storage-number-cachedisks}

Review the **Number of vSAN Cache Disks** value. The value depends on whether you checked the **High Performance Intel Optane** box.

#### Enable vSAN compression and deduplication
{: #vc_orderinginstance-vsan-storage-enable-comp}

vSAN storage depends on the number of servers and your total disk capacity.

If vSAN compression and deduplication is enabled (the default setting), a ratio of 3.5 is assumed. For example, 1 TB of data uses only 1/3.5 TB. Therefore, the **Total Estimated Usable Storage** is greater than the **Total Raw Storage**.

The following table shows the values for **Total Raw Storage** and **Total Estimated Usable Storage** when you enable vSAN compression and deduplication and when you do not enable it.

| Selected values | If compression is enabled | If compression is not enabled |
|:---------------------|:-------------------------|:-----------------------------|
| Number of Bare Metal Servers: 4</br>Disk Type and Size for vSAN Capacity Disks: 1.9 TB SSD SED</br>Number of vSAN Cache Disks: 4 | Total Raw Storage: 30.40 TB</br>Total Estimated Usable Storage: 55.52 TB | Total Raw Storage: 30.40 TB</br>Total Estimated Usable Storage: 15.52 TB |
{: caption="Table 6. vSAN Storage values if vSAN compression and deduplication is enabled and not enabled" caption-side="top"}

#### vSAN License
{: #vc_orderinginstance-vsan-storage-license}

Use the IBM-provided VMware license for the vSAN component by selecting **Include with purchase**, or Bring Your Own License (BYOL) by selecting **I will provide** and entering your own license key.

If your initial cluster was a vSAN cluster, any additional vSAN clusters use the same vSAN license and have the same configuration as the initial one. This is also true if any cluster in the instance has vSAN chosen to be deployed on it (initial or additional). The first time you're prompted for the vSAN license (BYOL or purchased) and the edition. The next time that you select vSAN for a new cluster, the license that is chosen initially is reused.

### NFS storage
{: #vc_orderinginstance-nfs-storage}

When you select **NFS Storage**, you can add file-level shared storage for your instance where all shares use the same settings or you can specify different configuration settings for each file share. The number of file shares must be in the range of 1 to 32.

Specify the following NFS options:
* **Configure shares individually**: Select to specify different configuration settings for each file share.
* **Number of Shares**: When you use the same configuration setting for each file share, specify the number of file shares for the NFS shared storage that you want to add.
* **Size (GB)**: Select the capacity that meets your shared storage needs.
* **Performance**: Select the IOPS (input/output operations per second) per GB based on your workload requirements.
* **Add Shared Storage**: Select to add individual file shares that use different configuration settings.

Choose performance level options according to your needs.

| Option        | Details       |
|:------------- |:------------- |
| 0.25 IOPS/GB | This option is designed for workloads that are not used often. Example applications include: vaulted data, hosting large databases with legacy data, or virtual disk images of virtual memory system as backup. |
| 2 IOPS/GB | This option is designed for most general-purpose workloads. Example applications include: hosting small databases, backing up web applications, or virtual machine disk images for a hypervisor. |
| 4 IOPS/GB | This option is designed for higher-intensity workloads that have a high percentage of active data at a time. Example applications include: transactional databases. |
| 10 IOPS/GB | This option is designed for the most demanding workload types, such as analytics. Example applications include: high-transaction databases and other performance-sensitive databases. This performance level is limited to a maximum capacity of 4 TB per file share. |
{: caption="Table 7. NFS performance level options" caption-side="top"}

### Local Disks (NSX-V SAP-certified only)
{: #vc_orderinginstance-local-disks}

The local disks option is available for the **SAP-certified** Quad Intel Xeon E7-8890 v4 processor Bare Metal configuration only.

Specify the following options:
* **Local Disk Count**: Select the number of disks that you want to add.
* **Local Disk type**: Select an option for the disk type that you need.

## Network interface settings
{: #vc_orderinginstance-network-interface-settings}

You must specify the following network interface settings when you order a vCenter Server instance.

### Host name prefix
{: #vc_orderinginstance-host-name-prefix}

The host name prefix must meet the following requirements:
* Only lowercase alphabetic, numeric, and dash (-) characters are allowed.
* The host name prefix must start with a lowercase alphabetic character.
* The host name prefix must end with a lowercase alphabetic or numeric character.
* The maximum length of the host name prefix is 10 characters.

### Subdomain label
{: #vc_orderinginstance-subdomain-label}

The subdomain label must meet the following requirements:
* Only lowercase alphabetic, numeric, and dash (-) characters are allowed.
* The subdomain label must start with a lowercase alphabetic character.
* The subdomain label must end with a lowercase alphabetic or numeric character.
* The maximum length of the subdomain label is 10 characters.
* The subdomain label must be unique within all instances in your multi-site configuration.

### Domain name
{: #vc_orderinginstance-domain-name}

The root domain name must meet the following requirements:
* The domain name must consist of two or more strings that are separated by period (.)
* The first string must start with a lowercase alphabetic character.
* The first string must end with a lowercase alphabetic or numeric character.
* All strings, except for the last one, can contain only lowercase alphabetic, numeric, and dash (-) characters.
* The last string can contain only lowercase alphabetic characters.
* The length of the last string must be in the range 2 - 24 characters.

The maximum length of the Fully Qualified Domain Name (FQDN) for hosts and VMs is 50 characters. Domain names must accommodate for this maximum length.
{:note}

### Enable private NICs only
{: #vc_orderinginstance-public-private-network}

Network interface card (NIC) enablement settings are based on your selection of **Public and Private Network** or **Private Network Only**.

**(NSX-V only)** If you select the **Private Network Only** option:
* VMware NSX Edge Services Gateways (ESG) are not provisioned (neither the management services ESG nor the customer-managed ESG).
* The following add-on services, which require public NICs, are not available:
  * F5 BIG-IP
  * Fortigate Virtual Appliance

### VLANs
{: #vc_orderinginstance-vlans}

Network settings are based on your selection of **Order New VLANs** or **Select Existing VLANs**.

One public VLAN and two private VLANs are required for your instance order. The two private VLANs are trunked into each Bare Metal Server.

#### Order New VLANs
{: #vc_orderinginstance-new-vlans}

Select to order one new public VLAN and two new private VLANs.

#### Select Existing VLANs
{: #vc_orderinginstance-existing-vlans}

Depending on the {{site.data.keyword.CloudDataCent_notm}} that you selected, existing public and private VLANs might be available.

When you select to reuse existing public and private VLANs, specify the VLANs and subnets:
* **Public VLAN** is for public network access. If you select the **Allocate a new one** option for this field, a new public VLAN is allocated automatically. This field is only available on the **Public and Private Network** tab.
* **Public Primary Subnet** is assigned to physical hosts for public network access. If you select the **Allocate a new one** option for this field, a new public primary subnet is allocated automatically. This field is only available on the **Public and Private Network** tab.
* **Private VLAN** is for connectivity among the data centers and services within the {{site.data.keyword.cloud_notm}}. If you select the **Allocate a new one** option for this field, a new private VLAN is allocated automatically.
* **Private Primary Subnet** is assigned to physical hosts for management traffic. If you select the **Allocate a new one** option for this field, a new private primary subnet is allocated automatically.
* **Secondary Private VLAN** is for VMware features such as vSAN. You can select an existing secondary private VLAN or select to allocate a new one.

Ensure that the firewall configuration on the selected VLANs does not block the management data traffic. Also, ensure that all the VLANs that you select are in the same pod. ESXi servers cannot be provisioned on mixed-pod VLANs.
{:important}

### DNS configuration
{: #vc_orderinginstance-dns-config}

Select the Domain Name System (DNS) configuration for your instance:

* **Single Public Windows VSI for Active Directory/DNS**: A single Microsoft Windows Server VSI for Microsoft Active Directory (AD), which functions as the DNS for the instance where the hosts and VMs are registered, is deployed and can be looked up. This option has been deployed by default for V1.9 and later instances.
* **Two highly available dedicated Windows Server VMs on the management cluster**: Two Microsoft Windows VMs are deployed, helping enhance security and robustness.

You must provide two Microsoft Windows Server 2016 Standard edition licenses if you configure your instance to use the two Microsoft Windows VMs.
{:important}

Each license can be assigned only to one single physical server and covers up to two physical processors. One Standard edition license can run two virtualized Microsoft Windows VMs per 2-processor server. Therefore, two licenses are required since two Microsoft Windows VMs are deployed in two different hosts.

You have 30 days to activate the VMs.

For more information on ordering Windows Server 2016 licenses, see [Get started with Windows Server 2016](https://docs.microsoft.com/en-us/windows-server/get-started/server-basics){:external}.

## Services settings (NSX-V only)
{: #vc_orderinginstance-addon-services}

When you order a vCenter Server with NSX-V instance, you can also order add-on services. For more information about the services, see [Available services for vCenter Server instances](/docs/services/vmwaresolutions?topic=vmware-solutions-vc_addingremovingservices#available-services-for-vcenter-server-instances).

A 12-month commitment is required when you order the VMware HCX service.
{:note}

## Summary
{: #vc_orderinginstance-order-summary}

Based on your selected configuration for the instance and add-on services, the estimated cost is instantly generated and displayed in the **Summary** right pane. Click **Pricing details** to generate a PDF document with the cost summary for the {{site.data.keyword.vmwaresolutions_short}} resources.

You can also add the provisioned resources to the {{site.data.keyword.cloud_notm}} estimate tool, by clicking **Add to estimate**. This is useful if you want to estimate the cost of the selected {{site.data.keyword.vmwaresolutions_short}} resources together with other {{site.data.keyword.cloud_notm}} resources that you might consider to purchase.

## Procedure to order vCenter Server instances
{: #vc_orderinginstance-procedure}

For information about deploying Multi Zone Stretched Clusters, see [Ordering multi-zone stretched clusters](/docs/services/vmwaresolutions?topic=vmware-solutions-mcv_ordering).
{:note}

1. In the {{site.data.keyword.vmwaresolutions_short}} console, click **Overview** from the left navigation pane.
2. In the **Start Provisioning** section, click the **VMware Solutions Dedicated** card.
3. On the **VMware Solutions Dedicated** page, click the **vCenter Server** card. Ensure that you are on the **Single Zone Cluster** tab.
4. If you want to create a new configuration, select **New Configuration**. If you want to update a saved configuration or create a new configuration based on a saved one, select a saved configuration.
5. Enter the instance name and then enter the initial cluster name.
6. Select the vSphere version. For NSX-T, only vSphere 6.7u2 is supported.
7. Select either **NSX-V** or **NSX-T** as the VMware NSX Networking solution.
8. Select the instance type:
   * Click **Primary Instance** to deploy a single instance in the environment or to deploy the first instance in a multi-site topology.
   * Click **Secondary Instance** to connect the instance with an existing (primary) instance in the environment for high availability. Select the primary instance that you want the secondary instance to be connected with, then enter the vCenter Server Administrator password for the primary instance.
9. Complete the license settings for the instance components.
    * To use IBM-provided licenses, ensure that the **Include with purchase** option is selected. For NSX, specify the license edition.
    * To use your own licenses, for each license, click **I will provide** and enter the license key.
10. Complete the Bare Metal Server settings for your instance.

   For NSX-T, complete steps 10 - 12 for both the Management Cluster and the Workload Cluster.
   {:note}

    1. Select the {{site.data.keyword.CloudDataCent_notm}} to host the instance or cluster.
    2. Select the Bare Metal Server configuration.
       * For **Skylake**, **Cascade Lake**, or **Broadwell** (NSX-V only), specify the CPU model and the RAM size.
       * For **SAP-certified**, choose one of the preset configurations.
    3. Specify the number of {{site.data.keyword.baremetal_short}}. If you're planning to use vSAN storage, a minimum of four {{site.data.keyword.baremetal_short}} are needed.
11. Complete the storage configuration.
  * If you select **vSAN Storage**, specify the following values:
    * Disk type and size for the vSAN capacity disks
    * Number of vSAN capacity disks
    * Disk size for vSAN cache disks
    * Number of vSAN cache disks
    * vSAN License edition

    If you want more storage, check the **High Performance Intel Optane** box.

    By default, the **Enable vSAN compression and deduplication** box is checked. If you don't want to enable vSAN compression and deduplication, clear the check box.

  * If you select **NFS Storage** and want to add and configure the same settings to all file shares, specify the **Number of Shares**, **Performance**, and **Size (GB)**.
  * If you select **NFS Storage** and want to add and configure file shares individually, select **Configure shares individually**. Then, click the **+** icon next to the **Add Shared Storage** label and select the **Performance** and **Size (GB)** for each file share. You must select at least one file share.
  * **(NSX-V SAP-certified only)** If you select **Local Disks**, specify the local disk count and local disk type.
12. Complete the network interface settings.
   1. Enter the host name prefix for the instance being provisioned, the subdomain label, and the root domain name. For a secondary instance, the domain name is automatically completed.
   2. Select the network setting of either **Public and Private Network** or **Private Network Only**.
   3. Select the VLAN settings:
      * If you want to order new public and private VLANs, click **Order New VLANs**.
      * If you want to reuse the existing public and private VLANs when they are available, click **Select Existing VLANs** and specify the VLANs and the subnets.
   4. Specify the DNS configuration.

13. **(NSX-V only)** Select the add-on services to deploy into the instance by clicking the corresponding service card. If a service requires configuration, complete the service-specific settings and click **Add Service** on the card. For more information about how to provide settings for a service, see the corresponding service ordering topic.

14. On the **Summary** pane, review the instance settings and the estimated cost.
   * To save the settings as a new configuration template without placing an order, click **Save Configuration**, enter a name for the configuration, and then click **Continue**.
   * To save the updates to a saved configuration, click **Save Configuration**, select **Modify current configuration**, and then click **Continue**.
   * To save the updates to a saved configuration as another configuration, click **Save Configuration**, select **Create new configuration**, enter a new name for the configuration, and then click **Continue**.
   * To place the order, ensure that the account to be charged is correct, review and accept the terms, and then click **Create**.

### Results if you saved a configuration
{: #vc_orderinginstance-results-config}

You get a console notification that the configuration is saved successfully, and then you can find the template in the **Instance Configurations** drop-down list. Next, you can manage the configuration template by viewing or deleting it in the **Instance Configurations** drop-down list.

### Results if you placed an order
{: #vc_orderinginstance-results-order}

The deployment of the instance starts automatically and you receive confirmation that the order is being processed. You can check the deployment status, including any issues that might require your attention, by viewing the **Deployment History** section of the instance details.

When the instance is successfully deployed, the components that are described in [Technical specifications for vCenter Server instances](/docs/services/vmwaresolutions?topic=vmware-solutions-vc_vcenterserveroverview#specs) are installed on your VMware virtual platform. If you ordered add-on services, the deployment of the services starts after your order is completed.

When the instance is ready to use, the status of the instance is changed to **Ready to Use** and you receive a notification by email.

When you order a secondary instance, the VMware vSphere Web Client for the primary instance (linked to the secondary one) might be restarted after your secondary instance order is completed.

Next, you can view and manage the vCenter Server instance that you ordered.

You must manage the {{site.data.keyword.vmwaresolutions_short}} components that are created in your {{site.data.keyword.cloud_notm}} account only from the {{site.data.keyword.vmwaresolutions_short}} console, not the	{{site.data.keyword.slportal}}, or any other means outside of the console.
If you change these components outside of the {{site.data.keyword.vmwaresolutions_short}} console, the changes are not synchronized with the console.
{:important}

**CAUTION:** Managing any {{site.data.keyword.vmwaresolutions_short}} components (which were installed into your {{site.data.keyword.cloud_notm}} account	 when you ordered the instance) from outside the {{site.data.keyword.vmwaresolutions_short}} console can make your environment unstable. These management activities include:
*  Adding, modifying, returning, or removing components
*  Expanding or contracting instance capacity through adding or removing ESXi servers
*  Powering off components
*  Restarting services

   Exceptions to these activities include managing the shared storage file shares from the 	{{site.data.keyword.slportal}}. Such activities include: ordering, deleting (which might impact data stores if mounted), authorizing, and mounting shared storage file shares.

## Related links
{: #vc_orderinginstance-related}

* [Signing up for an {{site.data.keyword.cloud_notm}} account](/docs/services/vmwaresolutions?topic=vmware-solutions-signing_required_accounts#signing_required_accounts￼-cloud)
* [Adding, viewing, and deleting clusters for vCenter Server instances](/docs/services/vmwaresolutions?topic=vmware-solutions-vc_addingviewingclusters#vc_addingviewingclusters)
* [Expanding and contracting capacity for vCenter Server instances](/docs/services/vmwaresolutions?topic=vmware-solutions-vc_addingremovingservers)
* [Deleting vCenter Server instances](/docs/services/vmwaresolutions?topic=vmware-solutions-vc_deletinginstance)
