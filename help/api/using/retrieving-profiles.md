---
solution: Campaign Standard
product: campaign
title: 检索用户档案
description: 进一步了解如何使用API检索用户档案。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: da0aa6c111f3e44bb502c1e5c4ad7feff9108d81
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 5%

---


# 检索用户档案 {#retrieving-profiles}

使用&#x200B;**用户档案**&#x200B;请求执行检索GET。

然后，您可以使用过滤器、排序和分页来优化搜索。 有关详细信息，请参阅[其他操作](../../api/using/sorting.md)部分。

此外，Campaign StandardAPI允许您根据以下字段之一搜索用户档案:电子邮件、名字、姓氏或任何自定义字段。 如需详细信息，请参阅[此部分](#searching-field)。

<br/>

***示例请求***

* 检索所有GET的示例用户档案请求。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
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
           },
           ...
   }
   ```

* 检索前10个电子邮件值的示例GET请求。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10 \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   响应请求。 “下一个”节点返回URL，该URL允许您访问下一个10个电子邮件值。

   ```
   {
   "content": [
       "amy.dakota@mail.com",
       "kristen.smith@mail.com",
       "omalley@mail.com",
       "xander.harrys@mail.com",
       "jane.summer@mail.com",
       "gloria.boston@mail.com",
       "edward.snow@mail.com",
       "dorian.simons@mail.com",
       "peter.paolini@mail.com",
       "mingam+test08@adobe.com"
   ],
   "next": {
       "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
       lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
   }
   }
   ```

## 基于字段{#searching-field}搜索用户档案

**[!UICONTROL filterType]**&#x200B;参数允许您根据以下字段之一检索用户档案:在扩展用户档案资源时，电子邮件、名字、姓氏或任何已在高级筛选中添加的自定义字段。

>[!NOTE]
>
>搜索区分大小写，只对前缀执行。 例如，您将无法使用姓氏的最后字母查找用户档案。

***示例请求***

* 基于名筛选用户档案的示例请求。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John&filterType=firstName \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* 根据姓氏筛选用户档案的示例请求。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Miller&filterType=lastName \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* 根据电子邮件筛选用户档案的示例请求。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John%40gmail.com&filterType=email \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* 基于“Hobby”自定义字段筛选用户档案的示例请求。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byText?cusHobby=Dancing&filterType=Hobby \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```
