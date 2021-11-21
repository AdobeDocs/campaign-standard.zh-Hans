---
title: 为何使用 Campaign Standard API?
description: 进一步了解Campaign StandardAPI及其使用方法。
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

Adobe Campaign Standard提供了API，允许现有系统与Campaign平台集成以实时解决实际问题。

注册或选择退出页面等公共网站需要连接到后端系统以存储配置文件信息。 后端系统(如Adobe Campaign)具有将配置文件数据摄取到中并对其执行自定义操作的灵活性和功能。

以下是一些示例：

* 潜在在线注册。
* 现有客户档案和营销沟通偏好管理。
* 基于事件的事务性通信触发 — 订单确认、预订行程、密码重置等
* 甚至是购物车放弃电子邮件通信。

注册登陆页面为客户或潜在客户提供了一种注册其名称和电子邮件地址的方式。 一旦Campaign Standard捕获了用户档案信息和首选项，便可以根据用户的兴趣发送个性化消息。

它们是使用以下元素构建的：

1. 使用Campaign API侦听器的注册表单。

   ![替换文本](assets/apis_uc1.png)

1. 要基于复选框执行的自定义操作。 与正常注册过程相比，选择“电子邮件特惠”的客户将收到带有礼品券的其他自定义邮件。

   ![替换文本](assets/apis_uc2.png)

1. 单击电子邮件中的“更新详细信息”链接后，用户档案可能会更改其详细信息。 这会将用户档案转到“更新用户档案和首选项详细信息”页面。 要执行该操作，用户档案详细信息(Pkey)将传递到Campaign服务器，并且会检索和显示用户档案。 用户档案单击“更新”按钮后，信息将更新到系统中(通过PATCH命令)。

   ![替换文本](assets/apis_uc3.png)

请求集合可帮助您熟悉Campaign StandardAPI请求。 此JSON格式的集合提供了代表常见用例的预设计API请求。

以下步骤描述了一个分步使用案例，用于导入和使用集合在Campaign Standard数据库中创建用户档案。

>[!NOTE]
>
>我们的示例使用Postman。 但是，请随时使用您最喜爱的REST客户端。

1. 通过单击 [此处](https://helpx.adobe.com/content/dam/help/en/campaign/kb/working-with-acs-api/_jcr_content/main-pars/download_section/download-1/KB_postman_collection.json.zip).

1. 打开Postman，然后选择 **文件** / **导入** 菜单。

1. 将下载的文件拖放到窗口中。 显示预先设计好的API请求，随时可供使用。

   ![替换文本](assets/postman_collection.png)

1. 选择 **创建用户档案** 请求，然后更新POST请求和 **标题** 选项卡，其中包含您自己的信息(&lt;organization>, &lt;api_key>, &lt;access_token>)。 如需详细信息，请参阅[此部分](../../api/using/setting-up-api-access.md)。

   ![替换文本](assets/postman_uc1.png)

1. 填写 **正文** 选项卡，然后单击 **发送** 按钮以执行请求。

   ![替换文本](assets/postman_uc2.png)

1. 创建对象后，会将主键(PKey)关联到该对象。 它在请求响应以及其他属性中可见。

   ![替换文本](assets/postman_uc3.png)

1. 打开您的Campaign Standard实例，然后检查是否创建了用户档案，并包含有效负载中的所有信息。

   ![替换文本](assets/postman_uc4.png)
