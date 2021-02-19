---
solution: Campaign Standard
product: campaign
title: 设置API访问
description: 了解如何设置对Campaign Standard API的访问。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 1%

---


# 设置 API 访问 {#setting-up-api-access}

Adobe Campaign Standard API访问通过以下步骤设置。 [AdobeIO文档](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)中详细介绍了这些步骤。

>[!IMPORTANT]
>
>要在Adobe IO中管理证书，请确保您对组织具有<b>系统管理员</b>权限，或在管理控制台中具有[开发人员帐户](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a>权限。

1. **请检查您是否有数字证书**，或根据需要创建数字证书。在以下步骤中需要随证书提供的公钥和私钥。
1. **在Adobe Campaign IO中创建一个与Adobe** Service的新集成并配置它。随后将生成您的凭据（API密钥、客户端机密……）。
1. **从先前生成的凭据创** 建JSON Web令牌(JWT)，然后使用私钥对其进行签名。JWT对Adobe验证您的身份和授予您对API的访问权限所需的所有身份和安全信息进行编码。
1. **通过POST请求将JWT** 交换为访问令牌。此访问令牌必须用于API请求的每个标头。

要建立安全的服务到服务Adobe I/O API会话，对Adobe服务的每个请求都必须在授权标头中包含以下信息。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**:这是您的个人组织ID，Adobe为每个实例提供一个组织ID:

   * &lt;organization> :您的生产实例，
   * &lt;organization-mkt-stage>:您的舞台实例。

   要获取您的组织ID值，请咨询您的管理员或您的Adobe技术联系人。 您还可以在许可证列表(请参阅<a href="https://www.adobe.io/authentication.html">Adobe IO文档</a>)中创建新集成时将其检索到Adobe I/O中。

* **&lt;access_token>**:您的个人访问令牌，在通过POST请求交换JSON Web令牌时检索到。

* **&lt;api_key>**:您的个人API密钥。它在创建与Adobe Campaign服务的新集成后在Adobe I/O中提供。

   ![替换文本](assets/tenant.png)

## 故障排除

在AdobeIO集成过程中，如果出现以下错误：

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


请咨询管理员或Adobe技术联系人，以检查CNAME参数是否创建正确。