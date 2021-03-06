---

copyright:

  years:  2020

lastupdated: "2020-01-30"

keywords: vmware compatibility, vsan compatibility, product compatibility

subcollection: vmware-solutions


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:note: .note}
{:important: .important}
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:table: .aria-labeledby="caption"}

# Product compatibility guide
{: #vmware-comp-guide}

Review the following tables for information about the products and versions that are supported in the current release of {{site.data.keyword.vmwaresolutions_full}}.

## Intel processors reference
{: #vmware-comp-guide-intel}

| CPU series | Cores/Threads | CPUID info | CPUIDs | IBM-supported releases | Link |
|:---------- |:------------- |:---------- |:------ |:---------------------- |:---- |
| Intel Xeon Gold 6200/5200 (Cascade Lake-SP) Series | 28c/56t | 6.55.6</br>6.55.7 | 0x00050656</br>0x00050657 | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3 | [VMware compatibility guide - CPU](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=cpu&productid=128&deviceCategory=cpu&details=1&cpu_series=128,129,130&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| Intel Xeon Silver 4200, Bronze 3200 (Cascade Lake-SP) Series | 28c/56t | 6.55.6</br>6.55.7 | 0x00050656</br>0x00050657 | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3 | [VMware compatibility guide - CPU](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=cpu&productid=130&deviceCategory=cpu&details=1&cpu_series=128,129,130&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| Intel Xeon Platinum 8200 (Cascade Lake-SP) Series | 28c/56t | 6.55.6</br>6.55.7 | 0x00050656</br>0x00050657 | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3 | [VMware compatibility guide - CPU](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=cpu&productid=129&deviceCategory=cpu&details=1&cpu_series=128,129,130&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| Intel Xeon Gold 6100/5100, Silver 4100, Bronze 3100 (Skylake-SP) Series | 28c/56t | 6.55.4 | 0x00050654 | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3, 6.5u2 | [VMware compatibility guide - CPU](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=cpu&productid=119&deviceCategory=cpu&details=1&cpu_series=119&page=1&display_interval=10&sortColumn=Partner&sortOrder=Aschttps://www.google.com/?gws_rd=ssl) |
| Intel Xeon E5-2600-v4 Series | 24c/48t | 6.4F | 0x000406F0 | ESXi 6.7u1, 6.7, 6.5u3, 6.5u2, 6.5u1, 6.5, 6.0 | [VMware compatibility guide - CPU](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=cpu&productid=111&deviceCategory=cpu&details=1&cpu_series=111&page=1&display_interval=10&sortColumn=Partner&sortOrder=Aschttps://www.google.com/?gws_rd=ssl) |
| Intel Xeon E7-8800/4800-v4 Series | 24c/48t | 6.4F | 0x000406F0 | ESXi 6.7u2, 6.7u1, 6.7, 6.5u2, 6.5u1, 6.5, 6.0 | [VMware compatibility guide - CPU](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=cpu&productid=116&deviceCategory=cpu&details=1&cpu_series=116&page=1&display_interval=10&sortColumn=Partner&sortOrder=Aschttps://www.google.com/?gws_rd=ssl) |
{: caption="Table 1. Intel processors reference" caption-side="top"}

## SuperMicro server reference
{: #vmware-comp-guide-supermicro-server}

| Server configuration | MOBO | CPU | RAID | NIC | TPM |
|:-------------------- |:---- |:--- |:---- |:--- |:--- |
| PIO-628U-TR4T+-ST031 (1U/2U)</br>SYS-6028U-TR4T+ | X10DRU-i+_R1.02b | E5-2600-v4</br>Intel® C612 chipset | (LSI) MegaRAID SAS 9361-8i | AOC-2UR6-i4XT</br>Intel X540-AT2 | AOM-TPM-9655V |
| PIO-648R-E1CR36L+-ST031 (4U)</br>SSG-6048R-E1CR36N | X10DRI-T4+</br>X10DRI-T4+_1.02 | E5-2600-v4</br>Intel® C612 chipset | (LSI) MegaRAID SAS 9361-8i | 4x Onboard X540 Quad port 10GBase-T Intel X540 | AOM-TPM-9655V |
| PIO-8048B-TRF4T-ST031 (4U)</br>SYS-8048B-TR4FT | X10QBI_R1.01A</br>X10QBi_R1.01B  – MEM1 | E7-8800/4800/2800-v2</br>Intel® C602J Chipset | (LSI) MegaRAID SAS 9361-8i | AOC-STG-i2T | Onboard |
| PIO-8048B-TRF4T-ST031 (4U)</br>SYS-8048B-TR4FT | X10QBi-MEM2 REV 1.21 | E7-8800/4800-v4</br>Intel® C602J Chipset | (LSI) MegaRAID SAS 9361-8i | AOC-STG-i2T | Onboard |
| PIO-6029U-E1CR4T-ST031 (2U)</br>SYS-6029U-E1CR4T | X11DPU+</br>X11DPU+_R1.10 | Intel Xeon Platinum 8100, Gold 6100/5100, Silver 4100, Bronze 3100 (Skylake-SP) Series, Intel Xeon Platinum 8200, Gold 6200/5200 (Cascade-Lake-SP) Series</br>Intel® C621 chipset | (LSI) MegaRAID SAS 9361-8i | AOC-2UR66-i4XTF (2U)</br>Intel XL710 | AOM-TPM-9671V |
| PIO-6019U-TN4R4T-ST031 (1U)</br>SYS-6019U-TN4R4T | X11DPU+</br>X11DPU+_R1.10 | Intel Xeon Platinum 8100, Gold 6100/5100, Silver 4100, Bronze 3100 (Skylake-SP) Series, Intel Xeon Platinum 8200, Gold 6200/5200 (Cascade-Lake-SP) Series</br>Intel® C621 chipset | (LSI) MegaRAID 9461-16i | AOC-UR-i4XTF (1U) Intel XL710 | AOM-TPM-9671V |
| SYS-2049U-TR4 | X11QPH+ R1.02 | Intel Xeon Platinum 8200/6200/5200 (Cascade Lake-SP) Series</br>Intel® C621 chipset | (LSI) MegaRAID 9461-16i | Intel X710-T4. Additional NICs X710-T4 may be installed in top RAID (secondary) slot | AOM-TPM-9671V |
{: caption="Table 2. SuperMicro server reference" caption-side="top"}

## Lenovo server reference
{: #vmware-comp-guide-lenovo-server}

| Server configuration | MOBO | CPU | RAID | NIC | TPM |
|:-------------------- |:---- |:--- |:---- |:--- |:--- |
| System x3550 M5 | Systemx3550-M5-V4 | E5-2600-v4</br>Intel C612 Chipset | LSI MegaRAID SAS 9361-8i | x2 Dual Port Intel X540-T2 10GbE | Onboard |
| System x3550 M5 | Systemx3550-M5-V4 | E5-2600-v4</br>Intel C612 Chipset | LSI MegaRAID SAS 9361-8i | x2 Dual Port Intel X540-T2 10GbE | Onboard |
{: caption="Table 3. Lenovo server reference" caption-side="top"}

## SuperMicro BIOS levels reference
{: #vmware-comp-guide-supermicro-bios}

| Server configuration | MOBO | CPU | IBM Cloud infrastructure BIOS level | SMC BIOS | IBM-supported releases | Link |
|:-------------------- |:---- |:--- |:----------------------------------- |:-------- |:---------------------- |:---- |
| PIO-628U-TR4T+-ST031 (1U/2U)</br>SYS-6028U-TR4T+ | X10DRU-i+_R1.02b</br>X10DRU-i+_R1.10 | E5-2600-v4</br>Intel® C612 chipset | 3.1 6-8-2018 | American Megatrends Inc. 3.1 (Boot Mode:Legacy BIOS) | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3, 6.5u2, 6.5u1, 6.5, 6.0 | [VMware compatibility guide - System](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=server&productid=42370&deviceCategory=server&details=1&partner=105&keyword=SYS-6028U-TR4T%20%20&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| PIO-648R-E1CR36L+-ST031 (4U)</br>SSG-6048R-E1CR36N | X10DRI-T4+</br>X10DRI-T4+_1.02 | E5-2600-v4</br>Intel® C612 chipset | 3.1 06-08-2018 | American Megatrends Inc. 3.1 (Boot Mode:Legacy BIOS) | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3, 6.5u2, 6.5u1, 6.5, 6.0 | [VMware compatibility guide - System](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=server&productid=46813&deviceCategory=server&details=1&keyword=SSG-6048R-E1CR36N&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| PIO-848B-TR4F4T-ST031 (4U)</br>SYS-8048B-TR4FT | X10QBi-MEM2 REV 1.21 | E7-8800/4800-v4</br>Intel® C602J Chipset | 3.1 06-12-2018 | American Megatrends Inc. 3.1 (Boot Mode:Legacy BIOS) | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3, 6.5u2, 6.5u1, 6.5, 6.0 | [VMware compatibility guide - System](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=server&productid=45398&deviceCategory=server&details=1&keyword=SYS-8048B-TR4FT&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| PIO-6029U-E1CR4T-ST031 (2U)</br>SYS-6029U-E1CR4T | X11DPU+</br>X11DPU+_R1.10 | Intel Xeon Platinum 8100, Gold 6100/5100, Silver 4100, Bronze 3100 (Skylake-SP) Series, Intel Xeon Platinum 8200, Gold 6200/5200 (Cascade-Lake-SP) Series</br>Intel® C621 chipset | 3.1a 9-25-2019 | 3.1a 9-25-2019 | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3, 6.5u2 | [VMware compatibility guide - System](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=server&productid=49256&deviceCategory=server&details=1&keyword=SYS-6029U-E1CR4T&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| PIO-6019U-TN4R4T-ST031 (1U)</br>SYS-6019U-TN4R4T | X11DPU+</br>X11DPU+_R1.10 | Intel Xeon Platinum 8100, Gold 6100/5100, Silver 4100, Bronze 3100 (Skylake-SP) Series, Intel Xeon Platinum 8200, Gold 6200/5200 (Cascade-Lake-SP) Series</br>Intel® C621 chipset | 3.1a 9-25-2019 | 3.1a 9-25-2019 | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3, 6.5u2 | [VMware compatibility guide - System](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=server&productid=44741&deviceCategory=server&details=1&keyword=SYS-6019U-TN4R4T%20&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| SYS-2049U-TR4 (2u) | X11QPH+ R1.02 | Intel Xeon Platinum 8200, Gold 6200/5200  (Cascade-Lake-SP) Series</br>Intel® C621 chipset | 3.0c 3-20-2019 for MOBO Rls R1.01</br>3.1 5-1-2019 for MOBO Rls R1.02 and R1.20 | American Megatrends Inc. 3.0c UEFIBIOS (Boot Mode :UEFI) and (Boot Mode:Legacy BIOS) | ESXi 6.7u2, 6.7u1 | [VMware compatibility guide - System](https://www.vmware.com/resources/compatibility/search.php?deviceCategory=server&details=1&keyword=SYS-2049U-TR4&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
{: caption="Table 4. SuperMicro BIOS levels reference" caption-side="top"}

## Lenovo BIOS levels reference
{: #vmware-comp-guide-lenovo-bios}

| Server configuration | MOBO | CPU | IBM Cloud infrastructure BIOS Level | Lenovo BIOS | IBM-supported releases | Link |
|:-------------------- |:---- |:--- |:----------------------------------- |:----------- |:---------------------- |:---- |
| System x3650 M5 | Systemx3650-M5-V4 | E5-2600-v4</br>Intel C612 Chipset | 2.91 6-3-2019UEFI | LENOVO -[TCE140D-2.90]- UEFI Mode | ESXi 6.7, 6.5u3, 6.5u2, 6.5u1, 6.5, 6.0 | [VMware compatibility guide - System](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=server&productid=39869&deviceCategory=server&details=1&partner=51&keyword=System%20x3650%20M5&page=1&display_interval=100&sortColumn=Partner&sortOrder=Asc) |
{: caption="Table 5. Lenovo BIOS levels reference" caption-side="top"}

## RAID Controllers reference
{: #vmware-comp-guide-raid-control}

| Model | Drivers | Firmware | Supported releases | Link |
|:----- |:------- |:-------- |:------------------ |:---- |
| (LSI) MegaRAID SAS 9361-8i | lsi-mr3 version 7.703.18.00-1OEM.650 | 4.680.00-8301 | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3,  6.5u2, 6.5u1, 6.5, 6.0 | [VMware compatibility guide - I/O device](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=vsanio&productid=40379&deviceCategory=vsanio&details=1&vsan_type=vsanio&io_partner=50&keyword=MegaRAID%20SAS%209361-8i&page=1&display_interval=50&sortColumn=Partner&sortOrder=Asc) |
| (LSI) MegaRAID SAS 9461-16i (Cascade Lake servers) | lsi_mr3 version 7.709.10.00-1OEM.670 | 5.070.00-1894 | ESXi 6.7 U2 (vSAN 6.7 Update 2), ESXi 6.7 U1 (vSAN 6.7 Update 1), ESXi 6.7 (vSAN 6.7), 6.5u3 | [VMware compatibility guide - I/O device](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=vsanio&productid=45822&deviceCategory=vsanio&details=1&vsan_type=vsanio&keyword=9461-16i&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
{: caption="Table 6. RAID Controllers reference" caption-side="top"}

## NICs with Intel Network Adapter reference
{: #vmware-comp-guide-nics}

| Model | Drivers | Firmware | IBM-supported releases | Link |
|:----- |:------- |:-------- |:------------------ |:---- |
| AOC-2UR6-i4XT</br>Intel X540-AT2 | ixgbe version 4.4.1</br>ixgben version 1.5.3</br>ixgben version 1.5.3 | N/A</br>0x80003e1</br>N/A | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3, 6.5u2, 6.5u1, 6.5, 6.0 | [VMware compatibility guide - I/O device](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=io&productid=42956&deviceCategory=io&details=1&partner=105&keyword=AOC-2UR6-i4XT&deviceTypes=6&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| AOC-STG-i2T</br>Intel X540-AT2 | i40en version 1.7.11</br>i40en version 1.9.5 in testing | 6.01</br>7.0 in testing | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3, 6.5u2 | [VMware compatibility guide - I/O device](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=io&productid=38693&deviceCategory=io&details=1&partner=105&keyword=AOC-STG-i2T&deviceTypes=6&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| AOC-2UR66-i4XTF (2U)</br>Intel X710-T4 | ixgbe version 4.4.1</br>ixgben version 1.5.3</br>ixgben version 1.5.3 | N/A</br>0x80003e1</br>N/A | ESXi 6.7u2, 6.7u1, 6.7, 6.5u2, 6.5u1, 6.5, 6.0 | [VMware compatibility guide - I/O device](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=io&productid=45006&deviceCategory=io&details=1&partner=105&keyword=AOC-2UR66-i4XTF%20&deviceTypes=6&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| Secondary NIC - Intel X540-AT2 10GbE | ixgben version 1.5.3 | N/A | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3, 6.5u2, 6.5u1, 6.5, 6.0 | [VMware compatibility guide - I/O device](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=io&productid=20362&deviceCategory=io&details=1&partner=46&keyword=X540&deviceTypes=6&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| Secondary NIC - Intel / X710-T4 / Intel 10 Gigabit 4 Port /4 | i40en version 1.7.11</br>i40en version 1.9.5 in testing | 6.01</br>7.0 in testing | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3, 6.5u2 | [VMware compatibility guide - I/O device](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=io&productid=37980&deviceCategory=io&details=1&partner=46&keyword=X710&deviceTypes=6&page=2&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| Intel(R) Ethernet Network Adapter E810-XXV-4 | icen version 1.0.6 | 1.02 | ESXi 6.7u2 | [VMware compatibility guide - I/O device](https://www.vmware.com/resources/compatibility/search.php?deviceCategory=io&details=1&keyword=E810&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
{: caption="Table 7. NICs with Intel Network Adapter reference" caption-side="top"}

## Micron SSDs reference
{: #vmware-comp-guide-micron-ssd}

| Model | Capacity | IBM Cloud infrastructure firmware | vSAN HCL firmware | IBM-supported releases | Applicable to | Link |
|:----- |:-------- |:--------------------------------- |:----------------- |:---------------------- |:------------- |:---- |
| 5100</br>MTFDDAK960TCC-1AR16ABYY | 960 GB | D0MU051 | D0MU051 | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3, 6.5u2, 6.5u1, 6.5, 6.0 | vSAN All Flash Caching Tier</br>vSAN All Flash Capacity Tier | [VMware compatibility guide - SSD](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=ssd&productid=41212&deviceCategory=ssd&details=1&vsan_type=vsanssd&ssd_partner=454&keyword=MTFDDAK960TCC-1AR16ABYY&vsanrncomp=true&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| 5100</br>MTFDDAK1T9TCC-1AR16ABYY | 1920 GB | D0MU051 | D0MU051 | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3, 6.5u2, 6.5u1, 6.5, 6.0 | vSAN All Flash Caching Tier</br>vSAN All Flash Capacity Tier | [VMware compatibility guide - SSD](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=ssd&productid=41375&deviceCategory=ssd&details=1&vsan_type=vsanssd&ssd_partner=454&keyword=%20MTFDDAK1T9TCC-1AR16ABYY&vsanrncomp=true&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| 5100</br>MTFDDAK3T8TCB-1AR16ABYY | 3840 GB | D0MU417 | D0MU417 | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3, 6.5u2, 6.5u1, 6.5, 6.0 | vSAN All Flash Capacity Tier | [VMware compatibility guide - SSD](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=ssd&productid=41440&deviceCategory=ssd&details=1&vsan_type=vsanssd&ssd_partner=454&keyword=%20MTFDDAK3T8TCB-1AR16ABYY&vsanrncomp=true&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| 5200</br>MTFDDAK960TDN-1AT16ABYY | 960 GB | D1MU006 | D1MU006 | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3, 6.5u2, 6.5u1, 6.5, 6.0 | vSAN All Flash Caching Tier</br>vSAN All Flash Capacity Tier | [VMware compatibility guide - SSD](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=ssd&productid=43546&deviceCategory=ssd&details=1&vsan_type=vsanssd&ssd_partner=454&keyword=MTFDDAK960TDN-1AT16ABYY&vsanrncomp=true&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| 5200</br>MTFDDAK1T9TDN-1AT16ABYY | 1920 GB | D1MU006 | D1MU006 | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3, 6.5u2, 6.5u1, 6.5, 6.0 | vSAN All Flash Caching Tier</br>vSAN All Flash Capacity Tier | [VMware compatibility guide - SSD](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=ssd&productid=43547&deviceCategory=ssd&details=1&vsan_type=vsanssd&ssd_partner=454&keyword=MTFDDAK1T9TDN-1AT16ABYY&vsanrncomp=true&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| 5200</br>MTFDDAK3T8TDD-1AT16ABYY | 3840 GB | D1MU506 | D1MU506 | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3, 6.5u2, 6.5u1, 6.5, 6.0 | vSAN All Flash Capacity Tier | [VMware compatibility guide - SSD](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=ssd&productid=43996&deviceCategory=ssd&details=1&vsan_type=vsanssd&ssd_partner=454&keyword=MTFDDAK3T8TDD-1AT16ABYY&vsanrncomp=true&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| 5200</br>MTFDDAK7T6TDC-1AT16ABYY</br>**Not Available at this time** | 7680 GB | D1MU804 | D1MU804 | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3, 6.5u2, 6.5u1, 6.5, 6.0 | vSAN All Flash Capacity Tier | [VMware compatibility guide - SSD](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=ssd&productid=44272&deviceCategory=ssd&details=1&vsan_type=vsanssd&ssd_partner=454&keyword=MTFDDAK7T6TDC-1AT16ABYY&vsanrncomp=true&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
{: caption="Table 8. Micron SSDs reference" caption-side="top"}

Do not mix SSD vendors in vSAN servers or clusters.
{:note}

## Intel SSDs reference
{: #vmware-comp-guide-intel-ssd}

| Model | Capacity | IBM Cloud infrastructure firmware | vSAN HCL firmware | IBM-supported releases | Applicable to | Link |
|:----- |:-------- |:--------------------------------- |:----------------- |:---------------------- |:------------- |:---- |
| Intel® SSD D3-S4610 Series SSDSC2KG960G8 (960GB, 2.5”) | 960 GB | XCV10100 | XCV10100 | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3, 6.5u2, 6.5u1, 6.5, 6.0 | vSAN All Flash Caching Tier</br>vSAN All Flash Capacity Tier | [VMware compatibility guide - SSD](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=ssd&productid=43954&deviceCategory=ssd&details=1&vsan_type=vsanssd&ssd_partner=46&keyword=SSDSC2KG960G8%20(960GB,%20S.5%22)&vsanrncomp=true&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| Intel® SSD D3-S4610 Series SSDSC2KG019T8 (1.92TB, 2.5”) | 1920 GB | XCV10100 | XCV10100 | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3, 6.5u2, 6.5u1, 6.5, 6.0 | vSAN All Flash Caching Tier</br>vSAN All Flash Capacity Tier | [VMware compatibility guide - SSD](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=ssd&productid=43950&deviceCategory=ssd&details=1&vsan_type=vsanssd&ssd_partner=46&keyword=SSDSC2KG019TB%20(1.92TB,%202.5%22)&vsanrncomp=true&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| Intel® SSD D3-S4610 Series SSDSC2KG038T8 (3.84TB, 2.5”) | 3840 GB | XCV10100 | XCV10100 | ESXi 6.7u2, 6.7u1, 6.7, 6.5u3, 6.5u2, 6.5u1, 6.5, 6.0 | vSAN All Flash Caching Tier</br>vSAN All Flash Capacity Tier | [VMware compatibility guide - SSD](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=ssd&productid=43951&deviceCategory=ssd&details=1&vsan_type=vsanssd&ssd_partner=46&keyword=SSDSC2KG038T8%20(3.84TB,%202.5%22)&vsanrncomp=true&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
{: caption="Table 9. Intel SSDs reference" caption-side="top"}

Do not mix SSD vendors in vSAN servers or clusters.
{:note}

## Intel Optane reference
{: #vmware-comp-guide-intel-optane}

| Model | Capacity | Dev driver | Firmware | IBM-supported releases | Applicable to | Link |
|:----- |:-------- |:---------- |:-------- |:---------------------- |:------------- |:---- |
| Intel® Optane™ SSD DC P4800X Series SSDPED1K750GA (750 GB, HHHL) | 750 GB | intel-nvme-vmd 1.4.0.1016-1OEM.650 async (Note: 650 identifies ESXi 6.5) | E2010435 | ESXi 6.7u2, 6.7u1, 6.7 | vSAN All Flash Caching Tier | [VMware compatibility guide - SSD](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=ssd&productid=42966&deviceCategory=ssd&details=1&vsan_type=vsanssd&ssd_partner=46&keyword=SSDPED1K750GA&vsanrncomp=true&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
| Intel® Optane™ SSD DC P4800X Series SSDPED1K750GA (750 GB, HHHL) | 750 GB | intel-nvme-vmd 1.4.0.1016-1OEM.670   async (Note: 670 identifies ESXi 6.7) | E2010435 | ESXi 6.7u2, 6.7u1, 6.7 | vSAN All Flash Caching Tier | [VMware compatibility guide - SSD](https://www.vmware.com/resources/compatibility/detail.php?deviceCategory=ssd&productid=42966&deviceCategory=ssd&details=1&vsan_type=vsanssd&ssd_partner=46&keyword=SSDPED1K750GA&vsanrncomp=true&page=1&display_interval=10&sortColumn=Partner&sortOrder=Asc) |
{: caption="Table 10. Intel Optane reference" caption-side="top"}

## Related links
{: #vmware-comp-guide-related}

* [FAQ](/docs/services/vmwaresolutions?topic=vmware-solutions-faq)
* [vCenter Server overview](/docs/services/vmwaresolutions?topic=vmware-solutions-vc_vcenterserveroverview)
* [VMware vSphere overview](/docs/services/vmwaresolutions?topic=vmware-solutions-vs_vsphereclusteroverview)
* [vCenter Server BOM](/docs/services/vmwaresolutions?topic=vmware-solutions-vc_bom)
* [VMware vSphere BOM](/docs/services/vmwaresolutions?topic=vmware-solutions-vs_bom)
