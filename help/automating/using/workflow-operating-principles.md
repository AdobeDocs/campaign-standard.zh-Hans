---
title: 工作流程操作原理
seo-title: 工作流程操作原理
description: 工作流程操作原理
seo-description: 了解工作流程的主要方面。
page-status-flag: 从未激活
uuid: 85755e85-617b-4a9b-bb30-96ba8833 f4 f0
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 关于工作流和数据管理
discoiquuid: a13785d-1ef7-4043-9927-2d495b83709f
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Workflow operating principles{#workflow-operating-principles}

A workflow is a **sequence of configurable activities**. 每个活动在流程中都有特定作用。The result of each activity is forwarded to the following activity by a **transition**, represented by an arrow.

在一个活动之间交换的数据类型，以及另一个活动之间的数据类型可能会影响以下活动的配置方式。例如，如果在电子邮件交付活动之前建立了人口，则可以作为相关电子邮件的目标。

您可以在执行工作流之前或之后打开活动以检查或编辑参数。

您可以打开过渡以检查发送的数据在执行工作流期间还是执行后是否正确。To access the detail view of the transitions, you have to check the **[!UICONTROL Keep interim results]** option in the **[!UICONTROL Execution]** section of the workflow properties.

![](assets/workflow_overview.png)

