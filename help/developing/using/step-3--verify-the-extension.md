---
solution: Campaign Standard
product: campaign
title: '"第 3 步：验证扩展"'
description: 了解如何使用Rest API访问扩展字段。
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: Data Model
role: Developer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 12%

---


# 第 3 步：验证扩展{#step-verify-the-extension}

1. 对用户档案和服务扩展API的元数据执行GET操作，以检查在用户档案自定义资源中添加的字段现在是否可用。

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. 它返回：

   ![](assets/extendpandsapiview.png)

   该字段现在可用于进一步开发和集成。

