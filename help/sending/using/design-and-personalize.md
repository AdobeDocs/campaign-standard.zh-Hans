---
title: 生成个性化内容
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 了解如何设计消息内容并尝试避免可能会阻止您执行投放的常见问题。 
feature: Deliverability
role: User
level: Intermediate
exl-id: 938989c9-ef19-4297-9b8b-c38eb1cec1f0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1039'
ht-degree: 4%

---

# 生成个性化内容 {#build-personalized-content}

在设计消息内容时，请尽量避免可能会阻止您执行投放的常见问题。 大多数时候，可能的错误与[个性化](../../designing/using/personalization.md)、使用现有内容[&#128279;](../../designing/using/using-existing-content.md)时的格式设置以及[转换HTML内容](../../designing/using/using-existing-content.md#converting-an-html-content)和[图像](../../designing/using/images.md)有关。

## 优化个性化 {#optimize-personalization}

为避免可能阻止您执行投放的常见问题并改善收件人体验，Adobe Campaign允许您个性化消息。

您可以使用存储在Adobe Campaign数据库中的收件人数据，或通过跟踪、登陆页面、订阅等收集的数据。
[本节](../../designing/using/personalization.md)中介绍了Personalization的基础知识。

确保消息内容设计正确，以避免出现任何错误，这些错误通常与个性化相关。

可以手动添加动态内容，以根据表达式编辑器中定义的条件向收件人显示不同的内容。 添加动态内容时，必须始终为不符合选定条件的收件人保留默认变体。
有关动态内容的更多信息，请参阅[此章节](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。

**提示** — 使用不同的测试配置文件预览您的电子邮件，以确保您的动态内容已正确配置。

## 构建优化内容 {#optimize-content}

在构建电子邮件时，请牢记以下一般最佳实践。

* 保持设计简单

* 请牢记移动用户

* 避免完全基于图像的电子邮件

* 使用电子邮件安全字体

* 编码特殊字符

### 主题行

处理[主题行](../../designing/using/subject-line.md)以提高打开率：

* 避免使用过长的主题。 最多使用50个字符

* 避免使用可被视为垃圾邮件的重复单词，如“free”或“offer”

* 避免使用大写字母和特殊字符，如“！”、“£”、“€”、“$”

### 镜像页面

始终包含镜像页面链接。 首选位置是电子邮件的顶部。 [了解详情](../../designing/using/personalization.md#adding-a-content-block)

### 退订链接

退订链接是必需的。 它必须可见且有效，并且表单必须有效。 在本节[&#128279;](../../designing/using/personalization.md#about-targeting-dimension)中了解退订链接准则。

默认情况下，在分析消息时，控件[类型规则](../../sending/using/control-rules.md)会检查是否包含选择退出链接，如果缺少该链接，则会生成警告。

**提示**：由于人为错误始终存在，因此请在每次发送前检查选择退出链接是否正常工作。 例如，在发送校样时，确保链接有效，表单处于联机状态且“不再联系此收件人”字段已更改为“是”。

了解如何在此部分[&#128279;](../../designing/using/personalization.md#adding-a-content-block)中插入选择退出链接。

### 电子邮件大小 {#email-size}

为避免性能或可投放性问题，建议的最大电子邮件大小约为&#x200B;**35KB**。

要将电子邮件保持在限制以内，请考虑以下事项：

* 删除多余或未使用的样式

* 将部分电子邮件内容移至[登陆页面](../../channels/using/getting-started-with-landing-pages.md)

* 缩小代码

确保在最终发送之前测试任何更改。

在Adobe Campaign中，电子邮件的默认最大大小设置为&#x200B;**100MB**。<!--This limit enables to prevent any error that could indefinitely increase the size of an email, which can lead to a system crash.-->

如果达到限制，则超出限制的消息将失败，并在投放日志中显示错误消息。 同一投放的其他消息将不受影响。 在这种情况下，您必须调整电子邮件模板的动态部分或投放使用的内容片段。<!--If you need assistance, or if you have any question or request about the **[!UICONTROL Maximum message size]** option, reach out to your Adobe contact.-->

Adobe建议保留最大邮件大小默认值。 但是，此值只能由[功能管理员](../../administration/using/users-management.md#functional-administrators)通过&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**&#x200B;菜单在&#x200B;**[!UICONTROL Maximum message size]**&#x200B;选项中更改。

>[!IMPORTANT]
>
>如果将此值设置为零，则不会应用任何限制。

### 短信长度

默认情况下，短信的字符数应符合GSM（全球移动通信系统）标准。 使用 GSM 编码的短信消息长度上限为 160 个字符，而对于分段发送的消息，每段短信的长度上限为 153 个字符。

音译指的是，如果GSM标准无法识别某个短信字符，则会用另一个字符替换该字符。 请注意，将个性化字段插入短信消息内容，可能会引入GSM编码无法识别的字符。 您可以通过选中对应&#x200B;**[!UICONTROL External account]**&#x200B;的SMPP渠道设置选项卡中的对应框来授权字符音译。
在本节[&#128279;](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)中了解更多。

**提示**：

* 要将短信消息中的所有字符都保持不变，例如不要更改正确名称，请不要启用音译。

* 但是，如果短信消息包含许多GSM标准无法识别的字符，请启用音译以限制发送消息的成本。

在本节[&#128279;](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)中了解更多。

### 响应式电子邮件设计

响应式设计可确保电子邮件以最佳方式呈现给打开它的设备。

* 使用响应式电子邮件HTML而不是WebHTML

* 使用预览模式和发送校样以尽可能多的在设备上测试渲染。 了解如何在发送之前[预览消息](../../sending/using/previewing-messages.md)。

* Campaign电子邮件Designer提供了用于移动设备的响应式设计格式模板。 请参阅[此页面](../../designing/using/using-reusable-content.md#content-templates)以了解详情。

## 管理图像 {#manage-images}

在使用图像时，请遵循以下准则。

### 防止图像阻塞

默认情况下，某些电子邮件客户端会阻止图像，而某些用户会更改其设置以阻止图像以供在数据使用时保存。 因此，如果不下载图像，则可能会丢失整个消息。 要避免这种情况：

* 使您的内容与图像和文本保持平衡。 避免完全基于图像的电子邮件。

* 如果文本必须包含在图像中，请使用替换文本和标题文本以确保消息正确传递。 设置替代/标题文本的样式以改进其外观。

* 避免使用背景图像，因为某些电子邮件客户端不支持这些图像。

### 使图像具有响应性

尝试使图像具有响应性且可调整大小。 请注意，这可能会产生成本影响，因为构建所需的时间较长。

### 使用绝对图像引用

要从外部访问，必须在外部可访问的服务器上存在电子邮件中使用的图像以及与营销活动关联的公共资源。

## 预览消息 {#preview-msg}

Adobe建议预览您的消息以检查其个性化设置以及收件人如何看到您的投放。

在Email Designer中，**[!UICONTROL Preview]**&#x200B;按钮允许您查看收件人的每个内容的呈现。 将内容的个性化字段和条件元素替换为所选用户档案的相应信息。 [了解详情](../../sending/using/previewing-messages.md)
