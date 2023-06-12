---
title: "第 3 步：验证扩展"
description: 了解如何使用Rest API访问扩展字段。
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: 34cb416c-ee3d-4b7c-a75b-640432db320d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 13%

---

# 第 3 步：验证扩展{#step-verify-the-extension}

1. 对Profiles &amp; Services扩展API的元数据执行GET操作，以检查添加到Profiles自定义资源中的字段现在是否可用。

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. 它会返回：

   ![](assets/extendpandsapiview.png)

   该字段现在可用于进一步开发和集成。
