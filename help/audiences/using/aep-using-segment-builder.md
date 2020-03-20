---
title: 使用统一的区段生成器
description: 了解如何使用统一的细分构建器创建受众。
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fcb6a145b19b68865babba659bf0bfb7623397c8

---


# 使用统一的区段生成器 {#using-the-unified-segment-builder}

>[!IMPORTANT]
>
>受众目标服务目前处于测试阶段，可能会在不另行通知的情况下频繁进行更新。 客户必须托管在Azure上（目前仅针对北美）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀。

Unified Segment Builder允许您根据来自Unified Profile Service的数据定义规则，从而建立 [受众](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation.html)。

本节介绍构建区段时的全局概念。 有关“统一的区段生成器”本身的详细信息，请参阅“区 [段生成器”用户指南](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)。

统一的区段生成器界面由以下部分组成：

* 左侧窗格通过将所需字段拖放到区段生成器工作区中，提供所有可用于构建区段的属性、事件和受众。
* 中心区域通过定义和组合可用字段中的规则，为构建区段提供工作区。
* 标题和右侧窗格显示区段的属性（例如，区段的名称、说明和估计的合格配置文件）。

![](assets/aep_audiences_interface.png)

## 构建区段

要构建区段，请执行以下步骤：

统一的区段生成器现在应显示在工作区中。 它允许您使用Adobe Experience Platform中的数据构建细分，最终用于创建受众。

1. 为区段命名，然后输入说明（可选）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. 确保在设置窗格中选择了所需的合并策略。

   有关合并策略的详细信息，请参阅“区段生成器”用户指 [南中的专用部分](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)。

   ![](assets/aep_audiences_mergepolicy.png)

1. 在左侧窗格中查找所需的字段，并将其拖动到中心工作区中。

   ![](assets/aep_audiences_dragfield.png)

1. 配置与拖动的字段对应的规则。

   ![](assets/aep_audiences_configure_rules.png)

1. Click the **[!UICONTROL Create segment]** button.

## 查找区段的正确字段

左侧窗格列出可用于构建规则的所有属性、事件和受众。

列出的字段是您的公司捕获的属性，并已通过体验数据模型( [XDM)系统提供](https://www.adobe.io/apis/experienceplatform/home/xdm.html)。

字段按选项卡进行组织：

* **[!UICONTROL Attributes]**:可能源自您的Adobe Campaign数据库和／或Adobe Experience Platform的现有配置文件属性。 它们指附加到个人资料的静态信息（例如，电子邮件地址、居住国家／地区、忠诚度计划状态等）。

   ![](assets/aep_audiences_attributestab.png)

* **[!UICONTROL Events]**:识别与贵公司客户接触点进行过某种互动的消费者的活动，例如“两周内订购两次的任何人”。 这可以从Adobe Analytics流式传输，或使用第三方ETL工具直接摄取到Adobe Experience Platform中。

   ![](assets/aep_audiences_eventstab.png)

>[!NOTE]
>
>**多实体细分** ，允许您根据产品、商店或其他非配置文件类，使用其他数据扩展配置文件数据。 连接后，来自其他类的数据将变为可用，就像它们是配置文件架构的本机数据一样。
>
>有关详细信息，请参阅专 [用文档](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/tutorials/segmentation/multi_entity_segmentation.md)。

默认情况下，“统一区段构建器”显示已存在数据的字段。 要显示完整架构（包括不存在数据的字段），请启用设 **[!UICONTROL Show full XDM schema]** 置中的选项。

![](assets/aep_audiences_populatedfields.png)

每个字段末尾的符号提供了有关属性及其使用方法的附加信息。

![](assets/aep_audiences_isymbol.png)

## 定义区段规则

>[!NOTE]
>
>以下部分提供有关规则定义的全局信息。 有关详细信息，请参阅“区段 [生成器”用户指南](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)。

要构建规则，请执行以下步骤：

1. 从左侧窗格中查找反映规则所基于的属性或事件的字段。

1. 将字段拖动到中心工作区上，然后根据所需的区段定义对其进行配置。 为此，可以使用多个字符串和日期／时间函数。

   在以下示例中，该规则将以性别等于“Male”的所有档案为目标。

   ![](assets/aep_audiences_malegender.png)

   在该节中自动重新计算与该段对应的估计人 **[!UICONTROL Segment Properties]** 口。

1. 通过 **[!UICONTROL View Profiles]** 该按钮可预览与规则对应的前20条记录，从而使您能够快速验证区段。

   ![](assets/aep_audiences_samplepreview.png)

   您可以根据需要添加任意数量的附加规则，以定位正确的配置文件。

   向容器添加规则时，该规则将附加到任何现有规则中的AND逻辑运算符。 如果需要，单击逻辑运算符可对其进行修改。

   ![](assets/aep_audiences_andoperator.png)

一旦链接在一起，这两个规则就构成一个容器。

## 比较字段

通过“统一的区段生成器”，您可以比较两个字段以定义规则。 例如，其家乡地址与工作地址的邮政编码不同的女性。

为此，请执行以下步骤：

1. 将要比较的第一个字段（例如，家庭地址邮政编码）拖动到中心工作区上。

   ![](assets/aep_audiences_comparing_1.png)

1. 选择将与第一个字段进行比较的第二个字段（例如，工作地址邮政编码）。

   将其拖动到中心工作区中，该工作区与框中的第一个字段位于同一容 **[!UICONTROL Drop here to compare operands]** 器中。

   ![](assets/aep_audiences_comparing_2.png)

1. 根据需要在两个字段之间配置运算符。 在此示例中，我们希望我们的细分针对的配置文件的主地址与工作地址不同。

   ![](assets/aep_audiences_comparing_3.png)

该规则现已配置好并可作为受众激活。
