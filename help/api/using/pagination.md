---
solution: Campaign Standard
product: campaign
title: 分页
description: 了解如何执行分页操作。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# 分页

默认情况下，在列表中加载25个资源。

使用 **_lineCount** 参数可以限制响应中列出的资源数。  然后，您可以使用 **下一个** 节点显示下一个结果。

>[!NOTE]
>
>始终使用在下一个节点中返回 **的** URL值执行分页请求。
>
>将计 **算** _lineStart请求，并且必须始终在下一个节点返回的URL **中使用** 。

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

响应请求，下一个节 **点** 将执行分页。

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

默认情况下， **与具** 有大量数据的表交互时，下一个节点不可用。 要能够执行分页，必须将 **_forcePagination=true** 参数添加到调用URL。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>在Campaign StandardXtkBigTableThreshold选项中定义表大于其上的 **记录数** 。 默认值是100,000条记录。
