---
title: 为何使用Campaign Standard API?
description: 进一步了解Campaign Standard API，以及使用它们的原因。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 47b5cf6aee969c7a199ec934b5be6bf80bee590e

---


# 为何使用Campaign Standard API {#why-using-campaign-standard-apis}

Adobe Campaign Standard提供API，使现有系统能与ACS平台集成以实时解决实际问题。

诸如注册或退出页面等公共网站需要连接到后端系统以存储配置文件信息。 后端系统（如Adobe Campaign）具有灵活性和强大功能，可将配置文件数据引入并对其执行自定义操作。

以下是一些示例：

* 潜在客户在线注册。
* 现有客户档案和营销沟通偏好管理。
* 基于事件的交易通信触发——订单确认、预订行程、密码重置等
* 甚至购物车放弃电子邮件通信。

注册登录页面为客户或潜在客户提供了一种注册其姓名和电子邮件地址的方式。 Campaign standard捕获个人资料信息和偏好后，可根据个人兴趣发送个性化消息。

它们是使用以下元素构建的：

1. 具有系列活动API监听器的注册表单。

   ![替换文本](assets/apis_uc1.png)

1. 要根据复选框执行的自定义操作。 与正常注册流程相比，选择“电子邮件特价优惠”的客户将收到另一封包含礼品券的自定义邮件。

   ![替换文本](assets/apis_uc2.png)

1. 在单击电子邮件中的“更新详细信息”链接后，配置文件可能会更改其详细信息。 这会将配置文件带到“更新您的配置文件和首选项详细信息”页面。 要执行该操作，配置文件详细信息(Pkey)会传递到Campaign服务器，并且会检索并显示配置文件。 配置文件单击“更新”按钮后，信息将更新到系统中（通过PATCH命令）。

   ![替换文本](assets/apis_uc3.png)

提供一组请求，帮助您熟悉Campaign Standard API请求。 此JSON格式的集合提供了预设计的API请求，这些请求表示常见用例。

以下步骤描述了在Campaign standard数据库中导入和使用集合创建配置文件的分步使用案例。

>[!NOTE]
>
>我们的示例使用邮递员。 但是，您可以随意使用您喜爱的REST客户端。

1. 单击此处下载JSON集 [合](https://helpx.adobe.com/content/dam/help/en/campaign/kb/working-with-acs-api/_jcr_content/main-pars/download_section/download-1/KB_postman_collection.json.zip)。

1. 打开邮递员，然后选择“文 **件** /导 **入** ”菜单。

1. 将下载的文件拖放到窗口中。 预设计的API请求显示，随时可用。

   ![替换文本](assets/postman_collection.png)

1. 选择创 **建配置文件请求** ，然后使用您自己的信息(&lt;ORGANIZATION&gt;、&lt;API_KEY&gt;、&lt;ACCESS_TOKEN&gt;)更新POST请求和 **** Headers选项卡。 如需详细信息，请参阅[此部分](../../api/using/setting-up-api-access.md)。

   ![替换文本](assets/postman_uc1.png)

1. 使用要添加到 **新配置文件的信息填充“正文** ”选项卡，然后单击“发送” **** 按钮以执行请求。

   ![替换文本](assets/postman_uc2.png)

1. 创建对象后，主键(PKey)即与其关联。 它显示在请求响应中以及其他属性中。

   ![替换文本](assets/postman_uc3.png)

1. 打开Campaign standard实例，然后检查是否已创建配置文件以及有效负荷中的所有信息。

   ![替换文本](assets/postman_uc4.png)
