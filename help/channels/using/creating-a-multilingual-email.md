---
title: 创建多语言电子邮件
seo-title: 创建多语言电子邮件
description: 创建多语言电子邮件
seo-description: 按照这些步骤，创建一封多语言电子邮件，定位使用不同首选语言的收件人。
page-status-flag: 从未激活
uuid: e90f4ec8-14e3-4304-b5 fc-bce0 ba08 a4 ef
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: 电子邮件消息
discoiquuid: 79231445-1d51-499a-adcf-3c0 f6 db1 cfa3
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Creating a multilingual email{#creating-a-multilingual-email}

您可以向具有不同首选语言的配置文件发送多语言电子邮件：每个配置文件都将收到其首选语言的电子邮件变体。

为此，请检查您是否有多语言电子邮件模板。If not, learn how to create one in [this section](../../start/using/creating-a-multilingual-template.md).

受众基于具有完整首选语言信息的档案。

1. Create a new email based on a [multilingual template](../../start/using/creating-a-multilingual-template.md).

   ![](assets/multi_create1.png)

1. 定义电子邮件的一般属性和目标受众，就像标准电子邮件一样。Refer to the [Creating audiences](../../audiences/using/creating-audiences.md) section.
1. 在创建向导的第四步，定义变体选项。If the [multilingual template](../../start/using/creating-a-multilingual-template.md) already contains all the right parameters, you can directly click on the **[!UICONTROL Create]** button.

   ![](assets/multi_create4.png)

   If needed, add variants using the **[!UICONTROL Add an element]** button. **[!UICONTROL Default]** 变量不能被删除。When set to **[!UICONTROL default]**, [the profile's preferred language](../../audiences/using/creating-profiles.md) is used to choose the variant. You can also set the **[!UICONTROL Default]** variant to any other language.

1. 确认电子邮件创建：随后将显示电子邮件仪表板。
1. 定义每个变体的电子邮件内容。根据您选择的模板，您可以定义多个主题、多个发送者名称或多个不同的内容。使用下拉菜单在元素的不同变体之间导航。For more information, consult the [content editor](../../designing/using/about-email-content-design.md) section.

   ![](assets/multi_selectcontent.png)

1. 测试和验证您的消息。Refer to the [Sending proof](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) section.
1. Schedule the send with the **[!UICONTROL Send after confirmation option]**.
1. 发送电子邮件后，您可以访问其日志和报告来评估营销活动的成功与否。For more on reporting, refer to [this section](../../reporting/using/about-dynamic-reports.md).

