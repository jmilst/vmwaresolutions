---

copyright:

  years:  2016, 2018

lastupdated: "2018-09-20"

---

# デプロイメント後の VMware インスタンスの考慮事項

{{site.data.keyword.vmwaresolutions_full}}、VMware vCenter Server、および VMware Cloud Foundation オファリングは、マネージド・サービスではありません。お客様は、すべてのソフトウェア・コンポーネントの構成、セキュリティー、管理、モニタリングについての責任があります。ソリューションに対して完全な管理アクセス権限を持つことで、高い制御性と柔軟性を獲得できますが、各種ドメインにおける技術、管理、運用面での高度な専門知識が必要となります。{{site.data.keyword.cloud_notm}} で VMware インスタンスを管理するには、オンプレミス・インスタンスの計画と同様の計画および専門知識が必要です。ソフトウェアで定義されたテクノロジー (VMware NSX、VMware vSAN など) は、インスタンス管理におけるいくつかの側面を大幅に簡素化しますが、新しいスキルとツールを適切に管理して操作しなければならない場合があります。{{site.data.keyword.cloud_notm}} の自動化された VMware デプロイメントのパワー、スピード、信頼性を、適切な運用計画およびテストと組み合わせることで、ハイブリッド・クラウドへの迅速かつ効率的なナビゲーションが保証されます。

以下の考慮事項を検討して、デプロイ前後にインスタンスを管理および操作する自分の責任について理解してください。 

**注:** 次のリストは、すべてを網羅しているわけではありません。詳しくは、[IBM Managed Services](../../services/managing_imi.html) を参照してください。

## IBM Cloud アカウントのアクセス

{{site.data.keyword.cloud_notm}} アカウントへのアクセスを管理するには、チームの他のメンバーに対し、{{site.data.keyword.vmwaresolutions_short}} コンソールでのインスタンスへのアクセスを許可します。詳しくは、[サービスとリソースにアクセスするようにユーザーを招待する](../../vmonic/iamuserinvite.html)を参照してください。

## 制限

インスタンスの以下の制限事項を把握しておいてください。

- [vCenter 成果物の変更による影響](../../vcenter/vcenter_chg_impact.html)
- [ネットワークに関する考慮事項と制限](../../vcenter/vc_networkingonvcenterserver.html)
- [よくある質問](../../vmonic/faq.html)

## ネットワーク設計と接続性

以下の手順を実行して、{{site.data.keyword.cloud_notm}} ネットワークおよび VMware 管理コンポーネントへのアクセスを管理し、{{site.data.keyword.cloud_notm}} ネットワーク・トポロジーを計画します。

