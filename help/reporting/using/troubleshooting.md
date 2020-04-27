---
title: 故障排除
description: 在此处查找与动态报告相关的常见问题。
page-status-flag: never-activated
uuid: a84a18bd-4e33-466e-a6ce-d7008fe12746
contentOwner: beneat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: troubleshooting
discoiquuid: bbb41c38-12c1-4625-85d5-69627e2f4b39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 001fc2df11e32bdcc31dfe917884460b4d3de541

---


# 故障排除{#troubleshooting}

您可以在本节中找到与动态报告相关的常见问题。

## 对于“唯一”打开和“唯一”单击，聚合行中的计数与单行中的计数不匹配 {#unique-open-clicks-no-match}

这是预期行为。
我们可以以以下示例来解释此行为。

将向用户档案P1和P2发送电子邮件。

P1在第一天打开两次电子邮件，第二天打开三次。

但是，P2会在第一天打开一次电子邮件，之后几天不再打开它。
以下是用户档案与已发送电子邮件互动的直观表现形式：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>日</strong><br /> </th> 
   <th align="center"> <strong>打开</strong> <br /> </th> 
   <th align="center"> <strong>唯一打开次数</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> 第1天<br /> </td> 
   <td align="center"> 2 + 1 = 3<br /> </td> 
   <td align="center"> 1 + 1 = 2<br /> </td> 
  </tr> 
  <tr> 
   <td align="center"> 第2天<br /> </td> 
   <td align="center"> 3 + 0 = 3<br /> </td> 
   <td align="center"> 1 + 0 = 1<br /> </td> 
  </tr>
 </tbody> 
</table>

要了解唯一打开次数的总数，我们需要总和其行计数， **[!UICONTROL Unique Opens]** 该计数值为3。 但是，由于电子邮件的目标只有2位用户档案，因此公开率应显示150%。

为了不获得高于100的百分比，将 **[!UICONTROL Unique Opens]** 的定义保留为打开的唯一广播的数量。 在这种情况下，即使P1在第1天和第2天打开电子邮件，其唯一打开次数仍为1。

这将产生下表：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>日</strong><br /> </th> 
   <th align="center"> <strong>打开</strong> <br /> </th> 
   <th align="center"> <strong>唯一打开次数</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> 第1天<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> 第2天<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>唯一计数基于基于HLL的草图，这可能在较大计数时造成细微的不准确。

## 打开计数与数据库计数不匹配 {#open-counts-no-match-database}

这可能是因为，在动态报告中使用启发式方法跟踪打开次数，即使我们无法跟踪操作也是如 **[!UICONTROL Open]** 此。

例如，如果用户在其客户端上禁用了图像，并单击了电子邮件中的链接，则数据库可能 **[!UICONTROL Open]** 不会跟踪该链接，但会跟 **[!UICONTROL Click]** 踪。

因此， **[!UICONTROL Open]** 跟踪日志计数在数据库中可能没有相同的计数。

此类情况会添加为“ **电子邮件单击意味着电子邮件打开”**。

>[!NOTE]
>
>由于唯一计数基于基于HLL的草图，因此可以体验计数之间细微的不一致。

## 颜色在我的报告表中有什么意义？ {#reports-color-signification}

报告中显示的颜色是随机的，无法个性化。 它们代表一个进度栏，并会显示出来以帮助您更好地突出显示报告中达到的最大值。

在以下示例中，单元格的颜色相同，因为其值为100%。

![](assets/troubleshooting_1.png)

如果您将“自定 **[!UICONTROL Conditional formatting]** 义”更改为“自定义”，则当值达到上限时，单元格将变得更绿色。 但是，如果达到下限，它会变得更红。

例如，在此，我们将 **[!UICONTROL Upper limit]** 设置为500 **[!UICONTROL Lower limit]** 和0。

![](assets/troubleshooting_2.png)

## 为什么值N/A显示在我的报告中？

![](assets/troubleshooting_3.png)

值 **N/A** 有时可显示在动态报告中。 这可以由于以下两个原因显示：

* 该投放已被删除，此处显示为 **N/A** ，以避免结果出现差异。
* 将维度拖放到 **[!UICONTROL Transactional Delivery]** 报表时，值 **N/A** 可能会因此显示。 这是因为动态报表会获取每个投放，即使它们不是事务性的。
将维度拖放到报表时也会发 **[!UICONTROL Delivery]** 生这种情况，但在这种情况下， **** N/A值将表示交易投放。
