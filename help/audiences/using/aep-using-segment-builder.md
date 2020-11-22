---
solution: Campaign Standard
product: campaign
title: 使用 Segment Builder
description: 了解如何使用区段生成器创建受众。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 4%

---


# 使用 Segment Builder {#using-the-segment-builder}

>[!IMPORTANT]
>
>受众目标服务目前处于测试阶段，可能会在不通知的情况下频繁进行更新。 客户必须托管在Azure上（目前仅限北美的beta版），才能访问这些功能。 如果您想要访问，请联系Adobe客户服务中心。

区段生成器允许您根据来自实时受众的数据定义 [规则，从而构建用户档案](https://docs.adobe.com/content/help/zh-Hans/experience-platform/profile/home.html)。

本节介绍在构建区段时的全局概念。 有关区段生成器本身的详细信息，请参阅“区 [段生成器用户指南](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html)”。

Segment Builder界面由以下部分组成：

* 左侧窗格通过将所需字段拖放到区段生成器工作区中，提供所有可用于构建区段的属性、事件和受众。
* 中心区域通过定义和组合可用字段中的规则，提供用于构建区段的工作区。
* 标题和右侧窗格显示区段的属性(例如，名称、说明以及区段的估计合格用户档案)。

![](assets/aep_audiences_interface.png)

## 构建区段

要构建区段，请按照以下步骤操作：

区段生成器现在应显示在工作区中。 它允许您使用Adobe Experience Platform的数据构建细分，最终用于创建受众。

1. 命名区段，然后输入说明（可选）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. 确保在设置窗格中选择了所需的合并策略。

   有关合并策略的详细信息，请参阅“Segment Builder用户指 [南”中的专用部分](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html)。

   ![](assets/aep_audiences_mergepolicy.png)

1. 在左窗格中查找所需的字段，并将它们拖入中心工作区。

   ![](assets/aep_audiences_dragfield.png)

1. 配置与拖动字段对应的规则。

   ![](assets/aep_audiences_configure_rules.png)

1. 单击 **[!UICONTROL Create segment]** 按钮。

## 查找区段的正确字段

左窗格列表所有可用于构建规则的属性、事件和受众。

所列字段是公司捕获的属性，并已通过体验数据 [模型(XDM)系统提供](https://docs.adobe.com/content/help/zh-Hans/experience-platform/xdm/home.html)。

字段按选项卡进行组织：

* **[!UICONTROL Attributes]**:现有用户档案属性可能源自您的Adobe Campaign库和／或Adobe Experience Platform。 它们指附加到用户档案的静态信息(例如，电子邮件地址、居住国家／地区、忠诚项目状态等)。

   ![](assets/aep_audiences_attributestab.png)

* **[!UICONTROL Events]**:识别与公司客户接触点进行过一些交互的消费者的活动，例如“两周内订购两次的任何人”。 这可以从Adobe Analytics进行流传输，或使用第三方ETL工具直接摄入Adobe Experience Platform。

   ![](assets/aep_audiences_eventstab.png)

>[!NOTE]
>
>**多实体细分** 允许您根据产品、商店或其他非用户档案类扩展用户档案数据，并添加其他数据。 连接后，来自其他类的数据将变得像用户档案模式的本机数据一样可用。
>
>有关更多信息，请参阅[专用文档](https://docs.adobe.com/content/help/en/experience-platform/segmentation/multi-entity-segmentation.html)。

默认情况下，区段生成器显示其中已有数据的字段。 要显示完整模式（包括没有数据的字段），请从设 **[!UICONTROL Show full XDM schema]** 置中启用选项。

![](assets/aep_audiences_populatedfields.png)

每个字段末尾的符号提供了有关属性及其使用方法的附加信息。

![](assets/aep_audiences_isymbol.png)

## 定义区段规则

>[!NOTE]
>
>以下部分提供有关规则定义的全局信息。 有关此方面的详细信息，请参 [阅“Segment Builder”用户指南](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html)。

要构建规则，请按照以下步骤操作：

1. 从左侧窗格中查找反映规则所基于的属性或事件的字段。

1. 将字段拖动到中心工作区上，然后根据所需的区段定义对其进行配置。 为此，可以使用几个字符串和日期／时间函数。

   在以下示例中，规则将目标所有性别等于“Male”的用户档案。

   ![](assets/aep_audiences_malegender.png)

   在该节中自动重新计算与该段对应的估计 **[!UICONTROL Segment Properties]** 人口。

1. 按 **[!UICONTROL View Profiles]** 钮将预览前20条记录，这些记录与规则对应，使您能够快速验证区段。

   ![](assets/aep_audiences_samplepreview.png)

   您可以根据需要添加任意数量的附加规则，以便目标正确的用户档案。

   在将规则添加到容器时，它将附加到任何现有规则中的AND逻辑运算符。 如果需要，单击逻辑运算符以修改它。

   ![](assets/aep_audiences_andoperator.png)

一旦链接在一起，这两条规则就形成了容器。

## 比较字段

区段生成器允许您比较两个字段以定义规则。 例如，其家乡地址与工作地址的邮政编码不同的女性。

为此，请执行以下步骤：

1. 将要比较的第一个字段（例如，家庭地址邮政编码）拖到中心工作区上。

   ![](assets/aep_audiences_comparing_1.png)

1. 选择将与第一个字段进行比较的第二个字段（例如，工作地址邮政编码）。

   将其拖动到中心工作区上，与框中的第一个字段容器 **[!UICONTROL Drop here to compare operands]** 相同。

   ![](assets/aep_audiences_comparing_2.png)

1. 根据需要在两个字段之间配置运算符。 在此示例中，我们希望我们的区段能够将家庭地址与工作地址不同的目标用户档案。

   ![](assets/aep_audiences_comparing_3.png)

规则现已配置好，可作为受众激活。
