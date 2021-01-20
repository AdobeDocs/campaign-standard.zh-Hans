---
title: 使用 Microsoft Dynamics 365 集成
description: 了解如何通过Campaign Standard集成使用Microsoft Dynamics 365
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: fe5d40235abc33c0ea7e929cd2e69b7030cea0b1
workflow-type: tm+mt
source-wordcount: '1607'
ht-degree: 0%

---


# 使用Microsoft Dynamics 365集成

Adobe Campaign Standard与Microsoft Dynamics 365集成可以执行若干数据流。 这些流在[此页](../../integrating/using/d365-acs-self-service-app-workflows.md)中有详细介绍。

有关数据流的更多详细信息，请在[文档流](#data-flows)部分中进一步查找。

## Adobe Campaign Standard用户体验

在Microsoft Dynamics 365中创建、修改或删除联系人（如果已启用删除）后，该联系人将发送到Campaign Standard。 这些联系人将显示在活动的用户档案屏幕中，并可定位在营销活动中。 查看下面的用户档案屏幕。

![](assets/MSdynamicsACS-usage1.png)

在活动中修改退出属性后，如果已选择&#x200B;**单向(活动到Microsoft Dynamics 365)**&#x200B;或&#x200B;**双向**&#x200B;选择退出配置，并且您正确映射了该特定属性，则该属性将反映在Dynamics 365中。

## Microsoft Dynamics 365用户体验

为了进展，以下电子邮件营销事件从活动发送到Dynamics 365，并在Microsoft Dynamics 365时间轴视图中以自定义活动显示：

* Adobe Campaign电子邮件发送

* Adobe Campaign电子邮件打开

* Adobe Campaign电子邮件URL单击

* Adobe Campaign电子邮件弹回

要视图联系人的时间轴，请通过单击Dynamics 365下拉菜单中的Sales Hub，导航到您的联系人列表。 然后，单击左侧菜单栏上的“联系人”并选择联系人。

>[!NOTE]
>
>AppSource中的&#x200B;**Microsoft Dynamics 365**&#x200B;应用程序的Adobe Campaign需要安装在Microsoft Dynamics 365实例中，才能视图这些事件。 [了解详情](../../integrating/using/d365-acs-configure-d365.md#install-appsource-app)。

在下面，您可以看到“Dynamics用户”的“联系人”屏幕的快照。 在“时间轴”视图中，您会注意到Dynamics用户已收到一封与活动名“2019LoyaltyCamp”和投放名“DM190”相关的电子邮件。 Dynamics用户打开了电子邮件，并点击了电子邮件中的URL;这两个操作都创建了事件，如下所示。 如果您看到右角，您将看到“关系助手”(RA)卡；当前，它包含一个任务，用于跟踪单击的URL。

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

有关Dynamics用户的时间轴视图的特写，请参见下文。

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

以下是关系助理(RA)卡的特写。 AppSource应用程序包含一个工作流，它监视Adobe电子邮件URL单击事件。 发生此事件时，它会创建任务并设置到期日。 这允许任务显示在RA卡中，从而增加其可见性。 Adobe电子邮件弹回事件也有一个类似的工作流，可添加一个任务来协调无效的电子邮件地址。 在解决方案中可以关闭这些工作流。

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

如果单击发送事件的主题，您将看到一个与下面类似的表单。 打开和弹回事件的表单类似。

![](assets/do-not-localize/mirror_page_url_send.png)

电子邮件url单击事件的表单为已单击的URL添加一个附加属性：

![](assets/do-not-localize/mirror_page_url_click.png)

以下是属性的列表和说明：

* **主题**:事件;由电子邮件活动的投放ID和投放ID组成

* **所有者**:在预配后步骤中创建的应用程序用户

* **关于**:联系人的姓名

* **活动名**:活动ID在Campaign Standard

* **投放名**:投放ID在Campaign Standard

* **发送／打开／单击／退回日期**:创建事件的日期／时间

* **跟踪URL**:已点击的URL

* **镜像页面URL**:发送／打开／单击／弹回的电子邮件镜像页面的URL。电子邮件镜像页面的到期期可以在相应活动电子邮件渠道活动的配置屏幕中修改。 [了解详情](../../administration/using/configuring-email-channel.md#validity-period-parameters)。

>[!NOTE]
>
>对于选择退出，当在Microsoft Dynamics 365中修改了选择退出属性时，如果您选择了&#x200B;**单向(活动到Microsoft Dynamics 365)**&#x200B;或&#x200B;**双向**&#x200B;选择退出配置，并且您正确映射了该特定属性，则选择退出属性将反映在活动中。

## 数据流{#data-flows}

### 联系人和自定义实体入口

新记录、更新记录和删除记录(注意：必须启用删除)从Microsoft Dynamics 365联系表发送到活动用户档案表。

可以在集成应用程序UI中配置表映射，以将Microsoft Dynamics 365表属性映射到活动表属性。 可以根据需要修改表映射以添加／删除属性。

数据流的初始运行旨在传输所有映射的记录，包括那些标为“非活动”的记录；随后，集成将只处理增量更新。 这种情况的例外是，如果重播数据或配置了过滤器；可以配置基于属性的基本筛选规则，以确定要同步到活动的记录。

基本的替换规则可在集成应用程序UI中配置，以用其他值替换属性值（例如，“#00FF00”为“green”,“F”为1等）。

根据记录的数量，可能需要使用活动SFTP存储进行初始数据传输。 [了解详情](#initial-data-transfer)。

活动用户档案表属性externalId必须填充Dynamics 365联系人属性contactId，以使联系人进入工作。 活动自定义实体还必须填充Dynamics 365唯一ID属性；但是，此属性可以存储在任何活动自定义实体属性（即，不必是externalId）中。

>[!NOTE]
>
>对于自定义实体入口，必须在Dynamics 365中为同步的自定义实体启用更改跟踪。

#### 自定义实体

[Microsoft Dynamics 365-Adobe Campaign Standard集成](../../integrating/using/d365-acs-get-started.md)支持自定义实体，使Dynamics 365中的自定义实体能够同步到活动中的相应自定义资源。

自定义资源中的新数据可用于多种用途，包括细分和个性化。

集成支持链接表和非链接表。 链接最多支持三个级别（即级别1->级别2->级别3）。

>[!IMPORTANT]
>
>如果任何活动自定义资源记录包含个人信息，则应用特定建议。 请阅读本节](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-data)了解更多信息。[


配置自定义实体数据流时，务必注意以下事项：

* 创建和修改活动自定义资源是敏感操作，必须由专家用户执行。
* 对于自定义实体数据流，必须在Dynamics 365中为同步的自定义实体启用更改跟踪。
* 如果在Dynamics 365中，父记录和链接的子记录在接近同一时间创建，则由于集成的并行处理，新的子记录在其父记录之前被写入活动的可能性很小。

* 如果使用&#x200B;**1基数简单链接**&#x200B;选项在活动端链接父记录和子记录，则子记录将保持隐藏且不可访问（通过UI或API），直到父记录到达活动。

* (假定&#x200B;**1基数简单链接**&#x200B;在活动中)如果在Dynamics 365中更新或删除子记录，并且该更改在父记录以活动显示之前写入活动（不太可能，但是可能是远程），则该更新或删除在活动中不会处理，并且将引发错误。 在更新的情况下，需要在Dynamics 365中再次更新相关记录，以同步更新的记录。 在删除的情况下，相关记录需要在活动端单独处理，因为Dynamics 365中不再有要删除或更新的记录。

* 如果您遇到这样的情况，即您认为自己有隐藏的子记录并且无法访问这些记录，则可以将基数链接类型临时更改为&#x200B;**0或1基数简单链接**&#x200B;以访问这些记录。

有关活动自定义资源的更全面概述，请参阅此部分](../../developing/using/key-steps-to-add-a-resource.md)。[

### 电子邮件营销事件流{#email-marketing-event-flow}

电子邮件营销事件从活动发送到Microsoft Dynamics 365以显示在时间轴视图中。

支持的营销事件类型:
* 发送——发送电子邮件至收件人
* 打开——由收件人打开的电子邮件
* 单击-收件人单击电子邮件中的URL
* 弹回——向收件人发送电子邮件时遇到硬弹回

Dynamics 365中显示以下事件属性：
* 营销活动名称
* 电子邮件投放名称
* 时间戳
* 电子邮件镜像页面URL
* 已单击URL(仅单击事件)

电子邮件营销事件可以按类型启用／禁用（发送、打开、单击、弹出），这样只有您选择的事件类型才会传递到Dynamics 365。

### 退出流{#opt-out-flow}

退出（例如）值阻止列表在系统之间同步；在入门时，您可以选择以下选项：

* **单向(Microsoft Dynamics 365到活动)**:Dynamics 365是退出的真相。退出属性将沿一个方向从Dynamics 365同步到Campaign Standard”
* **单向(活动到Microsoft Dynamics 365)**:Campaign Standard是选择退出的真相来源。退出属性将沿一个方向从Campaign Standard同步到Dynamics 365
* **双向**:Dynamics 365和Campaign Standard都是真理的源泉。退出属性将在Campaign Standard和Dynamics 365之间双向同步

或者，如果您有单独的过程来管理系统之间的退出同步，则可禁用集成的退出数据流。

>[!NOTE]
>
>在集成应用程序UI中，在单独的退出工作流中配置&#x200B;**单向(Microsoft Dynamics 365到活动)**&#x200B;和&#x200B;**双向**&#x200B;选择退出用例。 [了解详情](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)。
>
>**单向(活动到Microsoft Dynamics 365)**&#x200B;选择退出用例是例外；在入口(与用户档案联系)工作流中配置。


选择退出流映射由客户指定，因为不同公司之间的业务要求可能不同。 在活动端，只能使用OOTB退出属性进行退出映射：

* 阻止列表
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPushnotification
* ccpaOptOut

在Dynamics 365中，大多数选择退出字段带有“donot”前缀；但是，如果数据类型兼容，您也可以使用其他属性进行退出。

### 初始数据传输{#initial-data-transfer}

初始数据传输可能需要一段时间，具体取决于您从Microsoft Dynamics 365中摄取的记录数。 初始数据传输后，集成将获取增量更新。
