---
title: 设置API访问
description: 了解如何设置对Campaign StandardAPI的访问。
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
source-git-commit: fa80fefc1c897afb8448fc0121705102091ecf5c

---


# 设置 API 访问 {#setting-up-api-access}

Adobe Campaign标准API访问通过以下步骤设置。 [Adobe IO文档中详细介绍了这些步骤](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)。

>[!IMPORTANT]
>
>要在Adobe IO中管理证书，请确保您对组织具有系统管 <b>理员权限</b> ，或在“管理”控制台 [中拥有开发人员帐户](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a> 。

1. **检查您有数字证书**，或根据需要创建一个。 在以下步骤中需要随证书提供的公钥和私钥。
1. **在Adobe IO中创建与Adobe Campaign服务的新集成** ，并对其进行配置。 随后将生成您的凭据（API密钥、客户端机密……）。
1. **从先前生成的凭据创建JSON Web Token(JWT)** ，然后使用您的私钥对其进行签名。 JWT将编码Adobe验证您的身份并授予您对API的访问权所需的所有标识和安全信息。
1. **通过POST请求将JWT更换为访问令牌** 。 此访问令牌必须用在API请求的每个标头中。

要建立安全的服务对服务Adobe I/O API会话，对Adobe服务的每个请求都必须在授权标题中包含以下信息。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;组织>**:这是您的个人组织ID,Adobe为每个实例提供一个组织ID:

   * &lt;组织>:您的生产实例，
   * &lt;ORGANIZATION-mkt-stage>:您的舞台实例。
   要获取您的组织ID值，请咨询您的管理员或Adobe技术联系人。 在创建新集成时，您还可以在许可列表中将其检索到Adobe I/O中(请参阅 <a href="https://www.adobe.io/authentication.html">Adobe IO文档</a>)。

* **&lt;ACCESS_TOKEN>**:您的个人访问令牌，通过POST请求交换JSON Web令牌时已检索到它。

* **&lt;API_KEY>**:您的个人API密钥。 在创建与Adobe Campaign服务的新集成后，Adobe I/O中提供了该组件。

   ![替换文本](assets/tenant.png)
