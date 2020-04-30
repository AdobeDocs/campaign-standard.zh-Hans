---
title: '电子邮件设计人员常见问题解答 '
description: 有关电子邮件设计人员的常见问题解答。
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 23d6c78f924635a8ce512fd91b4a46db395e8bd1

---


# 电子邮件设计人员常见问题解答

## 内容块和内容片段之间有何差异？

内容块和内容片段是多个电子邮件中常见的可重用内容片段。 这些功能用于确保电子邮件之间的一致性，以及优化／标准化电子邮件创建。 内容块和内容片段之间的差异是可能的自定义级别。

* 内容块是纯HTML，其中手动插入HTML代码（不是用户友好型UI，而是直接源代码）。 尽管它真正面向具有HTML知识的用户，但它允许内容片段中不提供的个性化级别。

* 内容片段是通过电子邮件设计器使用其用户友好UI创建的可视内容片段。 但是，无法个性化内容。 如果需要个性化，则只能通过内容块进行个性化。

## 如何从HTML结构向元素添加填充？

您可以使用HTML痕迹导航添加填充。

1. 在屏幕左下角，单击HTML痕迹导航。

   ![](assets/breadcrumb.png)

1. 单击要添加填充的元素。
1. 单击HTML痕迹导航中的父标记。
您现在可以向此元素添加填充。

## 我是否可以在电子邮件设计器中导入HTML内容？

您可以将自己的HTML内容上传到电子邮件设计器。 如果尚未通过Email Designer创建它，它将以兼容模式加载，该模式旨在保留您的原始HTML，但通过UI限制了某些版本功能。

有关详细信息，请参阅兼 [容性模式](../../designing/using/using-existing-content.md#compatibility-mode)

## 如何创建我的第一封电子邮件内容？

首先，从主页创建电子邮件。
然后，要向电子邮件中添加内容，您需要添加结构组件，并在其中插入内容组件。

有关详细信息，请参 [阅从头开始创建电子邮件](../../designing/using/quick-start.md#from-scratch-email)

## 为什么需要更新片段？

电子邮件设计人员正在不断改进。 如果您从头开始、从现成模板创建电子邮件内容，或者如果您创建了片段，则可能需要将内容更新到最新版本以避免CSS冲突问题等问题。

有关详细信息，请参阅更 [新片段](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-updates)

## 是否可以在主题中保存样式？

样式无法保存为主题以供将来重用。 但是，CSS样式可保存在内容模板或电子邮件中。

有关详细信息，请参阅样 [式](../../designing/using/styles.md)

## 哪些字体可用？

编辑样式时，默认情况下，只有大多数电子邮件客户端正式支持的Web字体才可通过UI使用。 使用自定义字体需要更新HTML代码。
