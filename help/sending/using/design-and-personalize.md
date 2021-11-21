---
title: 生成个性化内容
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 了解如何设计消息内容并尽量避免可能阻止您执行投放的常见问题。 
feature: Deliverability
role: User
level: Intermediate
exl-id: 938989c9-ef19-4297-9b8b-c38eb1cec1f0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 7%

---

# 生成个性化内容 {#build-personalized-content}

在设计消息内容时，请尽量避免可能阻止您执行投放的常见问题。 大多数情况下，可能的错误都与 [个性化](../../designing/using/personalization.md)，格式设置 [使用现有内容](../../designing/using/using-existing-content.md)  — 和 [转换HTML内容](../../designing/using/using-existing-content.md#converting-an-html-content)  — 和 [图像](../../designing/using/images.md).

## 优化个性化 {#optimize-personalization}

为避免可能阻止您执行投放并改善收件人体验的常见问题，Adobe Campaign允许您个性化邮件。

您可以使用存储在Adobe Campaign数据库中的收件人数据，或通过跟踪、登陆页、订阅等方式收集的数据。
有关个性化的基础知识，请参阅 [此部分](../../designing/using/personalization.md).

确保您的消息内容设计正确，以避免任何与个性化通常相关的错误。

可以根据表达式编辑器中定义的条件手动添加动态内容以向收件人显示不同的内容。 添加动态内容时，必须始终为不符合所选条件的收件人保留默认变体。
有关动态内容的更多信息，请参阅 [此部分](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

**提示**  — 使用不同的测试用户档案预览电子邮件，以确保已正确配置动态内容。

## 构建优化内容 {#optimize-content}

在构建电子邮件时，请牢记以下一般最佳实践。

* 保持设计简单

* 请记住移动设备用户

* 避免完全基于图像的电子邮件

* 使用电子邮件安全字体

* 编码特殊字符

### 主题行

使用 [主题行](../../designing/using/subject-line.md) 要提高开放率，请执行以下操作：

* 避免话题太长。 最多使用50个字符

* 避免重复使用诸如“free”或“offer”之类的词语，这些词语可能会被视为垃圾邮件

* 避免使用大写字母和特殊字符，如“！”、“£”、“€”、“$”

### 镜像页面

始终包含镜像页面链接。 首选位置是电子邮件的顶部。 [了解详情](../../designing/using/personalization.md#adding-a-content-block)

### 退订链接

退订链接至关重要。 它必须可见且有效，并且表单必须有效。 了解退订链接准则 [在此部分中](../../designing/using/personalization.md#about-targeting-dimension).

默认情况下，分析消息时，控件 [类型规则](../../sending/using/control-rules.md) 检查是否包含选择退出链接，如果缺少，则会生成警告。

**笔尖**:由于始终可能出现人为错误，因此请在每次发送之前检查选择退出链接是否正常工作。 例如，在发送校样时，请确保链接有效、表单已联机且“No lent contact this recipient（不再与此收件人联系）”字段已更改为“Yes（是）”。

了解如何插入选择退出链接 [在此部分中](../../designing/using/personalization.md#adding-a-content-block).

### 电子邮件大小 {#email-size}

为避免出现性能或投放能力问题，建议电子邮件的最大大小为 **35KB**.

要限制您的电子邮件，请考虑以下事项：

* 删除冗余或未使用的样式

* 将一些电子邮件内容移到 [登陆页面](../../channels/using/getting-started-with-landing-pages.md)

* 缩小代码

确保在最终发送之前测试任何更改。

在Adobe Campaign中，电子邮件的默认最大大小设置为 **100MB**. <!--This limit enables to prevent any error that could indefinitely increase the size of an email, which can lead to a system crash.-->

如果达到限制，则超出限制的消息将失败，投放日志中将显示错误消息。 同一投放的其他消息将不会受到影响。 在这种情况下，您必须调整电子邮件模板的动态部分或投放使用的内容片段。 <!--If you need assistance, or if you have any question or request about the **[!UICONTROL Maximum message size]** option, reach out to your Adobe contact.-->

Adobe建议保留最大消息大小默认值。 但是，此值可在 **[!UICONTROL Maximum message size]** 选项，通过 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** 菜单，按 [功能管理员](../../administration/using/users-management.md#functional-administrators) 仅。

>[!IMPORTANT]
>
>如果将此值设置为零，则不会应用任何限制。

### 短信长度

默认情况下，短信的字符数应符合 GSM（全球移动通信系统）标准。使用 GSM 编码的短信消息长度上限为 160 个字符，而对于分段发送的消息，每段短信的长度上限为 153 个字符。

音译指的是，如果 GSM 标准无法识别某个短信字符，则会用另一个字符替换该字符。请注意，在短信消息内容中插入个性化字段可能会引入GSM编码无法识别的字符。 您可以通过选中相应的SMPP渠道设置选项卡中的相应框来授权字符音译 **[!UICONTROL External account]**.
了解更多 [在此部分中](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

**提示**:

* 若要将短信消息中的所有字符按原样保留，请不要更改正确的名称（例如），请勿启用音译。

* 但是，如果短信消息包含大量GSM标准未考虑的字符，则启用音译可限制发送消息的成本。

了解更多 [在此部分中](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

### 响应式电子邮件设计

响应式设计可确保电子邮件在打开时能够以最佳方式呈现。

* 使用响应式电子邮件HTML，而不是WebHTML

* 使用预览模式并发送校样，以在尽可能多的设备上测试渲染效果。 了解如何 [预览消息](../../sending/using/previewing-messages.md) 发送之前。

* Campaign Email Designer为移动设备提供了响应式设计格式模板。 请参阅[此页面](../../designing/using/using-reusable-content.md#content-templates)以了解详情。

## 管理图像 {#manage-images}

在使用图像时，请遵循以下准则。

### 防止图像阻塞

默认情况下，某些电子邮件客户端会阻止图像，而某些用户会更改其设置以阻止图像，以便保存数据。 因此，如果不下载图像，则整个消息可能会丢失。 要避免出现这种情况，请执行以下操作：

* 在内容与图像和文本之间取得平衡。 避免完全基于图像的电子邮件。

* 如果图像中必须包含文本，请使用替换文本和标题文本，以确保消息能够被传递。 设置替换/标题文本的样式以改进其外观。

* 避免使用背景图像，因为某些电子邮件客户不支持这些图像。

### 使图像具有响应性

尝试使图像具有响应性和可调整大小。 请注意，这可能会对成本产生影响，因为构建过程需要较长时间。

### 使用绝对图像引用

要从外部访问，链接到营销活动的电子邮件和公共资源中使用的图像必须显示在可从外部访问的服务器上。

## 预览消息 {#preview-msg}

Adobe建议预览消息以检查其个性化以及收件人将如何看到您的投放。

在Email designer中， **[!UICONTROL Preview]** 按钮可让您查看收件人的每个内容的呈现。 个性化字段和内容的条件元素将替换为选定用户档案的相应信息。 [了解详情](../../sending/using/previewing-messages.md)
