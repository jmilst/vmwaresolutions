---

copyright:

  years:  2016, 2020

lastupdated: "2020-02-03"

keywords: F5 BIG-IP, F5 install, tech specs F5

subcollection: vmware-solutions


---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}

# F5 BIG-IP overview
{: #f5_considerations}

The F5 BIG-IP service (F5 BIG-IP® Virtual Edition) provides intelligent L4-L7 load balancing and traffic management services at a local and global scale, robust network and web application firewall protection, and secure and federated application access. You can install more than one instance of this service as needed.
{: shortdesc}

The current BIG-IP VE version that is installed is v15.1.
{:note}

## Technical specifications for F5 BIG-IP
{: #f5_considerations-specs}

The following components are included with the F5 BIG-IP service:

### Virtual machines
{: #f5_considerations-specs-vms}

* Two virtual machines (VMs) with all options available.
* 2, 4, or 8 vCPUs per VM depending on the licensing option.
* 4, 8, or 16 GB RAM per VM depending on the licensing option.

### Networking
{: #f5_considerations-specs-network}

* Private Virtual Extensible LAN (VXLAN) for High Availability (HA) synchronization.
* Access to Traffic Management Shell (TMSH) and Management Console through private management network.

### Licenses and fees
{: #f5_considerations-specs-license}

License fees for each VM are applied to each billing cycle depending on the licensing option (Good, Better, or Best) and the selected bandwidth.

You cannot change the licensing level after service installation. To change the licensing level, you must remove the existing service and reinstall the service using a different licensing option.
{:important}

## Considerations when you install F5 BIG-IP
{: #f5_considerations-install}

Before you install the F5 BIG-IP service, review the following considerations.

Based on the license model and bandwidth that you select, two BIG-IP VE VMs are deployed with the following configuration:

| Maximum Bandwidth | License Model: Good | License Model: Better | License Model: Best |
|:------------------|:--------------------|:----------------------|:--------------------|
| 25 Mbps           | 2 vCPU, 4 GB RAM    | 4 vCPU, 8 GB RAM      | 8 vCPU, 16 GB RAM   |
| 200 Mbps          | 2 vCPU, 4 GB RAM    | 4 vCPU, 8 GB RAM      | 8 vCPU, 16 GB RAM   |
| 1 Gbps            | 2 vCPU, 4 GB RAM    | 4 vCPU, 8 GB RAM      | 8 vCPU, 16 GB RAM   |
| 3 Gbps            | 8 vCPU, 16 GB RAM   | 8 vCPU, 16 GB RAM     | 8 vCPU, 16 GB RAM   |
| 5 Gbps            | 8 vCPU, 16 GB RAM   | 8 vCPU, 16 GB RAM     | 8 vCPU, 16 GB RAM   |
| 10 Gbps           | 8 vCPU, 16 GB RAM   | 8 vCPU, 16 GB RAM     | 8 vCPU, 16 GB RAM   |
{: caption="Table 1. CPU and RAM deployments for different bandwidth and license model selections" caption-side="top"}

### Additional considerations
{: #f5_considerations-additional}

* F5 BIG–IP limits the appliance throughput based on your chosen maximum bandwidth. Because network performance is affected by many factors, not all configurations and topologies may be able to achieve your chosen maximum bandwidth.
* The pair of BIG-IP VE VMs suitable for high availability (HA) configuration will be deployed only into the default cluster.

  In addition, 100% of CPU and RAM for the two BIG-IP VE VMs are also reserved because these VMs are in the data plane of the network communications and it is critical that resources are still available for them.

  To calculate the CPU and RAM reservation for a single BIG-IP VE VM, use the following formula:

  `CPU reservation = CPU speed of ESXi server * number of vCPUs` (from Table 1)

  `RAM reservation = RAM size` (from Table 1)

* {{site.data.keyword.vmwaresolutions_full}} does not preconfigure HA. For more information, see the AskF5 article [Creating an Active-Standby Configuration Using the Setup Utility](https://techdocs.f5.com/kb/en-us/products/big-ip_ltm/manuals/product/tmos-implementations-11-5-0/2.html){:external}.
* For information about the activities you should perform after you deploy F5 networks, see [Working with F5 Networks BigIP in IBM Cloud for VMware](https://developer.ibm.com/recipes/tutorials/working-with-f5-networks-bigip-in-ibm-cloud-for-vmware/){:external}.

### Planning considerations
{: #f5_considerations-planning}

You must meet the following requirements to avoid failures with F5 BIG-IP:
* At least two active ESXi servers are available for the two BIG-IP VE VMs to be deployed with the anti-affinity rule of keeping the VMs on separate servers.
* The two active ESXi servers have enough resources available so that one BIG-IP VE VM can be hosted on each ESXi server with 100% CPU and RAM reservation.
* VMware vSphere HA has enough resources to host two BIG-IP VMs with 100% CPU and RAM.

Due to these requirements, you must plan for the space that is needed for F5 BIG-IP. If needed, before you order F5 BIG-IP, add 1-2 ESXi servers to your instance, or reduce vSphere HA CPU reservation for failover, or both.

**Notes**:

* Before the service is installed in your environment, a check is performed against the available capacity of the default cluster in the environment to ensure that the service components can fit.
* If the capacity check fails, the service is not installed and the service state is set to **Capacity Validation Failed** on the console. In addition, a console message with more details is displayed and you are notified by email.
* To install the service, you must increase the capacity in your default cluster by either adding more hosts or by freeing up RAM, CPU, or disk space, and then add the service again in the console. After that, you can remove the existing service in the **Capacity Validation Failed** state by clicking the delete icon next to it.

## F5 BIG-IP order example
{: #f5_considerations-example}

You order a VMware vCenter Server **Small** instance with 2 ESXI servers with the following configuration: sixteen cores at 2.10 GHz each with 128 GB RAM. For F5 BIG-IP, you select the **Best** license model and a value of 5 Gbps for **Maximum Bandwidth**.

In this case, a single BIG-IP VM requires, on each server:
* 2.1 GHz * 8 vCPU = 16.8 GHz of CPU
* 16 GB RAM

In total, that is 33.6 GHz CPU and 32 GB RAM for two BIG-IP VMs.

Each ESXi server has a capacity of 16 cores * 2.1 GHz = 33.6 GHz, so we meet the first two requirements if both servers are active and there is at least 16.8 GHz of CPU and 16 GB RAM available on each server.

However, by default, vSphere HA reserves 50 percent of CPU and RAM for failover on vCenter Server instances that were initially deployed with 2 ESXi servers. For this example, the following is available:

`50% of 2 * 16 cores * 2.1 GHz = 33.6 GHz available`

Since there will be other workloads present on the ESXi servers, for example, VMware vCenter Server, VMware NSX Controller, VMware NSX Edge, using these resources we cannot satisfy the third requirement, because we need 33.6 GHz of CPU and 32 GB RAM for the two BIG-IP VMs.

In this case, the F5 BIG-IP installation might fail, unless at least one ESXi server is added to the environment and vShpere HA failover reservations are updated appropriately to ensure that there are enough resources for two BIG-IP VE VMs. If additional resources are needed to run the F5 BIG-IP service, you can add more ESXi servers before installing F5 BIG-IP.

## Considerations when you remove F5 BIG-IP
{: #f5_considerations-remove}

Before you remove the F5 BIG-IP service, ensure that the existing BIG-IP VE configuration is removed correctly. Specifically, network traffic must be routed around BIG-IP VE instead of through BIG-IP VE. Otherwise, the existing data traffic from your environment might be impacted.

## Related links
{: #f5_considerations-related}

* [Ordering F5 BIG-IP](/docs/services/vmwaresolutions?topic=vmware-solutions-f5_ordering)
* [Managing F5 BIG-IP](/docs/services/vmwaresolutions?topic=vmware-solutions-managing_f5)
* [Contacting IBM Support](/docs/services/vmwaresolutions?topic=vmware-solutions-trbl_support)
* [FAQ](/docs/services/vmwaresolutions?topic=vmware-solutions-faq)
* [F5 website](https://www.f5.com/){:external}
