---
title: API疑难解答
description: 进一步了解与Campaign StandardAPI相关的常见问题
feature: API
role: Data Engineer
level: Experienced
exl-id: 404356cd-021f-4739-a88f-b8b1b79e19bc
source-git-commit: b65bf28565c25072c6a95cebdb999ce38a2e2e1a
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 1%

---

# API 疑难解答 {#troubleshooting}

* **转到Adobe.io控制台时，您会收到以下错误：“Adobe I/O控制台仅可用于选择企业帐户的成员。 如果您认为您应该拥有访问权限，请与您的系统管理员联系。”**

您只能为您所管理的组织创建API密钥。 如果显示此消息，且您想要创建API密钥，并且想要请求组织的一位管理员。

* **向Adobe.io发出请求时，您会收到{&quot;error_code&quot;:&quot;403023&quot;,&quot;message&quot;:&quot;Profile is not valid&quot;}**

这表示在IMS配置您的特定Campaign产品时出现问题：IMS团队需要修复该问题。

要获取更多详细信息，您可以使用令牌调用IMS API，以查看IMS配置文件的外观：您需要具有一个prodCtx，其中organization_id与您放置在URL中的organization_id相同，以便Adobe.io能够路由您的请求。
如果缺少IMS设置，则需要修复。

```
-X GET https://mc.adobe.io/{ORGANIZATION}/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它会返回以下错误。

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

在响应中， ORGANIZATION_ID值必须在第一个GET请求中相同。

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

* **向Adobe.io发出请求时，您会收到{&quot;code&quot;:500, &quot;message&quot;:&quot;Aoh。 出现错误. 请检查您的URI，然后重试。&quot;}**

Adobe.io声明了您的无效URI:您请求的URI很可能无效。 在Adobe.io上，选择Campaign服务时，您会获得一个选取器，其中包含可能的organization_id列表。 您需要检查您选择的是URL中放置的URL。

* **向Adobe.io发出请求时，您会收到{&quot;error_code&quot;:&quot;401013&quot;,&quot;message&quot;:&quot;Oauth令牌无效&quot;}**

您的令牌无效（用于生成令牌的IMS调用不正确）或令牌已过期。

* **创建后，我看不到个人资料**

根据实例配置，创建的配置文件需要关联到 **orgUnit**. 要了解如何在创建中添加此字段，请查阅 [此部分](../../api/using/creating-profiles-api.md).

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
