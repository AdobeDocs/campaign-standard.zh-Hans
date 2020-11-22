---
solution: Campaign Standard
product: campaign
title: 设置API访问
description: 了解如何设置对Campaign StandardAPI的访问。
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

Adobe Campaign StandardAPI访问通过以下步骤设置。 这些步骤均详见 [AdobeIO文档](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)。

>[!IMPORTANT]
>
>要在AdobeIO中管理证书，请确保您对组 <b>织或Admin</b> Console中的开发人 [员帐户拥有](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a> 系统管理员权限。

1. **检查您有数字证书**，或根据需要创建数字证书。 在以下步骤中需要随证书提供的公钥和私钥。
1. **在Adobe CampaignIO中创建与Adobe服务的新集成** ，并对其进行配置。 随后将生成您的凭据（API密钥、客户端机密……）。
1. **从先前生成的凭据创建JSON Web** Token(JWT)，然后使用您的私钥对其进行签名。 JWT对Adobe验证您的身份并授予您对API的访问权限时所需的所有身份和安全信息进行编码。
1. **通过访问令牌请求将JWT** 换为POST。 此访问令牌必须用于API请求的每个头中。

要建立安全的服务到服务AdobeI/O API会话，对Adobe服务的每个请求都必须在授权标头中包含以下信息。

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

   要获取您的组织ID值，请咨询您的管理员或Adobe技术联系人。 创建新集成时，您还可以在许可证列表中将其检索到AdobeI/O中(请参阅 <a href="https://www.adobe.io/authentication.html">AdobeIO文档</a>)。

* **&lt;ACCESS_TOKEN>**:您的个人访问令牌，通过POST请求交换JSON Web令牌时检索到该。

* **&lt;API_KEY>**:您的个人API密钥。 它在创建与Adobe服务的新集成后在Adobe CampaignI/O中提供。

   ![替换文本](assets/tenant.png)

## 故障排除

在AdobeIO集成过程中，如果出现以下错误：

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


请咨询管理员或Adobe技术联系人，检查CNAME参数是否创建正确。