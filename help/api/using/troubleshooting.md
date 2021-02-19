---
solution: Campaign Standard
product: campaign
title: 故障排除
description: 进一步了解与常见问题相关的Campaign StandardAPI。
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 0%

---


# 故障排除 {#troubleshooting}

* **转到Adobe.io控制台时，您会收到以下错误：“Adobe I/O控制台仅可用于选择企业帐户的成员。如果您认为您应该具有访问权限，请与您的系统管理员联系。&quot;**

您只能为您所管理的IMS组织创建API密钥。 如果显示此消息，并且您想创建API密钥，并且想要向IMS组织的管理员之一询问。

* **向Adobe.io发出请求时，您会得到{&quot;error_code&quot;:&quot;403023&quot;,&quot;message&quot;:&quot;用户档案无效&quot;}**

这意味着您的特定活动产品的IMS设置存在问题：IMS团队需要修复它。

要获取更多详细信息，您可以使用您的令牌调用IMS API，以查看IMS用户档案的外观：您需要有一个prodCtx，其中organization_id与您放入URL中的organization.id相同，以便Adobe.io能够路由您的请求。
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

使用此请求检查您的IMS用户档案。

```
-X GET https://ims-na1.adobelogin.com/ims/profile/v1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

在响应中，ORGANIZATION_ID值在您的第一个GET请求中必须相同。

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

* **向Adobe.io发出请求时，您会得到{&quot;code&quot;:500, &quot;message&quot;:&quot;糟糕。出了点问题。 请检查您的URI并重试。&quot;}**

Adobe.io声明了您的无效URI:您请求的URI很可能无效。 在Adobe.io上，当您选择活动服务时，您会得到一个具有可能的organization_id列表的选取器。 您需要检查您选择的是否是您放入URL的。

* **向Adobe.io发出请求时，您会得到{&quot;error_code&quot;:&quot;401013&quot;,&quot;message&quot;:&quot;Oauth token is not valid&quot;}**

您的令牌无效（用于生成令牌的不当IMS调用）或您的令牌已过期。

* **我在创作后看不到我的用户档案**

根据实例配置，创建的用户档案需要与&#x200B;**orgUnit**&#x200B;关联。 要了解如何在创建中添加此字段，请参阅[本节](../../api/using/creating-profiles.md)。

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
