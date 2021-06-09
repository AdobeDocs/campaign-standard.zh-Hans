---
solution: Campaign Standard
product: campaign
title: 筛选
description: 了解如何执行过滤操作。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: cdb050b7-d327-42f7-b534-d32d988c8ffb
source-git-commit: f946a7565c30a3e53b2bd6876e880100fa8a0be2
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 1%

---

# 筛选 {#filtering}

## 检索过滤器元数据

每个资源都有过滤器。 要识别与资源关联的过滤器，您需要对资源元GET执行数据请求。 此请求会返回为给定资源定义所有过滤器的URL。 有关元数据的更多信息，请参阅[此部分](../../api/using/metadata-mechanism.md)。

要识别过滤器的元GET并确定如何使用该元数据，您必须对先前返回的URL执行元数据请求。

<br/>

***示例请求***

以下示例负载显示如何检索“profile”资源的“byText”过滤器元数据。 首先，对“profile”资源元数据执行GET请求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它会返回描述过滤器的URL。

```
{
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>/filters/"
    }
  }
```

对URL执行GET请求。 它会返回用户档案资源的过滤器列表，以及与每个过滤器关联的元数据。

```
{
"birthday": {
        "PKey": "@FL-CbDFXbnHbXcVpeCGWL46VXJLn1LqxLMPagt2vz8sCxQ52lvB15KiUaxXkxJYQw-tZXYrgUWG6K8QcB4gxVY9RKoba5bRFY3294YFshDmorRr8",
        "category": "0150_profile",
        "condition": ...,
        "data": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/birthday?type=$value&precision=$value&operator=$value&day=$value&month=$value&includeStart=$value&endDay=$value&endMonth=$value&includeEnd=$value&relativeValue=$value&nextUnitsValue=$value&previousUnitsValue=$value",
        "formType": "webPage",
        "fragmentName": "",
        "label": "Birthday",
}
```

## 过滤器元数据结构

每个过滤器具有相同的元数据结构：

* **@formType**&#x200B;和&#x200B;**@webPage**&#x200B;字段是技术字段。
* **data**&#x200B;字段提供了有关如何使用过滤器的示例。
* **metadata**&#x200B;节点描述过滤器参数。
* **条件**&#x200B;节点描述过滤器要执行的操作。 元数据节点中描述的过滤器参数用于创建过滤条件。 对于每个筛选条件，如果&#x200B;**enabledIf**&#x200B;为true，则将应用&#x200B;**expr**。

<br/>

过滤器元数据结构示例：

```
"byText": {
        "PKey": "...",
        "category": "99_none",
        "condition": ...,
        "data": "/profileAndServices/profile/byText?text=$value",
        "formType": "none",
        "fragmentName": "",
        "label": "By name or email",
    }
```

## 使用过滤器

可通过以下请求进行筛选：

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/by<filterName>?<filterParam>=<filterValue>`

可以在一个请求中组合使用多个过滤器：

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/<filter1name>/<filter2name>?<filter1param>=<filter1value>&<filter2param>=<filter2value>`

<br/>

***示例请求***

* 用于检索类型为“email”的“service”资源的GET请求示例。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel?channel=email \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   响应请求。

   ```
   {
       "content": [
           {
               "PKey": "<PKEY>",
               "created": "2019-09-25 23:20:35.000Z",
               "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/@I_FIiDush4OQPc0mbOVR9USoh36Tt5CsD35lATvQjdWlXrYc0lFkvle2XIwZUbD8GqTVvSp8AfWFUvjkGMe1fPe5nok",
               "label": "Marketing Newsletter",
               "lastModified": "2019-09-25 23:20:35.000Z",
               "limitedDuration": false,
               "messageType": "email",
               "mode": "newsletter",
               ...
           },
           ...
       ],
       ...
   }
   ```

* 用于检索包含“Doe”的“profile”资源的示例GET请求，位于
电子邮件或姓氏字段（byText筛选器可搜索电子邮件和姓氏字段）。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Doe \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   响应请求。

   ```
   {
       "content": [
           {
               "PKey": "<PKEY>",
               "firstName": "John",
               "lastName":"Doe",
               "birthDate": "1980-10-24",
               ...
           }
           ...
       ],
       ...
   }
   ```

* 用于检索类型为“email”且标签为“sport”的服务资源的示例GET请求。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/byText?channel=email&text=sport \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   响应请求。

   ```
   {
       "content": [
           {
               "PKey": "<PKEY>",
               "created": "2019-09-26 09:36:01.014Z",
               "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
               "label": "sport",
               "lastModified": "2019-09-26 09:36:01.014Z",
               "limitedDuration": false,
               "messageType": "email",
               "mode": "newsletter",
               "name": "SVC13",
               ...
           }
       ],
       ...
   }
   ```

## 自定义过滤器

如果要使用自定义过滤器，则必须在Adobe Campaign Standard界面中创建和自定义该过滤器。 然后，自定义过滤器将具有与现成过滤器相同的行为：

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/by<customFilterName>?<customFilterparam>=<customFilterValue>`

有关更多信息，请参阅Campaign Standard文档：

* [配置过滤器定义](https://helpx.adobe.com/campaign/standard/developing/using/configuring-filter-definition.html).
* [用例：使用复合标识键调用资源](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/adding-or-extending-a-resource/uc-calling-resource-id-key.html)。

<br/>

***示例请求***

用于检索交易金额为100$或更多的“配置文件”资源的示例GET请求。 请注意，“byAmount”过滤器首先在Adobe Campaign Standard界面中定义，并链接到“Transaction”自定义表。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byAmount?amount_parameter=100 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!--
Response to the request.

```

{
    "content": [
        {
            "PKey": "<PKEY>",
            "builtIn": false,
            "created": "2019-09-26 09:36:01.014Z",
            "desc": "",
            "end": "",
            "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
            ...
        }
    ],
}

```

-->

<!-- exemple à vérifier de bout en bout-->

<!--+category = query editor
privacy ?
displayFOrmat ?
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
-->





<!--
 if link ou collection.* resName +
* resTarget tout ca, ca va ensemble : le système de lien, resTarget va donner la ressource targetée par le lien. type
resType = type technique (long..) resType = link alors unbound='false' ou 'true'
If type = enumeration alors champ "values" rajouté et les valeurs sont dans values
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
ail faut que la valeur poster soit conforme ,elle doit valider la dataPolicy . La dataPolicy peut soit controler la valeur (email invalide), soit transformé (cas du smartCase par exemple)
type dans les metadata = type de haut-niveau (nombre, text)
-->
