---

copyright:

  years:  2016, 2018

lastupdated: "2018-06-07"

---

# KMIP for VMware on IBM Cloud 개요

KMIP for VMware on {{site.data.keyword.cloud}} 서비스는 {{site.data.keyword.cloud_notm}}의 VMware에서 사용되는 암호화 키를 관리하기 위해 고가용성 서비스를 연중무휴로 제공합니다. 이 서비스는 고객이 암호화 키를 작성, 검색, 활성화, 취소 및 영구 삭제할 수 있도록 런타임 기능을 제공하고, 또한 클라이언트 신임 정보와 해당 암호화 키 사이에 연관을 유지보수하는 관리 기능도 제공합니다.

**가용성**: 이 서비스는 V2.2 이상 릴리스에 배치된 인스턴스에서만 사용 가능합니다.

## KMIP for VMware on IBM Cloud 설치 시 고려사항

KMIP for VMware on {{site.data.keyword.cloud_notm}}는 암호화 키를 작성, 암호화 및 복호화하도록 IBM Cloud 서비스를 위한 IBM Key Protect를 사용하십시오. 그러므로 서비스를 설치하기 전에 사용 가능한 Key Protect 서비스를 주문했는지 확인하십시오. 한편, 작성한 Key Protect 서비스 인스턴스에 액세스할 수 있도록 [서비스 ID 작성](https://console.bluemix.net/docs/iam/serviceid.html#creating-a-service-id)의 단계를 따라 {{site.data.keyword.cloud_notm}} 서비스 ID가 작성되었습니다.

서비스 ID에 대한 다음 액세스 레벨을 부여했는지 확인하십시오.
* 플랫폼 액세스 레벨: IBM Key Protect 인스턴스에 대한 뷰어 권한.
* 서비스 액세스 레벨: IBM Key Protect 인스턴스에 대한 작성자 권한

작성된 서비스 ID에 대한 API 키는 서비스를 주문할 때 필요합니다.

서비스는 사용자가 [루트 키 작성](https://console.bluemix.net/docs/services/keymgmt/keyprotect_create_root.html#create_root_keys)의 단계를 따르거나 [IBM Key Protect](https://console.bluemix.net/apidocs/639-ibm-key-protect)의 RESTful API를 사용하여 Key Protect 사용자 인터페이스에서 하나 이상의 고객 루트 키(CRK)를 이미 작성했다고 간주합니다.

CRK 없이 서비스를 주문할 수 없습니다. 기존 키 자료를 통해 CRK를 작성할 수 있는 방법을 사용하고 작성 중인 키 자료를 백업하는 것이 좋습니다. 이를 수행하여 IBM Key Protect가 CRK를 저장하도록 적용된 데이터 센터에 장애가 발생하는 경우 키를 복구할 수 있음을 확인합니다.

## KMIP for VMware on IBM Cloud 사용 시 고려사항

* VMware vCenter Server에 등록된 KMS(Key Management Server)로 주문된 KMIP for VMware on {{site.data.keyword.cloud_notm}} 서비스를 사용하려면 vCenter Server와 주문된 KMIP for VMware on {{site.data.keyword.cloud_notm}} 서비스에 대한 엔드포인트 간의 네트워크 연결이 작동되도록 구성이 올바르게 배치되었는지 확인해야 합니다.
* VMware vSAN 암호화를 위해 서비스를 사용하려면 대상 vSAN의 호스트와 주문된 KMIP for VMware on {{site.data.keyword.cloud_notm}} 서비스의 엔드포인트 간의 네트워크 연결이 작동하는지 확인해야 합니다.


## KMIP for VMware on IBM Cloud 제거 시 고려사항

서비스를 주문하거나 사용할 때 제공한 VMware 공용 인증서가 서비스 인스턴스와 통신하는 데 클라이언트 인증서로 사용됩니다. 서비스가 제거되면 연관된 VMware 공용 인증서에 대해 이 서비스 인스턴스에서 작성된 모든 암호화 키가 함께 제거됩니다.

그러므로 서비스를 제거하기 전에 KMIP 서비스로 작성된 키를 사용하여 가상 머신 또는 vSAN이 암호화되고 있지 않은지 확인해야 합니다.

## 관련 링크

* [KMIP for VMware on IBM Cloud 주문](kmip_ordering.html)
* [IBM Key Protect for {{site.data.keyword.cloud_notm}}](https://console.bluemix.net/docs/services/keymgmt/index.html#getting-started-with-key-protect)
* [IBM Key Protect](https://console.bluemix.net/apidocs/639-ibm-key-protect?&language=javascript_jquery#introduction)
* [vSphere Security](https://docs.vmware.com/en/VMware-vSphere/6.5/com.vmware.vsphere.security.doc/GUID-52188148-C579-4F6A-8335-CFBCE0DD2167.html)
* [FAQ](../vmonic/faq.html)
* [IBM 지원 센터에 문의](../vmonic/trbl_support.html)