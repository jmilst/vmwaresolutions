---

copyright:

  years:  2016, 2020

lastupdated: "2019-02-10"

keywords: Zerto certificate, Zerto config, update Zerto replication

subcollection: vmware-solutions


---

{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Managing Zerto
{: #managingzertodr}

After the Zerto service is deployed into your instance, you can configure or update Zerto Virtual Replication, and deploy more Virtual Replication Appliances to newly added ESXi servers.

## Using your own certificate for Zerto
{: #managingzertodr-ssl-cert}

As a best practice, use your own SSL certificate for Zerto Virtual Manager. After you deployed Zerto, replace the SSL certificate for Zerto Virtual Manager with your own certificate. For more information, see the article [How to use a CER SSL Certificate to Replace the Self-Signed Certificate for Zerto Virtual Manager, ZSSP, or ZCM](https://www.zerto.com/myzerto/knowledge-base/how-to-use-a-cer-ssl-certificate-to-replace-the-self-signed-certificate-for-the-zvm-zssp-or-zcm/){:external}

## Managing the configuration of Zerto replications
{: #managingzertodr-manage}

To manage the configuration of Zerto replications, log in to the Zerto Virtual Replication console by using the vCenter credentials with administrator permissions. For example, re-pairing Zerto instances or configuring virtual protection groups to replicate virtual machines.

When you're replicating between different {{site.data.keyword.cloud_notm}} Zerto instances, you can configure replication directly between the Zerto instances. If you're replicating between the {{site.data.keyword.cloud_notm}} Zerto instance and your own data center, you must install Zerto yourself in your own data center. This instance can license itself automatically when you pair it with the {{site.data.keyword.cloud_notm}} Zerto instance.

Zerto replication doesn't support Network Address Translation (NAT) traversal. Establishing connectivity between the {{site.data.keyword.cloud_notm}} Zerto instance and your own data center might require customization of routes on the Zerto Virtual Manager appliances or Zerto Virtual Replication Appliances (VRAs) on either side. Establishing connectivity might also require secure tunneling between the sites. When you're configuring or reconfiguring routes on Zerto Virtual Manager appliances, you must ensure that all Zerto Virtual Manager appliances can connect successfully to `zerto.com` for usage reporting. You can verify this connection by opening a browser session to `https://www.zerto.com` from the Zerto Virtual Manager appliance.

The Management VMware NSX Edge Services Gateway (ESG) is preconfigured to allow outbound HTTPS (TCP port 443) communications that originate from Zerto Virtual Manager.
{:note}

## Updating Zerto Virtual Replication
{: #managingzertodr-update}

To update Zerto Virtual Replication, log in to the Zerto Virtual Replication console.

## Deploying VRAs to newly added ESXi servers
{: #managingzertodr-deploy}

When you add or remove ESXi servers for the primary cluster of your instance, VRAs are automatically deployed or removed. VRAs aren't automatically deployed to ESXi servers in the secondary clusters of your instance. You can deploy VRAs yourself from the Zerto Virtual Replication console.

## Related links
{: #managingzertodr-related}

* [Zerto overview](/docs/services/vmwaresolutions?topic=vmware-solutions-addingzertodr)
* [Managed Disaster Recovery Services](/docs/services/vmwaresolutions?topic=vmware-solutions-managing_zerto_services)
* [zerto.com website](https://www.zerto.com){:external}
* [Zerto technical documentation](https://www.zerto.com/myzerto/technical-documentation/){:external}
* [Zerto disaster recovery](https://www.ibm.com/cloud/architecture/architectures/virtualizationArchitecture/zerto){:external}
* [Explanation of Zerto Virtual Replication Alerts](https://www.zerto.com/myzerto/knowledge-base/explanation-of-zvr-alerts/){:external}
