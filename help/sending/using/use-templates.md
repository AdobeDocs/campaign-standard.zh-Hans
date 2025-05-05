---
title: 使用投放模板
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: “通过为最常见的活动类型提供现成的方案，交付模板可以提高效率。”
feature: Deliverability
role: User
level: Intermediate
exl-id: ca134a7f-9035-4885-b4cb-1170b6ec10cc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 10%

---

# 使用模板 {#use-templates}

通过为最常见的活动类型提供现成的方案，交付模板可以提高效率。 借助模板，营销人员可以在更短的时间内部署具有最小自定义的新营销活动。

在[本节](../../start/using/marketing-activity-templates.md)中了解有关投放模板的更多信息。

## 投放模板入门 {#gs-templates}

[投放模板](../../start/using/marketing-activity-templates.md#creating-a-new-template)允许您定义一组技术和功能属性，这些属性既适合您的需求，又可用于将来投放。 然后，您可以节省时间并在需要时标准化交付。

在Adobe Campaign中管理多个品牌时，Adobe建议每个品牌具有一个子域。 例如，银行可以具有与其每个区域机构对应的多个子域。 如果银行拥有bluebank.com域，则其子域可以是@ny.bluebank.com、@ma.bluebank.com、@ca.bluebank.com等。 每个子域拥有一个投放模板，让您能够始终为每个品牌使用正确的预配置参数，从而避免错误并节省您的时间。

**提示**：为了避免在Campaign中出现配置错误，我们建议您复制本机模板并更改其属性，而不是创建新模板。

## 配置地址

* 必须提供发件人地址，才能发送电子邮件。

* 有些ISP（Internet服务提供商）在接受消息之前会检查发件人地址的有效性。

* 格式错误的地址可能导致接收服务器拒绝该地址。 您必须确保提供了正确的地址。

* 地址必须明确识别发件人。 域必须归发件人所有并向其注册。

* Adobe建议创建对应于为投放和回复指定的地址的电子邮件帐户。 请与您的邮件系统管理员联系。

在电子邮件模板属性的&#x200B;**[!UICONTROL Advanced parameters]**&#x200B;部分中，**[!UICONTROL From (email address)]**&#x200B;字段对应于发件人的地址。

![](assets/template-parameters.png)

地址域必须与配置的子域相同。

**[!UICONTROL Reply to]**&#x200B;字段对应于用于回复的电子邮件地址和名称。

**提示** -Adobe建议使用现有的真实地址，如您品牌的客户关怀部门。 在这种情况下，如果收件人发送回复，客户关怀团队将能够处理。

若要更改出现在已发送邮件标题中的发件人名称，请转到Email Designer主页的&#x200B;**[!UICONTROL Properties]**&#x200B;选项卡（可通过主页图标访问），然后单击&#x200B;**[!UICONTROL Default sender name]**&#x200B;块。

![](assets/template-content.png)

为了提高投放的打开率，Adobe建议使用收件人可轻松识别的名称，如您的品牌名称。

**提示** — 为进一步改善收件人的体验，您可以添加人员的姓名，例如“Emma from Megastore”。

有关个性化发件人名称的更多信息，请参阅[电子邮件发件人](../../designing/using/subject-line.md#email-sender)。

## 个性化设置短信发送者姓名

在短信模板属性的&#x200B;**高级参数**&#x200B;部分中，**从**&#x200B;选项允许您使用字符串将短信消息发送者的名称个性化。 该名称在收件人的手机显示为短信消息的发送者。

如果此字段为空，则将显示所用外部帐户中提供的源号码。如果未提供源号码，则将使用短代码。有关更多信息，请参阅[短信配置](../../administration/using/configuring-sms-channel.md)。

**提示** — 检查您所在国家/地区有关修改发件人地址的法规。 您还应与短信服务提供商进行核实，了解他们是否提供此功能。

## 设置对照组

发送投放后，您可以将排除的收件人的行为与接收投放的收件人的行为进行比较。 然后，您可以衡量营销活动的效率。 了解有关控制组的详细信息[本节](../../sending/using/control-group.md)。

## 使用类型应用过滤器或控制规则

分类包含在发送任何消息之前，在分析阶段应用的检查规则。

在模板属性的&#x200B;**[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]**&#x200B;部分中，根据需要更改默认分类。

例如，为了更好地控制出站流量，您可以通过定义每个子域的一个关联并为每个关联创建一个类型来定义可以使用的IP地址。 相关性在实例的配置文件中定义。 联系Adobe Campaign管理员。

有关类型的详细信息，请参阅[此部分](../../sending/using/managing-typologies.md)。

## 将品牌链接到模板

与品牌标识相关的已发送电子邮件参数（如品牌徽标或发件人地址）在Adobe Campaign中受到集中管理。 您可以创建一个或多个品牌并将它们链接到投放模板。

有关在Adobe Campaign中使用和配置品牌的更多信息，请参阅品牌策略。

要显示或更改分配给投放模板的品牌，请选择模板的“编辑属性”按钮，然后导航到品牌的详细信息。

![](assets/template-brand.png)

有关将品牌链接到模板的更多信息，请参阅[将品牌分配给电子邮件](../../administration/using/branding.md#assigning-a-brand-to-an-email)。

在本节[&#128279;](../../administration/using/branding.md#creating-a-brand)中了解如何创建配置品牌。
