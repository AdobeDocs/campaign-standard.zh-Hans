---
title: 使用 Segment Builder
description: 了解如何使用区段生成器创建受众。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 9a6c542e-10ed-4e77-abb3-36324e1cb38f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 3%

---

# 使用 Segment Builder {#using-the-segment-builder}

>[!IMPORTANT]
>
>Audience Destinations服务目前处于测试阶段，可能会频繁更新，恕不另行通知。 需要在Azure上托管客户（目前仅适用于北美地区的测试版）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀团队。

区段生成器允许您通过根据来自 [实时客户资料](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html).

本节介绍构建区段时的全局概念。 有关区段生成器本身的详细信息，请参阅 [区段生成器用户指南](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html).

区段生成器界面由以下部分组成：

* 左侧窗格通过将所需字段拖放到区段生成器工作区中，提供了可用于生成区段的所有属性、事件和受众。
* 中心区域提供一个工作区，用于通过定义和组合可用字段中的规则来构建区段。
* 标题和右侧窗格显示区段的属性（即，名称、描述和区段的预计合格用户档案）。

![](assets/aep_audiences_interface.png)

## 构建区段

要构建区段，请执行以下步骤：

现在，区段生成器应会显示在您的工作区中。 利用此功能，可使用Adobe Experience Platform中的数据构建区段，最终将用于创建受众。

1. 命名区段，然后输入描述（可选）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. 确保在“设置”窗格中选择所需的合并策略。

   有关合并策略的更多信息，请参阅 [区段生成器用户指南](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html).

   ![](assets/aep_audiences_mergepolicy.png)

1. 在左窗格中查找所需的字段，并将其拖到中心工作区中。

   ![](assets/aep_audiences_dragfield.png)

1. 配置与拖动字段对应的规则。

   ![](assets/aep_audiences_configure_rules.png)

1. 单击 **[!UICONTROL Create segment]** 按钮。

## 查找区段的正确字段

左侧窗格列出了可用于构建规则的所有属性、事件和受众。

所列字段是您的公司捕获的属性，已通过 [Experience Data Model(XDM)系统](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html).

字段按选项卡进行组织：

* **[!UICONTROL Attributes]**:可能源自Adobe Campaign数据库和/或Adobe Experience Platform的现有配置文件属性。 它们是指附加到用户档案的静态信息（例如，电子邮件地址、居住国家/地区、忠诚度计划状态等）。

   ![](assets/aep_audiences_attributestab.png)

* **[!UICONTROL Events]**:标识与您公司的客户接触点进行过一些交互的消费者的活动，例如“在两周内订购过两次的任何人”。 这可以从Adobe Analytics流式传输，或使用第三方ETL工具直接摄取到Adobe Experience Platform中。

   ![](assets/aep_audiences_eventstab.png)

>[!NOTE]
>
>**多实体分段** 允许您根据产品、商店或其他非配置文件类使用其他数据扩展配置文件数据。 连接后，来自其他类的数据将变得可用，就像它们是配置文件架构的本机数据一样。
>
>有关更多信息，请参阅[专用文档](https://experienceleague.adobe.com/docs/experience-platform/segmentation/multi-entity-segmentation.html)。

默认情况下，区段生成器会显示其中已存在数据的字段。 要显示完整架构（包括不存在数据的字段），请启用 **[!UICONTROL Show full XDM schema]** 选项。

![](assets/aep_audiences_populatedfields.png)

每个字段末尾的符号提供有关属性及其使用方式的其他信息。

![](assets/aep_audiences_isymbol.png)

## 定义区段的规则

>[!NOTE]
>
>以下部分提供了有关规则定义的全局信息。 有关更多信息，请参阅 [区段生成器用户指南](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html).

要构建规则，请执行以下步骤：

1. 从左侧窗格中查找字段，以反映规则所基于的属性或事件。

1. 将字段拖动到中心工作区上，然后根据所需的区段定义对其进行配置。 要实现此目的，可使用多个字符串和日期/时间函数。

   在以下示例中，规则将定向性别等于“Male”的所有用户档案。

   ![](assets/aep_audiences_malegender.png)

   与区段对应的预计群体将在 **[!UICONTROL Segment Properties]** 中。

1. 的 **[!UICONTROL View Profiles]** 按钮可预览与规则对应的前20条记录，从而快速验证区段。

   ![](assets/aep_audiences_samplepreview.png)

   您可以根据需要添加任意数量的其他规则，以定向正确的用户档案。

   将规则添加到容器时，它将附加到任何现有规则中，并包含AND逻辑运算符。 如果需要，请单击逻辑运算符以对其进行修改。

   ![](assets/aep_audiences_andoperator.png)

将这两个规则链接在一起后，即构成一个容器。

## 比较字段

区段生成器允许您比较两个字段以定义规则。 例如，其家乡地址与工作地址不同的邮政编码为女性。

为此，请执行以下步骤：

1. 将要比较的第一个字段（例如，家庭地址邮政编码）拖到中心工作区上。

   ![](assets/aep_audiences_comparing_1.png)

1. 选择将与第一个字段进行比较的第二个字段（例如，工作地址邮政编码）。

   将其拖动到与第一个字段位于同一容器中的中心工作区上 **[!UICONTROL Drop here to compare operands]** 框中。

   ![](assets/aep_audiences_comparing_2.png)

1. 根据需要在两个字段之间配置运算符。 在本例中，我们希望区段定向的用户档案的主页地址与工作地址不同。

   ![](assets/aep_audiences_comparing_3.png)

规则现已配置完毕，可随时作为受众激活。
