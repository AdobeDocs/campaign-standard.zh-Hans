---
title: '"第 3 步：验证扩展"'
description: 了解如何使用Rest API访问扩展字段。
page-status-flag: 从未激活
uuid: 35ba89a5-a354-466f-91a0-50de11a2e00
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 开发
content-type: 参考
topic-tags: use-case-extending-the-api
discoiquuid: 21bad242-5921-445c-8df9-3d57dbe35197
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 第 3 步：验证扩展{#step-verify-the-extension}

1. 对Profiles &amp; Services Extension API的元数据执行GET操作，以检查在Profiles自定义资源中添加的字段现在是否可用。

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. 它返回：

   ![](assets/extendpandsapiview.png)

   该字段现在可用于进一步开发和集成。

