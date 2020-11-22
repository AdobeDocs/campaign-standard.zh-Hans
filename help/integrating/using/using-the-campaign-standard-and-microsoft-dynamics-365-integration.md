---
solution: Campaign Standard
product: campaign
title: 使用 Microsoft Dynamics 365 集成
description: 了解如何通过Campaign Standard集成使用Microsoft Dynamics 365
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1186'
ht-degree: 0%

---


# 使用 Microsoft Dynamics 365 集成

此集成可执行以下几个作业：

* **入口**:

   * 将联系人 **从** Dynamics 365导入活动

   * **自定义实体**:将自定义表从Dynamics 365引入活动。 在本节 [中了解更多](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md)。

* **出口**:将电子邮件营销事件从ACS导入D365（电子邮件发送、打开、单击、弹出）

* **选择退出**:双向同步退出状态(例如阻止列表)

有关数据流的更多详细信息，请 [参阅本节](#data-flows)。

## Adobe Campaign Standard用户体验

在Dynamics 365中创建或修改（或删除，如果启用）联系人后，该联系人将发送到活动。  这些联系人将显示在活动的用户档案屏幕中，并可定位在营销活动中。  查看下面的用户档案屏幕。

![](assets/MSdynamicsACS-usage1.png)

在活动中修改退出属性后，如果您选择了活动到Dynamics 365或双向退出配置，并且您正确映射了该特定属性，则该属性将反映在Dynamics 365中。

## Microsoft Dynamics 365用户体验

对于出口，以下电子邮件营销事件从活动发送到Dynamics 365并在Dynamics 365时间轴视图中显示为自定义活动:

* Adobe Campaign电子邮件发送

* Adobe Campaign电子邮件打开

* Adobe Campaign电子邮件URL单击

* Adobe Campaign电子邮件弹回

要视图联系人的时间轴，请通过单击Dynamics 365下拉菜单中的Sales Hub，导航到您的联系人列表。  然后，单击左侧菜单栏上的“联系人”并选择联系人。

>[!NOTE]
>
>AppSource中Dynamics 365应用程序的Adobe Campaign需要安装在Dynamics 365实例中，才能视图这些事件。

在下面，您可以看到“Dynamics用户”的“联系人”屏幕的快照。  在“时间轴”视图中，您会注意到Dynamics用户已收到一封与活动名“2019LoyaltyCamp”和投放名“DM190”相关的电子邮件。  Dynamics用户打开了电子邮件，并点击了电子邮件中的URL;这两个操作都创建了事件，如下所示。  如果您看到右角，您将看到“关系助手”(RA)卡；当前，它包含一个任务，用于跟踪单击的URL。

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

有关Dynamics用户的时间轴视图的特写，请参见下文。

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

以下是关系助理(RA)卡的特写。  AppSource应用程序包含一个工作流，它监视Adobe电子邮件URL单击事件。  发生此事件时，它会创建任务并设置到期日。  这允许任务显示在RA卡中，从而增加其可见性。  Adobe电子邮件弹回事件也有一个类似的工作流，可添加一个任务来协调无效的电子邮件地址。  在解决方案中可以关闭这些工作流。

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

如果单击发送事件的主题，您将看到一个与下面类似的表单。  打开和弹回事件的表单类似。

![](assets/do-not-localize/mirror_page_url_send.png)

电子邮件url单击事件的表单为已单击的URL添加一个附加属性：

![](assets/do-not-localize/mirror_page_url_click.png)

以下是属性的列表和说明：

* 主题：事件;由电子邮件活动的投放ID和投放ID组成

* 所有者：在预配后步骤中创建的应用程序用户

* 关于：联系人的姓名

* 活动名：活动ID在Campaign Standard

* 投放名：投放ID在Campaign Standard

* 发送／打开／单击／退回日期：创建事件的日期／时间

* 跟踪URL:已点击的URL

* 镜像页面URL:发送／打开／单击／弹回的电子邮件镜像页面的URL

>[!NOTE]
>
>可以在相应镜像页面电子邮件渠道的配置屏幕中修改电子邮件活动的到期期间(请参 [阅有效期参数](../../administration/using/configuring-email-channel.md#validity-period-parameters))。

>[!NOTE]
>
>对于选择退出，当在Dynamics 365中修改了选择退出属性时，如果您已选择Dynamics 365到活动或双向选择退出配置，并且您正确映射了该特定属性，该属性将反映在活动中。

## 数据流 {#data-flows}

### 联系人和自定义实体入口

新记录和更新（如果已启用，则删除）记录将从Dynamics 365联系表发送到活动用户档案表。

表映射可以配置为将Dynamics 365表属性映射到活动表属性。 可以根据需要修改表映射以添加／删除属性。

数据流的初始运行旨在传输所有映射的记录，包括那些标为“非活动”的记录；随后，集成将只处理增量更新。 这的例外是，如果配置了过滤器；可以配置基于属性的基本筛选规则，以确定要同步到活动的记录。

基本替换规则可配置为用不同的值替换属性值（例如，“#00FF00”为“green”,“F”为1等）。

根据记录的数量，可能需要使用活动SFTP存储进行初始数据传输。  请参阅“初始数据传输”一节。

活动用户档案表属性externalId必须填充Dynamics 365联系人属性contactId，以使联系人进入工作。 活动自定义实体还必须填充Dynamics 365唯一ID属性；但是，此属性可以存储在任何活动自定义实体属性（即，不必是externalId）中。

>[!NOTE]
>
>对于自定义实体入口，必须在Dynamics 365中为同步的自定义实体启用更改跟踪。

### 电子邮件营销事件流

电子邮件营销事件从活动发送到Dynamics 365以显示在时间轴视图中。

支持的营销事件类型:
* 发送——发送电子邮件至收件人
* 打开——由收件人打开的电子邮件
* 单击-收件人单击电子邮件中的URL
* 弹回——向收件人发送电子邮件时遇到硬弹回

D365中显示以下事件属性：
* 营销活动名称
* 电子邮件投放名称
* 时间戳
* 电子邮件镜像页面URL
* 已单击URL(仅单击事件)

电子邮件营销事件可以按类型启用／禁用（发送、打开、单击、弹出），这样只有您选择的事件类型才会传递到Dynamics 365。

### 退出流程

退出（例如）值阻止列表在系统之间同步；在入门时，您可以选择以下选项：
* Dynamics 365是退出选择的真相来源：退出属性将沿一个方向从Dynamics 365同步到Campaign Standard
* Campaign Standard是选择退出的真相来源：退出属性将沿一个方向从Campaign Standard同步到Dynamics 365
* Dynamics 365 ANDCampaign Standard既是真理的源泉：退出属性将在Campaign Standard和Dynamics 365之间双向同步

或者，如果您有单独的过程来管理系统之间的退出同步，则可禁用集成的退出数据流。

选择退出流映射由客户指定，因为不同公司之间的业务要求可能不同。  在活动端，只能使用OOTB退出属性进行退出映射：
* 阻止列表
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPushnotification
* ccpaOptOut

在Dynamics 365中，大多数选择退出字段带有“donot”前缀；但是，如果数据类型兼容，您也可以使用其他属性进行退出。

### 初始数据传输

需要将超过50万条记录的Dynamics 365表导出到活动SFTP存储，以便通过活动工作流导入。

初始数据传输是基于文件的一次性数据传输。 数据传输后，集成将使用API进行增量更新。
