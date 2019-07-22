---
title: 疑难解答
seo-title: 疑难解答
description: 疑难解答
seo-description: 查找与动态报告相关的常见问题。
page-status-flag: 从未激活
uuid: a84a18bd-4e33-466e-a6 ce-d7008 fe12746
contentOwner: bentain
products: SG_ CAMPAIGN/STANDARD
audience: 报告报告
content-type: reference
topic-tags: 疑难解答
discoiquuid: bbb41c38-12c1-4625-85d5-69627e2f4b39
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: e0cbdfecde495d7c9f8bfa33dd5ee8598cdfe60a

---


# Troubleshooting{#troubleshooting}

您可以在此部分中找到与动态报告相关的常见问题。

## For Unique opens and Unique clicks, the count in the aggregate row is not matching the ones in individual rows {#unique-open-clicks-no-match}

这是预期行为。
我们可以采取以下示例来解释此行为。

电子邮件将发送到配置文件P和P2。

P在第一天打开电子邮件两次，然后在第二天打开一次。

但是，P在第一天打开电子邮件一次，但在几天内不会重新打开它。
以下是配置文件与发送的电子邮件交互的可视演示：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong><br /> </th> 
   <th align="center"> <strong>打开时间</strong><br /> </th> 
   <th align="center"> <strong>唯一打开次数</strong><br /> </th> 
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

To understand the overall number of unique opens, we need to sum up the row counts of **[!UICONTROL Unique Opens]** which gives us the value 3. 但是，由于电子邮件仅面向个配置文件，因此打开率应显示150%。

To not obtain percentage higher than 100, the definition of **[!UICONTROL Unique Opens]** is maintained to be the number of unique broadlogs that were opened. 在这种情况下，即使P在第天和第日打开电子邮件，其唯一打开仍将保持为1。

这将导致下表：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong><br /> </th> 
   <th align="center"> <strong>打开时间</strong><br /> </th> 
   <th align="center"> <strong>唯一打开次数</strong><br /> </th> 
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
>唯一计数基于基于HLL的草图，这可能会导致较大的计数不准确。

## Open counts do not match the Database count {#open-counts-no-match-database}

This may be due to the fact that, heuristics are used in Dynamic reporting to track opens even when we can't track the **[!UICONTROL Open]** action.

For example, if a user has disabled images on their client and click on a link in the email, the **[!UICONTROL Open]** may not be tracked by the database but the **[!UICONTROL Click]** will.

Therefore, the **[!UICONTROL Open]** tracking logs counts may not have the same count in the database.

Such occurrences are added as **"an email click implies an email open"**.

>[!NOTE]
>
>由于独特计数基于基于HLL的草图，因此可以体验到计数之间的细微不一致。

## 计算重复/交易交付的计数是多少？

在处理重复和交易交付时，计数将归因于父和子交付。

We can take the example of a recurring delivery named **R1** set to run every day on day 1 (RC1), day 2 (RC2) and day 3 (RC3).

假设只有一人多次打开所有子交付。In this case, the individual recurring child deliveries will show the **[!UICONTROL Open]** count as 1 for each.

However, since the same person clicked on all the deliveries, the parent recurring delivery will also have **[!UICONTROL Unique open]** as 1.

After the Adobe Campaign Standard 19.2.1 release, the definition of **Unique counts** is changed from **Number of unique persons interacting with the delivery** to **Number of unique messages interacted**.

在Adobe Campaign Standard19.2.1版本之前，报告如下所示：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>交付</strong><br /> </th> 
   <th align="center"> <strong>已发送</strong><br /> </th> 
   <th align="center"> <strong>已交付</strong><br /> </th>
   <th align="center"> <strong>打开时间</strong><br /> </th> 
   <th align="center"> <strong>唯一打开次数</strong><br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong>R1<br/> </td> 
   <td align="center"> <strong>100<br/> </td> 
   <td align="center"> <strong>90<br/> </td> 
   <td align="center"> <strong>10<br/> </td> 
   <td align="center"> <strong>1<br/> </td> 
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

在Adobe Campaign Standard19.2.1版本之后，报告如下所示：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>交付</strong><br /> </th> 
   <th align="center"> <strong>已发送</strong><br /> </th> 
   <th align="center"> <strong>已交付</strong><br /> </th>
   <th align="center"> <strong>打开时间</strong><br /> </th> 
   <th align="center"> <strong>唯一打开次数</strong><br /> </th>
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

## What is the colors' signification in my reports' table? {#reports-color-signification}

报告中显示的颜色是randomized的，不能个性化。它们表示进度栏并显示以帮助更好地突出显示报表中达到的最大值。

在以下示例中，单元格的颜色相同，因为其值为100%。

![](assets/troubleshooting_1.png)

If you change the **Conditional formatting** to custom, when the value reaches the upper limit the cell will get greener. 但是，如果达到较低的限制，它将获得较低的值。

For example, here, we set the **Upper limit** to 500 and **Lower limit** to 0.

![](assets/troubleshooting_2.png)