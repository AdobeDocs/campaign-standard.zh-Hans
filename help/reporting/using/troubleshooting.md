---
title: 动态报告疑难解答
description: 请在此处找到与动态报告相关的常见问题。
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
ht-degree: 4%

---

# 故障排除{#troubleshooting}

您可以在此部分中找到与动态报告相关的常见问题。

## 对于“唯一”打开数和“唯一”点击数，聚合行中的计数与各个行中的计数不匹配 {#unique-open-clicks-no-match}

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

要了解唯一打开的总数，我们需要汇总 **[!UICONTROL Unique Opens]** 这就给了我们3的价值。 但是，由于电子邮件仅定向到2个用户档案，因此打开率应显示150%。

为了不获得高于100的百分比，定义 **[!UICONTROL Unique Opens]** 将维护为已打开的唯一broadlog数。 在这种情况下，即使P1在第1天和第2天打开了电子邮件，其唯一打开次数仍将为1。

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
>独特计数基于基于HLL的草图，这可能会在较大计数时造成轻微的不准确。

## 打开计数与数据库计数不匹配 {#open-counts-no-match-database}

这可能是因为，在动态报告中使用启发式算法来跟踪打开次数，即使我们无法跟踪 **[!UICONTROL Open]** 操作。

例如，如果用户在其客户端上禁用了图像，然后单击电子邮件中的链接，则 **[!UICONTROL Open]** 数据库可能不会跟踪，但 **[!UICONTROL Click]** 中。

因此， **[!UICONTROL Open]** 跟踪日志计数在数据库中可能不具有相同的计数。

此类发生次数将添加为 **“电子邮件点击意味着电子邮件打开”**.

>[!NOTE]
>
>由于独特计数基于基于HLL的草图，因此可能会遇到计数之间细微的不一致。

## 如何计算定期/事务性投放的计数？ {#counts-recurring-deliveries}

使用定期投放和事务投放时，计数将同时归属于父投放和子投放。
我们可以以名为 **R1** 设置为在第1天(RC1)、第2天(RC2)和第3天(RC3)运行。
假设只有一个人多次打开所有子投放。 在这种情况下，单个定期子投放将显示 **[!UICONTROL Open]** 计为1。
但是，由于同一人点击了所有投放，因此父定期投放也将 **[!UICONTROL Unique open]** 作为1。

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

## 这些颜色在我的报表表格中的含义是什么？ {#reports-color-signification}

报表中显示的颜色是随机排列的，无法进行个性化。 它们表示一个进度条，用于帮助您更好地突出显示报表中达到的最大值。

在以下示例中，单元格的颜色相同，因为其值为100%。

![](assets/troubleshooting_1.png)

如果您更改 **[!UICONTROL Conditional formatting]** 对于自定义，当值达到上限时，单元格将变得更绿。 然而，如果达到下限，它会变得更红。

例如，在此，我们将 **[!UICONTROL Upper limit]** 到500和 **[!UICONTROL Lower limit]** 0。

![](assets/troubleshooting_2.png)

## 为什么值N/A会显示在我的报表中？

![](assets/troubleshooting_3.png)

值 **不适用** 有时会显示在动态报表中。 显示此参数的原因有三：

* 投放已删除，如下所示 **不适用** 不会造成结果不一致。
* 拖放 **[!UICONTROL Transactional Delivery]** 维度，值 **不适用** 可能会显示为结果。 之所以会出现这种情况，是因为动态报告会获取每个投放，即使它们不是事务型投放。 在拖放 **[!UICONTROL Delivery]** 维度，但在本例中， **不适用** 值将表示事务型投放。
* 当维度与与维度无关的量度一起使用时。 在以下示例中，添加了一个划分，其中包含 **[!UICONTROL Tracking URL]** 维度，即使 **[!UICONTROL Click]** 在此投放中，count被设置为0。

   ![](assets/troubleshooting_4.png)

## 使用自定义Target映射时，投放的报表显示不完整的数据

如果您在投放中使用导入的自定义目标映射，并且不同报表中未显示任何数据，则这可能意味着未为这些目标映射创建报表增量。

要解决此问题，请执行以下操作：

* 从XML导入Target映射后，您还需要导入报告扩充。

* 您可以直接在Adobe Campaign Standard中创建Target映射，而不是导入Target映射，这将自动创建报表扩充。
