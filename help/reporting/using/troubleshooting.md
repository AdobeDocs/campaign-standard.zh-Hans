---
solution: Campaign Standard
product: campaign
title: 故障排除
description: 请在此处找到与动态报告相关的常见问题。
audience: reporting
content-type: reference
topic-tags: troubleshooting
feature: 报告
role: Leader
level: Intermediate
exl-id: 0f99a109-2923-4e64-8131-80fcacf79c82
source-git-commit: 81ffe6a7e59a745a6f61941dff69be85edf4fe45
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 5%

---

# 故障排除{#troubleshooting}

您可以在此部分中找到与动态报告相关的常见问题。

## 对于“唯一打开数”和“唯一点击数”，聚合行中的计数与单行{#unique-open-clicks-no-match}中的计数不匹配

这是预期行为。
我们可以以以下示例来解释此行为。

向用户档案P1和P2发送电子邮件。

P1在第一天打开电子邮件两次，第二天打开三次。

然而，P2会在第一天打开一次电子邮件，之后几天不会重新打开它。
以下是用户档案与已发送电子邮件交互的直观表示形式：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong> <br /> </th> 
   <th align="center"> <strong>打开</strong> <br /> </th> 
   <th align="center"> <strong>唯一打开数</strong> <br /> </th> 
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

要了解唯一打开的总数，我们需要汇总&#x200B;**[!UICONTROL Unique Opens]**&#x200B;的行计数，该计数为值3。 但是，由于电子邮件仅定向到2个用户档案，因此打开率应显示150%。

为了获得不高于100的百分比，**[!UICONTROL Unique Opens]**&#x200B;的定义将保持为已打开的唯一广播的数量。 在这种情况下，即使P1在第1天和第2天打开了电子邮件，其唯一打开次数仍将为1。

这将产生下表：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong></strong> <br /> </th> 
   <th align="center"> <strong>打开</strong> <br /> </th> 
   <th align="center"> <strong>唯一打开数</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong> Day </strong><br /> </td> 
   <td align="center"> <strong> 6  </strong><br /> </td> 
   <td align="center"> <strong> 2</strong><br /> </td>
  </tr> 
  <tr> 
   <td align="center"> 第1天<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> 第2天<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>独特计数基于基于HLL的草图，这可能会在较大计数时造成轻微的不准确。

## 打开计数与数据库计数{#open-counts-no-match-database}不匹配

这可能是因为，在动态报告中使用启发式算法来跟踪打开次数，即使我们无法跟踪&#x200B;**[!UICONTROL Open]**&#x200B;操作也是如此。

例如，如果用户在其客户端上禁用了图像，并单击电子邮件中的链接，则数据库可能不会跟踪&#x200B;**[!UICONTROL Open]**，但&#x200B;**[!UICONTROL Click]**&#x200B;将跟踪。

因此，**[!UICONTROL Open]**&#x200B;跟踪日志计数在数据库中可能不具有相同的计数。

此类事件将添加为&#x200B;**&quot;电子邮件点击意味着电子邮件打开&quot;**。

>[!NOTE]
>
>由于独特计数基于基于HLL的草图，因此可能会遇到计数之间细微的不一致。

## 如何计算定期/事务性投放的计数？{#counts-recurring-deliveries}

使用定期投放和事务投放时，计数将同时归属于父投放和子投放。
我们可以举一个名为**R1**的定期投放的示例，该投放设置为每天在第1天(RC1)、第2天(RC2)和第3天(RC3)运行。
假设只有一个人多次打开所有子投放。 在这种情况下，单个定期子投放的**[!UICONTROL Open]**计数将显示为每个的1。
但是，由于同一人点击了所有投放，因此父定期投放的**[!UICONTROL Unique open]**&#x200B;也将作为1。

报表应如下所示：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>投放</strong> <br /> </th> 
   <th align="center"> <strong>已发送</strong> <br /> </th> 
   <th align="center"> <strong>已交付</strong> <br /> </th>
   <th align="center"> <strong>打开</strong> <br /> </th> 
   <th align="center"> <strong>唯一打开数</strong> <br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong>R1</strong><br/> </td> 
   <td align="center"> <strong>100</strong><br/> </td> 
   <td align="center"> <strong>90</strong><br/> </td> 
   <td align="center"> <strong>10</strong><br/> </td> 
   <td align="center"> <strong>1</strong><br/> </td> 
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

## 这些颜色在我的报表表格中的含义是什么？{#reports-color-signification}

报表中显示的颜色是随机排列的，无法进行个性化。 它们表示一个进度条，用于帮助您更好地突出显示报表中达到的最大值。

在以下示例中，单元格的颜色相同，因为其值为100%。

![](assets/troubleshooting_1.png)

如果将&#x200B;**[!UICONTROL Conditional formatting]**&#x200B;更改为自定义，则当值达到上限时，单元格将变得更加绿色。 然而，如果达到下限，它会变得更红。

例如，在本例中，我们将&#x200B;**[!UICONTROL Upper limit]**&#x200B;设置为500，将&#x200B;**[!UICONTROL Lower limit]**&#x200B;设置为0。

![](assets/troubleshooting_2.png)

## 为什么值N/A会显示在我的报表中？

![](assets/troubleshooting_3.png)

值&#x200B;**N/A**&#x200B;有时可能会显示在动态报告中。 显示此参数的原因有三：

* 投放已删除，此处显示为&#x200B;**N/A**，以不导致结果不一致。
* 将&#x200B;**[!UICONTROL Transactional Delivery]**&#x200B;维度拖放到报表时，值&#x200B;**N/A**&#x200B;可能会因此而显示。 之所以会出现这种情况，是因为动态报告会获取每个投放，即使它们不是事务型投放。 在将&#x200B;**[!UICONTROL Delivery]**&#x200B;维度拖放到报表时，也可能会发生这种情况，但在这种情况下，**N/A**&#x200B;值将表示事务性投放。
* 当维度与与维度无关的量度一起使用时。 在以下示例中，添加了包含&#x200B;**[!UICONTROL Tracking URL]**&#x200B;维度的划分，即使在此投放中将&#x200B;**[!UICONTROL Click]**&#x200B;计数设置为0也是如此。

   ![](assets/troubleshooting_4.png)

