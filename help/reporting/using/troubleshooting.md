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

## 对于“唯一”打开和“唯一”单击，聚合行中的计数与单行{#unique-open-clicks-no-match}中的计数不匹配

这是预期行为。
我们可以举下例来解释此行为。

向用户档案P1和P2发送电子邮件。

P1在第一天打开两次电子邮件，第二天打开三次。

但是，P2会在第一天打开一次电子邮件，在之后几天内不再重新打开。
以下是用户档案与已发送电子邮件交互的直观表示：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong> <br /> </th> 
   <th align="center"> <strong>打开</strong> <br /> </th> 
   <th align="center"> <strong>唯一打开</strong> <br /> </th> 
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

要了解唯一打开次数的总数，我们需要总和&#x200B;**[!UICONTROL Unique Opens]**&#x200B;的行计数，这给出值3。 但是，由于电子邮件的目标仅为2个用户档案，因此开放率应显示150%。

为了不获得大于100的百分比，**[!UICONTROL Unique Opens]**&#x200B;的定义将保持为已打开的唯一广播的数量。 在这种情况下，即使P1在第1天和第2天打开电子邮件，其唯一打开次数仍为1。

这将产生下表：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>日</strong> <br /> </th> 
   <th align="center"> <strong>打开</strong> <br /> </th> 
   <th align="center"> <strong>唯一打开</strong> <br /> </th> 
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
>唯一计数基于基于HLL的草图，这可能导致在大计数时出现轻微的不准确。

## 打开计数与数据库计数{#open-counts-no-match-database}不匹配

这可能是因为，在“动态”报告中使用启发式方法来跟踪打开情况，即使无法跟踪&#x200B;**[!UICONTROL Open]**&#x200B;操作。

例如，如果用户在其客户端上禁用了图像，并单击电子邮件中的链接，则数据库可能无法跟踪&#x200B;**[!UICONTROL Open]**，但&#x200B;**[!UICONTROL Click]**&#x200B;将跟踪。

因此，**[!UICONTROL Open]**&#x200B;跟踪日志计数在数据库中可能不具有相同的计数。

此类事件添加为&#x200B;**“电子邮件单击表示电子邮件打开”**。

>[!NOTE]
>
>由于唯一计数基于基于HLL的草图，因此可以体验计数之间的细微不一致。

## 如何计算循环/交易投放的计数？{#counts-recurring-deliveries}

处理经常性投放和事务性投放时，计数将同时归属于父和子客户。
我们可以举一个名为**R1**的循环投放的示例，该循环设置为每天在第1天(RC1)、第2天(RC2)和第3天(RC3)运行。
假设只有一个人多次打开所有子投放。 在这种情况下，单个循环子投放将每个的**[!UICONTROL Open]**计数显示为1。
但是，由于同一人单击了所有投放，因此父重复投放也将**[!UICONTROL Unique open]**&#x200B;设置为1。

报告应如下所示：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>投放</strong> <br /> </th> 
   <th align="center"> <strong>已发送</strong> <br /> </th> 
   <th align="center"> <strong>已交付</strong> <br /> </th>
   <th align="center"> <strong>打开</strong> <br /> </th> 
   <th align="center"> <strong>唯一打开</strong> <br /> </th>
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

## 颜色在我报表的表格中意味着什么？{#reports-color-signification}

报告中显示的颜色是随机的，无法个性化。 它们代表一个进度条，并显示以帮助您更好地突出显示报表中达到的最大值。

在以下示例中，单元格的颜色相同，因为其值为100%。

![](assets/troubleshooting_1.png)

如果将&#x200B;**[!UICONTROL Conditional formatting]**&#x200B;更改为自定义，则当值达到上限时，单元格将变得更绿。 然而，如果它达到下限，它会变得更红。

例如，在此，我们将&#x200B;**[!UICONTROL Upper limit]**&#x200B;设置为500，将&#x200B;**[!UICONTROL Lower limit]**&#x200B;设置为0。

![](assets/troubleshooting_2.png)

## 为什么值N/A显示在我的报表中？

![](assets/troubleshooting_3.png)

值&#x200B;**N/A**&#x200B;有时可能显示在动态报表中。 可以显示此图标，原因有二：

* 该投放已被删除，并在此显示为&#x200B;**N/A**，以避免结果出现差异。
* 将&#x200B;**[!UICONTROL Transactional Delivery]**&#x200B;维度拖放到报表时，值&#x200B;**N/A**可能会因此出现。 这是因为动态报表会获取每个投放，即使它们不是事务性的。
当将**[!UICONTROL Delivery]**&#x200B;维度拖放到报表时，也会发生这种情况，但在这种情况下，**N/A**&#x200B;值将表示事务投放。
