---
title: 集成应用程序工作流
description: Campaign和Dynamics集成工作流
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 51f07f08-5d57-4c4c-aff2-d03e5956ec6f
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 0%

---

# Campaign - Microsoft Dynamics 365集成工作流

**[!UICONTROL Workflows]**&#x200B;页面列出了技术工作流及其状态。

集成应用程序附带三个工作流：

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365至Campaign**
* 将&#x200B;*联系人*&#x200B;从Microsoft Dynamics 365发送到Adobe Campaign
* *自定义实体*：将自定义表从Microsoft Dynamics 365引入Adobe Campaign。 [了解详情](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* 这也称为&#x200B;**入口**(指从Microsoft Dynamics 365到Adobe Campaign的数据入口)

**营销活动到Microsoft Dynamics 365**
* Adobe Campaign Standard中的电子邮件营销事件会发送到Dynamics 365（电子邮件发送、打开、单击、退回）。 [了解详情](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* 这也称为&#x200B;**出口**(指数据从Adobe Campaign到Microsoft Dynamics 365的出口)

**选择加入/退出**

选择退出状态(例如，阻止列表)可以从Microsoft Dynamics 365同步到Adobe Campaign，也可以从Adobe Campaign同步到Microsoft Dynamics 365。 数据也可以双向同步（即数据双向流动）。 [了解详情](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)。

>[!IMPORTANT]
>
>强烈建议您在将更改发布到Microsoft Dynamics或Microsoft Dynamics 365之前停止&#x200B;**Adobe Campaign Standard 365到Campaign**&#x200B;工作流程。 这些更改包括对集成当前使用的资源/实体（及其关联字段）、链接、标识符列等的更新。 否则，可能会导致数据丢失和/或工作流意外停止。

## 工作流积压

此集成应用程序首先读取数据，然后将数据写入目标。 **[!UICONTROL Backlog]**&#x200B;列指示已排队并等待写入的记录数。 当您需要处理大量数据（例如，您是首次运行集成、正在重放数据等）时，此值预计会增加。

>[!NOTE]
>如果您的Microsoft Dynamics 365和/或Campaign记录未更新，则应首先检查是否有大量记录等待写入目标。
>

## 工作流状态 {#workflow-status}

**[!UICONTROL Status]**&#x200B;列指示与工作流关联的后台进程的状态。 可能的值包括：

* **正在运行**：进程当前正在运行，您的数据应同步。
* **已停止**：进程当前未运行，因此不应期望同步数据。
* **正在启动**：您已请求启动工作流进程。 应用程序尚未开始同步与此工作流关联的数据，但您可以预期它将在几分钟后同步（此时将显示&#x200B;**正在运行**&#x200B;的状态）
* **失败**：工作流进程正在运行，但遇到了错误，无法从这些错误中恢复。

## 可用操作

下面列出了可能的操作。

* **编辑**：单击铅笔图标会将您发送到另一个页面，该页面允许您更新工作流。 请记住，您所做的任何更改只有在停止工作流并重新启动它之后才会生效。

* **启动**：“启动”按钮请求启动已停止的工作流。 仅当与工作流关联的进程当前停止时，此按钮才会显示。 进程将首先更改为“STARTING”，然后更改为“RUNNING”。 在工作流处于“正在运行”状态之前，与工作流关联的数据不会开始同步。

  “开始”按钮是切换按钮。 如果工作流进程已经启动，则该按钮将更改为&#x200B;**停止**&#x200B;按钮。

* **停止**： **停止**&#x200B;按钮请求停止正在运行的工作流。 仅当与工作流关联的进程当前正在运行时，此按钮才会出现。

在编辑工作流时，不会将更新立即合并到正在运行的进程的规则中，除非停止该工作流，然后单击“**开始**”按钮。 然后，您的更新将合并到正在运行的进程中（一旦该进程返回到&#x200B;**RUNNING**&#x200B;状态）。

**停止**&#x200B;按钮中添加了警告指示，以告知您(a)已更新工作流，但(b)尚未完成此工作流的停止/启动。

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)
