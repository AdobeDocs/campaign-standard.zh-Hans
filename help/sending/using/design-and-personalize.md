---
solution: Campaign Standard
product: campaign
title: 生成个性化内容
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 了解如何设计消息内容并尝试避免可能妨碍您执行投放的常见问题。 
feature: Deliverability
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 7%

---


# 生成个性化内容 {#build-personalized-content}

在设计消息内容时，请尝试避免可能妨碍您执行投放的常见问题。 大多数时间中，可能的错误与[个性化](../../designing/using/personalization.md)、使用现有内容](../../designing/using/using-existing-content.md)时的格式设置和[转换HTML内容](../../designing/using/using-existing-content.md#converting-an-html-content)时的格式设置有关。[[](../../designing/using/images.md)

## 优化个性化{#optimize-personalization}

为避免可能妨碍您执行投放并改善收件人体验的常见问题，Adobe Campaign使您能够个性化您的信息。

您可以使用存储在Adobe Campaign数据库中或通过跟踪、登陆页、订阅等收集的收件人数据。
在[本节](../../designing/using/personalization.md)中介绍了个性化基础知识。

确保您的消息内容设计得当，以避免任何与个性化通常相关的错误。

可以根据在收件人编辑器中定义的条件手动添加动态内容以向表达式显示不同的内容。 添加动态内容时，您必须始终为不符合选定条件的收件人保留默认变体。
有关动态内容的详细信息，请参阅[本节](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。

**提示**  — 用不同的测试用户档案预览电子邮件，以确保您的动态内容已正确配置。

## 构建优化内容{#optimize-content}

在构建电子邮件时，请牢记以下一般最佳实践。

* 使设计变得简单

* 让移动用户牢记

* 避免完全基于图像的电子邮件

* 使用电子邮件安全字体

* 对特殊字符进行编码

### 主题行

在[主题行](../../designing/using/subject-line.md)上工作以提高开放率：

* 避开过长的对象。 最多使用50个字符

* 避免重复使用“free”或“优惠”等可能被视为垃圾邮件的词语

* 避免大写字母和特殊字符，如&quot;!&quot;、&quot;£&quot;、&quot;€&quot;、&quot;$&quot;

### 镜像页面

始终包含镜像页面链接。 首选职位是电子邮件的顶部。 [了解详情](../../designing/using/personalization.md#adding-a-content-block)

### 退订链接

退订链接至关重要。 它必须可见且有效，并且表单必须能够正常工作。 了解本节](../../designing/using/personalization.md#about-targeting-dimension)中的退订链接指南[。

默认情况下，当分析消息时，控件[类型规则](../../sending/using/control-rules.md)检查是否包含退出链接，并在消息缺失时生成警告。

**提示**:由于人为错误总是可能发生，因此在每次发送之前，请检查退出链接是否工作正常。例如，在发送验证时，请确保链接有效、表单联机且“不再与此收件人联系”字段更改为“是”。

了解如何在本节](../../designing/using/personalization.md#adding-a-content-block)中插入退出链接[。

### 电子邮件大小

为避免性能或交付性问题，建议电子邮件的最大大小约为&#x200B;**35KB**。

要限制您的电子邮件，请考虑以下事项：

* 删除冗余或未使用的样式

* 将部分电子邮件内容移动到登陆页

* 简化代码

确保在最终发送之前测试所有更改

### SMS长度

默认情况下，短信的字符数应符合 GSM（全球移动通信系统）标准。使用 GSM 编码的短信消息长度上限为 160 个字符，而对于分段发送的消息，每段短信的长度上限为 153 个字符。

音译指的是，如果 GSM 标准无法识别某个短信字符，则会用另一个字符替换该字符。请注意，在SMS消息的内容中插入个性化字段可能会引入GSM编码未考虑的字符。 您可以通过选中相应&#x200B;**[!UICONTROL External account]**的SMPP渠道设置选项卡中的相应框来授权字符音译。
请阅读本节](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)了解更多信息。[

**提示**:

* 要保留SMS消息中所有字符的原样，例如，不要更改正确的名称，请不要启用音译。

* 但是，如果您的SMS消息包含许多GSM标准未考虑的字符，则允许音译以限制发送消息的成本。

请阅读本节](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)了解更多信息。[

### 响应式电子邮件设计

响应式设计可确保电子邮件能够针对打开电子邮件的设备进行最佳呈现。

* 使用响应式电子邮件HTML而非Web HTML

* 使用预览模式并发送验证，以在尽可能多的设备上测试渲染。 了解如何在发送前[预览消息](../../sending/using/previewing-messages.md)。

* 活动电子邮件设计器附带适用于移动设备的响应式设计格式模板。 请阅读本页](../../designing/using/using-reusable-content.md#content-templates)了解更多信息。[

## 管理映像{#manage-images}

在使用图像时，请遵循以下准则。

### 防止图像阻塞

默认情况下，某些电子邮件客户端会阻止图像，而一些用户会更改其设置以阻止图像以保存数据使用情况。 因此，如果不下载图像，则会丢失整个消息。 要避免这种情况：

* 在内容与图像和文本之间取得平衡。 避免完全基于图像的电子邮件。

* 如果图像中必须包含文本，请使用alt和title文本来确保消息传递过来。 设置替代/标题文本的样式以改进其外观。

* 避免使用背景图像，因为某些电子邮件客户不支持这些图像。

### 使图像具有响应性

尝试使图像具有响应性和可调整大小。 请注意，这可能会因构建时间过长而产生成本影响。

### 使用绝对图像引用

要从外部访问，链接到活动的电子邮件和公共资源中使用的图像必须存在于可从外部访问的服务器上。

## 预览消息{#preview-msg}

Adobe建议预览您的消息，以检查其个性化以及收件人如何看到您的投放。

在“电子邮件设计器”中，**[!UICONTROL Preview]**&#x200B;按钮允许您视图收件人的每个内容的呈现。 个性化字段和内容的条件元素被替换为所选用户档案的相应信息。 [了解详情](../../sending/using/previewing-messages.md)
