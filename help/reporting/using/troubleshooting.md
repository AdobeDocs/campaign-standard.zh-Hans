---
solution: Campaign Standard
product: campaign
title: 故障排除
description: 在此处查找与动态报告相关的常见问题。
audience: reporting
content-type: reference
topic-tags: troubleshooting
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 5%

---


# 故障排除{#troubleshooting}

您可以在本节中找到与动态报告相关的常见问题。

## 对于“唯一”打开和“唯一”单击，聚合行中的计数与单个行中的计数不匹配 {#unique-open-clicks-no-match}

这是预期行为。
我们可以举下例来解释此行为。

向用户档案P1和P2发送电子邮件。

P1在第一天打开电子邮件两次，第二天打开三次。

但是，P2会在第一天打开一次电子邮件，在之后几天不再重新打开它。
以下是用户档案与已发送电子邮件交互的直观表现形式：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong> <br /> </th> 
   <th align="center"> <strong>打开</strong> <br /> </th> 
   <th align="center"> <strong>唯一打开次数</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Day 1<br /> </td> 
   <td align="center"> 2 + 1 = 3<br /> </td> 
   <td align="center"> 1 + 1 = 2<br /> </td> 
  </tr> 
  <tr> 
   <td align="center"> Day 2<br /> </td> 
   <td align="center"> 3 + 0 = 3<br /> </td> 
   <td align="center"> 1 + 0 = 1<br /> </td> 
  </tr>
 </tbody> 
</table>

要了解唯一打开次数的总数，我们需要总和其行计数， **[!UICONTROL Unique Opens]** 其中给出值3。 但是，由于电子邮件的目标用户档案只有2位，因此公开率应显示150%。

为了不获得高于100的百分比， **[!UICONTROL Unique Opens]** 定义将保留为已打开的唯一广播数。 在这种情况下，即使P1在第1天和第2天打开电子邮件，其唯一打开次数仍为1。

这将产生下表：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong> <br /> </th> 
   <th align="center"> <strong>打开</strong> <br /> </th> 
   <th align="center"> <strong>唯一打开次数</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Day 1<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> Day 2<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>唯一计数基于基于HLL的草图，这可能在较大计数时造成轻微的不准确。

## 打开计数与数据库计数不匹配 {#open-counts-no-match-database}

这可能是因为，在动态报告中使用启发式方法跟踪打开次数，即使我们无法跟踪操作 **[!UICONTROL Open]** 时。

例如，如果用户在其客户端上禁用了图像，并单击电子邮件中的链接，则数据库 **[!UICONTROL Open]** 可能不会跟踪该图像，但将跟踪该 **[!UICONTROL Click]** 图像。

因此，跟踪日志 **[!UICONTROL Open]** 计数在数据库中可能没有相同的计数。

此类事件会添加 **为“电子邮件单击意味着电子邮件打开”**。

>[!NOTE]
>
>由于唯一计数基于基于HLL的草图，因此可以体验计数之间的细微不一致。

## 如何计算重复／交易投放的计数？ {#counts-recurring-deliveries}

在使用重复投放和事务投放时，计数将同时归属于父和子数据。
我们可以举一个名为R1的 **重复投放** ，该设置为每天在第1天(RC1)、第2天(RC2)和第3天(RC3)运行。
我们假设只有一个人多次打开所有子投放。 在这种情况下，单个重复的子投放将每 **[!UICONTROL Open]** 个的计数显示为1。
但是，由于同一人点击了所有投放，因此父代重复投放也将 **[!UICONTROL Unique open]** 具有1。

报告应如下所示：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>投放</strong> <br /> </th> 
   <th align="center"> <strong>已发送</strong> <br /> </th> 
   <th align="center"> <strong>已交付</strong> <br /> </th>
   <th align="center"> <strong>打开</strong> <br /> </th> 
   <th align="center"> <strong>唯一打开次数</strong> <br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong>R1<br/> </td> 
   <td align="center"> <strong>100<br/> </td> 
   <td align="center"> <strong>90<br/> </td> 
   <td align="center"> <strong>10<br/> </td> 
   <td align="center"> <strong>3<br/> </td> 
  </tr> 
  <tr> 
   <td align="center"> RC1<br/> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr>
    <tr> 
   <td align="center"> RC2<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 30<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
    <tr> 
   <td align="center"> RC3<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 颜色在我的报告表中有什么意义？ {#reports-color-signification}

报告中显示的颜色是随机的，无法个性化。 它们代表一个进度栏，并会显示它们，以帮助您更好地突出显示报告中达到的最大值。

在以下示例中，单元格的颜色相同，因为其值为100%。

![](assets/troubleshooting_1.png)

如果将“自定 **[!UICONTROL Conditional formatting]** 义”更改为“自定义”，则当值达到上限时，单元格将变得更绿色。 而如果达到下限，则会变得更红。

例如，在此，我们将 **[!UICONTROL Upper limit]** 设置为500 **[!UICONTROL Lower limit]** 和0。

![](assets/troubleshooting_2.png)

## 为什么值N/A显示在我的报告中？

![](assets/troubleshooting_3.png)

值N/ **A有时** ，可能显示在动态报告中。 可以出于以下两个原因显示此图标：

* 该投放已被删除，并 **在此显示为** N/A，不会导致结果不一致。
* 将维拖放到 **[!UICONTROL Transactional Delivery]** 报表时，值 **N/A** 可能会因此显示。 这是因为动态报表会获取每个投放，即使它们不是事务性的。
将维拖放到报表时也会发 **[!UICONTROL Delivery]** 生这种情况，但在这种情况下， **** N/A值将表示事务投放。
