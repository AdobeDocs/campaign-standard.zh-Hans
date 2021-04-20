---
solution: Campaign Standard
product: campaign
title: 分页
description: 了解如何执行分页操作。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 1%

---


# 分页

默认情况下，在列表中加载25个资源。

**_lineCount**&#x200B;参数允许您限制响应中列出的资源数。  然后，可以使用&#x200B;**next**&#x200B;节点显示下一个结果。

>[!NOTE]
>
>始终使用在&#x200B;**next**&#x200B;节点中返回的URL值执行分页请求。
>
>将计算&#x200B;**_lineStart**&#x200B;请求，并且必须始终在&#x200B;**下一个**&#x200B;节点中返回的URL中使用。

<br/>

***示例请求***

显示GET资源1个记录的示例用户档案请求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

响应请求，使用&#x200B;**next**&#x200B;节点执行分页。

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
    ],
    "next": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
        lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
    }
    ...
}
```

默认情况下，与具有大量数据的表交互时，**next**&#x200B;节点不可用。 要执行分页，必须将&#x200B;**_forcePagenation=true**&#x200B;参数添加到调用URL中。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>在Campaign Standard **XtkBigTableThreshold**&#x200B;选项中定义表大于其的记录数。 默认值为100,000条记录。
