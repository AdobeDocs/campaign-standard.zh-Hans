---
title: 配置SMS频道
seo-title: 配置SMS频道
description: 配置SMS频道
seo-description: “了解SMS配置步骤：路由、编码、格式和高级属性。"
page-status-flag: 从未激活
uuid: 5f13dbd5-9522-419-8d9a-44c397cb2458
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: 配置渠道
discoiquuid: 356d4d4f-3d5a-468c-bff8-96767cd8 fff6
context-tags: extAccountMobile，概述；extAccount，main；交付，SMSContent，返回
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 866567d63dd2798eb56d42d4e163e5484c9b4d68

---


# Configuring SMS channel{#configuring-sms-channel}

To send SMS messages, one or several external accounts must be configured by an administrator under the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL SMS]** &gt; **[!UICONTROL SMS accounts]** menu.

[外部帐户](../../administration/using/external-accounts.md) 部分详细介绍了创建和修改外部帐户的步骤。您将在特定于外部帐户的参数下找到SMS消息。

## Defining an SMS Routing {#defining-an-sms-routing}

The external account **[!UICONTROL SMS routing via SMPP]** is provided by default, but it can be useful to add other accounts.

如果要使用SMTP协议，还可以创建新的外部帐户。For more information on SMS protocol and settings, refer to this [technical note](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html).

1. Create a new external account from **[!UICONTROL Administration > Application settings > External accounts]**.
1. Define the account type as **[!UICONTROL Routing]**, the channel as **[!UICONTROL Mobile (SMS)]** and the delivery mode as **[!UICONTROL Bulk delivery]**.

   Once these routing parameters have been defined, the SMS connector ( **[!UICONTROL Generic SMPP]** ) is selected automatically. 此连接器允许Adobe Campaign通过SMTP协议连接到短消息服务中心(SMS-C)，将SMS消息直接发送到目标配置文件。

   ![](assets/sms_routing.png)

1. 定义连接设置。

   要输入特定于发送SMS消息的连接设置，请与您的SMS服务提供商联系，向您解释如何完成不同的外部帐户字段。

   ![](assets/sms_connection.png)

   The **[!UICONTROL Enable TLS over SMPP]** option allows you to encrypt SMPP traffic.

   **[!UICONTROL Enable verbose SMPP traces in the log file]** 允许您转储日志文件中的所有SMTP流量。必须启用此选项才能对连接器进行故障诊断，并与提供商看到的流量进行比较。