- [{{site.data.keyword.cloud_notm}} VPN](https://www.softlayer.com/vpn-access) または [{{site.data.keyword.cloud_notm}}Direct-Link 接続](https://www.ibm.com/cloud/direct-link)を使用してインスタンス管理エンドポイントにアクセスします。
- インスタンス内からパブリック・ネットワーク接続のための戦略を策定します。選択肢として、サンプルのカスタマー向け VMware NSX Edge Services Gateway (ESG)、ゲートウェイ・アプライアンス (Vyatta、FortiGate など)、{{site.data.keyword.cloud_notm}} ネットワークまたは DirectLink を介してアクセスする独自のネットワークのいずれかにデプロイされたプロキシー・サーバーです。
- [{{site.data.keyword.cloud_notm}} ポータブル IP アドレス](https://console.bluemix.net/docs/infrastructure/subnets/getting-started.html)を使用して {{site.data.keyword.cloud_notm}} VLAN にワークロードをデプロイするか、または[独自の IP アドレスを使用して NSX 論理スイッチ (VXLAN)](../nsx/nsx_overview.html) にデプロイするのかを計画します。NSX ソフトウェア定義ネットワーク (SDN) を使用すると、{{site.data.keyword.cloud_notm}} でワークロード・ネットワークを非常に柔軟に管理および保護することができます。
- NSX ESG、[IBM Cloud Vyatta](https://console.bluemix.net/catalog/infrastructure/virtual-router-appliance)、および DirectLink ピアリングを使用して、ワークロード (ネットワーク・アドレス変換、仮想プライベート・ネットワーク、ルーティング) への接続に関する計画を立てます。
- Cross-vCenter NSX を実装する場合は、ローカル・ワークロードをデプロイする前に、ローカル・セグメントの ID 範囲が重複していないことを確認してください。

## セキュリティーの計画と強化

企業、業界、および規制上の標準を満たすために、VMware インスタンスとワークロードの保護、暗号化、およびモニタリングをお客様の責任で行う必要があります。以下の手順を実行して、適切なセキュリティーを確保してください。

- {{site.data.keyword.vmwaresolutions_short}} コンソールに表示されるすべてのパスワードを変更し、独自のパスワード管理システムを使用します。IBM は、継続的な自動化とサポートに利用する目的で、個別のユーザー ID を保持しています。
- すべてのコンポーネントでパスワード・ポリシー (複雑さ、有効期限など) を確認します。
- すべてのコンポーネントの暗号化設定を確認します。
- NSX Distributed Firewall (DFW)、NSX ESG、[Fortigate Virtual Appliance on {{site.data.keyword.cloud_notm}}](../../services/fortinetvm_considerations.html)、[IBM Cloud Vyatta](https://console.bluemix.net/catalog/infrastructure/virtual-router-appliance) など、適切な物理または仮想ファイアウォール・ソリューションを計画し、実装します。
- 適切なアプリケーション・ロード・バランシング・ソリューションとセキュリティー・ソリューション ([F5 on {{site.data.keyword.cloud_notm}}](../../services/f5_considerations.html) など) を計画し、実装します。
- 適切なセキュリティー情報およびイベント管理 (SIEM) ソリューション ([IBM QRadar](https://www.ibm.com/us-en/marketplace/hosted-security-intelligence) など) を計画し、実装します。
- 適切な脆弱性スキャンを計画し、実装します。
- [HyTrust CloudControl on {{site.data.keyword.cloud_notm}}](../../services/htcc_considerations.html) などのソリューションを使用して、インスタンスの適切な変更管理、承認、監査、およびアクセス制御を計画し、実装します。

## カスタマイズ

以下の手順を実行して、要件に合わせて VMware インスタンスの基本インストールをカスタマイズしてください。

- 独自の認証局 (CA) を使用して、vCenter、VMware Platform Services Controller (PSC)、NSX Manager などのコンポーネントの証明書を生成します。
- デプロイされたサービスを構成します。例えば次のようにします。
  - HyTrust CloudControl on {{site.data.keyword.cloud_notm}} の場合は、AD 統合、アクセス制御、Simple Mail Transfer Protocol (SMTP) 設定、およびコンプライアンス・ポリシーを構成します。
  - Zerto on {{site.data.keyword.cloud_notm}} の場合は、ネットワーク・アドレス変換機構 (NAT) のトラバーサルがサポートされないため、Zerto Virtual Replication Appliance (VRA) の通信の IP アドレッシングとルーティングを計画します。アドレッシングとルーティングが適切に行われるように、VRA のトンネリングまたは再デプロイメントを検討してください。
  - Veeam on {{site.data.keyword.cloud_notm}} や IBM Spectrum Protect Plus on {{site.data.keyword.cloud_notm}} などのバックアップ・サービスの場合は、バックアップ・ジョブを構成し、追加のストレージをオプションで構成し、モニタリング・アラートを構成します。
  - F5 on {{site.data.keyword.cloud_notm}} や FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}} などのネットワーキングおよびセキュリティー・サービスの場合は、ネットワーク・トポロジーやその他の要件に応じて、ネットワーク・インターフェース、証明書、高可用性 (HA) 構成、およびルールを構成します。

## アクティブ・ディレクトリー

以下の手順を実行して、シングル・サインオン (SSO) を適切に構成および管理してください。

- Active Directory (AD) サーバーの更新とリブートのスケジュールを構成します。
- vSphere クラスターに AD サーバーをデプロイするオプションを選択した場合は、サーバーがコンプライアンスと可用性を確保できるように、Microsoft Windows のライセンスとアクティベーションの情報を入力します。
- インスタンスとオンプレミス AD サーバー間の相互信頼関係を確立します。
- NSX VPN を AD SSO と統合します (該当する場合)。
- ESXi ホストを AD SSO と統合します。

## 保守計画

以下の手順を実行して、ソフトウェア保守の適切な計画を立ててください。

- VMware の更新情報を入手するように、プロキシー経由で VMware Update Manager (VUM) をセットアップします。
- 該当する場合は、vSAN ハードウェア互換性リスト (HCL) データベースを保守するように、プロキシー経由で vSAN をセットアップします。
- VUM でサポートされていない VMware コンポーネントの定期保守を計画します。例えば、VMware vCenter、PSC、NSX などです。
- vSphere Enhanced vMotion Compatibility (EVC) の構成を確認します。ご使用のハードウェア・レベルでは現在のバージョンの vSphere が EVC をサポートしていない場合、クラスターで EVC が有効になるように構成されていない可能性があります。
- アドオン・サービス (Veeam on {{site.data.keyword.cloud_notm}}、Zerto on {{site.data.keyword.cloud_notm}}、F5 on {{site.data.keyword.cloud_notm}} など) の定期保守の計画を立てます。

## モニタリング

インスタンスおよびインスタンス・コンポーネントをモニタリングするための以下のソリューションを計画し、実装してください。

- ロギング・サーバー。すべてのインスタンス・コンポーネントのログ転送または収集と適切なログ保存を含みます。
- アラート・インフラストラクチャー。必要に応じて、SMTP サーバーとショート・メッセージ・サービス (SMS) ゲートウェイの構成を含みます。
- ホスト、ドライブ、管理ソフトウェア、およびネットワークのプロアクティブなモニタリング。
- vSAN のモニタリング (該当する場合)。
- キャパシティーのモニタリングと計画。[クラスターを追加および削除](../../vcenter/vc_addingviewingclusters.html)したり、{{site.data.keyword.vmwaresolutions_short}} コンソールから[インスタンスにホストを追加または削除](../../vcenter/vc_addingremovingservers.html)したりすることができます。
- バックアップ・インフラストラクチャーとバックアップ・ジョブのモニタリング。

## ビジネスの継続性と可用性

VMware インスタンスは、{{site.data.keyword.cloud_notm}} のベア・メタル・サーバー上で実行されます。以下の手順を実行して、高可用性とビジネス継続性の適切な計画を立ててください。

- 要件に合わせて vSphere HA および vSphere Distributed Resource Scheduler (DRS) の構成を確認します。
- 要件に合わせてネットワークとストレージの I/O 制御構成を確認します。
- 要件に合わせて仮想マシンの始動順序を構成します。
- 必要に応じて、管理とワークロード用にリソース・プールを構成します。
- [インスタンス管理コンポーネント](solution_backingup.html)とワークロードの両方のバックアップ・ソリューションを計画、実装、モニターします。
- インスタンス管理の高可用性 (複数のインスタンス、複数のクラスター、vCenter HA、PSC HA の可能性を含む) を計画します。
- [Zerto 災害復旧](../../services/addingzertodr.html)、[Veeam Backup と Replication](../../services/veeam_considerations.html)、[IBM Spectrum Protect Plus](../../services/spp_considerations.html) などのソリューションを使用して、ワークロードのビジネス継続性を計画します。

## ストレージの計画

以下の手順を実行して、キャパシティー・プランニングに加えて、ストレージ構成がパフォーマンスおよび可用性の要件を確実に満たすようにしてください。

- ストレージのパフォーマンスは、RAID 構成とディスク・ストライピング、ネットワーク構成、ブロック・サイズ、Network Attached Storage の IOPS (1 秒あたりの入出力操作) の構成、VM ハードウェアの構成とストレージ接続の方法、クラスタリングと複製の方法、ストレージ・ポリシー (暗号化、重複排除、圧縮など) の使用など、さまざまな要因によって異なります。ストレージ・パフォーマンスのニーズを満たすように構成をテストおよび調整するための時間を計画します。
- vSAN ストレージ・ポリシーの確認
  - RAID-1 は、RAID-5 よりパフォーマンスが向上し、順次障害の影響を受ける期間 (再ビルド時間など) が短縮されます。ただし、RAID-5 の方がストレージ・オーバーヘッドは少なくて済みます。
  - RAID-6 は二重障害に対する保護を提供しますが、6 台以上のホストが必要です。RAID-5 の場合に必要なホストが 4 台です。
- vSAN クラスターにストレージをさらに追加するには、新しいホストをクラスターに追加するか、代わりに {{site.data.keyword.cloud_notm}} Endurance NFS ストレージを追加する必要があります。現在、既存のホストにディスクを追加することはできません。
- 追加の {{site.data.keyword.cloud_notm}} Endurance NFS ストレージをクラスターにマウントする場合は、アーキテクチャーのガイダンスに従い、`SDDC-DPortGroup-NFS` ポート・グループ・アドレスを使用してストレージへのホスト・ルートを構成します。ストレージに対して、ホスト自体ではなく、これらのアドレスを許可する必要があります。詳しくは、[接続ストレージのインフラストラクチャー管理](../attached-storage/storage-infra-mgmt.html#vsphere-host-static-routing)を参照してください。developerWorks レシピも参照してください。このレシピでは、IBM Spectrum Protect Plus を例として使用して、[VMware クラスターにエンデュランス・ストレージをさらに追加](https://developer.ibm.com/recipes/tutorials/how-to-increase-vsnap-storage-for-ibm-spectrum-protect-plus-on-ibm-cloud-post-deployment/)する方法が示されています。

### 関連リンク

* [ソリューションの概要](solution_overview.html)
* [設計の概要](design_overview.html)
* [キャパシティーの拡張](solution_scaling.html)
