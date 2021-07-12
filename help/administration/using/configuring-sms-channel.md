---
solution: Campaign Standard
product: campaign
title: 配置短信渠道
description: “了解短信配置步骤：路由、编码、格式和高级属性。”
audience: administration
content-type: reference
topic-tags: configuring-channels
context-tags: extAccountMobile,overview;extAccount,main;delivery,smsContent,back
feature: 实例设置
role: Admin
level: Experienced
exl-id: 5ff1d636-eac7-4909-be16-4f4b439b19ff
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '1567'
ht-degree: 95%

---

# 配置短信渠道{#configuring-sms-channel}

要发送短信消息，管理员必须通过 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL SMS]** > **[!UICONTROL SMS accounts]** 菜单配置一个或多个外部帐户。

有关创建和修改外部帐户的详细步骤，请参见[外部帐户](../../administration/using/external-accounts.md)一节。下文中介绍了专用于外部帐户发送短信消息的参数。

## 定义短信路由 {#defining-an-sms-routing}

默认提供外部帐户 **[!UICONTROL SMS routing via SMPP]**，但也可添加其他帐户。

如果想要使用 SMPP 协议，您也可以创建新的外部帐户。有关短信协议和设置的更多信息，请参阅此[技术说明](https://helpx.adobe.com/cn/campaign/kb/sms-connector-protocol-and-settings.html)。

1. 从 **[!UICONTROL Administration > Application settings > External accounts]** 创建新的外部帐户。
1. 将帐户类型定义为 **[!UICONTROL Routing]**、渠道定义为 **[!UICONTROL Mobile (SMS)]**，投放模式定义为 **[!UICONTROL Bulk delivery]**。

   ![](assets/sms_routing.png)

1. 定义连接设置。

   要输入专用于发送短信消息的连接设置，请与短信服务提供商联系，提供商将向您说明如何填写各种外部帐户字段。

   ![](assets/sms_connection.png)

   利用 **[!UICONTROL Enable TLS over SMPP]** 选项，可加密 SMPP 通信。

   利用 **[!UICONTROL Enable verbose SMPP traces in the log file]** 可将所有 SMPP 通信记录转储到日志文件中。必须启用此选项才能对连接器进行故障诊断，并与提供商的通信记录进行对比。

1. 联系 Adobe，Adobe 将根据所选的提供商为您提供用于输入到 **[!UICONTROL SMS-C implementation name]** 字段中的值。
1. 定义 SMPP 渠道设置。有关更多信息，请参见[短信编码和格式](#sms-encoding-and-formats)一节。

   如果您希望将所有传入的短信存储在 inSMS 表格中，请启用 **[!UICONTROL Store incoming MO in the database]**。有关如何检索传入短信的更多信息，请参阅此[章节](../../channels/using/managing-incoming-sms.md#storing-incoming-sms)。

   利用 **[!UICONTROL Enable Real-time KPI updates during SR processing]** 选项，可在发送投放后实时更新 **[!UICONTROL Delivered]** 或 **[!UICONTROL Bounces + Errors]** KPI。这些 KPI 会显示在 **[!UICONTROL Deployment]** 窗口中，并可根据接收自提供商的 SR（状态报告）重新计算。

   ![](assets/sms_connection_1.png)

1. 定义 **[!UICONTROL Throughput and timeouts]** 参数。

   您可以指定叫客消息的最大吞吐量（其单位为每秒 MT 数，其中的“MT”指的是“终端终止”）。如果在对应的字段中输入“0”，则吞吐量将没有限制。

   对应于持续时间的所有字段值，都必须填写以秒为单位的值。

1. 需要定义特定编码映射时，可定义 SMS-C 特定参数。有关更多信息，请参阅 [SMSC 详情](#smsc-specifics)一节。

   如果您不想遵守 SMPP 协议，且想要将 **[!UICONTROL +]** 前缀转移给短信提供商的服务器 (SMS-C)，请启用 **[!UICONTROL Send full phone number (send characters other than digits)]** 选项。

   但是，鉴于某些提供商需要使用 **[!UICONTROL +]** 前缀，建议您与提供商进行核实，他们将会提供是否有必要启用此选项的建议。

1. 如果需要，可定义自动回复以根据回复的内容触发操作。有关更多信息，请参阅[此章节](../../channels/using/managing-incoming-sms.md#managing-stop-sms)。
1. 保存短信路由外部帐户的配置。

您现在可以通过 Adobe Campaign，使用新路由发送短信消息。

## 短信编码和格式 {#sms-encoding-and-formats}

### 短信编码、长度和音译 {#sms-encoding--length-and-transliteration}

默认情况下，短信的字符数应符合 GSM（全球移动通信系统）标准。

使用 GSM 编码的短信消息长度上限为 160 个字符，而对于分段发送的消息，每段短信的长度上限为 153 个字符。

>[!NOTE]
>
>某些字符会被计为两个字符（大括号、方括号、欧元符号等）。可用 GSM 字符的列表，请参见[字符表 - GSM 标准](#table-of-characters---gsm-standard)一节。

如果需要，您可通过勾选对应的方框来授权字符音译。

![](assets/sms_transliteration.png)

音译指的是，如果 GSM 标准无法识别某个短信字符，则会用另一个字符替换该字符。

* 如果&#x200B;**授权**&#x200B;音译，则发送消息后，无法识别的每个字符都将被替换为 GSM 字符。例如，字母“ë”会被替换为“e”。因此，消息会有些微变化，但字符限制将保持不变。
* **未授权**&#x200B;音译时，包含无法识别字符的每条消息都将以二进制格式 (Unicode) 发送：这样，所有字符都会按原样发送。但是，使用 Unicode 的短信消息长度上限为 70 个字符（对于分段发送的消息，每段短信的长度上限为 67 个字符）。如果超过最大字符数，则会分段发送多条消息，这可能会产生额外的费用。

>[!IMPORTANT]
>
>将个性化字段插入短信消息内容，可能会引入 GSM 编码无法识别的字符。有关内容的示例，请参见[个性化短信消息](../../channels/using/personalizing-sms-messages.md)一节。

默认情况下，字符音译处于禁用状态。如果您希望将短信消息中的所有字符都按原样保留，以免名称等内容被错误地更改，我们建议您不要启用此选项。

但是，如果短信消息包含大量会生成 Unicode 消息的字符，则可以选择加入此选项以限制发送消息的成本。

### 字符表 - GSM 标准 {#table-of-characters---gsm-standard}

本节介绍 GSM 标准可识别的字符。除下方所列的字符外，插入消息正文的所有其他字符都会导致整个消息被转换为二进制格式 (Unicode)，从而使其长度限制变成 70 个字符。有关更多信息，请参阅[短信编码、长度和音译](#sms-encoding--length-and-transliteration)一节。

**基本字符**

<table> 
 <tbody> 
  <tr> 
   <td> @<br /> </td> 
   <td> <img height="21px" src="assets/delta.png" /> <br /> </td> 
   <td> SP<br /> </td> 
   <td> 0<br /> </td> 
   <td> ¡<br /> </td> 
   <td> P<br /> </td> 
   <td> ¿<br /> </td> 
   <td> P<br /> </td> 
  </tr> 
  <tr> 
   <td> £<br /> </td> 
   <td> _<br /> </td> 
   <td> !<br /> </td> 
   <td> 1<br /> </td> 
   <td> A<br /> </td> 
   <td> Q<br /> </td> 
   <td> a<br /> </td> 
   <td> q<br /> </td> 
  </tr> 
  <tr> 
   <td> $<br /> </td> 
   <td> <img height="21px" src="assets/phi.png" /> <br /> </td> 
   <td> "<br /> </td> 
   <td> 2<br /> </td> 
   <td> B<br /> </td> 
   <td> R<br /> </td> 
   <td> b<br /> </td> 
   <td> r<br /> </td> 
  </tr> 
  <tr> 
   <td> ¥<br /> </td> 
   <td> <img height="21px" src="assets/gamma.png" /> <br /> </td> 
   <td> #<br /> </td> 
   <td> 3<br /> </td> 
   <td> C<br /> </td> 
   <td> S<br /> </td> 
   <td> c<br /> </td> 
   <td> s<br /> </td> 
  </tr> 
  <tr> 
   <td> è<br /> </td> 
   <td> <img height="21px" src="assets/delta.png" /> <br /> </td> 
   <td> ¤<br /> </td> 
   <td> 4<br /> </td> 
   <td> D<br /> </td> 
   <td> T<br /> </td> 
   <td> d<br /> </td> 
   <td> t<br /> </td> 
  </tr> 
  <tr> 
   <td> é<br /> </td> 
   <td> <img height="21px" src="assets/omega.png" /> <br /> </td> 
   <td> %<br /> </td> 
   <td> 5<br /> </td> 
   <td> E<br /> </td> 
   <td> U<br /> </td> 
   <td> e<br /> </td> 
   <td> u<br /> </td> 
  </tr> 
  <tr> 
   <td> ù<br /> </td> 
   <td> <img height="21px" src="assets/pi.png" /> <br /> </td> 
   <td> &amp;<br /> </td> 
   <td> 6<br /> </td> 
   <td> F<br /> </td> 
   <td> V<br /> </td> 
   <td> f<br /> </td> 
   <td> v<br /> </td> 
  </tr> 
  <tr> 
   <td> ì<br /> </td> 
   <td> <img height="21px" src="assets/psi.png" /> <br /> </td> 
   <td> '<br /> </td> 
   <td> 7<br /> </td> 
   <td> G<br /> </td> 
   <td> W<br /> </td> 
   <td> g<br /> </td> 
   <td> w<br /> </td> 
  </tr> 
  <tr> 
   <td> ò<br /> </td> 
   <td> <img height="21px" src="assets/sigma.png" /> <br /> </td> 
   <td> (<br /> </td> 
   <td> 8<br /> </td> 
   <td> H<br /> </td> 
   <td> X<br /> </td> 
   <td> h<br /> </td> 
   <td> x<br /> </td> 
  </tr> 
  <tr> 
   <td> Ç<br /> </td> 
   <td> <img height="21px" src="assets/theta.png" /> <br /> </td> 
   <td> )<br /> </td> 
   <td> 9 </td> 
   <td> I<br /> </td> 
   <td> Y<br /> </td> 
   <td> i<br /> </td> 
   <td> y<br /> </td> 
  </tr> 
  <tr> 
   <td> LF<br /> </td> 
   <td> <img height="21px" src="assets/xi.png" /> <br /> </td> 
   <td> *<br /> </td> 
   <td> :<br /> </td> 
   <td> J<br /> </td> 
   <td> Z<br /> </td> 
   <td> j<br /> </td> 
   <td> z<br /> </td> 
  </tr> 
  <tr> 
   <td> Ø<br /> </td> 
   <td> ESC<br /> </td> 
   <td> +<br /> </td> 
   <td> ;<br /> </td> 
   <td> K<br /> </td> 
   <td> Ä<br /> </td> 
   <td> k<br /> </td> 
   <td> ä<br /> </td> 
  </tr> 
  <tr> 
   <td> ø<br /> </td> 
   <td> Æ<br /> </td> 
   <td> ,<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> L<br /> </td> 
   <td> Ö<br /> </td> 
   <td> l<br /> </td> 
   <td> ö<br /> </td> 
  </tr> 
  <tr> 
   <td> CR<br /> </td> 
   <td> æ<br /> </td> 
   <td> -<br /> </td> 
   <td> = </td> 
   <td> M<br /> </td> 
   <td> Ñ<br /> </td> 
   <td> m<br /> </td> 
   <td> ñ<br /> </td> 
  </tr> 
  <tr> 
   <td> Å<br /> </td> 
   <td> ß<br /> </td> 
   <td> .<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> N<br /> </td> 
   <td> Ü<br /> </td> 
   <td> n<br /> </td> 
   <td> ü<br /> </td> 
  </tr> 
  <tr> 
   <td> å<br /> </td> 
   <td> É<br /> </td> 
   <td> /<br /> </td> 
   <td> ?<br /> </td> 
   <td> O<br /> </td> 
   <td> §<br /> </td> 
   <td> o<br /> </td> 
   <td> à<br /> </td> 
  </tr> 
 </tbody> 
</table>

SP：空格键

ESC：Escape 键

LF：换行

CR：回车

**高级字符（计为两个字符）**

^ { } [ ~ ] | €

### SMSC 详情 {#smsc-specifics}

>[!NOTE]
>
>利用这些选项，可调整连接器以使用非标准 SMSC（即不完全遵循 SMPP 3.4 规范）或特定编码要求，并且只应由高级用户进行配置。

发送短信消息时，Adobe Campaign 可以使用一个或多个文本编码。每个编码都有属于自己的特定字符集，可确定其适合短信消息的字符数。

利用 **[!UICONTROL DATA_CODING]** 字段，Adobe Campaign 可与用于编码的 SMS-C 通信。

>[!NOTE]
>
>**Data_coding** 值与实际使用的编码之间的映射，经过标准化处理。但是，某些 SMS-C 具有属于自己的特定映射：在这种情况下，**Adobe Campaign** 管理员需要声明该映射。有关更多信息，请咨询您的提供商。

利用 **[!UICONTROL Define a specific mapping of encodings]** 功能，可声明 **data_codings**，并在必要时强制进行编码：要实现此目的，请指定表格中的一种编码。

**配置**

* 未勾选 **[!UICONTROL Define a specific mapping of encodings]** 功能时，连接器会采取常规行为：

   * 它会尝试将 GSM 编码用于分配值 **data_coding = 0**。
   * 如果 GSM 编码失败，则会将 **UCS2** 编码用于分配值 **data_coding = 8**。

   ![](assets/sms_data_coding.png)

* 勾选 **[!UICONTROL Define a specific mapping of encodings]** 功能后，您可以定义要使用的编码以及链接的 **[!UICONTROL data_coding]** 字段值。Adobe Campaign 将尝试使用列表中的第一种编码，如果第一种编码被证实不可用，则使用后续的编码。

   声明的顺序很重要：建议您按照&#x200B;**成本**&#x200B;的升序方式排列编码列表，以选出可尽量减少短信消息发送条数的编码。

   仅声明您要使用的编码。如果 SMS-C 提供的某些编码与您的使用目的并不对应，请不要在列表中声明这些编码。

   ![](assets/sms_data_coding1.png)

### 发送给 MO 的自动回复 {#automatic-reply-sent-to-the-mo}

当某个用户档案回复通过 Campaign 发送的短信消息时，您可以配置自动发回给他的消息以及要自动执行的操作。

有关更多信息，请参见[此章节](../../channels/using/managing-incoming-sms.md)。

## 配置短信属性 {#configuring-sms-properties}

本节详细介绍短信投放或短信模板的属性屏幕中特有的短信参数列表。

用于发送短信消息的特定参数，被重组到了 **[!UICONTROL Send]** 和 **[!UICONTROL Advanced parameters]** 章节。

![](assets/sms_options.png)

从&#x200B;**[!UICONTROL Advanced parameters]**&#x200B;部分：

* **[!UICONTROL Short code]**&#x200B;允许您向投放添加特定的短代码。 在准备消息时，将自动排除选择退出此特定短代码的收件人。 有关如何配置短代码的更多信息，请参阅[此部分](../../channels/using/managing-incoming-sms.md)。

   >[!NOTE]
   >
   >如果&#x200B;**[!UICONTROL Short code]**&#x200B;字段留空，则将使用外部帐户中设置的&#x200B;**[!UICONTROL Short code]**&#x200B;字段值。

从短信模板的&#x200B;**[!UICONTROL Send]**&#x200B;部分：

* 利用 **[!UICONTROL Maximum number of SMS per message]** 选项，可定义用于发送消息的短信消息数量。如果超出此数量，则不会发送消息。

   >[!IMPORTANT]
   >
   >如果在短信消息内容中插入了个性化字段或条件文本，则消息的长度以及发送短信消息的数量，可能会因收件人而异。有关更多信息，请参阅[个性化短信消息](../../channels/using/personalizing-sms-messages.md)一节。

   ![](assets/sms_smpp_3.png)

* 利用 **[!UICONTROL Transmission mode]** 字段，可确定短信消息的投放方法：

   * **[!UICONTROL Saved on SIM card]**：消息存储在收件人的手机 SIM 卡上。
   * **[!UICONTROL Saved on mobile]**：消息存储在手机的内部存储中。
   * **[!UICONTROL Flash]**：消息将作为通知显示在收件人的手机上，然后通知会消失且不进行保存。
