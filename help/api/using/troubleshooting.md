---
title: 故障排除
description: 进一步了解与常见问题相关的Campaign Standard API。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ab5725b326de2f1cb4c5d15d0d3c0303a6bf0f06

---


# 故障排除 {#troubleshooting}

* **转到Adobe.io控制台时，您会收到以下错误：“Adobe I/O控制台仅对企业帐户的选定成员可用。 如果您认为您应该具有访问权限，请联系您的系统管理员。”**

您只能为您所管理的IMS组织创建API密钥。 如果显示此消息，并且您要创建API密钥，并且要向IMS组织的管理员之一询问。

* **向Adobe.io发出请求时，您会收到{"error_code":"403023","message":"Profile is not valid"}**

这意味着您的特定Campaign产品的IMS配置存在问题：IMS团队需要修复它。

要获取更多详细信息，您可以使用您的令牌调用IMS API，以查看IMS配置文件的外观：您需要有一个prodCtx，其中organization_id与您放入的URL中的organization_id相同，这样Adobe.io才能路由您的请求。
如果缺少IMS设置，则需要修复。

```
-X GET https://mc.adobe.io/{ORGANIZATION}/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它返回以下错误。

```
{"error_code":"403023","message":"Profile is not valid"}
```

使用此请求检查您的IMS配置文件。

```
-X GET https://ims-na1.adobelogin.com/ims/profile/v1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

在响应中，ORGANIZATION_ID值必须与第一个GET请求中的值相同。

```
{
  "countryCode": "FR",
  "mrktPermEmail": null,
  "projectedProductContext": [
    {
    "prodCtx": {
      "statusCode": "ACTIVE",
      "ident": "ZQ9FRQK7BF09YXAESFY9DDQP1G",
      "modDts": 1448307260000,
      "organization_id": "actest",
      "owningEntity": "6096892F54B5819E0A4C98A2@AdobeOrg",
      "serviceCode": "dma_tartan",
      "label": "Adobe Marketing Cloud",
      "serviceLevel": "standard",
      "createDts": 1421181343000,
      "deal_id": " "
      }
    }
  ]
}
```

* **向Adobe.io发出请求时，您会收到{"code":500, "message":"糟糕。 出了点问题。 检查您的URI，然后重试。"}**

Adobe.io声明您的无效URI:您请求的URI很可能无效。 在Adobe.io上，选择Campaign服务时，您会得到一个选取器，其中包含可能的organization_id列表。 您需要检查您选择的是否是您放入URL的。

* **向Adobe.io发出请求时，您会收到{"error_code":"401013","message":"Oauth token is not valid"}**

您的令牌无效（用于生成令牌的不当IMS调用）或您的令牌已过期。

* **我在创建后看不到个人资料**

根据实例配置，创建的配置文件需要关联到 **orgUnit**。 要了解如何在您的创建中添加此字段，请查阅 [此部分](../../api/using/managing-profiles.md)。

<!-- * (error duplicate key : quand tu crées un profile qui existe déjà , il faut faire un patch pour updater le profile plutôt qu’un POST)

With Curl
List all profiles

Create a profile

Update the mobilePhone attribute of a profile

API Calls on Service

GET the list of services

-->

<!--

How to find and use a filter?
Error codes:

* PAtch sur Age = message d'erreur :
500
Cannot update the 'age' property that is read-only
'age' property is not valid for the 'profile' resource.
-->

<!--
How to filter a list of subscribed profiles with available profile filters ? by date (by les filtres dispo sur la ressource) ?

Pattern classique :

recupérer la liste des subscriptions filtrées d'un profile
1) get sur profile
2) recup PKey
3) get sur PKey
4) get sur href des subscriptions

Comment savoir quel filtre appliquer ?

1) get sur metadata de profile
2) retourne description de la collection subscription
3) get sur la valeur du champ resTarget
4) get sur le href dans filters
5) retourne les filtres applicables sur l'url des data.

-->
