---
title: 疲劳规则
description: 创建疲劳规则以管理与配置文件的过度通信。
page-status-flag: 从未激活
uuid: fa5e3ded-36c2-4f16-b97a-119b85adf679
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 参考
topic-tags: 排版规则
discoiquuid: 4337a80b-0fb9-4a37-bce3-fe2121a66586
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 疲劳规则{#fatigue-rules}

## 关于疲劳规则 {#about-fatigue-rules}

疲劳规则允许营销人员设置全局跨渠道业务规则，这些规则将自动从营销活动中排除过度请求的档案。

要实施疲劳规则，您需要为每个配置文件定义最大消息数，并选择将应用该规则的期间。 在交付准备过程中，配置文件会根据已发送给它们的消息数量从交付中排除（如果适用）。

>[!NOTE]
>
>要应用疲劳规则，您需要为交货定义联系日期。 如果选择立即发送消息，则不会应用疲劳规则。

相关主题：

* [准备](../../administration/using/configuring-email-channel.md#preparation)
* [管理类型](../../administration/using/about-typology-rules.md#managing-typologies)
* [排版规则](../../administration/using/about-typology-rules.md#typology-rules)
* [优化通信频率以防止接触疲劳](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)

## 创建疲劳规则 {#creating-a-fatigue-rule}

要创建和配置排 **[!UICONTROL Fatigue]** 版规则，请应用以下步骤：

1. 单击界面左上角的Adobe Campaign徽标，然后选择 **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** &gt; **[!UICONTROL Typology rules]**。

   ![](assets/fatigue4.png)

1. 在排版规则列表中，单击 **[!UICONTROL Create]**。

   ![](assets/fatigue.png)

1. 在字段 **[!UICONTROL Rule type]** 中，选择 **[!UICONTROL Fatigue]**。

   ![](assets/fatigue3.png)

1. 在字段 **[!UICONTROL Channel]** 中，选择您的规则将应用到的渠道。 您可以选择单个渠道（电子邮件、SMS、直邮、移动应用程序）或选择 **[!UICONTROL All channels]**。 请参 [阅选择渠道](#choosing-the-channel)。

   ![](assets/fatigue5.png)

1. 在选项卡 **[!UICONTROL General]** 中，定义用于计算每个配置文件最大消息数的方法。 您可以选择常数阈值或变量。 您还可以调整配置文件和提交的阈值。 有关此问题的详细信息，请参 [阅定义阈值](#defining-the-threshold)。

   ![](assets/fatigue2.png)

1. 选择 **[!UICONTROL Sliding period]** 将应用该类型规则的类型。 有关详细信息，请参阅 [设置滑动周期](#setting-the-sliding-period)。

   ![](assets/fatigue6.png)

   在此示例（请参阅以前的屏幕截图）中，我们选择在15天的滑动时间内最多发送4条消息。

1. 在标签 **[!UICONTROL Application criteria]** 中，您可以选择将此规则应用于所有提交，或根据要发送的消息限制规则的适用性。 规则仅在满足应用程序条件时才执行。 例如，您只能对标签以给定单词开头或ID包含某些字母的消息应用该规则。 请参 [阅限制筛选规则的适用性](../../administration/using/filtering-rules.md#restricting-the-applicability-of-a-filtering-rule)。

   ![](assets/fatigue20.png)

1. 选择选 **[!UICONTROL Typologies]** 项卡，并将您的排版规则链接到用于提交的排版。 请参 [阅管理排版](../../administration/using/about-typology-rules.md#managing-typologies) 和 [排版规则](../../administration/using/about-typology-rules.md#typology-rules)。

   ![](assets/fatigue12.png)

   >[!NOTE]
   >
   >可以在分发模板中定义类型，以自动应用到使用此模板创建的所有分发。

在交付准备过程中，配置文件会根据已发送给他们的交付数量从交付中排除（如果适用）。 您可以查看交付日志中的疲劳规则执行结果。 请参 [阅查看疲劳结果](#viewing-the-fatigue-results)。

![](assets/fatigue16.png)

>[!CAUTION]
>
>为了使疲劳规则有效，您需要为交付定义联系日期。 如果选择立即发送消息，则不会应用疲劳规则。

## 选择渠道 {#choosing-the-channel}

疲劳规则适用于各种渠道。 该渠道在排版规则设 **[!UICONTROL Channel]** 置的字段中定义。 您可以选择单个渠道或选择 **[!UICONTROL All channels]**。

![](assets/fatigue5.png)

**可用渠道**

可使用以下渠道：

* 电子邮件
* 移动(SMS)
* 直邮
* 移动应用程序：此渠道允许您向配置文件或应用程序订阅者发送推送通知。 如果选择向配置文件发送通知，则通知将与多渠道疲劳规则兼容。

   >[!CAUTION]
   >
   >疲劳规则与发送给应用程序订阅者的推送通知不兼容。 如果向应用程序订阅者发送消息，则疲劳规则不适用。

* 所有渠道：此选项允许您将规则应用于所有渠道。 例如，您可以决定在任何渠道上每月最多发送3条消息。 如果您上周向一个配置文件发送了2封电子邮件，并且今天尝试发送推送通知，则将排除同一个配置文件。

**交付类型**

疲劳规则与所有交付类型兼容：一次性投递、重复投递、工作流投递和交易消息。

**交易消息** ，可用于发送以活动(rtEvent)为目标的服务消息以及营销消息（定位配置文件），例如再营销消息。 疲劳规则仅与营销消息（定位配置文件）兼容。 事件事务消息不包含配置文件信息，因此它们与疲劳规则不兼容（即使在丰富了配置文件的情况下）。 借助交易消息中的营销消息支持，您可以将疲劳 **规则应用于所有渠道，包括营销交易消息**。

## 定义阈值 {#defining-the-threshold}

每个疲劳规则定义一个阈值，即在给定时间段内可以发送到一个配置文件的消息的最大数量。 一旦达到此阈值，则在所考虑的期间结束之前，再也不能提交。 通过此过程，在消息超过设置的阈值时，您可以自动从分发中排除配置文件，从而避免过度请求。

阈值可以是常数或变量。 这意味着在给定的时间段内，阈值可能因一个配置文件而异，甚至可能因同一配置文件而异。

**使用修复阈值**

阈值表示在相关期间可发送到配置文件的消息的最大数量。

默认情况下，阈值为常数，您需要指示规则授权的最大消息数。

![](assets/fatigue2.png)

**使用可变阈值**

要定义变量阈值，请在字 **[!UICONTROL Depends on the recipient]** 段中选择 **[!UICONTROL Threshold type]** 值。

![](assets/fatigue15.png)

然后您有两个选项：

* 选择配置文件字段：每个配置文件的阈值将根据所选字段而不同。 例如，如果您已使用“通信频率”字段扩展了配置文件资源，请单击该字段右侧的按钮并 **[!UICONTROL Threshold computation formula]** 选择您的字段。 对于每个配置文件，阈值将采用“通信频率”字段的值。

   ![](assets/fatigue21.png)

* 定义公式：单击字段右侧的第二个按钮 **[!UICONTROL Threshold computation formula]** 可定义高级阈值计算公式。 例如，您可以根据配置文件所属的区段索引授权消息的数量。 这意味着属于“Web”区段的配置文件可能会收到比其他配置文件更多的消息。 类型 **[!UICONTROL Iif (@origin='Web', 5, 3)]** 公式可授权向Web区段的配置文件发送5条消息，向其他区段发送3条消息。

   ![](assets/fatigue14.png)

**优化档案和交付的阈值**

默认情况下，所有消息都会考虑到阈值计算。 选中此 **[!UICONTROL Refine Threshold on profiles and deliveries]** 框可过滤配置文件和提交以在准备提交时计数。

在以下示例中，仅计数男性配置文件，并且只计数标签以Newsletter开头的 **分发** 。

![](assets/fatigue13.png)

优化提交时的阈值与限制整个规则（标签）的适用性 **[!UICONTROL Application criteria]** 不同：

* **[!UICONTROL Application criteria]**:您可以根据特定条件选择是否执行该规则。 例如，如果应用程序条件为“以Newsletter开头添加标签”，则规则将仅适用于符合此条件的分发。 如果分发的标签以“升级”开头，则该规则根本不会执行。
* **[!UICONTROL Refine threshold on profiles and deliveries > Deliveries to count]**:使用此类型规则的所有交付将执行该规则，但您决定在过去和计划的交付中要计算哪些交付。 例如，如果限制为“标签以Newsletter开头”，则即使传送标签以“Promo”开头，也将执行规则。 在选定的滑动期内，它将计算其标签以“Newsletter”开头的提交数。

## 设置滑动周期 {#setting-the-sliding-period}

在n-d轧制周期中定义疲劳规则。 该期间在部分中 **[!UICONTROL Sliding period]** 进行配置，例如2周、7天或5小时。

![](assets/fatigue6.png)

执行规则时，将考虑过去的交付和计划的交付。 这保证在给定的滑动周期中，阈值不会超过。

例如，如果您定义48小时的时间段，则系统将在联系日期前48 **小时查看** ，在联系日 **期后48小时查看**。 因此，选定的期间翻倍，以便能够整合未来交货和以前交货。

要将交货限制在2周期间内，请在“滑动期间” **部分输入****Day和7** 或1周 **** 。 在计算中将考虑在交货日期之前7天以及在应用规则的交货日期之后7天之前发送的交货。

## 查看疲劳结果 {#viewing-the-fatigue-results}

在交付准备过程中，配置文件会根据已发送给他们的交付数量从交付中排除（如果适用）。 要查看疲劳规则执行结果，请单击块右下角的按 **[!UICONTROL Deployment]** 钮。

![](assets/fatigue22.png)

有三个选项卡，显示疲劳执行结果的详细信息，包括所应用规则的名称：

* 交付日志：

   ![](assets/fatigue17.png)

* 排除日志：

   ![](assets/fatigue18.png)

* 排除原因：

   ![](assets/fatigue19.png)

## 查看疲劳规则摘要报告 {#viewing-the-fatigue-rule-summary-report}

Adobe Campaign专门提供疲劳规则报告，帮助您了解疲劳规则如何应用于您的营销活动。 这使您能够了解营销活动如何影响彼此并做出正确的调整。

可 **[!UICONTROL Fatigue rules summary]** 以从每个计划、营销 **[!UICONTROL Reports]** 活动和消息右上角的按钮访问报告。

![](assets/fatigue27.png)

在屏幕的左侧，您可以过滤提交的联系日期的报告数据。 默认情况下，选定期间从当前日期前15天开始，到当前日期后15天结束。 您还可以根据特定疲劳规则进行筛选。

饼图显示选定时段的以下信息：

* **[!UICONTROL Total targeted]**:消息准备前的总目标
* **[!UICONTROL Excluded]**:由于应用疲劳规则而导致的排除总数
* **[!UICONTROL Other exclusions]**:其他类型规则所导致的排除总数
* **[!UICONTROL To deliver]**:准备消息后要传送的消息总数( **[!UICONTROL To deliver]** = **[!UICONTROL Total targeted]** - **[!UICONTROL Excluded]** - **[!UICONTROL Other exclusions]** )

在图表右侧，您将找到按疲劳规则划分的排除数。

底部表格显示选定期间内的所有交货。 对于每次交付，您都可以看到已应用的疲劳规则和相应的排除。 没有联系日期的提交也会显示在表中。

* **[!UICONTROL 0]** 表示已应用疲劳规则但没有排除。
* **[!UICONTROL -N]** 表示出现了N个排除。
* 空字段表示疲劳规则不适用。

>[!NOTE]
>
>显示的数据与您从中访问报告的程序、消息或营销活动不相关。 此报告显示所有组织单位的所有疲劳规则和交货。 这样，您就可以获得所有交货的全局视图，以了解营销活动如何受其他营销活动的影响。

## 示例 {#examples}

在疲劳管理实施方面，有许多可能。 以下是您可以执行的操作的一些示例：

* 使用适用于所有通道 **的常数阈值** ，创建疲劳 **规则**:

   假设您创建了多通道规则，在7天的滑动期内，阈值不变为3。

   上周，您的高级档案收到了一封促销电子邮件和一封交易再营销电子邮件。 您还安排了下周发送的短信， 现在，您决定发送针对所有配置文件的推送通知。 高级配置文件将被排除在今天的推送之外，因为已经到达其2周内的最大消息数。

   ![](assets/fatigue23.png)

* 根据配置文件字段，使 **用可变阈值** ，创建疲劳 **规则**:

   您已使用“通信限制”字段扩展了配置文件资源，以为每个配置文件定义不同的阈值。 在疲劳规则中，根据此字段定义一个可变阈值，并选择2天的滑动周期。 让我们举两个档案示例：John的通信限制为1，而David的通信限制为2。 昨天，这两家公司都已收到新闻稿电子邮件。 您决定立即再给他们发送一封电子邮件。 只有David会收到它，因为John已被排除在目标之外。

   ![](assets/fatigue24.png)

* 使用阈值计算公式创 **建疲劳规则**:

   您希望根据个人资料的年龄更改阈值。 如果配置文件低于40，则您希望定义4的限制，而对于较旧的配置文件，定义2的限制。 您可以在疲劳规则中直接创建一个公式来根据配置文件的年龄计算阈值，而不是为每个具有扩展字段的配置文件定义此阈值。 在我们的例子中，公式是 **[!UICONTROL Iif (@age<40, 4, 2)]**。

   ![](assets/fatigue25.png)

   >[!NOTE]
   >
   >本节还包括使用阈值计算公式的疲劳规则的分步示例。

* 创建可细化配置文 **件和提交阈值** 的疲劳规则：

   您已使用“分数”字段扩展了配置文件资源，并且您还使用“类型”字段扩展了提交资源。 您要定义一个恒定的阈值3，但是要从计数中排除“警报”或“黑色星期五”类型的所有提交以及得分大于10的所有配置文件。 当规则执行时，它将在过去和计划的分发中计算所有不属于“警报”或“黑色星期五”类型的分发发送到得分小于10的配置文件。

   ![](assets/fatigue26.png)

这里是一个使用阈值计算公式的疲劳规则的分步示例。

在此用例中，我们希望创建一个排版规则，以防止每周向高级配置文件发送超过2条消息，并防止每周向标准配置文件发送2条消息。

为了识别客户和潜在客户，我们通过字段扩展了配置文件资源， **[!UICONTROL Status]** 该字段包含0表示高级配置文件，1表示标准配置文件。

要创建规则，请应用以下步骤：

1. 创建新的 **Fatuigy** type排版规则。
1. 在该部 **[!UICONTROL Threshold]** 分中，我们要创建一个公式来根据每个配置文件计算阈值。 在字 **[!UICONTROL Depends on the recipient]** 段中选 **[!UICONTROL Threshold type]** 择值，然后单击字段右侧的第二个按钮的图 **[!UICONTROL Threshold computation formula]** 标。

   ![](assets/fatigue7.png)

1. 在部 **[!UICONTROL List of functions]** 分中，双击节点中 **的Iif** 函 **[!UICONTROL Others]** 数。

   ![](assets/fatigue8.png)

1. 然后，在部分中选择配置 **文件的** “状态 **[!UICONTROL Available fields]** ”。

   ![](assets/fatigue9.png)

1. 输入所需的值以创建以下公式： **Iif(@status=0,2,4)**

   ![](assets/fatigue10.png)

   如果状态等于0，则通过此公式可分配值2，对于所有其他状态，则可分配值4。

1. 单击 **[!UICONTROL Confirm]** 以批准公式。
1. 指示 **[!UICONTROL Sliding period]** 将应用该规则的位置：在这种情况下，将交货期限限制为2周。

   ![](assets/fatigue11.png)

1. 现在，将您刚刚创建的规则关联到一个类型学，以便将其应用到您的交付。 为此，请选择选 **[!UICONTROL Typologies]** 项卡，单 **[!UICONTROL Create element]** 击并选择用于提交的类型。

   ![](assets/fatigue12.png)

1. 保存规则以批准创建。

该规则将应用于所有基于类型的交付。
