---
title: 集成应用程序工作流
description: Campaign和Dynamics集成工作流
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 51f07f08-5d57-4c4c-aff2-d03e5956ec6f
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---

# Campaign - Microsoft Dynamics 365集成工作流

的 **[!UICONTROL Workflows]** 页面列出了技术工作流及其状态。

集成应用程序附带三个工作流：

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365到Campaign**
* 发送 *联系人* 从Microsoft动力365到Adobe Campaign
* *自定义实体*:将自定义表从Microsoft Dynamics 365导入Adobe Campaign。 [了解详情](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* 这也称为 **入口** (指数据从Microsoft Dynamics 365进入Adobe Campaign)

**Campaign到Microsoft Dynamics 365**
* 来自Adobe Campaign Standard的电子邮件营销事件会发送到Dynamics 365（电子邮件发送、打开、单击、退回）。 [了解详情](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* 这也称为 **出口** (指数据从Adobe Campaign到Microsoft Dynamics 365的进度)

**选择启用/禁用**

选择退出状态(例如，阻止列表)可以从Microsoft Dynamics 365同步到Adobe Campaign，也可以从Adobe Campaign同步到Microsoft Dynamics 365。 数据也可以通过双向同步（即数据在两个方向上流动）。 [了解详情](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)。

>[!IMPORTANT]
>
>强烈建议您停止 **Microsoft Dynamics 365到Campaign** 工作流，然后再将更改发布到Adobe Campaign Standard或Microsoft Dynamics 365。 这些更改包括对集成当前正在使用的资源/实体（及其关联字段）、链接、标识符列等的更新。 如果不这样做，可能会导致数据丢失和/或工作流意外停止。

## 工作流积压

此集成应用程序首先读取数据，然后将数据写入目标。 的 **[!UICONTROL Backlog]** 列指示已排队并正在等待写入的记录数。 当您要处理大量数据时（例如，您首次运行集成，您重播数据等），此值应会增加。

>[!NOTE]
>如果您的Microsoft Dynamics 365和/或Campaign记录未更新，则应首先检查是否有大量记录正在等待写入目标。

## 工作流状态 {#workflow-status}

的 **[!UICONTROL Status]** 列指示与工作流关联的后台进程的状态。 可能的值包括：

* **正在运行**:该进程当前正在运行，您的数据应已同步。
* **已停止**:该进程当前未运行，因此您不应期望同步数据。
* **开始**:您已请求启动工作流进程。 应用程序尚未开始同步与此工作流关联的数据，但您可能预计会在几分钟后(此时将显示 **正在运行**)
* **失败**:工作流进程正在运行，但遇到错误，无法从这些进程中恢复。

## 可用操作

下面列出了可能的操作。

* **编辑**:单击铅笔图标会将您发送到另一个页面，以便您对工作流进行更新。 请记住，在停止工作流并重新启动该工作流之前，您所做的任何更改都不会生效。

* **开始**:“开始”按钮请求启动已停止的工作流。 仅当与工作流关联的进程当前停止时，才会显示此按钮。 流程将首先更改为“STARTING”，然后更改为“RUNNING”。 在工作流处于“正在运行”状态之前，与工作流关联的数据将不会开始同步。

   “开始”按钮是一个切换开关。 如果工作流进程已启动，则按钮将更改为 **停止** 按钮。

* **停止**:A **停止** 按钮请求停止正在运行的工作流。 仅当与工作流关联的进程当前运行时，才会显示此按钮。

编辑工作流时，在停止工作流并单击 **开始** 按钮。 然后，您的更新将纳入到运行的流程中(当流程返回到 **正在运行** 状态)。

向 **停止** 按钮以告知您何时(a)对工作流进行了更新，但(b)尚未停止/启动此工作流。

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)
