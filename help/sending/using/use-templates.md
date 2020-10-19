---
title: 使用投放模板
seo-title: 使用投放模板
page-status-flag: never-activated
uuid: a540efc7-105d-4c7f-a2ee-ade4d22b3445
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
discoiquuid: 0cbc4e92-482f-4dac-a1fb-b738e7127938
index: y
translation-type: tm+mt
source-git-commit: 100f7eef03d10a66832920708ad415f8f0d3883c
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 9%

---


# 使用模板 {#use-templates}

投放模板为大多数常见类型的活动提供现成方案，从而提高效率。 借助模板，营销人员可以在更短的时间内以最少的自定义次数部署新活动。

在本节中进一步了 [解投放模板](../../start/using/marketing-activity-templates.md)。

## 开始使用投放模板 {#gs-templates}

投放模板 [使](../../start/using/marketing-activity-templates.md#creating-a-new-template) 您只需定义一组技术属性和功能属性，这些属性可以满足您的需求，并且可以再用于将来的投放。 然后，您可以节省时间并在需要时实现投放标准化。

在Adobe Campaign中管理多个品牌时，Adobe建议每个品牌有一个子域。 例如，银行可以具有与其每个区域机构对应的多个子域。 如果银行拥有bluebank.com域，其子域可以是@ny.bluebank.com、@ma.bluebank.com、@ca.bluebank.com等。 每个子域有一个投放模板使您始终能够为每个品牌使用正确的预配置参数，从而避免错误并节省您的时间。

**提示**: 为避免在活动中出现配置错误，我们建议您重复本机模板并更改其属性，而不是创建新模板。

## 配置地址

* 发送者的地址是强制性的，允许发送电子邮件。

* 某些ISP(Internet服务提供商)在接受消息前检查发送者地址的有效性。

* 格式不良的地址可能导致接收服务器拒绝它。 您必须确保提供正确的地址。

* 地址必须明确标识发件人。 域必须由发送方拥有并注册。

* Adobe建议创建与为投放和回复指定的地址对应的电子邮件帐户。 请咨询邮件系统管理员。

在电 **[!UICONTROL Advanced parameters]** 子邮件模板属性的部分，该字 **[!UICONTROL From (email address)]** 段对应于发件人的地址。

![](assets/template-parameters.png)

地址域必须与您配置的子域相同。

字段 **[!UICONTROL Reply to]** 与用于回复的电子邮件地址和名称相对应。

**提示** -Adobe建议使用现有真实地址，如您品牌的客户关怀。 在这种情况下，如果收件人发送回复，客户服务中心将能够处理。

要更改将显示在所发送邮件标题中的发件人姓名，请转 **[!UICONTROL Properties]** 到“电子邮件设计器”主页卡（可通过主页图标访问），然后单击 **[!UICONTROL Default sender name]** 块。

![](assets/template-content.png)

要提高投放的开业率，Adobe建议使用收件人可轻松识别的名称，如品牌名称。

**提示** -要进一步改善收件人的体验，您可以添加个人姓名，例如“Emma from Megastore”。

有关个性化发件人姓名的详细信息，请参 [阅电子邮件发件人](../../designing/using/subject-line.md#email-sender)。

## 个性化SMS发件人姓名

在SMS **模板** 属性的“高级参数”部分，“发件人 **** ”选项允许您使用字符串个性化SMS消息发送者的名称。 该名称在收件人的手机显示为短信消息的发送者。

如果此字段为空，则将显示所用外部帐户中提供的源号码。如果未提供源号码，则将使用短代码。有关更多信息，请参阅[短信配置](../../administration/using/configuring-sms-channel.md)。

**提示** -检查您所在国家／地区有关修改发件人地址的法律。 您还应与短信服务提供商进行核实，了解他们是否提供此功能。

## 设置对照组

发送投放后，您可以将被排除收件人的行为与收到投放的收件人进行比较。 然后，您可以衡量活动的效率。 进一步了解 [对照组](../../sending/using/control-group.md)。

## 使用类型应用过滤器或控制规则

类型学包含在分析阶段应用的检查规则，然后发送任何消息。

在模板 **[!UICONTROL Advanced parameters]** 属 **[!UICONTROL Preparation]** 性的“>”部分，根据您的需要更改默认的类型。

例如，为了更好地控制出站流量，您可以通过为每个子域定义一个关联，为每个关联创建一个类型来定义可以使用的IP地址。 关联在实例的配置文件中定义。 与Adobe Campaign管理员联系。

For more on typologies, refer to [this section](../../sending/using/managing-typologies.md).

## 将品牌链接到模板

与品牌标识相关的已发送电子邮件的参数（如品牌徽标或发件人地址）在Adobe Campaign中集中管理。 您可以创建一个或多个品牌并将它们关联到投放模板。

有关在Adobe Campaign中使用和配置品牌的更多信息，请参阅品牌。

要显示或更改分配给投放模板的品牌，请选择模板的“编辑属性”按钮并导航到品牌的详细信息。

![](assets/template-brand.png)

有关将品牌关联到模板的更多信息，请参 [阅将品牌分配到电子邮件](../../administration/using/branding.md#assigning-a-brand-to-an-email)。

本节了解如何创建和配 [置品牌](../../administration/using/branding.md#creating-a-brand)。
