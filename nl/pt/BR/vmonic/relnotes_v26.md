---

copyright:

  years:  2016, 2018

lastupdated: "2018-09-20"

---

# Notas sobre a liberação da V2.6

Esta liberação inclui novos recursos, atualizações de componentes, aprimoramentos de usabilidade e correções de bug. Para obter uma lista de problemas corrigidos em diferentes liberações, problemas conhecidos com o produto e dicas para usar o {{site.data.keyword.vmwaresolutions_full}}, consulte o [{{site.data.keyword.vmwaresolutions_short}}dW Answers](https://developer.ibm.com/answers/topics/cloudvmw/){:new_window}.

## Correção para Spectre e Meltdown

O {{site.data.keyword.vmwaresolutions_short}} liberou correções do VMware em resposta a vulnerabilidades relacionadas ao Spectre e ao Meltdown (CVE-2017-5753, CVE-2017-5715 e CVE-2017-5754).

* CVEID: [CVE-2017-5753](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5753)
* CVEID: [CVE-2017-5715](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5715)
* CVEID: [CVE-2017-5754](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5754)

Para obter mais informações, veja [Tratando as vulnerabilidades Spectre e Meltdown](../vmonic/trbl_fix_spectre.html).

## Alto desempenho com a opção Intel Optane

Esta liberação fornece a opção de incluir cache de alto desempenho para armazenamento vSAN quando você está pedindo uma nova instância ou quando inclui um novo cluster vSAN após a implementação inicial.

Essa opção permite aumentar o número de discos com capacidade de armazenamento de oito para um máximo de dez.

A opção Alto desempenho com Intel Optane está disponível somente para configurações customizadas com os processadores Dual Intel Xeon Gold 5120 e Dual Intel Xeon Gold 6140.

Para obter mais informações, consulte o tópico de solicitação apropriado de sua instância ou tipo de cluster.

## Ativando uma rede pública ou privada

Agora é possível implementar instâncias do vCenter Server e do vCenter Server with Hybridity Bundle, bem como clusters do VMware vSphere, com placas de interface de rede (NICs) públicas e privadas ativadas ou NICs somente privadas ativadas. Essa opção também está disponível ao incluir um novo cluster na instância do vCenter Server e do vCenter Server with Hybridity Bundle.

Alguns serviços complementares requerem NICs públicas e não estarão disponíveis se você selecionar a ativação de uma rede somente privada.

Para obter mais informações, consulte a seção _Configurações da interface de rede_ nos tópicos a seguir:

* [Pedindo instâncias do vCenter Server](../vcenter/vc_orderinginstance.html#network-interface-settings)
* [Pedindo instâncias do vCenter Server with Hybridity Bundle](../vcenter/vc_hybrid_orderinginstance.html#network-interface-settings)
* [Pedindo novos clusters do vSphere](../vsphere/vs_orderinginstances.html#network-interface-settings)

## Excluindo servidores ESXi

Agora será possível excluir qualquer servidor ESXi da instância do vCenter Server, do vCenter Server with Hybridity Bundle ou do Cloud Foundation se você atender aos requisitos mínimos de sua instância.

Para obter mais informações sobre os requisitos do servidor ESXi, consulte os tópicos a seguir:

* [Expandindo e contraindo capacidade para instâncias do vCenter Server](../vcenter/vc_addingremovingservers.html)
* [Expandindo e contraindo a capacidade para instâncias do vCenter Server with Hybridity Bundle](../vcenter/vc_hybrid_addingremovingservers.html)
* [Expandindo e contraindo capacidade para instâncias do Cloud Foundation](../sddc/sd_addingremovingservers.html)

## Atualizações para instâncias do VMware vCenter Server

Esta liberação aplica os upgrades e melhorias a seguir:

* vSphere ESXi 6.5 Atualização 2c
* vCenter Server Appliance 6.5 Atualização 2c
* Platform Services Controller 6.5 Atualização 2c
* NSX for vSphere 6.4.1

## Atualizações para o VMware vCenter Server with Hybridity Bundle

### Removendo o Hybridity Bundle de uma instância do vCenter Server

Agora é possível remover a licença do Hybridity Bundle de sua instância do vCenter Server. Para isso, será necessário substituir as chaves de licença de aluguel do VMware NSX e do VMware vSAN pelas chaves de Bring Your Own License (BYOL) e abrir um chamado de suporte para cancelar os encargos das licenças de aluguel.

Para obter mais informações, consulte [Removendo o Hybridity Bundle de uma instância do vCenter Server](../vcenter/vc_hybrid_deletingbundle.html).

### Disponibilidade do vCenter Server with Hybridity Bundle

Os Parceiros de Negócios podem agora pedir uma instância do vCenter Server with Hybridity Bundle. Os Parceiros de Negócios não podem fazer upgrade de uma instância existente do vCenter Server para uma instância do vCenter Server with Hybridity Bundle e não podem remover o Hybridity Bundle de uma a instância do vCenter Server with Hybridity Bundle.

Para obter mais informações, veja os tópicos a seguir:

* [vCenter Server com visão Hybridity Bundle](../vcenter/vc_hybrid_overview.html)
* [Pedindo instâncias do vCenter Server with Hybridity Bundle](../vcenter/vc_hybrid_orderinginstance.html)

## Atualizações para instâncias do VMware Cloud Foundation

Esta liberação aplica os upgrades e melhorias a seguir:

* vSphere ESXi 6.5 Atualização 2c
* vCenter Server Appliance 6.5 Atualização 2c
* Platform Services Controller 6.5 Atualização 2c
* NSX for vSphere 6.4.1

## Atualizações para serviços complementares

### HyTrust KeyControl on IBM Cloud

O serviço HyTrust KeyControl on {{site.data.keyword.cloud_notm}} está agora disponível para instâncias do VMware Cloud Foundation e do VMware vCenter Server que estão executando o vSphere 6.5 e que são implementadas ou submetidas a upgrade para a V2.5 e liberações mais recentes. O serviço simplifica o gerenciamento de cargas de trabalho criptografadas automatizando e simplificando o ciclo de vida de chaves de criptografia. O serviço pode gerenciar facilmente as chaves de criptografia em escala usando a criptografia compatível com FIPS 140-2. Ao usar esse serviço, é possível gerenciar as chaves de criptografia de todas as máquinas virtuais e armazenamentos de dados criptografados, além de escalá-lo para suportar milhares de cargas de trabalho criptografadas em grandes implementações.

É possível pedir instâncias com o serviço incluído quando você pede a sua instância ou incluir esse serviço em suas instâncias existentes posteriormente.

Para obter mais informações, veja os tópicos a seguir:
* [Componentes e considerações para o HyTrust KeyControl on {{site.data.keyword.cloud_notm}}](../services/htkc_considerations.html)
* [Gerenciando o HyTrust KeyControl on {{site.data.keyword.cloud_notm}}](../services/managinghtkc.html)

### HyTrust CloudControl on IBM Cloud

A liberação atual instala o HyTrust CloudControl 5.4 em todas as instâncias recém-implementadas. Para obter mais informações sobre os novos recursos no HyTrust CloudControl 5.4, consulte [Conjunto de documentação on-line do HyTrust CloudControl v 5.4](https://docs.hytrust.com/CloudControl/5.4.0/Online/index.html).

### HyTrust DataControl on IBM Cloud

A liberação atual instala o HyTrust DataControl 4.2 em todas as instâncias recém-implementadas. Para obter mais informações sobre os novos recursos no HyTrust DataControl 4.2, consulte [O que há de novo no HyTrust DataControl 4.x](https://docs.hytrust.com/DataControl/4.2/Admin_Guide-4.2/Content/Books/aaCommon/New-Changed-4x.htm).

### Suporte do Veeam on IBM Cloud para o vSphere ESXi V6.5 atualização 2c

A partir da V2.6, novas instâncias e novos hosts foram provisionados usando o vSphere ESXi V6.5 Atualização 2c. Se você estiver usando o Veeam Backup and Replication, a Veeam recomenda atualizar a instância do Veeam on {{site.data.keyword.cloud_notm}} para a V9.5u3a ou mais recente para assegurar a melhor compatibilidade com o vSphere ESXi 6.5 Atualização 2c.

Recomenda-se que as instâncias existentes do Cloud Foundation que têm o Veeam on {{site.data.keyword.cloud_notm}} instalado também sejam atualizadas para a V9.5u3a ou mais recente.

Para obter mais informações sobre o Veeam on {{site.data.keyword.cloud_notm}}, consulte [Visão geral do Veeam on {{site.data.keyword.cloud_notm}}](../services/veeam_considerations.html).

### VMware HCX on IBM Cloud

A liberação atual instala o VMware HCX 3.5.1 R106 em todas as instâncias recém-implementadas. Para obter mais informações sobre os novos recursos no HCX 3.5.1 R106, consulte [Documentação do VMware NSX Hybrid Connect](https://docs.vmware.com/en/VMware-NSX-Hybrid-Connect/index.html).

## Documentação nova e atualizada

### Arquitetura de Referência da documentação
O documento de arquitetura do {{site.data.keyword.vmwaresolutions_short}} foi atualizado para incluir considerações importantes para entender suas responsabilidades de gerenciamento e operação da instância do VMware.

Para obter mais informações, consulte [Considerações pós-implementação para a instância do VMware](../archiref/solution/solution_considerations.md).

## Atualizações e aprimoramentos da interface com o usuário

A interface com o usuário é atualizada e fornece os aprimoramentos a seguir:

* Várias mensagens de erro e aprimoramentos de dicas de ferramenta estão disponíveis para ajudá-lo na seleção da configuração apropriada na interface com o usuário.