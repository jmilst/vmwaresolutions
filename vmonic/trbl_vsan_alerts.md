---

copyright:

  years:  2016, 2019

lastupdated: "2019-12-12"

keywords: troubleshooting, SAN health, virtual SAN issue

subcollection: vmware-solutions


---

{:external: target="_blank" .external}

# Virtual SAN Health alerts and warnings
{: #trbl_vsan_alerts}

## Alerts and warnings on the VMware vSphere Web Client Monitor page
{: #trbl_vsan_alerts-problem}

You might see alerts and warnings that relate to Virtual SAN Health issues on the VMware vSphere Web Client Monitor page. These warnings are non-issues and do not indicate functional problems.

However, if you want to clear the warnings from the vSphere Web Client, use the following procedure.

1. Go to http://partnerweb.vmware.com/service/vsan/all.json and save the JSON file, with the name `all.json`, on your local system.
2. Ensure that you completed the steps in [vCenter console timeout](/docs/services/vmwaresolutions?topic=vmware-solutions-trbl_timeout_vc_console).
3. On the details page of the instance, click **vCenter console** and log in to the vSphere Web Client by using the credentials displayed on the {{site.data.keyword.vmwaresolutions_full}} console.
4. On the vSphere Web Client, go to **Manage > Settings** and open the **Virtual SAN > Health > HCL Database** section. Click **Update from file**, then upload the `all.json` file that you saved previously.
5. To clear the warnings, go to the **Alarms** pane on the upper right of the vSphere Web Client. Right-click each of the alarms and select **Reset to green**.

For more information, see [How to download offline vSAN HCL file for vSAN Health Check Plugin](https://www.virtuallyghetto.com/2015/05/how-to-download-offline-vsan-hcl-file-for-vsan-health-check-plugin.html){:external}.

## vSAN extended configuration in sync warning
{: #trbl_vsan_alerts-sync-warn}

On the vSAN health page, a vSAN extended configuration in sync warning might be displayed, with the recommendation to Host reboot. The warning is a non-issue and does not indicate functional problems. You can reboot to resolve the issue.
