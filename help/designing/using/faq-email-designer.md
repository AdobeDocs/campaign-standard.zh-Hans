---
title: 'Email Designer常见问题解答 '
description: 有关Email Designer的常见问题解答。
audience: designing
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Email Design
role: User
level: Intermediate
exl-id: f3208380-a4cf-4944-aa24-883995d1075d
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 7%

---

# Email Designer常见问题解答

## 内容块和内容片段之间有何区别？

内容块和内容片段是多个电子邮件中通用的可重复使用内容片段。 这些功能用于确保电子邮件的一致性，并优化/标准化电子邮件创建。 内容块和内容片段之间的差异是可进行自定义的级别。

* 内容块是纯HTML，其中手动插入HTML代码（不是用户友好UI，而是直接源代码）。 尽管它真的面向具有HTML知识的用户，但它允许内容片段中不提供个性化级别。

* 内容片段是通过Email Designer使用用户友好UI创建的可视内容片段。 但是，无法个性化内容。 如果需要个性化，则只能通过内容块完成。

## 如何从HTML结构向元素添加内边距？

您可以使用HTML痕迹导航添加内边距。

1. 在屏幕左下方，单击HTML痕迹导航。

   ![](assets/do-not-localize/breadcrumb.png)

1. 单击要添加内边距的元素。
1. 在HTML痕迹导航中单击父标记。
您现在可以向此元素添加内边距。

## 能否在Email Designer中导入HTML内容？

您可以将自己的HTML内容上传到Email Designer。 如果尚未通过Email Designer创建该页面，则该页面将以兼容模式加载，该模式旨在保留原始HTML，但会通过UI限制某些版本功能。

有关更多信息，请参阅[兼容模式](../../designing/using/using-existing-content.md#compatibility-mode)

## 如何创建我的第一个电子邮件内容？

首先，从主页创建电子邮件。
然后，要向电子邮件添加内容，您需要添加结构组件，并在其中插入内容组件。

有关更多信息，请参阅[从头开始创建电子邮件](../../designing/using/quick-start.md#from-scratch-email)

## 为何需要更新片段？

Email Designer 正在不断改进。如果您从头开始、从现成模板创建电子邮件内容，或者如果您创建了片段，则可能需要将内容更新到最新版本，以避免CSS冲突问题等问题。

有关更多信息，请参阅[更新片段](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-updates)

## 能否在主题中保存样式？

无法将样式另存为主题以供将来重用。但是，CSS 样式可保存在内容模板或电子邮件中。

有关更多信息，请参阅[Styles](../../designing/using/styles.md)

## 哪些字体可用？

在编辑样式时，默认情况下，只有大多数电子邮件客户端正式支持的Web字体才能通过UI使用。 使用自定义字体需要更新HTML代码。
