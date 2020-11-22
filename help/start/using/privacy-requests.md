---
solution: Campaign Standard
product: campaign
title: 隐私请求
description: 了解如何在Adobe Campaign Standard管理隐私请求
audience: start
content-type: reference
topic-tags: discovering-the-interface
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1711'
ht-degree: 0%

---


# 管理隐私请求 {#privacy-requests}

有关隐私管理的一般演示文稿，请参 [阅本节](../../start/using/privacy-management.md)。

此信息适用于GDPR、CCPA、PDPA和LGPD。 For more on these regulations, see [this section](../../start/using/privacy-management.md#privacy-management-regulations).

CCPA特有的个人信息销售选择退出部分将在本节 [中说明](#sale-of-personal-information-ccpa)。

>[!IMPORTANT]
>
>从19.4开始，已弃用访问和删除请求的活动API和接口。 对于任何GDPR、CCPA、PDPA或LGPD访问和删除请求，您需要使用隐私核 [心服务集成](#create-privacy-request) 方法。

## 关于隐私请求 {#about-privacy-requests}

为了帮助您提高隐私准备，Adobe Campaign允许您处理访问和删除请求。 本 **节介绍了** “访问权 **”和“被遗忘权** （删除请求）” [等内容](../../start/using/privacy-management.md#right-access-forgotten)。

要执行这些请求，您必须使用隐 **私核心服务** 集成。 从隐私核心服务推送到所有Experience Cloud解决方案的隐私请求由活动通过专用工作流自动处理。

### 先决条件{#prerequesites}

Adobe Campaign优惠数据管理者工具，用于创建和处理Adobe Campaign中存储的数据的隐私请求。 但是，数据管理者有责任处理与数据主体（电子邮件、客户关怀或门户网站）的关系。

因此，您作为数据管理者的责任是确认发出请求的数据主体的身份，并确认返回给请求者的数据与数据主体有关。

>[!NOTE]
>
>有关个人数据以及管理数据的不同实体（数据控制者、数据处理者和数据主体）的详细信息，请参 [阅个人数据和角色](../../start/using/privacy.md#personal-data)。

### 命名空间 {#namesspaces}

在创建隐私请求之前，您需要定义要使用的命名空间。 命名空间是用于在Adobe Campaign数据库中标识数据主体的键。 现成提供两种命名空间:电子邮件和手机。 如果您需要其他命名空间(例如，用户档案自定义字段)，请按照以下步骤操作。

另请参阅本 [教程](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/namespaces-for-privacy-requests.html?lang=en#privacy) ，了解如何创建命名空间。

>[!NOTE]
>
>如果您使用多个命名空间，则需要为每个命名空间创建一个隐私请求。

1. Click the Adobe Campaign logo in the top left corner, then select **[!UICONTROL Administration]** > **[!UICONTROL Namespaces]**.

   ![](assets/privacy-namespaces.png)

1. 在命名空间列表中，单击 **[!UICONTROL Create]**。

   ![](assets/privacy-namespace-create.png)

1. 输入 **[!UICONTROL Label]**。

   ![](assets/privacy-namespace-label.png)

1. 如果要使用现有标识服务命名空间，请选 **[!UICONTROL Map from Identity Namespace Service]** 择列表并从命名空间中选择 **[!UICONTROL Identity Service Namespaces]** 。

   ![](assets/privacy-map-from-namespace.png)

   如果要在中创建新命名空间并在活动 **[!UICONTROL Identity Service]** 中进行映射，请选 **[!UICONTROL Create new]** 择并在字段中输入 **[!UICONTROL Identity namespace name]** 名称。

   ![](assets/privacy-create-new-namespace.png)

   要进一步了解身份命名空间，请参阅 [Experience Platform文档](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=en) 。

1. 一个身份服务命名空间映射到活动中的一个命名空间。 您需要指定如何在命名空间中协调活动。

   选择目标映射&#x200B;**[!UICONTROL Recipients]**( **[!UICONTROL Real-time event]** 或 **[!UICONTROL Subscriptions to an application]**)。 如果要使用多个目标映射，您需要为每个目标映射创建一个命名空间。

   ![](assets/privacy-namespace-target-mapping.png)

1. 选择 **[!UICONTROL Reconciliation key]**。 此字段将用于在Adobe Campaign库中标识数据主体。

   ![](assets/privacy-namespace-reconciliation-key.png)

1. 单击 **[!UICONTROL Create]**。您现在可以根据新命名空间创建隐私请求。 如果您使用多个命名空间，则需要为每个命名空间创建一个隐私请求。

### Creating a Privacy request {#create-privacy-request}

>[!IMPORTANT]
>
>隐私 **核心服务集** 成是您应用于所有访问和删除请求的方法。
>
>从19.4开始，已弃用访问和删除请求的活动API和接口。 对任何GDPR、CCPA、PDPA或LGPD访问和删除请求使用核心Privacy Service。

隐私核心服务集成允许您通过单个JSON API调用在多解决方案上下文中自动处理您的隐私请求。 从隐私核心服务推送到所有Experience Cloud解决方案的隐私请求由活动通过专用工作流自动处理。

请参阅 [Experience PlatformPrivacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) 文档，了解如何从隐私核心服务创建隐私请求。

在活动中，每个隐私核心服务作业被划分为多个隐私请求，这取决于使用的命名空间数，一个请求对应于一个命名空间。 此外，一个作业可以在多个实例上运行。 因此，为一个作业创建多个文件。 例如，如果一个请求具有两个命名空间，并且在三个实例上运行，则总共会发送六个文件。 每个命名空间和实例一个文件。

文件名的模式为： `<InstanceName>-<NamespaceId>-<ReconciliationKey>.xml`

* **实例名称**:活动实例名称
* **命名空间Id**:已使用的命名空间的标识服务命名空间ID
* **合并关键项**:编码合并关键项

### 资源列表 {#list-of-resources}

执行删除或访问隐私请求时，Adobe Campaign会根据所有资源中具有指向用户档案资源（自有类型）链接的“对帐 **** ”值搜索所有数据主体的数据。

以下是执行隐私请求时考虑的现成资源列表:

* 用户档案语(收件人)
* 用户档案投放日志语(broadLogRcp)
* 用户档案跟踪日志语(trackingLogRcp)
* 投放日志语(订阅到应用程序)(broadLogAppSubRcp)
* 跟踪日志语(订阅到应用程序)(trackingLogAppSubRcp)
* 订阅到应用程序(appSubscriptionRcp)
* 订阅历史用户档案(subHistoRcp)
* 用户档案订阅(subscriptionRcp)
* 访客语(访客)

如果您创建的自定义资源具有指向用户档案资源（自己的类型）的链接，则也会考虑这些资源。 例如，如果您有一个事务处理资源链接到用户档案资源，而一个事务处理详细信息资源链接到事务处理资源，则这两个资源都将被考虑在内。

另请参阅 [本教程](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/custom-resources-for-privacy-requests.html?lang=en#privacy) ，了解如何修改自定义资源。

要使此功能正常工作，您需要在自定 **[!UICONTROL Deleting the target record implies deleting records referenced by the link]** 义资源中选择选项：

1. Click the Adobe Campaign logo in the top left corner, then select **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**.

1. 选择包含指向用户档案资源（自有类型）的链接的自定义资源。

1. 单击该 **[!UICONTROL Links]** 部分。

1. 对于每个链接，单击铅笔图标(**[!UICONTROL Edit properties]**)。

1. In the **[!UICONTROL Behavior if deleted/duplicated]** section, select the **[!UICONTROL Deleting the target record implies deleting records referenced by the link]** option.

   ![](assets/privacy-cus-resource-option.png)

### 隐私请求状态 {#privacy-request-statuses}

以下是隐私请求的不同状态：

* **[!UICONTROL New]** / **[!UICONTROL Retry pending]**:正在进行中，该工作流尚未处理请求。
* **[!UICONTROL Processing]** / **[!UICONTROL Retry in progress]**:工作流正在处理请求。
* **[!UICONTROL Delete pending]**:该工作流已确定要删除的所有收件人数据。
* **[!UICONTROL Delete in progress]**:工作流正在处理删除。
   <!--**[!UICONTROL Delete Confirmation Pending]** (Delete request in 2-steps process mode): the workflow has processed the Access request. Manual confirmation is requested to perform the deletion. The button is available for 15 days.-->
* **[!UICONTROL Complete]**:请求的处理已完成，无错误。
* **[!UICONTROL Error]**:工作流遇到错误。 原因显示在列的隐私请求列表 **[!UICONTROL Request status]** 中。 例如， **[!UICONTROL Error data not found]** 表示在收件人库中找不到与数据主体 **[!UICONTROL Reconciliation value]** 匹配的数据。

### 禁用2步进程 {#disabling-two-step-process}

核心Privacy Service不支持2步流程。

>[!IMPORTANT]
>
>在使用核心Privacy Service集成管理您的隐私请求之前，您必须禁用从Campaign Standard界面删除请求的两步流程。

如果未禁用此选项，则通过隐私核心服务管理的所有删除请求将保持挂起状态，且将无法完成。

默认情况下，将激活两步流程。

要更改此模式， **[!UICONTROL Edit properties]**&#x200B;请单击屏幕右上角的， **[!UICONTROL Privacy Requests]** 然后取消选中 **[!UICONTROL Activate the 2-step process]** 选项。

![](assets/privacy-disable-2-step-process.png)

## 选择退出个人信息销售 (CCPA) {#sale-of-personal-information-ccpa}

The **California Consumer Privacy Act** (CCPA) provides California residents new rights in regards to their personal information and imposes data protection responsibilities on certain entities whom conduct business in California.

访问和删除请求的配置和使用方式对GDPR和CCPA都是通用的。 本节介绍个人数据的销售选择，具体内容取决于CCPA。

除了Adobe Campaign提 [供的](../../start/using/privacy-management.md#consent-management) “同意”管理工具外，您还可以跟踪消费者是否已选择出售个人信息。

消费者通过您的系统决定不允许将其个人信息销售给第三方。 在Adobe Campaign中，您将能够存储和跟踪此信息。

>[!NOTE]
>
>您可以通过活动界面和API选择退出销售个人信息。 您不能通过隐私核心服务使用它。

>[!IMPORTANT]
>
>您作为数据管理者有责任接收数据主体的请求并跟踪CCPA的请求日期。 作为技术提供商，我们只提供一种选择退出的方式。 有关您作为数据管理者的角色的更多信息，请参 [阅个人数据和角色](../../start/using/privacy.md#personal-data)。

### 自定义表的先决条件 {#ccpa-prerequisite}

从19.4开 **[!UICONTROL CCPA Opt-Out]** 始，该字段在活动接口和API中现成提供。 默认情况下，该字段可用于标准 **[!UICONTROL Profile]** 资源。

如果您使用自定义用户档案资源，则需要扩展该资源并添加字段。 我们建议您使用不同于现成字段的名称，例如： **[!UICONTROL Opt-Out for CCPA]** (optoutccpa)。 创建新字段时，活动API将自动支持该字段。

有关如何扩展用户档案资源的更多详细信息，请参 [阅此部分](../../developing/using/extending-the-profile-resource-with-a-new-field.md)。

>[!NOTE]
>
>修改资源是一个敏感操作，只能由专家用户执行。

1. 转到 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**。 单击自定义用户档案资源。 有关扩展资源的详细信息，请参 [阅此部分](../../developing/using/creating-or-extending-the-resource.md)。

   ![](assets/privacy-ccpa-extend-cus.png)

1. 单击 **[!UICONTROL Add field]** 或， **[!UICONTROL Create Element]**&#x200B;添加标签、ID并选择 **[!UICONTROL Boolean]** 类型。 对于名称，请 **对CCPA使用退出**。 对于ID，请使用： **optOutCcpa**。

   ![](assets/privacy-ccpa-extend-field.png)

1. 在选项 **[!UICONTROL Screen definition]** 卡的下 **[!UICONTROL Detail screen configuration]**&#x200B;面，添加字段并选择 **[!UICONTROL Input field]**。 这将使该字段在用户档案列表和详细信息中可用。  有关配置屏幕定义的详细信息，请参 [阅此部分](../../developing/using/configuring-the-screen-definition.md)。

   ![](assets/privacy-ccpa-extend-screen.png)

1. 转到> **[!UICONTROL Administration]** > **[!UICONTROL Development]** ，准 **[!UICONTROL Publishing]**&#x200B;备发布并发布修改。 有关发布资源的详细信息，请参 [阅此部分](../../developing/using/updating-the-database-structure.md)。

   ![](assets/privacy-ccpa-extend-pub.png)

1. 验证字段是否可用于用户档案的详细信息。 有关更多信息，请参阅[此章节](#usage)。

### 使用情况 {#usage}

数据管理者有责任填写现场价值，并遵循CCPA关于数据销售的准则和规则。

要填充这些值，可使用以下几种方法：

* 通过编辑活动的详细信息（请参阅下文），使用收件人的界面
* 使用活动隐私API(请参阅 [API文档](../../api/using/managing-ccpa-opt-out.md))
* 通过数据导入工作流

然后，您应确保永远不要向任何第三方销售已选择退出的用户档案的个人信息。

1. 在活动的界面中，编辑用户档案以更改退出状态。

   ![](assets/privacy-ccpa-profile-opt-out.png)

1. 当字段的值为时， **[!UICONTROL True]**&#x200B;该信息将显示在用户档案的详细信息上。

   ![](assets/privacy-ccpa-profile-opt-out-true.png)

1. 您可以配置用户档案列表以显示输出列。 要了解如何配置列表，请参 [阅此部分](../../start/using/customizing-lists.md)。

   ![](assets/privacy-ccpa-profile-configure-list.png)

1. 您可以单击该列，根据退出信息对收件人进行排序。

   ![](assets/privacy-ccpa-profile-sorting.png)
