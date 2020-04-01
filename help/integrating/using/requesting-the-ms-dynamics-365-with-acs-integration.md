---
title: 通过Campaign Standard集成请求和配置Microsoft Dynamics 365
description: 了解如何通过Campaign Standard集成请求和配置Microsoft Dynamics 365
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a1bc9d23163d12517c4501a572fc92aac6aacbc6

---


# 请求Microsoft Dynamics 365并集成Campaign Standard

要配置此集成，您需要执行以下步骤。

请注意，此集成使用第三方提供商Unifi。  在您寻求支持协助的请求中，Adobe可能需要与Unifi共享您的Adobe Campaign实例信息。

请按照以下流程图和流程图详细信息请求和配置集成。

![](assets/provisioning-wf.png)

流程图详细信息（映射到上面的步骤）:

1. 您必须已配置Campaign Standard和Microsoft Dynamics 365，并具有对实施此集成的开始的管理员访问权限。

1. 阅读本文，检查声明和配置步骤。

1. 向adobe-support@unifisoftware.com发送帐户请求；在您请求帐户时，Unifi将要求提供以下信息：
* 用户名
* 用户名
* 用户电子邮件
* 公司名称
* 地区（北美、EMEA或APAC）
* 使用类型： 客户类型（将在此集成中使用其生产数据的客户用户）或合作伙伴类型(测试集成以更好地了解集成以帮助其活动客户的合作伙伴顾问)或内部类型（测试集成以更好地了解解决方案的Adobe内部用户）
* Campaign Standard数据状态（从干净数据库开始或将现有数据集成到集成中）
* 活动租户ID(请参阅配置活动集成部分第3步以获取您的租户ID)
* 活动实例URL

Unifi预期响应时间：美国正常营业时间为1小时（太平洋时间周一至周五上午9点至下午5点，节假日除外）。

1. 完整的Microsoft Dynamics 365后置备步骤和Campaign Standard。
此外，还可以直接或通过Adobe联系人向Adobe客户服务中心提交票证，以便在活动实例中启用单点登录功能标记。 合作伙伴应联系其Adobe合作伙伴沙箱代表，而不是联系Adobe客户关怀团队，以启用该功能标记。
如果您有活动中的现有数据计划并入集成中，请遵循“现有活动数据”中的指导，并在继续操作之前与Adobe技术联系人密切协商。

1. 在Unifi中完成初始入职步骤，方法是导航到Unifi，单击入职屏幕，填写Dynamics 365和Campaign Standard帐户凭据，并在完成后通知Unifi。

1. Unifi将要求客户进行其所需的退出配置和退出属性映射。

1. 客户将指示选定的退出配置和退出属性映射。
Unifi预期响应时间：1个工作日（周一至周五，节假日除外）

1. 配置Unifi涉及查看OOTB映射、过滤器、作业等。 如有必要，作出修改。  有关详细信息，请参阅Unifi用户指南。
此步骤涉及设置Unifi计划的运行频率
* 在Unifi的计划屏幕中设置计划的运行频率；但是，对于“入口”和“出口”计划，请在设置计划频率之前手动运行这些
* 建议使用以下计划频率：入口（15分钟）、出口（15分钟）、删除（一天一次）、退出（一天一次）

**在配置Unifi时，建议您与Unifi和／或Adobe咨询（联系您的Adobe客户团队）合作。**

要实现Adobe Campaign标准版与Microsoft Dynamics 365之间的集成，客户必须如本文档所述，与第三方提供商Unifi创建用户帐户。   作为Unifi系统的最终用户，对于客户在Unifi系统内发起的与数据请求相关的任何查询，客户应与Unifi联系。

## 配置此集成

需要为此集成配置和配置三个系统：Adobe Campaign标准版、Microsoft Dynamics 365 for Sales and Unifi。 配置文章链接如下。

>[!CAUTION]
>
>对于每个系统，这些步骤需要由管理员执行。
>
>以下文章中的步骤将指导您完成创建涉及分配权限和／或管理员访问权限的集成／注册。  您有责任确保这些步骤在执行之前符合您的公司政策，并谨慎执行。

在ADOBE CAMPAIGN中，您需要设置API访问并为Unifi配置新集成。 要实现此目的，请参阅 [本文](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)。

在MICROSOFT DYNAMICS 365中，您需要创建新的应用程序注册并使应用程序用户能够使用该集成。  要配置Microsoft Dynamics 365以进行此集成，请参阅 [本文](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)。

在UNIFI中，您需要设置集成并配置映射或添加自定义属性。 要为此集成配置Unifi，请参阅 [本文](../../integrating/using/configure-unifi-for-microsoft-dynamics-365-integration.md)。

## 请求支持

如果您遇到问题，请联系Unifi客户支持： [support@unifisoftware.atlassian.net](mailto:support@unifisoftware.atlassian.net)。

Unifi预期响应时间：美国正常营业时间为4小时（太平洋时间周一至周五上午9点至下午5点，节假日除外）。

>[!CAUTION]
>
>在您寻求支持协助的请求中，Adobe可能需要与Unifi共享您的Adobe Campaign实例信息。