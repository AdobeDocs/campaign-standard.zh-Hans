---
title: 使用 Microsoft Dynamics 365 集成
description: 了解如何将Microsoft Dynamics 365与Campaign Standard集成结合使用
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: fb464183-13bf-4b47-ac27-4b785bafef37
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '1607'
ht-degree: 0%

---

# 使用Microsoft Dynamics 365集成

Adobe Campaign Standard与Microsoft Dynamics 365集成会执行多个数据流。 这些流量在 [本页](../../integrating/using/d365-acs-self-service-app-workflows.md).

有关数据流的更多详细信息，请参阅 [数据流](#data-flows)  中。

## Adobe Campaign Standard用户体验

在Microsoft Dynamics 365中创建、修改或删除联系人（如果已启用删除）后，该联系人将被发送到Campaign Standard。 这些联系人将显示在Campaign的“用户档案”屏幕中，并可在营销活动中定位。 请参阅下面的Profiles屏幕。

![](assets/MSdynamicsACS-usage1.png)

在Campaign中修改选择退出属性后，如果您选择了 **单向(营销活动到Microsoft Dynamics 365)** 或 **双向** 选择退出配置，并且如果您正确映射了该特定属性。

## Microsoft Dynamics 365用户体验

对于出口，以下电子邮件营销事件从Campaign发送到Dynamics 365，并在Microsoft Dynamics 365时间轴视图中显示为自定义活动：

* Adobe Campaign电子邮件发送

* Adobe Campaign电子邮件打开

* Adobe Campaign电子邮件URL点击

* Adobe Campaign电子邮件退回

要查看联系人的时间轴，请通过单击Dynamics 365下拉菜单中的Sales Hub ，导航到您的联系人列表。 然后，单击左侧菜单栏上的“联系人”(Contacts)，并选择一个联系人。

>[!NOTE]
>
>的 **Adobe Campaign for Microsoft Dynamics 365** 应用程序源中的应用程序需要安装在Microsoft Dynamics 365实例中，才能查看这些事件。 [了解详情](../../integrating/using/d365-acs-configure-d365.md#install-appsource-app)。

在下方，您可以看到“Dynamics用户”的“联系人”屏幕快照。 在时间轴视图中，您会注意到Dynamics用户已发送一封与促销活动名称“2019LoytayCamp”和投放名称“DM190”关联的电子邮件。 Dynamics用户打开了电子邮件，并点击了电子邮件中的URL;这两个操作都会创建事件，如下所示。 如果您看右角，将看到“关系助理”(RA)卡；目前，它包含一项跟踪所点击URL的任务。

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

有关Dynamics用户的时间轴视图的特写，请参阅下文。

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

以下是关系助理(RA)卡的特写。 AppSource应用程序包含一个可监视Adobe电子邮件URL点击事件的工作流。 发生此事件时，会创建任务并设置到期日期。 这允许任务显示在RA卡中，从而使其具有更多可见性。 Adobe电子邮件退回事件的工作流程类似，可添加一项任务以协调无效的电子邮件地址。 可以在解决方案中关闭这些工作流。

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

如果单击发送事件的主题，您将看到与下面类似的表单。 打开和跳出事件的表单类似。

![](assets/do-not-localize/mirror_page_url_send.png)

电子邮件URL点击事件的表单为已点击的URL添加了一个附加属性：

![](assets/do-not-localize/mirror_page_url_click.png)

以下是属性列表和描述：

* **主题**:活动主题；由电子邮件投放的促销活动ID和投放ID组成

* **所有者**:在预配后步骤中创建的应用程序用户

* **关于**:联系人的姓名

* **营销活动名称**:促销活动ID，Campaign Standard

* **投放名称**:投放ID(在Campaign Standard中)

* **发送/打开/点击/退回的日期**:事件的创建日期/时间

* **跟踪URL**:已点击的URL

* **镜像页面URL**:已发送/打开/单击/退回的电子邮件的镜像页面的URL。 可以在相应Campaign电子邮件渠道活动的配置屏幕中修改电子邮件镜像页面的到期期限。 [了解详情](../../administration/using/configuring-email-channel.md#validity-period-parameters)。

>[!NOTE]
>
>对于选择退出，当在Microsoft Dynamics 365中修改了选择退出属性时，如果您选择 **单向(营销活动到Microsoft Dynamics 365)** 或 **双向** 选择退出配置，并且如果您正确映射了该特定属性。

## 数据流 {#data-flows}

### 联系和自定义实体入口

新记录、更新记录和删除记录(注意：必须启用“删除”)从Microsoft Dynamics 365联系人表发送到Campaign用户档案表。

可以在集成应用程序UI中配置表映射，以将Microsoft Dynamics 365表属性映射到Campaign表属性。 可以根据需要修改表映射以添加/删除属性。

数据流的初始运行旨在传输所有映射的记录，包括标记为“不活动”的记录；随后，集成将只处理增量更新。 重播数据或配置过滤器时，会出现这种情况；可以配置基于属性的基本筛选规则，以确定要同步到Campaign的记录。

基本的替换规则可在集成应用程序UI中配置，以将属性值替换为其他值(例如，“#00FF00”为“绿色”，“F”为1，等等)。

根据记录量的不同，可能需要使用Campaign SFTP存储进行初始数据传输。 [了解详情](#initial-data-transfer)。

必须使用Dynamics 365联系人属性contactId填充Campaign配置文件表属性externalId，才能使联系人进入工作。 Campaign自定义实体还必须使用Dynamics 365唯一ID属性进行填充；但是，此属性可存储在任何Campaign自定义实体属性中（即，不必是externalId）。

>[!NOTE]
>
>对于自定义实体入口，必须在Dynamics 365中为同步的自定义实体启用更改跟踪。

#### 自定义实体

的 [Microsoft Dynamics 365-Adobe Campaign Standard集成](../../integrating/using/d365-acs-get-started.md) 支持自定义实体，使Dynamics 365中的自定义实体能够同步到Campaign中的相应自定义资源。

自定义资源中的新数据可用于多种目的，包括分段和个性化。

该集成支持链接的表和未链接的表。 最多支持三个级别（即，级别1->级别2->级别3）的链接。

>[!IMPORTANT]
>
>如果任何Campaign自定义资源记录包含个人信息，则应用特定推荐。 了解更多 [在此部分中](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-data).

配置自定义实体数据流时，请务必注意以下事项：

* 创建和修改Campaign自定义资源是敏感操作，必须仅由专家用户执行。
* 对于自定义实体数据流，必须在Dynamics 365中为同步的自定义实体启用更改跟踪。
* 如果由于集成的并行处理，在Dynamics 365中几乎同时创建了父记录和链接的子记录，则在其父记录之前，可能会略有可能将新子记录写入Campaign。

* 如果父项和子项在营销活动端使用 **1个基数简单链接** 选项，则在父记录到达Campaign之前，子记录将保持隐藏状态且不可访问（通过UI或API）。

* (假定 **1个基数简单链接** （在Campaign中）如果子记录在Dynamics 365中更新或删除，并且该更改在父记录在Campaign中显示之前写入Campaign（不可能，但是是远程可能），则该更新或删除不会在Campaign中处理，并且会引发错误。 在更新时，需要在Dynamics 365中再次更新相关记录，以同步更新的记录。 在删除的情况下，需要在Campaign端单独处理相关记录，因为Dynamics 365中不再有要删除或更新的记录。

* 如果您遇到这样一种情况，即您认为自己有隐藏的子记录并且无法访问这些记录，则可以临时将基数链接类型更改为 **0或1个基数简单链接** 来访问这些记录。

可以找到Campaign自定义资源的更全面概述 [在此部分中](../../developing/using/key-steps-to-add-a-resource.md).

### 电子邮件营销事件流程{#email-marketing-event-flow}

电子邮件营销事件从Campaign发送到Microsoft Dynamics 365，以显示在时间轴视图中。

支持的营销事件类型：
* 发送 — 发送给收件人的电子邮件
* 打开 — 收件人打开的电子邮件
* Click — 收件人点击的电子邮件中的URL
* 跳出 — 电子邮件发送给收件人时遇到硬退回

Dynamics 365中显示以下事件属性：
* 营销活动名称
* 电子邮件投放名称
* 时间戳
* 电子邮件镜像页面URL
* 已单击URL（仅限点击事件）

可以按类型启用/禁用电子邮件营销事件（发送、打开、单击、退出），以便仅将您选择的事件类型传递到Dynamics 365。

### 选择退出流程 {#opt-out-flow}

选择退出（例如）值阻止列表在系统之间进行同步；载入时，您可以选择以下选项：

* **单向(Microsoft Dynamics 365到Campaign)**:Dynamics 365是选择退出的真相来源。 选择退出属性将在从Dynamics 365到Campaign Standard的一个方向上同步”
* **单向(营销活动到Microsoft Dynamics 365)**:Campaign Standard是选择退出的真相来源。 选择退出属性将在从Campaign Standard到Dynamics 365的一个方向上进行同步
* **双向**:Dynamics 365 ANDCampaign Standard都是真理的来源。 选择退出属性将在Campaign Standard和Dynamics 365之间双向同步

或者，如果您有一个单独的流程来管理系统之间的选择退出同步，则可以禁用集成的选择退出数据流。

>[!NOTE]
>
>在集成应用程序UI中， **单向(Microsoft Dynamics 365到Campaign)** 和 **双向** 选择退出用例在单独的选择退出工作流程中进行配置。 [了解详情](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)。
>
>的 **单向(营销活动到Microsoft Dynamics 365)** 选择退出用例是例外；在入口（联系用户档案）工作流中配置。

选择退出流程映射由客户指定，因为不同公司之间的业务要求可能不同。 在营销活动端，只能使用OOTB选择退出属性进行选择退出映射：

* 阻止列表
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPushnotification
* ccpaOptOut

在Dynamics 365中，大多数选择退出字段都带有“donot”前缀；但是，如果数据类型兼容，您还可以将其他属性用于选择退出目的。

### 初始数据传输 {#initial-data-transfer}

初始数据传输可能需要一些时间，具体取决于您从Microsoft Dynamics 365中摄取的记录数。 初始数据传输后，集成将会获取增量更新。
