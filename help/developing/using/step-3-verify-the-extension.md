---
title: 第 3 步：验证扩展
description: 了解如何使用Rest API访问扩展字段。
audience: developing
content-type: reference
topic-tags: use-case-extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: 34cb416c-ee3d-4b7c-a75b-640432db320d
TQID: https://experienceleague.adobe.com/XadrenC5de4Xh6MSCUiQUc-qXaTKr-xpG-7znnlWeeQ
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 61
ht-degree: 16%

---

# 第 3 步：验证扩展{#step-verify-the-extension}

1. 对Profiles &amp; Services扩展API的元数据执行GET操作，以检查添加到Profiles自定义资源中的字段现在是否可用。

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. 它会返回：

   ![](assets/extendpandsapiview.png)

   该字段现在可用于进一步开发和集成。