1. Contact Adobe who will give you the value to enter into the **[!UICONTROL SMS-C implementation name]** field, depending on the provider chosen.
1. 定义SMTP通道设置。You can learn more in the [SMS encoding and formats](../../administration/using/configuring-sms-channel.md#sms-encoding-and-formats) section.

   Enable the **[!UICONTROL Store incoming MO in the database]** if you want all incoming SMS to be stored in the inSMS table. For more information on how to retrieve your incoming SMS, refer to this [section](../../channels/using/managing-incoming-sms.md#storing-incoming-sms).

   **[!UICONTROL Enable Real-time KPI updates during SR processing]** 此选项可在发送交付后实时更新 **[!UICONTROL Delivered]** 或 **[!UICONTROL Bounces + Errors]** 更新KPI。These KPIs can be found in the **[!UICONTROL Deployment]** window and are directly recalculated from the SR (Status Report) received from the provider.

   ![](assets/sms_connection_1.png)

1. Define the **[!UICONTROL Throughput and timeouts]** parameters.

   您可以以MT每秒的速率指定出站消息的最大吞吐量(“MT”、“已终止”)。如果在对应字段中输入“0”，则吞吐量将无限制。

   所有与持续时间对应的字段的值需要在秒内完成。

1. 定义SMS-C特定参数，以防您需要定义特定编码映射。For more information, refer to the [SMSC specifics](../../administration/using/configuring-sms-channel.md#smsc-specifics) section.

   Enable the **[!UICONTROL Send full phone number (send characters other than digits)]** option if you don't want to respect the SMPP protocol and transfer the **[!UICONTROL +]** prefix to the server of the SMS provider (SMS-C).

   However, given that certain providers require the use of the **[!UICONTROL +]** prefix, it is advised that you check with your provider and they will suggest that you enable this option if necessary.

1. 根据需要定义自动回复，以根据回复内容触发触发操作。For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).
1. 保存SMS路由外部帐户的配置。

您现在可以使用新的路由功能通过Adobe Campaign发送SMS消息。

## SMS encoding and formats {#sms-encoding-and-formats}

### SMS encoding, length and transliteration {#sms-encoding--length-and-transliteration}

默认情况下，SMS中的字符符合GSM(全球系统for Mobile Communications)标准。

对于在多个部分发送的消息，使用GSM编码的SMS消息仅限于160个字符，或每个SMS的153个字符。

>[!NOTE]
>
>某些字符计为两个(大括号、方括号、欧元符号等)。The list of available GSM characters is presented in the [Table of characters - GSM Standard](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard) section.

如果您喜欢，可以通过选中相应的框来授权字符翻译。

![](assets/sms_transliteration.png)

翻译包括在GSM标准未考虑到该字符时替换另一个SMS字符的其他字符。

* **如果授权**，则在发送消息时，未考虑到的每个字符都将替换为GSM字符。例如，字母“ë”替换为“e”。因此消息会略微更改，但字符限制将保持不变。
* When transliteration is **not authorized**, each message that contains characters that are not taken into account is sent in binary format (Unicode): all of the characters are therefore sent as they are. 但是，使用Unicode的SMS消息仅限于70个字符(对于在多个部分发送的消息，则为每SMS67个字符)。如果超过最大字符数，则会发送多条消息，这可能会造成额外的费用。

>[!CAUTION]
>
>在SMS消息内容中插入个性化字段可引入GSM编码未考虑到的字符。A content example is offered in the [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md) section.

默认情况下，字符翻译被禁用。如果您希望保留SMS消息中的所有字符，但不要更改正确的姓名，我们建议您不要启用此选项。

但是，如果SMS消息包含大量生成Unicode消息的字符，则可以选择启用此选项来限制发送消息的成本。

### Table of characters - GSM Standard {#table-of-characters---gsm-standard}

本节介绍GSM标准中考虑的字符。插入到邮件正文中的所有字符(除下面提到的内容之外)将整个消息转换为二进制格式(Unicode)，因此将其限制为70个字符。For more on this, refer to the [SMS encoding, length and transliteration](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

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

SP：Space(空间)

ESC：Escape

LF：Line Feed

CR：回车

**高级字符(计数两次)**

^ { } [ ~ ] | €

### SMSC specifics {#smsc-specifics}

>[!NOTE]
>
>这些选项允许您调整连接器以使用非标准SMSC(即不遵循SMTP3.4规范)或特定编码要求，并且只应由高级用户配置。

发送SMS消息时，Adobe Campaign可使用一个或多个文本编码。每个编码都有自己的特定字符集，并确定适合SMS消息的字符数。

**[!UICONTROL DATA_CODING]** 该字段允许Adobe Campaign与使用编码的SMS-C通信。

>[!NOTE]
>
>**data_ coding** 值与实际使用的编码之间的映射是标准化的。Nevertheless, certain SMS-C have their own specific mapping: in this case, your **Adobe Campaign** administrator needs to declare this mapping. 请咨询您的提供商了解更多信息。

**[!UICONTROL Define a specific mapping of encodings]** 该功能允许您声明 **data_ combings** 并根据需要强制编码：为此，请在表中指定一个编码。

**配置**

* When the **[!UICONTROL Define a specific mapping of encodings]** functionality is not checked, the connector takes on a generic behavior:

   * It will try to use GSM encoding to which it assigns the value **data_coding = 0**.
   * If GSM encoding fails, it will use **UCS2** encoding to which it assigns the value **data_coding = 8**.
   ![](assets/sms_data_coding.png)

* When the **[!UICONTROL Define a specific mapping of encodings]** functionality is checked, you can define the encodings that you would like to use as well as the linked **[!UICONTROL data_coding]** field values. 如果未完成第一个编码，Adobe Campaign将尝试使用列表中的第一个编码，然后尝试使用以下编码。

   The order of declaration is important: it is recommended that you put the list in ascending order **of cost** in order to favor the encodings allowing you to fit as many characters as possible in each SMS message.

   仅声明要使用的编码。如果SMS-C提供的某些编码不应与您使用的目的相对应，请勿在列表中声明这些编码。

   ![](assets/sms_data_coding1.png)

### Automatic reply sent to the MO {#automatic-reply-sent-to-the-mo}

当配置文件回复通过Campaign发送的SMS消息时，您可以配置自动发送回他和执行操作的消息。

For more information, refer to [this section](../../channels/using/managing-incoming-sms.md).

## Configuring SMS properties {#configuring-sms-properties}

本节详细介绍SMS交付或SMS模板属性屏幕中SMS特有的参数列表。

The specific parameters for sending SMS messages are regrouped in the **[!UICONTROL Send]** and in the **[!UICONTROL Advanced parameters]** sections.

![](assets/sms_options.png)

* **[!UICONTROL From]** 此选项允许您使用字符串个性化SMS消息发送者的姓名。这是收件人移动电话上的SMS消息发送者姓名的名称。

   如果此字段为空，则它将是将使用的外部帐户中提供的源编号。如果没有提供源编号，则将为将使用的短代码。The external account specific to SMS delivery is presented in the [External SMS account](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) section.

   ![](assets/sms_smpp.png)

   >[!CAUTION]
   >
   >请检查您所在国家/地区关于修改发送方地址的法律。您还应咨询SMS服务提供商，了解他们是否提供此功能。

* **[!UICONTROL Maximum number of SMS per message]** 此选项允许您定义用于发送消息的SMS消息数。如果超出此数量，则不会发送邮件。

   >[!CAUTION]
   >
   >如果您在SMS消息的内容中插入了个性化字段或条件文本，则消息的长度也会随之增加，因此发送的SMS消息的数量可能因一个收件人而异。For more on this, refer to the [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md) section.

* **[!UICONTROL Transmission mode]** 该字段允许您确定SMS消息的传送方法：

   * **[!UICONTROL Saved on SIM card]**：消息存储在收件人的电话SIM卡上。
   * **[!UICONTROL Saved on mobile]**：消息存储在电话的内部内存上。
   * **[!UICONTROL Flash]**：该消息作为通知显示在收件人的移动电话上，然后它消失时不会被保存。

