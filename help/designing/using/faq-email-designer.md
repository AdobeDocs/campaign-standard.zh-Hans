---
title: 向Designer发送电子邮件常见问题解答
description: 关于向Designer发送电子邮件的常见问题解答。
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
ht-degree: 3%

---

# 向Designer发送电子邮件常见问题解答

## 内容块与内容片段之间有何区别？

内容块和内容片段是可重复使用的内容片段，在多个电子邮件中很常见。 它们用于确保电子邮件之间的一致性，并优化/标准化电子邮件创建。 内容块和内容片段之间的区别在于可能的自定义级别。

* 内容块是手动插入HTML代码的纯HTML（对用户不友好的UI，它是直接源代码）。 尽管它实际上面向具有HTML知识的人员，但它允许内容片段中不提供的个性化级别。

* 内容片段是通过Email Designer创建的可视内容片段，使用其用户友好的UI。 但是，无法个性化内容。 如果需要个性化，则只能通过内容块完成个性化。

## 如何从HTML结构向元素添加边距？

您可以使用HTML痕迹导航添加内边距。

1. 在屏幕左下方，单击HTML痕迹导航。

   ![](assets/do-not-localize/breadcrumb.png)

1. 单击要添加内边距的元素。
1. 单击HTML痕迹导航中的父标记。
现在，您可以向此元素添加内边距。

## 我是否可以在电子邮件Designer中导入HTML内容？

您可以将自己的HTML内容上传到Email Designer。 如果它不是通过Email Designer创建的，则它将以兼容性模式加载，该模式旨在保留原始HTML，但通过UI限制某些版本功能。

有关详细信息，请参阅[兼容模式](../../designing/using/using-existing-content.md#compatibility-mode)

## 如何创建我的第一个电子邮件内容？

首先，从主页创建电子邮件。
然后，要将内容添加到电子邮件，您需要添加一个结构组件，并在其中插入一个内容组件。

有关详细信息，请参阅[从头开始创建电子邮件](../../designing/using/quick-start.md#from-scratch-email)

## 为什么需要更新片段？

Email Designer 正在不断改进。如果您从头开始创建、从现成模板创建电子邮件内容，或者如果您创建了片段，则可能需要将内容更新到最新版本以避免CSS冲突问题之类的问题。

有关详细信息，请参阅[更新片段](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-updates)

## 能否保存主题中的样式？

无法将样式另存为主题以供将来重用。但是，CSS样式可以保存在内容模板或电子邮件中。

有关详细信息，请参阅[样式](../../designing/using/styles.md)

## 哪些字体可用？

在编辑样式时，默认情况下，只有大多数电子邮件客户端正式支持的Web字体才可以通过UI使用。 使用自定义字体需要更新HTML代码。
