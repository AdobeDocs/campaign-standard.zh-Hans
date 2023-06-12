---
title: 动态报告故障诊断
description: 在此处查找与动态报告相关的常见问题。
audience: reporting
content-type: reference
topic-tags: troubleshooting
feature: Reporting
role: Leader
level: Intermediate
exl-id: 0f99a109-2923-4e64-8131-80fcacf79c82
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 5%

---

# 故障排除{#troubleshooting}

您可以在此部分找到与动态报告相关的常见问题。

## 对于唯一打开数和唯一点击数，聚合行中的计数与单个行中的计数不匹配 {#unique-open-clicks-no-match}

这是预期行为。
我们可以通过以下示例来解释此行为。

向用户档案P1和P2发送电子邮件。

P1在第一天打开电子邮件两次，然后在第二天打开电子邮件树状结构。

但是，P2会在第一天打开电子邮件一次，并且不会在接下来的几天内重新打开它。
以下是用户档案与已发送电子邮件的交互的可视表示形式：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong> <br /> </th> 
   <th align="center"> <strong>打开</strong> <br /> </th> 
   <th align="center"> <strong>独特打开次数</strong> <br /> </th> 
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

要了解唯一打开的总数，我们需要将 **[!UICONTROL Unique Opens]** 也就是说值3。 但由于电子邮件仅针对2个用户档案，因此打开率应显示150%。

若要获得高于100的百分比，则定义为 **[!UICONTROL Unique Opens]** 将保留为已打开的唯一broadlog的数量。 在这种情况下，即使P1在第1天和第2天打开了电子邮件，其唯一打开次数仍将为1。

这将生成下表：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong></strong> <br /> </th> 
   <th align="center"> <strong>打开</strong> <br /> </th> 
   <th align="center"> <strong>独特打开次数</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong> Day </strong><br /> </td> 
   <td align="center"> <strong> 6 </strong><br /> </td> 
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
>独特计数基于基于HLL的草图，这可能会导致大量计数稍有不准确。

## 打开计数与数据库计数不匹配 {#open-counts-no-match-database}

这可能是因为，动态报告中使用启发式来跟踪打开次数，即使我们无法跟踪 **[!UICONTROL Open]** 操作。

例如，如果用户在其客户端上禁用了图像并单击了电子邮件中的链接，则 **[!UICONTROL Open]** 不能由数据库跟踪，但 **[!UICONTROL Click]** 会的。

因此， **[!UICONTROL Open]** 跟踪日志计数在数据库中可能没有相同的计数。

此类发生次数添加为 **“电子邮件点击表示电子邮件已打开”**.

>[!NOTE]
>
>由于独特计数基于基于HLL的草图，因此可能会出现计数之间的细微不一致。

## 如何计算定期/事务性投放的计数？ {#counts-recurring-deliveries}

处理循环投放和事务投放时，这些计数将同时归属于父投放和子投放。
我们以名为的定期投放为例 **R1** 设置为在第1天(RC1)、第2天(RC2)和第3天(RC3)每天运行。
假设只有一个人员多次打开了所有子投放。 在这种情况下，各个定期子投放将显示 **[!UICONTROL Open]** 每次都计为1。
但是，由于同一人单击了所有投放，因此父定期投放也将具有 **[!UICONTROL Unique open]** as 1.

报表应如下所示：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>投放</strong> <br /> </th> 
   <th align="center"> <strong>已发送</strong> <br /> </th> 
   <th align="center"> <strong>已投放</strong> <br /> </th>
   <th align="center"> <strong>打开</strong> <br /> </th> 
   <th align="center"> <strong>独特打开次数</strong> <br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong>R1</strong><br/> </td> 
   <td align="center"> <strong>100</strong><br/> </td> 
   <td align="center"> <strong>90</strong><br/> </td> 
   <td align="center"> <strong>10</strong><br/> </td> 
   <td align="center"> <strong>3</strong><br/> </td> 
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

## 颜色在报表表格中的含义是什么？ {#reports-color-signification}

报表中显示的颜色是随机的，无法进行个性化。 它们表示进度条并显示，以帮助您更好地突出显示报表中达到的最大值。

在下面的示例中，单元格的颜色相同，因为其值为100%。

![](assets/troubleshooting_1.png)

如果您更改 **[!UICONTROL Conditional formatting]** 自定义，当值达到上限时，单元格将变得更加绿色。 反之，如果达到下限，就会变红。

例如，在此，我们设置 **[!UICONTROL Upper limit]** 到500和 **[!UICONTROL Lower limit]** 更改为0。

![](assets/troubleshooting_2.png)

## 为什么值N/A出现在我的报表中？

![](assets/troubleshooting_3.png)

值 **不适用** 有时可能出现在动态报告中。 显示原因有三个：

* 投放已被删除，此处显示为 **不适用** 不会导致结果不一致。
* 拖放 **[!UICONTROL Transactional Delivery]** 维度，值 **不适用** 可能会显示为一个结果。 发生这种情况的原因是，动态报告会获取每个投放，即使它们不是事务型投放。 拖放 **[!UICONTROL Delivery]** 维度，但在本例中， **不适用** 值将表示事务性投放。
* 当维度与维度无关的量度一起使用时。 在下面的示例中，添加了一个划分，其中 **[!UICONTROL Tracking URL]** 维度，即使 **[!UICONTROL Click]** 在此投放中，计数设置为0。

   ![](assets/troubleshooting_4.png)

## 使用自定义目标映射时，投放报表显示不完整的数据

如果您在投放中使用导入的自定义Target映射，并且没有数据显示在不同的报表中，则可能意味着没有为这些目标映射创建报表增强功能。

要解决此问题：

* 从XML导入Target映射后，您还需要导入Reporting扩充。

* 您可以直接在Adobe Campaign Standard中创建映射，而不是导入您的Target映射，这会自动创建报表扩充。
