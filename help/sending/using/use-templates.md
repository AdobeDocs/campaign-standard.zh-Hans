---
title: 使用投放模板
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: “通过为最常见类型的活动提供现成的方案，交付模板可以提高效率。”
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

通过为最常见类型的活动提供现成的方案，交付模板可以提高效率。 借助模板，营销人员可以在更短的时间内部署具有最小自定义的新营销活动。

要了解有关投放模板的更多信息，请参阅 [本节](../../start/using/marketing-activity-templates.md).

## 投放模板入门 {#gs-templates}

A [投放模板](../../start/using/marketing-activity-templates.md#creating-a-new-template) 允许您定义一次可满足您需求且可重复用于未来投放的一组技术和功能属性。 然后，您可以节省时间并在需要时实现交付的标准化。

在Adobe Campaign中管理多个品牌时，Adobe建议每个品牌拥有一个子域。 例如，银行可以具有与其每个地区机构对应的多个子域。 如果银行拥有bluebank.com域，则其子域可以是@ny.bluebank.com、@ma.bluebank.com、@ca.bluebank.com等。 每个子域拥有一个投放模板使您能够为每个品牌始终使用正确的预配置参数，从而避免错误并节省您的时间。

**笔尖**：为避免在Campaign中出现配置错误，我们建议您复制本机模板并更改其属性，而不是创建新模板。

## 配置地址

* 发件人的地址是允许发送电子邮件的必填项。

* 有些ISP（Internet服务提供商）在接受消息之前会检查发件人地址的有效性。

* 格式错误的地址可能导致接收服务器拒绝该地址。 您必须确保提供正确的地址。

* 地址必须明确标识发件人。 域必须由发件人拥有并向其注册。

* Adobe建议创建对应于为投放和回复指定的地址的电子邮件帐户。 请与您的消息传递系统管理员联系。

在 **[!UICONTROL Advanced parameters]** 电子邮件模板属性的部分， **[!UICONTROL From (email address)]** 对应于发件人地址的字段。

![](assets/template-parameters.png)

地址域必须与配置的子域相同。

此 **[!UICONTROL Reply to]** 字段对应于用于回复的电子邮件地址和名称。

**笔尖** -Adobe建议使用现有的真实地址，如您品牌的客户关怀团队。 在这种情况下，如果收件人发送回复，客户关怀部门将能够处理。

要更改发送者的名称（将显示在已发送邮件的标题中），请转到 **[!UICONTROL Properties]**  选项卡（可通过主页图标访问），然后单击 **[!UICONTROL Default sender name]** 块。

![](assets/template-content.png)

为了提高投放的打开率，Adobe建议使用收件人易于识别的名称，例如您的品牌名称。

**笔尖**  — 为了进一步改善收件人的体验，您可以添加人员的姓名，例如“Emma from Megastore”。

有关个性化发件人名称的更多信息，请参阅 [电子邮件发件人](../../designing/using/subject-line.md#email-sender).

## 个性化短信发送者姓名

在 **高级参数** 短信模板属性的部分， **起始日期** 选项允许您使用字符串个性化短信消息发送者的名称。 该名称在收件人的手机显示为短信消息的发送者。

如果此字段为空，则将显示所用外部帐户中提供的源号码。如果未提供源号码，则将使用短代码。有关更多信息，请参阅[短信配置](../../administration/using/configuring-sms-channel.md)。

**笔尖**  — 查看您所在国家/地区有关修改发件人地址的法律。 您还应与短信服务提供商进行核实，了解他们是否提供此功能。

## 设置控制组

发送投放后，您可以将排除的收件人的行为与接收投放的收件人的行为进行比较。 然后，您可以衡量营销活动的效率。 了解有关控制组的更多信息 [本节](../../sending/using/control-group.md).

## 使用类型应用过滤器或控制规则

分类包含在发送任何消息之前在分析阶段应用的检查规则。

在 **[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]** ，并根据需要更改默认分类。

例如，为了更好地控制出站流量，您可以通过定义每个子域一个关联并为每个关联创建一个类型来定义可以使用的IP地址。 相关性在实例的配置文件中定义。 联系Adobe Campaign管理员。

有关分类的详细信息，请参阅 [本节](../../sending/using/managing-typologies.md).

## 将品牌链接到模板

与品牌标识相关的已发送电子邮件的参数（如品牌徽标或发件人地址）在Adobe Campaign中集中管理。 您可以创建一个或多个品牌并将它们链接到投放模板。

有关在Adobe Campaign中使用和配置品牌的更多信息，请参阅品牌策略。

要显示或更改分配给投放模板的品牌，请选择模板的“编辑属性”按钮，然后导航到品牌的详细信息。

![](assets/template-brand.png)

有关将品牌链接到模板的更多信息，请参阅 [为品牌分配电子邮件](../../administration/using/branding.md#assigning-a-brand-to-an-email).

了解如何创建并配置品牌 [在此部分中](../../administration/using/branding.md#creating-a-brand).
