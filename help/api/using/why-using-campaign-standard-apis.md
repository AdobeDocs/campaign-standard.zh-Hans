---
title: 为何使用 Campaign Standard API?
description: 了解有关Campaign StandardAPI及其使用原因的更多信息。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: ef045e5d-cd02-44a0-9a1e-d468483a38d9
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 3%

---

# 为何使用 Campaign Standard API {#why-using-campaign-standard-apis}

Adobe Campaign Standard提供了API，允许现有系统与Campaign平台集成，实时解决现实世界中的问题。

注册或选择退出页面等公共网站需要连接到后端系统以存储用户档案信息。 像Adobe Campaign这样的后端系统灵活而强大，可以将配置文件数据摄取到其中并对其执行自定义操作。

以下是一些示例：

* 潜在客户在线注册。
* 现有的客户个人资料和营销通信偏好管理。
* 基于事件的交易通信触发 — 订单确认、预订行程、密码重置等。
* 甚至放弃电子邮件通信。

注册登陆页面为客户或潜在客户提供了一种注册其姓名和电子邮件地址的方法。 一旦Campaign Standard捕获了用户档案信息和偏好设置，它就可以根据用户的兴趣发送个性化消息。

它们使用以下元素构建：

1. 带有Campaign API侦听器的注册表单。

   ![替换文字](assets/apis_uc1.png)

1. 要根据复选框执行的自定义操作。 与普通注册流程相比，选择“Email Special Offers”（电子邮件特别优惠）的客户将收到一封包含礼品券的自定义邮件。

   ![替换文字](assets/apis_uc2.png)

1. 在单击电子邮件中的“更新详细信息”链接后，用户档案可能会更改其详细信息。 这会将配置文件带到“更新您的配置文件和首选项详细信息”页面。 要执行该操作，会将配置文件详细信息(Pkey)传递到Campaign服务器，并检索和表示配置文件。 一旦用户档案单击“更新”按钮，信息就会更新到系统中(通过PATCH命令)。

   ![替换文字](assets/apis_uc3.png)

提供了一组请求，以帮助您熟悉Campaign StandardAPI请求。 此收藏集采用JSON格式，提供了表示常见用例的预设计API请求。

以下步骤描述了导入和使用该集合在Campaign Standard数据库中创建用户档案的分步使用案例。

>[!NOTE]
>
>我们的示例使用Postman。 但是，请随意使用您最喜爱的REST客户端。

1. 通过单击以下载JSON收藏集 [此处](https://helpx.adobe.com/content/dam/help/en/campaign/kb/working-with-acs-api/_jcr_content/main-pars/download_section/download-1/KB_postman_collection.json.zip).

1. 打开Postman，然后选择 **文件** / **导入** 菜单。

1. 将下载的文件拖放到窗口中。 预先设计的API请求随即显示，可供使用。

   ![替换文字](assets/postman_collection.png)

1. 选择 **创建用户档案** ，然后更新POST请求和 **标头** 制表符和您的信息(&lt;organization>， &lt;api_key>， &lt;access_token>)。 如需详细信息，请参阅[此部分](../../api/using/setting-up-api-access.md)。

   ![替换文字](assets/postman_uc1.png)

1. 填写 **正文** 选项卡，并选择要添加到新配置文件的信息，然后单击 **发送** 按钮以执行请求。

   ![替换文字](assets/postman_uc2.png)

1. 创建对象后，会为其关联一个主键(PKey)。 它显示在请求响应中以及其他属性中。

   ![替换文字](assets/postman_uc3.png)

1. 打开您的Campaign Standard实例，然后检查是否创建了用户档案，其中包含有效负载中的所有信息。

   ![替换文字](assets/postman_uc4.png)
