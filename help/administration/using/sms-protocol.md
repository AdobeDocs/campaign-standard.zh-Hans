---
solution: Campaign Standard
product: campaign
title: SMS连接器协议和设置
description: 进一步了解SMS连接器以及如何配置它。
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 6ac2a2d5b2a0924847e54068145d6def22f8023f
workflow-type: tm+mt
source-wordcount: '8382'
ht-degree: 0%

---


# SMS连接器协议和设置{#sms-connector-protocol}

>[!NOTE]
>
>在此[页面](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.htmln#sending-messages)中可找到Adobe Campaign Classic的&#x200B;**SMS连接器协议和设置**。
>
>通过此文档，所有对协议详细信息、字段名称和值的引用都引用[SMPP 3.4规范](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)。

## 概述 {#overview}

短信可能仅限于发送不带格式的短文本消息，但其简单性使其成为一种宝贵的通信渠道。

发送SMS的主要方式有两种：

* 手动从电话发送，这是在人与人之间直接通信的常用方式。

* 从Internet发送，Adobe Campaign发送消息的方式。 为此，您需要一个SMS服务提供商，将Internet连接到移动网络。
Adobe Campaign使用SMPP协议将SMS发送到服务提供商。

此文档将指导您完成在Adobe Campaign和SMPP提供商之间建立的连接。

SMPP提供商有时可能会偏离官方规范，但Adobe Campaign的SMS连接器提供了许多选项来调整其行为，使其与大多数提供商兼容。

>[!IMPORTANT]
>
>设置与新提供程序的连接可能需要一些技术技能、TCP知识、二进制、十六进制表示和文本编码。 它还需要与提供商积极合作。

### SMS类型{#sms-types}

当通过短信提供商发送大量短信时，您会遇到三种不同的短信：

* **SMS MT（已终止移动）**:通过SMPP提供商向移动电话发送Adobe Campaign的SMS。

* **SMS MO（源自移动）**:由移动设备通过SMPP提供商发送给Adobe Campaign的SMS。

* **SMS SR（状态报告）或DR或DLR(投放收据)**:由移动设备通过SMPP提供商发送给Adobe Campaign的返回回执，表明SMS已成功接收。Adobe Campaign还可能收到指示无法传递消息的SR，通常带有错误的描述。

您需要区分鸣谢（RESP PDU, SMPP协议的一部分）和SR:SR是一种通过网络端对端发送的SMS，而确认只是确认一次传输成功。

确认和SR都可能触发错误，区分二者将有助于故障排除。

### SMS {#information-sms}携带的信息

短信携带的信息比文本多。 下面是您在SMS中可以找到的列表:

* 文本（限制为140字节），表示70到160个字符，具体取决于编码。 有关详细信息和限制，请参见下面的[SMS文本编码](../../administration/using/sms-protocol.md#sms-text-encoding)。

* 收件人地址，有时称为`ADC`或`MSISDN`。 这就是接收短信的手机号码。

* 发件人地址，可以称为`oADC`或有时称为`sender id`。 这可以是日常使用中的电话号码、通过提供商发送的简短代码或姓名。 名称是可选功能，在这种情况下，您无法回复SMS。

* 一个标志，用于指示消息是否为Flash消息。 闪存消息是不存储在内存中的弹出消息。

* 指示是否需要SR的标志。

* 有效日期，之后不允许网络设备重试。

* 一个`data_coding`字段，指示文本的编码。

## SMPP协议{#smpp-protocol}

Adobe Campaign Standard支持SMPP协议3.4版。这是一种广泛的协议，允许向提供商(SMSC)发送SMS，并接收SMS和接收。 有关详细信息，请参阅[SMPP文档](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)。

SMS服务提供商端的网络设备通常称为SMSC。

### SMPP连接{#smpp-connections}

Adobe Campaign通过TCP连接到SMS服务提供商的网络设备。 SMPP协议设置从Adobe Campaign到提供者的永久TCP连接。 TCP连接始终由Adobe Campaign启动，甚至接收消息。
SMPP会打开1个或2个TCP连接，具体取决于其模式。 所有连接始终由Adobe Campaign启动。

SMPP协议可以在两种模式下工作：

* **发射机+接收机（或TX+RX）**:两个单独的TCP连接用于发送和接收消息。
* **收发器(Abor TRX)**:单个TCP连接用于发送和接收消息。

>[!NOTE]
>
>TRX更适合Adobe Campaign Standard，因为它减少了连接数，并在出现故障时简化了连接恢复。

### SMPP PDU {#smpp-pdu}

SMPP传输单元（“数据包”）称为PDU。 **PDU**&#x200B;包含命令、状态、序列号和数据。

每个PDU必须由`SMPP RESP PDU`（同步响应）进行确认。 请求可以流水线处理：发送方无需等待`RESP`即可发送多个命令，随时可以流水的请求数称为窗口。 `RESP PDU` 可能以任何顺序到达，而与其相应的启动器PDU的顺序无关。

在分离的&#x200B;**Transmitter+receiver**&#x200B;模式中，所使用的连接取决于所传输的消息类型。 发射机连接用于MT，接收机连接用于MO和SR。 每种消息的请求和响应都通过同一TCP连接发送。

例如，在发送MT时，使用发射器连接，并且确认MT的`RESP`也通过发射器渠道发送。 当您收到MO（或SR）时，接收器连接用于接收MO并发送确认MO的`RESP`。

![](assets/sms_protocol_1.png)

在Adobe Campaign Standard,MT和SR协调是MTA的固有，因此没有专用的SMS过程。

成功的`SUBMIT_SM_RESP PDU`在发送日志中触发“已发送”消息状态，而成功的`DELIVER_SM (SR) PDU`触发“已接收”消息状态。

### 安全方面{#security-aspects}

协议本身未加密。 大多数提供者在时实允许列表施IP的变体，因此Adobe Campaign服务器IP地址必须声明给提供者。

Adobe Campaign支持在绑定阶段传递登录名和口令。 它还支持SMPP而不是TLS。 应当指出，需要证书才能获得适当的安全。 尽管SMPP连接器允许绕过证书检查，但它只应用于测试，因为没有证书的TLS提供的安全级别显着降低。

连接器使用系统`openssl`库提供的默认证书。 通常由Debian上的`/etc/ssl/certs`目录提供。 默认情况下，此目录由“ca-certificates”包提供，但可以对其进行自定义。

### 每种PDU{#information-pdu}中的信息

每种PDU都有不同的字段，这些字段携带不同的信息。 [SMPP 3.4规范](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)中详细介绍了这些PDU。

以下各节介绍PDU及其同步响应(`*_RESP PDU`)。 所有PDU都必须由相应的`RESP`进行确认，这是规范的必需部分。

PDU可以有可选字段。 此处只介绍最常见的字段。 有关详细信息，请参阅[SMPP 3.4规范](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)。

#### BIND_TRANSMITTER / BIND_RECEIVER / BIND_RENSIVER {#bind-transmitter}

此PDU用于启动与SMSC的连接。 **发射机**、 **** 接收机 **** 和收发机模式只改变允许通过此连接传输的SMS的类型，具体来说：

| 模式 | 允许的短信种类 |
|:-:|:-:|
| 发射机 | MT |
| 接收器 | MO + SR |
| 收发器 | MT + MO + SR |

`BIND_* PDU`中值得注意的字段：

* **system_id**:用于身份验证的登录名。设置外部帐户。

* **密码**:用于身份验证的口令。设置外部帐户。

* **system_type**:需要为某些提供者设置特定值。在外部帐户中设置，所有版本均可用。 通常区分不同类型的合同、渠道、国家等。

* **addr_** tonand  **addr_npi**:某些提供商要求。由外部帐户中的`Bind TON`和`Bind NPI`设置进行设置。

* **address_range**:某些提供商要求。大多数情况下，这是此连接上允许的一列表简短代码。 设置外部帐户。

`BIND_*_RESP` 没有特定字段，它会确认连接是否成功。

#### 解除绑定{#unbind}

此PDU必须由系统发送，然后才能断开连接。 在关闭连接之前，它必须等待匹配的`UNBIND_RESP PDU`。

符合SMSC的TCP连接不能关闭，TCP连接由Adobe Campaign连接器控制。

#### SUBMIT_SM {#submit-sm}

此PDU向SMSC发送MT。 其响应PDU提供MT的ID。

`SUBMIT_SM PDU`中值得注意的字段：

* **service_type**:需要。在投放属性中设置。

* **source_addr_** ton和 **source_addr_npi**:指示传输的源地址类型。这些字段的含义是标准化的，但由于某些提供者使用它的方式不同，您应要求提供者提供其正确的值。 设置外部帐户。

* **source_addr**:MT的源地址/oADC。它将显示在手机上。 在外部帐户和投放中设置，投放中的值优先于外部帐户的值。

* **dest_addr_** ton和 **dest_addr_npi**:指示传输的目标地址类型（例如，本地或国际格式）。这些字段的含义是标准化的，但由于某些提供者使用它的方式不同，您应要求提供者提供其正确的值。 设置外部帐户。

* **destination_addr**:收件人地址、电话号码或MSISDN。

* **esm_class**:用于判断文本字段中是否使用了UDH。如果未使用`message_payload`模式，则连接器将自动启用拆分SMS。

* **priority_flag**:此消息的优先级高于其他消息。这与投放本身的优先性有关。

* **validity_period**:不应尝试重试的时间戳。在投放中设置。

* **registered_投放**:告诉是否请求SR。Adobe Campaign始终设置此标志，但自动回复除外。 对于多部件消息，仅为第一部分设置标志。 所有版本都具有相同的行为。

* **data_coding**:指示文本字段中使用的编码。有关详细信息，请参阅[SMS文本编码](../../administration/using/sms-protocol.md#sms-text-encoding)部分。

* **short_message**:消息的文本。如果使用UDH，则还包含UHD头。

Adobe Campaign支持以下可选字段：

* **dest_addr_subumit**:用于指定SMS的目标:Flash、移动或SIM卡。在投放属性中设置。

* **message_payload**:在外部帐户中启用时，长消息将在单个PDU中发送，文本将在此字段而非字段中 `short_message` 传输。

#### SUBMIT_SM_RESP {#submit-sm-resp}

此PDU将包含MT的ID。 这有助于将其与传入的SR匹配。

>[!IMPORTANT]
>
>许多提供者以十六进制形式传输MT ID。 确保在外部帐户中正确设置MT确认&#x200B;**中的** ID格式。

一些提供者在发送SR后发送`SUBMIT_SM_RESP`。 为了解释该行为，Adobe Campaign在将&#x200B;**无效消息ID**&#x200B;回复到SR时等待30秒。

#### DELIVER_SM {#delivery-sm}

此PDU由SMSC发送给Adobe Campaign。 它包含MO或SR。

大多数字段与其`SUBMIT_SM`对应字段具有相同的含义。 以下是有用字段的列表:

* **source_addr**:MO/SR的源地址。通常这是电话号码。

* **destination_addr**:接收MO或SR的短代码。

* **esm_class**:用来判断PDU是MO还是SR。

* **short_message**:文本。对于SR，它包含SMPP协议规范附录B中描述的数据。 有关详细信息，请参见[SR错误管理](../../administration/using/sms-protocol.md#sr-error-management)。

Adobe Campaign可以通过一些配置调整来读取`receipted_message_id`可选字段中的消息ID。

#### DELIVER_SM_RESP {#deliver-sm-resp}

此PDU由Adobe Campaign发送以确认SR和MO。

Adobe Campaign Standard仅在所有处理步骤均成功后发送`DELIVER_SM_RESP`。 这保证在仍有处理错误的风险时不确认SR或MO。

#### INQUIRE_LINK {#enquire-links}

此PDU仅用于检查连接是否处于实时状态。 应根据提供商的需要设置频率。

默认60秒应与外部帐户中设置的大多数配置相匹配。

#### INQUIRE_LINK_RESP {#enquire-links-resp}

此PDU确认连接处于活动状态。

### 多部件SMS（长SMS）{#multipart}

多部分SMS或长SMS是多部分发送的SMS。 由于移动网络协议中的技术限制，SMS不能大于140字节，否则需要拆分。 请参阅[SMS文本编码](../../administration/using/sms-protocol.md#sms-text-encoding)部分，进一步了解适合SMS的字符数。

长信息的每个部分都是单独的SMS。 这些部件在网络上独立运行，并由接收移动电话组装。 为了处理重试和连接问题，Adobe Campaign以反向顺序发送这些部件，并仅在消息的第一部分请求SR，最后发送。 由于手机在收到第一部分时只显示一条消息，因此附加部分上的重试不会在手机上产生重复。

使用&#x200B;**投放**&#x200B;中的&#x200B;**每条消息的最大SMS数**&#x200B;设置，可以设置每条投放模板的最大SMS数。 在发送时，超过此限制的消息将失败，原因是短信故障过长。

有2种方法可发送长短信：

* **UDH**:发送长消息的默认和推荐方式。在此模式下，连接器将消息拆分为多个`SUBMIT_SM PDU`，其中包含UDH信息。 此协议是手机本身使用的协议。 这意味着Adobe Campaign对消息生成的控制度最高，因此能够准确计算发送的部件数量和拆分方式。

* **message_payload**:一次发送长信的方式 `SUBMIT_SM PDU`。提供商必须将其拆分，这意味着Adobe Campaign不可能确切知道发送了多少个部件。 某些提供商需要此模式，但我们建议您仅在它们不支持UDH时使用它。

有关协议和格式的详细信息，请参阅[ SUBMIT_SM PDU](../../administration/using/sms-protocol.md#information-pdu)的`esm_class`、`short_message`和`message_payload`字段的说明。

### 吞吐量上限和窗口{#throughput-capping}

大多数提供商要求每个SMPP连接都有吞吐量限制。 这可以通过在外部帐户中设置多个SMS来实现。 请注意，每个连接发生吞吐量限制，总有效吞吐量是每个连接的限制乘以连接总数。 这在[同时连接](../../administration/using/sms-protocol.md#connection-settings)一节中有详细介绍。

要达到最大的吞吐量，您需要微调最大发送窗口。 发送窗口是可以发送的`SUBMIT_SM PDU`数，无需等待`SUBMIT_SM_RESP`。 有关详细信息，请参阅[发送窗口设置](../../administration/using/sms-protocol.md#throughput-timeouts)部分。

### SR和错误管理（“附录B”）{#sr-error-management}

SMPP协议定义`RESP PDU`s中的标准同步错误，但它不定义SR的错误代码。 每个提供者都使用其自己的错误代码及其含义。

在[SMPP协议规范](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)（第167页）的附录B部分中提出建议，但这不列表实际错误代码及其含义。

为了适应错误管理，Adobe Campaign的广播消息系统已被用于正确设置错误及其严重性（硬、软等）。

如上所述，存在两种不同的错误：

* `SUBMIT_SM_RESP`中在消息发送到SMSC后立即发生的同步回复
* 可能稍后在移动设备收到消息或消息超时时收到的收据。 在这种情况下，错误在SR中找到。

收到SR时，其`short_message`字段中可找到状态和错误（例如，附录B符合要求的实现）。 PDU的`short_message`字段通常称为&#x200B;**文本字段**，因为它包含MT中的文本。 对于SR，它包含技术信息加一个名为&#x200B;**Text**&#x200B;的子字段。 这2个字段不同，`short_message`实际包含&#x200B;**Text**&#x200B;字段和其他信息。

#### SR文本字段格式{#sr-text-field-format}

规范建议对SR文本字段使用此格式。 它是子字段的列表，用冒号分隔空格，以分隔字段名称及其值。 字段名称不区分大小写。

与附录B建议匹配的SR文本字段示例：

```
id:1234567890 sub:001 dlvrd:001 submit date:1608011415 done date:1608011417 stat:DELIVRD err:000 Text:Hello Adobe world
```

id字段是`SUBMIT_SM_RESP PDU`中收到的ID，即MT的确认。

`sub` 而 `dlvrd` 且应该计算所传送的部件和所传送消息的数量，但Adobe Campaign没有使用这个，因为广播系统提供了更好、更集成的信息。

`submit date` 字段 `done date` 是指MT何时发送以及移动设备何时发送SR的指示时间戳。由于设置了错误日期的手机给出的时区问题，甚至时间戳错误。

stat字段很重要，因为它会告知消息的状态。 唯一重要的状态是`DELIVRD`、`UNDELIV`和`REJECTD`。 `DELIVRD`状态表示成功，另外两个表示错误。 其他值是可能的，但通常是中间通知，例如MT到达移动运营商，但不是移动电话。 Adobe Campaign会忽略这些中间通知。

错误字段包含提供程序特定的错误代码。 提供者必须提供可能的错误代码表及其含义，才能解释此值。

最后，文本字段通常包含MT文本的开头。 Adobe Campaign会忽略这一点，一些提供商不会通过传输它来避免PII泄漏和网络带宽消耗。 它可在故障排除过程中通过阅读此字段来更轻松地发现与测试MT匹配的SR。

### Adobe Campaign Standard扩展通用SMPP {#sr-processing}中SR处理的示例

此示例显示了在附录B建议下实施的情况、外部帐户中的默认值和成功的SMS MT。

```
id:1234567890 sub:001 dlvrd:001 submit date:1608011415 done date:1608011417 stat:DELIVRD err:000 Text:Hello Adobe world
```

首先，应用`id extraction`正则表达式提取ID并将其与相应的MT协调。

然后，应用`status extraction`正则表达式和`error code extraction`正则表达式来提取这些字段并附加到字符串。

广播消息由此信息构建，并附加原始未更改的字符串以供参考：

```
SR ExampleProvider DELIVRD 000|MESSAGE=id:1234567890 sub:001 dlvrd:001 submit date:1608011415 done date:1608011417 stat:DELIVRD err:000 Text:Hello Adobe world
```

然后，该消息被标准化，删除该消息部分以能够匹配具有相同状态和错误代码的多个消息。

```
SR ExampleProvider DELIVRD 000|#MESSAGE#
```

如果广播消息表中尚未设置消息，则将使用整个消息&#x200B;**firstText**&#x200B;和标准化消息创建新条目。 然后，连接器使用success和`error`正则表达式确定它是成功还是失败：

* 如果它与`success`正则表达式匹配，则它将被视为成功。

* 如果与`error`正则表达式匹配，则消息被限定为错误。

* 如果这两个正则表达式都不匹配，则忽略SR。 它可能是中间通知，不由Adobe Campaign处理。

默认情况下，所有错误都设置为软错误。 这意味着必须手动设置硬错误。

### SMS文本编码{#sms-text-encoding}

如果编码问题&#x200B;**，应始终与SMSC提供者联系。**&#x200B;只有SMSC提供商能够准确了解他们支持的编码以及可能因技术平台限制而适用的特殊规则。

SMS消息使用特殊的7位编码，通常称为GSM7编码。

在SMPP协议中，GSM7文本将扩展为每个字符8位，以便更轻松地进行故障排除。 SMSC将在将其发送到移动设备之前将其打包为7位／字符。 这意味着SMS的`short_message`字段在SMPP帧中最长可达160字节，而在移动网络上发送时，该字段长度限制为140字节。

在编码问题时，需要检查以下重要事项：

* 确保您知道哪些字符属于哪个编码。 GSM7不完全支持音符（重音）。 尤其是法语，在法语中，é和è是GSM7的一部分，但ê或ï不是。 西班牙语也是如此。

* 带有Cedilla(ç)的C仅在GSM7字母的大写中存在，但某些电话以小写或“智能”大小写显示它。 一般建议是完全避免它，并删除代码区或切换到UCS-2。

* **除非SMSC提供者明确** 请求，否则请勿在SMS中使用ASCII。这种编码浪费了空间，因为它具有8位字符，并且比GSM7的覆盖范围更小。 在北美使用的CDMA网络可能需要这种编码。

* 并非始终支持拉丁语-1。 尝试使用Latin-1之前，请检查与SMSC提供商的兼容性。

* 国家语言班次表不受Adobe Campaign连接器支持。 必须改用UCS-2或其他`data_coding`。

* UCS-2和UTF-16通常由电话混合。 使用UCS-2中不存在的表情符号和其他字符时，会出现此问题。

* 大多数手机没有所有UCS-2字符的字体字形。 智能手机往往能够很容易地显示稀有字符，但功能手机通常对它们所购买的国家母语中有用的功能的支持有限。 如果要使用emoji或ASCII图，请在发送前在各种电话上测试它。 Adobe Campaign预览不模拟缺失的字形，并将显示Web浏览器上可用的符号。

`data_coding`字段会告诉您使用的编码。 一个主要问题是，值0表示规范中的默认SMSC编码，通常指GSM7。 请咨询与`data_coding` = 0关联的SMSC合作伙伴，该Adobe Campaign仅支持该编码。 其他`data_coding`值往往遵循规范，但唯一确保的方法是与SMSC提供程序进行核对。

消息的最大大小取决于其编码。 下表总结了所有相关信息：

| 编码 | 常用data_coding | 邮件大小（字符） | 多部件SMS的部件大小 | 可用字符 |
|:-:|:-:|:-:|:-:|:-:|
| GSM7 | 0 | 160 | 152 | GSM7基本字符集+扩展（扩展字符需要2个字符） |
| 拉丁语-1 | 3 | 140 | 134 | ISO-8859-1 |
| UCS-2 <br>UTF-16 | 8 | 70 | 67 | Unicode（因电话而异） |

## SMPP外部帐户参数{#SMPP-parameters-external}

SMPP协议的每个实现都有许多不同。 为了提高兼容性和适应性，可以使用许多设置来更改SMPP连接器的行为。 本节介绍每个参数及其对连接器的影响。

### 常规参数和路由{#general-parameters-routing}

**限制此帐户的MTA实例**

可以设置允许连接到SMPP提供程序的MTA实例数的限制。 选中后，您最多可以指定使用的MTA数。

此选项允许对连接数进行更精细的控制，请参见[同时连接](../../administration/using/sms-protocol.md#connection-settings)。

如果设置的值高于正在运行的MTA的数量，则所有MTA都将正常运行：此选项仅限于，无法生成其他MTA。

如果您需要精确控制连接数，例如提供者要求，建议始终设置此选项，即使当前部署运行的MTA数量正确。 如果之后添加其他MTA，则仍将遵守连接限制。

### 连接设置{#connection-settings}

#### SMPP连接模式{#smpp-connection-mode}

在&#x200B;**收发器**&#x200B;模式或分离的&#x200B;**发射器+接收器**&#x200B;模式中设置连接。 当切换到分离的&#x200B;**发射机+接收机**&#x200B;模式时，**SMPP连接模式**&#x200B;部分中的设置将应用于发射机，而&#x200B;**接收机连接设置**&#x200B;部分中的设置将应用于接收机连接，只有选中&#x200B;**对接收机**&#x200B;使用不同的参数复选框。

#### SMSC实现名称{#smsc-implementation-name}

设置SMSC实现的名称。 它应设置为提供者的名称。 请与管理员或交付能力团队联系，了解要在此字段中添加的内容。 在[SR错误管理](../../administration/using/sms-protocol.md#sr-error-management)部分中介绍了此字段的角色。

#### 服务器{#server}

要连接到的服务器的DNS名称或IP地址。

#### 端口{#port}

要连接的TCP端口。

#### 帐户{#account}

连接的登录名。 在BIND PDU的`system_id`字段中传递。

#### 密码{#password}

SMPP连接的口令。 在BIND PDU的密码字段中传递。

#### 系统类型{#system-type}

在BIND PDU的`system_id`字段中传递的值。 此处有些提供商需要特定值。

#### 同时连接{#simultaneous-connections}

在Adobe Campaign Standard，它定义每个SMS线程和每个MTA进程的连接数。
MTA流程的数量由部署决定：通常有2个MTA和1个线程。 在config-instance.xml文件中，可以使用smppConnectorThreads设置更改线程数。 通常，每个容器有1个MTA进程，每个MTA进程有1个线程。

Adobe Campaign Standard的总连接公式：

* **总连接数=同时连接数*线程数* MTA数**

在外部帐户中设置并发连接，在config-instance.xml文件(smppConnectorThreads)中设置线程数，在外部帐户中可以限制MTA数。

在分离的&#x200B;**发射机／接收机**&#x200B;模式中，以上连接数表示&#x200B;**发射机／接收机**&#x200B;对的数量，这意味着总连接数将达到两倍。

#### 在SMPP上启用TLS {#enable-TLS}

使用TLS连接到提供程序。 连接将加密。 TLS连接由OpenSSL库管理，任何适用于OpenSSL的连接都对此连接适用。

#### 在日志文件{#enable-verbose-log-file}中启用详细的SMPP跟踪

此设置会转储日志文件中的所有SMPP流量。 通常需要在初始设置过程中调整参数。 在排除连接器故障时必须启用此功能，并将其与提供者看到的流量进行比较。

### 接收器连接设置{#receiver-connection}

此部分仅在分离的&#x200B;**发射器+接收器**&#x200B;模式下可见。

#### 对接收器{#receiver-parameters}使用不同的参数

当该框未选中时，发送器和接收器也使用相同的设置。

当选中该框时，**连接设置**&#x200B;部分的设置将应用于发射器，而&#x200B;**接收器连接**&#x200B;设置中的设置将应用于接收器。

**接收服务器、端口、帐户、密码、系统类型**

在&#x200B;**发射机+接收机**&#x200B;模式下，这些设置适用于接收机。 它们的工作方式与发射器部分类似，有关更多详细信息，请参阅上文。

### SMPP渠道设置{#smpp-channel-settings}

#### 允许字符音译{#allow-character-transliteration}

音译是寻找与缺失字符等效的过程。 例如，GSM编码中缺少法语“ê”（带扬抑符）字符，但可以用“e”替换，而不会损害可读性。

如果未选中此框，则文本编码将失败（如果它无法按原样对字符串进行完全编码）。

选中此框后，文本编码将尝试将字符串转换为近似版本，而不是失败。 如果某些字符在目标编码中没有等效字符，文本编码将失败。

有关编码过程的更一般说明，请参见[定义编码设置的特定映射。](../../administration/using/sms-protocol.md#SMSC-specifics)

#### 在数据库{#incoming-mo-storing}中存储传入的MO

启用后，传入的MO将存储在数据库的inSMS表中。 可以使用任何工作流的查询活动查询此表。

#### 在SR处理{#real-time-kpi}期间启用实时KPI更新

启用后，当收到错误SR时，KPI将在主投放页上实时更新。

缺点是性能较低，因为它会生成数据库争用。 如果禁用，则统计信息由&#x200B;**syncfromexec**&#x200B;工作流更新，每20分钟运行一次。

#### 源编号{#source-number}

定义消息的默认源地址。 仅当源编号在投放中留空时，此设置才适用。

默认情况下，源编号字段不会传递，因此提供程序将用它替换短代码。

这允许发送者地址/oADC覆盖功能。

#### 短代码{#short-code}

指示帐户的主短代码。 如果此帐户使用了多个短代码，或者短代码未知，请将此字段留空。

指定短代码对以下两个功能很有帮助：

* 如果未提供源代码，预览将显示短代码。 它将反映手机上的真实行为。

* 自动阻止列表回复功能的隔离设置仅向用户发送特定短代码。

#### 源吨/NPI，目标吨/NPI {#ton-npi}

[SMPP 3.4规范](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)（第117页）的第5.2.5节介绍了TON（编号类型）和NPI（编号计划指标）。 这些值应根据提供者的需要设置。

在`SUBMIT_SM PDU`的`source_addr_ton`、`source_addr_npi`、`dest_addr_ton`和`dest_addr_npi`字段中按原样传输它们。

#### 服务类型{#service-type}

此字段按原样在`SUBMIT_SM PDU`的`service_type`字段中传输。 根据提供者的需要设置它。

### 吞吐量和超时{#throughput-timeouts}

这些设置控制SMPP渠道的所有计时方面。 一些提供者需要非常精确地控制消息速率、窗口和重试定时。 这些设置应设置为与提供商的容量及其合同中指明的条件相匹配的值。

#### 发送窗口{#sending-window}

窗口是无需等待匹配`SUBMIT_SM_RESP`即可发送的`SUBMIT_SM PDU`数。

最大窗口为4的传输示例：

![](assets/sms_protocol_2.png)

当网络链路具有高延迟时，该窗口有助于提高吞吐量。  窗口的值必须至少是SMS/s的数量乘以链路的等待时间（以秒为单位），这样连接器在发送下一条消息之前就不会等待`SUBMIT_SM_RESP`。
如果窗口太大，您可能会发送更多重复消息以防连接出现问题。 此外，大多数提供商对窗口有非常严格的限制，拒绝超出限制的消息。

如何计算最佳发送窗口公式：

* 测量`SUBMIT_SM`和`SUBMIT_SM_RESP`之间的最大延迟。

* 将此值（以秒为单位）乘以最大MT吞吐量。 这将给出最佳发送窗口值。

示例：如果在最大MT吞吐量中设置300个SMS/s，并且在`SUBMIT_SM`和`SUBMIT_SM_RESP`之间平均有100ms的延迟，则最佳值为`300×0.1 = 30`。

#### 最大MT吞吐量{#max-mt-throughput}

每秒和每个连接的最大MT数。 严格强制执行此设置，MTA将永远不会以超过此限制的速度推送消息。 它对于需要精确限制的提供商很有用。

要了解总吞吐量限制，请将此数字乘以上述公式中详述的连接总数。

0表示无限制，MTA将尽快发送MT。

通常建议将此设置保持在1000以下，因为除非以最终架构和特别请求的SMPP提供者为基准，否则无法保证超出此数目的精确吞吐量。 最好将连接数增加到1000 MT/s以上。

#### 重新连接{#time-reconnection}之前的时间

当TCP连接丢失时，连接器将等待此秒数，然后尝试建立连接。

#### MT {#expiration-period}的过期时间

`SUBMIT_SM`与其匹配的`SUBMIT_SM_RESP`之间的超时。 如果未按时收到`RESP`，则消息将被视为失败，并且MTA的全局重试策略将适用。

#### 绑定超时{#bind-timeout}

TCP连接尝试和`BIND_*_RESP`回复之间的超时。 超时时，Adobe Campaign连接器将关闭连接，在重新连接之前将等待时间，然后再重试。

#### inquire_link期间{#enquire-link-period}

`enquire_link` 是发送的一种特殊类型的PDU，用于保持连接生存。此时段以秒为单位。 活动连接器仅在连接空闲时发送`enquire_link`以节省带宽。 如果在此期间两次后未收到RESP，则连接将被视为失效，并将触发重新连接过程。

### SMSC 详情{#SMSC-specifics}

这些设置是高级设置，可使Adobe Campaign连接器适应大多数SMPP实现特性。

#### 定义编码{#encoding-specific-mapping}的特定映射

有关文本编码的详细信息，请参见[SMS文本编码](../../administration/using/sms-protocol.md#sms-text-encoding)部分。

此设置允许您定义自定义编码映射（不同于规范）。 您将能够声明编码的列表及其`data_coding`值。

MTA将尝试使用列表中的第一个编码进行编码。 如果失败，它将尝试在列表上使用下一个编码，等等。 如果无法使用编码对消息进行编码，则会发生错误。 找到编码后，MTA将创建包含编码文本的`SUBMIT_SM PDU`字段，并使用表中指定的值设置`data_coding`字段。

表中项目的顺序很重要：编码从上到下进行尝试。 您应将最便宜或推荐使用的编码放在列表的顶部，然后添加越来越昂贵的编码。

请注意，UCS-2永远不会失败，因为它可以对Adobe Campaign支持的所有字符进行编码，并且UCS-2 SMS的最大长度要小得多：仅70个字符。

您还可以使用此设置，通过在映射表中仅声明1行来强制始终使用特定编码。

未选中复选框时使用的默认映射与下表相同：

| data_coding | 编码 |
|---|---|
| 0 | GSM |
| 9 | UCS-2 |

这意味着MTA将尝试在GSM中对消息进行编码。 如果成功，它将在`data_coding`设置为0时发送。

如果消息无法在GSM中编码，则它将在UCS-2中编码，并将`data_coding`设置为8。

#### 启用message_payload {#enable-message-payload}

如果未选中，长SMS将被MTA拆分，并与UDH一起以多个`SUBMIT_SM PDU`s发送。 消息将由手机按照UDH数据重组。

选中后，长SMS将发送到一个SUBMIT_SM PDU中，并将文本放在message_payload可选字段中。 有关此的详细信息，请参见[SMPP规范](../../administration/using/sms-protocol.md#ACS-SMPP-connector)。

如果启用此功能，Adobe Campaign将无法单独计算SMS部件：所有消息将计为一部分发送。

#### 发送完整电话号码{#send-full-phone-number}

如果未选中此复选框，则只向提供者发送电话号码的数字（`SUBMIT_SM`字段的`destination_addr`字段）。 这是默认行为，因为国际数字指示符（通常为+前缀）在SMPP中被TON和NPI字段替换。

选中此复选框后，电话号码将按原样发送，没有预处理和潜在空格，+前缀或井号／哈希／星号。

此功能还影响自动回复功能的阻止列表行为：如果未选中此复选框，将在插入隔离表的电话号码中添加+前缀，以补偿SMPP协议本身从电话号码中删除的+前缀。

#### 跳过TLS证书检查{#skip-tls}

启用TLS后，跳过所有证书检查。

如果选中，则连接不再安全，在生产中不应启用它。

它可用于调试或测试目的。

#### 绑定TON/NPI {#bind-ton-npi}

[SMPP 3.4规范](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)第5.2.5节中描述的TON（编号类型）和NPI（编号计划指标）（第117页）。 这些值应设置为提供者需要的任何值。

它们按原样在BIND PDU的`addr_ton`和`addr_npi`字段中传输。

#### 地址范围{#address-range}

在BIND PDU的address_range字段中按原样发送。 此值应设置为提供者需要的任何值。

#### 无效ID确认计数{#invalid-id}

限制可为单个SR发送的&#x200B;**消息ID无效** `DELIVER_SM_RESP`的数量。

**这应仅用于作为工作场所进行故** 障排除，并在正常情况下设置为0。

Fox示例，设置为2时：

* 提供程序发送ID为“1234”的SR(`DELIVER_SM`)。

* 在数据库中找不到ID“1234”。

* 连接器对该ID计数1 **无效ID**&#x200B;错误，因此它使用“消息ID无效”错误代码（正常行为）发送`DELIVER_SM_RESP`。

* 提供商重试ID为“1234”的同一SR。

* 在数据库中仍找不到ID“1234”。

* 连接器对该ID计数2 **无效ID**&#x200B;错误，因此它发送`DELIVER_SM_RESP` &quot;OK&quot;，即使它未正确处理。

* 此功能用于在无效SR块合法且无法处理消息时刷新提供方的SR缓冲区。

将此字段设置为0将禁用始终返回&#x200B;**消息ID无效**&#x200B;的机制，这是正常行为。

将此字段设置为1会使连接器始终响应“OK”，即使ID无效也是如此。 此值应设置为仅在监管下为1，以排除故障并保持最短的时间，例如从提供方问题中恢复。

#### 提取SR {#regex-extraction}中ID的正则表达式

SR格式并非严格由SMPP协议规范强制执行。 它只是说明书[附录B](../../administration/using/sms-protocol.md#sr-error-management)（第167页）中所述的建议。 某些SMPP实现程序以不同的格式设置此字段，因此Adobe Campaign需要一种方法来提取正确的字段。

默认情况下，它在`id:`后最多捕获10个字母数字字符。

正则表达式必须只有一个捕获组，并且括号中包含一个部件。 括号必须在ID部分周围。 正则表达式格式为PCRE。

调整此设置时，请务必尽可能多地包含上下文以避免错误触发器。 如果有特定前缀（如标准中的`id:`），则在正则表达式中包含这些前缀。 还尽可能使用单词分隔符(\b)以避免捕获单词中间的文本。

正则表达式中不包含足够的上下文可能会引入一个小的安全漏洞：消息的实际内容可以包含在SR中。 如果仅匹配没有上下文的特定ID格式（如UUID），则它可能解析实际的文本内容，如嵌入在文本字段中的UUID，而不是ID。

#### 应用正则表达式以确定成功／错误状态{#regex-applied}

当遇到具有未知stat/err字段组合的消息时，这些正则表达式将应用于stat字段，以确定SR是成功还是错误。 忽略stat值与任何这些regex不匹配的SR。

默认情况下，以`DELIV`开头的stat值，如[附录B](../../administration/using/sms-protocol.md#sr-error-management)中的`DELIVRD`将被视为已成功传送，且所有与错误匹配的stat值，如`REJECTED`、`UNDELIV`被视为错误。

#### MT确认{#id-format-mt}中的ID格式

这表示在`SUBMIT_SM_RESP PDU`的`message_id`字段中返回的ID的格式。

* **请勿修改**:ID按原样存储在数据库中，如ASCII编码的文本。不进行预处理或过滤。

* **小数**:ID应为ASCII格式的十进制数。使用此设置时，前导和尾部空格以及前导零被删除。

* **十六进制数字**:ID应为ASCII格式的十六进制数，不带前导0x，也不带尾随h。ID随后将转换为十进制数字，然后存储在数据库中。

* **十六进制字符串**:ID应为ASCII编码的文本，它本身是一个字节字符串，以十六进制编码。例如，在PDU中，您会找到`0x34 0x31 0x34 0x32 0x34 0x33`，它转换为ASCII &quot;414243&quot;。 然后，该字符串被解码为十六进制字节字符串，并因此您获得“ABC”:您将ID“ABC”存储在数据库中。

#### SR {#id-format-sr}中的ID格式

这表示由SR中ID的`Extraction`正则表达式捕获的ID的格式。 值与上述MT中的格式具有相同的含义和行为。

**可选字段中的SR ID或错误代码**

如果选中，则可选字段的内容将附加到以上区域处理的文本中。 文本的格式为`0xTAG:VALUE`, `0xTAG`是大写中标记的4位十六进制值，如`0x002E`。

例如，您可能希望在`receipted_message_id`字段中捕获该ID。 为此，请启用此复选框，以下文本将添加到状态：

```
0x001E:05e3299e-8d37-49d0-97c6-8e4fe60c7739
```

在此示例中，0x001E是可选字段的标记，UUID是字段的值。

为了捕获此值，您现在可以在SR字段的ID的提取正则表达式中设置以下正则表达式：

```
\b0x001E:([0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12})\b
```

>[!IMPORTANT]
>
>只能捕获具有文本(ASCII/UTF-8)值的可选字段。 具体而言，二进制字段无法用当前正则表达式系统可靠地捕获。

**文本字段中的SR ID或错误代码**

如果选中，则在处理SR的状态文本时，将保留&#x200B;**Text**&#x200B;字段。

如果提供程序在此字段中放置重要数据（如ID或状态），则此功能很有用。 通常，可以安全地丢弃此字段，因为它可能包含具有非ASCII编码的文本并中断正则表达式处理。

如果SR字段中ID的`Extraction`正则表达式不够具体，启用此选项可能会引入非常小的安全缺陷。 **Text**&#x200B;字段的内容可以解析为ID，攻击者可以使用它插入伪造的ID，这可能导致部分拒绝服务情况。

**服务ID标记**

允许添加自定义TLV。 此字段设置标记部分。 可以根据&#x200B;**服务中的投放或项目ID**&#x200B;值中投放的高级参数自定义该值。

此设置只允许为每个消息添加一个TLV选项。

### 发送给 MO 的自动回复{#automatic-reply}

此功能允许快速将文本回复给MO并处理向阻止列表发送的每短代码。

**关键字**&#x200B;和&#x200B;**短代码**&#x200B;列定义了触发自动回复的条件。 如果两个字段都匹配，则发送MO并触发其他操作。 要指定通配符，应将字段留空。 关键字与MO文本中的第一个字母数字单词匹配，将忽略标点和前导空格。 这意味着&#x200B;**Keyword**&#x200B;字段不能包含空格，且必须是单个单词。

**关键字**&#x200B;设置是前缀。 例如，如果指定“AD”，它将匹配“AD”、“ADAPT”和“ADOBE”。 如果您有多个带有公共前缀的关键字，则需要注意顺序，因为关键字是自上而下处理的。

**Reply**&#x200B;列是要回复的文本。 此字段中不提供个性化。 如果将此字段留空，则不会回复任何消息，但仍将触发其他操作。

当&#x200B;**关键字**&#x200B;和&#x200B;**短代码**&#x200B;匹配时，**附加操作**&#x200B;列提供额外操作，空短代码匹配所有短代码。 您可以发送到隔离或从隔离中删除，并且不考虑对文本的回复。 如果指定&#x200B;**附加操作**，但将&#x200B;**回复**&#x200B;字段留空，则将执行该操作，但不会发送回复。 隔离仅应用于指定的短代码，如果字段为空，则应用所有短代码。

>[!IMPORTANT]
>
>发送完整电话号码设置对自动回复隔离机制的行为有影响：如果未选中“发送完整电话号码”，则输入隔离的电话号码将前缀加号(“+”)，使其与国际电话号码格式兼容。

表中的所有条目将按指定顺序处理，直到一个规则匹配。 如果多个规则与一个MO匹配，则只应用最前面的规则。

## SMS投放模板参数{#sms-delivery-template-parameters}

某些参数可以按投放模板设置。

### 发件人字段{#from-field}

此字段为可选字段。 它允许覆盖发送者地址(oADC)。 此字段的内容位于`SUBMIT_SM PDU`的`source_addr`字段中。

SMPP规范将字段限制为21个字符，但某些提供者可能允许更长的值。 另请注意，在某些国家／地区可能会应用非常严格的限制，例如长度、内容和允许的字符。

### 投放参数 {#delivery-parameters}

#### 每条消息的最大SMS数{#maximum-sms}

仅当禁用&#x200B;**消息有效负荷**&#x200B;设置时，此设置才起作用。 有关此项的详细信息，请参阅此[页面](../../administration/using/configuring-sms-channel.md)。 如果消息需要的SMS大于此值，则将触发错误。

SMS协议将SMS限制在255个部分，但一些手机很难将长消息与大约10个部分组合起来，这一限制取决于确切的型号。 我们建议您不要在每封邮件中查看5个以上部分。

由于个性化消息在Adobe Campaign中的作用，消息的大小可能会有所不同。 发送大量长消息可能会增加发送成本。

#### 传输模式{#transmission-mode}

此字段指示要传输的SMS类型：普通或闪存消息，存储在移动或SIM卡上。

此设置将在`SUBMIT_SM PDU`的`dest_addr_subunit`可选字段中传输。

* **未** 指定的PDU不发送可选字段。

* **** Flash将值设置为1。它发送闪存消息，该消息弹出到移动设备上，而不存储在内存中。

* **标** 准化将值设置为0。它发送一条正常消息。

* **在移动** 设备上保存会将值设置为2。它告诉电话将短信存储在内存中。

* **结束时** 保存会将值设置为3。它告诉电话把手机短信存储在SIM卡中。

#### 有效期{#validity-period}

有效期在`SUBMIT_SM PDU`的`validity_period`字段中传输。 日期始终以绝对UTC时间格式设置，日期字段将以“00+”结束。

## SMPP连接器{#ACS-SMPP-connector}

![](assets/sms_protocol_3.png)

箭头表示数据流。

这里需要注意的最重要的一点是有多个SMPP连接器线程。 这些线程都相同，并且共享相同的配置。 因此，连接数总是乘以线程数。

客户无法更改线程数，因为它需要更改配置文件。

### SMPP连接器{#behavior-smpp-connector}行为说明

#### 匹配MT、SR和广播条目{#matching-mt-sr}

在Adobe Campaign中，消息是广播条目。 在Adobe Campaign Standard，外部连接器只需了解工作的广播表：`nmsBroadLogExec`。 工作流负责将广播条目复制回其特定定位维度(nmsBroadLogXXX)。

很遗憾，SMPP不允许发送ID和消息：提供者为每个MT提供一个MT ID，然后提供一个或多个具有相同ID的SR。

提供程序提供的ID存储在`nmsBroadLogExec`表的`sProviderId`列中。 SR始终在成功发送和确认MT后到达，但有时可能出现故障，在Adobe Campaign中称为出众SR。 处理线程将这些SR临时存储在RAM中，直到完整信息到达。

确认MT(`SUBMIT_SM_RESP`)后，将立即在数据库中更新`sProviderId`。

每个SR由SMPP处理线程单独处理。 此过程是伪同步的：它被视为与外部同步，但通过事件驱动的实现在内部实现。 仅当广播成功更新时，如果遇到错误，则SR被拒绝。

以下是应用于每个SR的过程：

* SR的ID是使用正则表达式提取的。
* 在`nmsBroadLogExec:sProviderId`中搜索该ID。
* 状态+错误代码是使用regex从SR中提取的。
* 广播消息机制用于限定错误并查找广播消息ID。
* 此广播将使用上述所有信息进行更新。
* SR得到确认。

检查上述步骤需要&#x200B;**启用详细SMPP跟踪**&#x200B;以手动检查是否正确应用了所有步骤。 每次Adobe Campaign连接到新的SMPP提供商时，都需要此设置。

## 上线前{#checklist}

此清单提供了上线前应检查的列表。 设置不完整可能会导致许多问题。

### 检查外部帐户冲突{#external-account-conflict}

检查您没有旧的短信外部帐户。 如果将测试帐户保留为禁用状态，您将面临在生产系统上重新启用该帐户并生成潜在冲突的风险。

如果同一Adobe Campaign实例上有多个帐户连接到同一提供程序，请与提供程序联系，确保它们实际区分这些帐户之间的连接。 拥有多个具有相同登录名的帐户需要额外配置。

### 在检查{#enable-verbose}期间启用详细的SMPP跟踪

您应始终在检查期间启用详细的SMPP跟踪。
即使您无法自己检查日志，支持人员也会更轻松地为您提供帮助。

### 测试SMS {#test}

* **发送包含各种字符**
的SMS如果您需要发送包含非GSM或非ASCII字符的SMS，请尝试发送包含尽可能多不同字符的消息。如果设置自定义字符映射表，请至少为所有可能的用户发送一个SMS 
`data_coding` values.

* **检查SR是否正**
确处理SM应在投放日志中标记为已接收SMS。投放日志应成功，如下所示：

检查是否已更改投放提供程序名称。 投放日志不应包含    `SR yourProvider stat=DELIVRD err=000|#MESSAGE`
检查是否已更改投放提供程序名称。投放日志在生产环境上不应包含**SR Generic**。

* **检查是否已处**
理MO如果需要处理MO（自动回复、将MO存储在数据库中等）尝试做一些测试。 发送几个SMS以获取所有自动回复关键字，并检查回复是否足够快，不超过几秒。
检查Adobe Campaign成功回复的日志 
`DELIVER_SM_RESP` (command_status=0)。

### 检查PDU {#check-pdus}

即使消息看起来成功，检查PDU的格式是否正确也很重要。

连接到以前未连接到Adobe Campaign的提供程序时，此步骤是必需的。

#### BIND {#bind}

检查是否已正确发送`BIND_* PDUs`。 要检查的最重要的一点是提供程序始终返回成功的`BIND_*_RESP PDUs`(command_status = 0)。

检查`BIND_* PDU`s不太多。如果其中太多，则表明连接不稳定。 有关详细信息，请参见[连接不稳定的问题](../../administration/using/sms-protocol.md#issues-unstable-connection)部分。

#### INQUIRE_LINK {#enquire-link-pdus}

检查连接空闲时是否定期交换`ENQUIRE_LINK PDU`。

#### SUBMIT_SM / DELIVER_SM {#submit-sm-deliver-sm}

发送消息，然后在日志中搜索相应的`SUBMIT_SM`、`SUBMIT_SM_RESP`、`DELIVER_SM`和`DELIVER_SM_RESP PDU`。

使用`SUBMIT_SM PDU`:

* 检查`data_coding`是否正确，默认情况下为0。
* 检查`short_message`是否已正确编码。 尝试使用支持多个编码的十六进制转换器对其进行解码。

使用`SUBMIT_SM_RESP PDU`:

* 检查它是否成功，command_status = 0。
* 检查其正文是否包含格式正确的ID，后跟“0”字节。

使用`DELIVER_SM PDU`:

* 解码十六进制`short_message`字段。
* 使用正则表达式检查工具，确认在SR中ID的`Extraction`正则表达式中定义的正则表达式只返回一个捕获组，并且捕获消息中的整个ID。
* 检查提取的ID是否与`SUBMIT_SM_RESP`中的ID匹配。
* 检查在SR中状态的`Extraction`正则表达式中定义的正则表达式是否返回stat字段的内容。
* 检查在SR中错误的`Extraction`正则表达式中定义的正则表达式是否返回错误字段的内容。

使用`DELIVER_SM_RESP PDU`:

* 检查收到`DELIVER_SM PDU`后是否快速发送，通常不到1秒。
* 检查它是否成功，command_status = 0。

### 询问提供者是否一切正常{#provider}

即使您的SMS成功，也要与提供商联系以查看所有内容是否都正确。

### 禁用详细SMPP跟踪{#disable-verbose}

完成所有检查后，最后一件事是&#x200B;**禁用详细SMPP跟踪**&#x200B;以不生成太多日志。 即使在生产系统上，您也可以重新启用它们以排除故障。
