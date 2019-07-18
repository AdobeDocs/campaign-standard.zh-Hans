---
title: “步骤3：验证扩展”
seo-title: “步骤3：验证扩展”
description: “步骤3：验证扩展”
seo-description: 了解如何使用Rest API访问扩展字段。
page-status-flag: 从未激活
uuid: 35ba89a5-a354-466f-91a0-50de111 a2 e00
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-case—extending-the-api
discoiquuid: 21不良242-5921-445c-8df9-3d57dobe35197
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Step 3: Verify the extension{#step-verify-the-extension}

1. 对配置文件和服务扩展API的元数据执行GET操作，以检查在配置文件自定义资源中添加的字段现在是否可用。

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. 它返回：

   ![](assets/extendpandsapiview.png)

   现在，该字段可用于进一步开发和集成。

