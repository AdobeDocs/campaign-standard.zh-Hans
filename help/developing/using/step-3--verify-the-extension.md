---
solution: Campaign Standard
product: campaign
title: '"第 3 步：验证扩展"'
description: 了解如何使用Rest API访问扩展字段。
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 13%

---


# 第 3 步：验证扩展{#step-verify-the-extension}

1. 对GET和服务扩展API的元数据执行用户档案操作，以检查在用户档案自定义资源中添加的字段现在是否可用。

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. 它返回：

   ![](assets/extendpandsapiview.png)

   该字段现在可用于进一步开发和集成。

