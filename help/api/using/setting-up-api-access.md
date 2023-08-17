---
title: 设置API访问
description: 了解如何设置对Campaign StandardAPI的访问权限。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: efbbd0cd-9c56-4ad0-8bcb-efba4b63c28b
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 2%

---

# 设置 API 访问 {#setting-up-api-access}

Adobe Campaign Standard API访问可通过以下步骤进行设置。 有关每个步骤的详情，请参见 [Adobe Developer文档](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>在中管理证书 [Adobe Developer](https://developer.adobe.com/)，确保您拥有 **系统管理员** 对组织或机构的权限 [开发人员帐户](https://helpx.adobe.com/enterprise/using/manage-developers.html) 在Admin Console中。

1. **检查您是否拥有数字证书**，或根据需要创建一个。 以下步骤需要随证书一起提供的公钥和私钥。
1. **创建与Adobe Campaign服务的新集成** 在 [Adobe Developer](https://developer.adobe.com/) 并进行配置。 随后将生成您的凭据（API密钥、客户端密钥……）。
1. **创建JSON Web令牌(JWT)** 使用之前生成的凭据，并使用您的私钥签名。 JWT对Adobe验证您的身份并授予您访问API的权限所需的所有身份和安全信息进行编码。
1. **将JWT交换为访问令牌** 通过POST请求。 必须在API请求的每个标头中使用此访问令牌。

要建立安全的服务到服务Adobe I/OAPI会话，对Adobe服务的每个请求都必须在Authorization标头中包含以下信息。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**：这是您的个人组织ID，Adobe会为您每个实例提供一个组织ID：

   * &lt;organization> ：您的生产实例，
   * &lt;organization-mkt-stage>：您的暂存实例。

  要获取您的组织ID值，请咨询您的管理员或您的Adobe技术联系人。 您还可以在创建新集成时，在许可证列表中将其检索到Adobe I/O中(请参阅 <a href="https://developer.adobe.com/developer-console/docs/guides/authentication/">Adobe Developer文档</a>)。

* **&lt;access_token>**：您的个人访问令牌，在通过POST请求交换您的JSON Web令牌时检索。

* **&lt;api_key>**：您的个人API密钥。 在创建了与Adobe Campaign服务的新集成后，可在Adobe I/O中提供。

  ![替换文本](assets/tenant.png)

## 故障排除

在AdobeIO集成期间，如果出现以下错误：

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


请咨询您的管理员或Adobe的技术联系人，以检查CNAME参数是否正确创建。
