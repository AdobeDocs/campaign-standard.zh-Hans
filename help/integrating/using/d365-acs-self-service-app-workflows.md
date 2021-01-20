---
title: 集成应用程序工作流
description: 活动和动态集成工作流
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: 6be7a20cde8fcaee73972b8919765ea631f2f1ee
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---


# 活动- Microsoft Dynamics 365集成工作流

**[!UICONTROL Workflows]**&#x200B;页面列表技术工作流及其状态。

该集成应用程序附带三个工作流:

![](assets/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365到活动**
* 将&#x200B;*联系人*&#x200B;从Microsoft Dynamics 365发送到Adobe Campaign
* *自定义实体*:将自定义表从Microsoft Dynamics 365引入Adobe Campaign。[了解详情](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* 这也称为&#x200B;**Ingress**(指数据从Microsoft Dynamics 365进入Adobe Campaign)

**活动到Microsoft Dynamics 365**
* 来自Adobe Campaign Standard的电子邮件营销事件会发送到Dynamics 365（电子邮件发送、打开、单击、弹出）。 [了解详情](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* 这也称为&#x200B;**Egress**(指Adobe Campaign到Microsoft Dynamics 365的数据输出)

**选择加入／退出**

退出状态（例如，）阻止列表可从Microsoft Dynamics 365同步到Adobe Campaign，或从Adobe Campaign同步到Microsoft Dynamics 365。 数据也可以通过双向同步（即数据双向流动）。 [了解详情](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)。

>[!IMPORTANT]
>
>强烈建议在发布对Adobe Campaign Standard或Microsoft Dynamics 365的更改之前，停止&#x200B;**从Microsoft Dynamics 365到活动**&#x200B;的工作流。 这些更改包括对当前由集成使用的资源／实体（及其关联字段）、链接、标识符列等的更新。 否则可能导致数据丢失和／或工作流意外停止。

## 工作流积压

此集成应用程序首先读取数据，然后将数据写入目标。 **[!UICONTROL Backlog]**&#x200B;列指示已排队并等待写入的记录数。 当您有大量要处理的数据时（例如，您是第一次运行集成，您正在重播数据等），此值应该会增大。

>[!NOTE]
>如果您的Microsoft Dynamics 365和／或活动记录未更新，您应首先检查是否有大量记录等待写入目标。


## 工作流状态{#workflow-status}

**[!UICONTROL Status]**&#x200B;列指示与工作流关联的后台进程的状态。 可能的值有：

* **正在运行**:该进程当前正在运行，您的数据应当已同步。
* **已停止**:该进程当前未运行，因此您不应期望您的数据应同步。
* **开始**:您已请求工作流进程开始。应用程序尚未开始同步与此工作流关联的数据，但您可能希望它在几分钟后（当它稍后将显示&#x200B;**RUNNING**&#x200B;的状态）
* **失败**:工作流进程正在运行，但遇到错误，无法从这些进程恢复。

## 可用操作

以下列出了可能的操作。

* **编辑**:单击铅笔图标将发送到另一个允许您更新工作流的页面。请记住，您所做的任何更改只有在停止工作流并重新启动后才会生效。

* **开始**:开始按钮请求启动已停止的工作流。此按钮仅在与工作流关联的进程当前停止时显示。 进程将首先更改为“开始”，然后更改为“正在运行”。 在工作流处于“RUNNING”状态之前，与工作流关联的开始不会同步。

   开始按钮是一个切换按钮。 如果工作流进程已启动，则按钮将变为&#x200B;**停止**&#x200B;按钮。

* **停止**:“停 **** 止”按钮请求停止正在运行的工作流。此按钮仅在与工作流关联的进程当前正在运行时显示。

编辑工作流时，在您停止工作流并单击&#x200B;**开始**&#x200B;按钮之前，更新不会立即并入正在运行的进程的规则中。 然后，您的更新被并入正在运行的进程中（一旦进程返回&#x200B;**RUNNING**&#x200B;状态）。

在&#x200B;**停止**&#x200B;按钮中添加警告指示，以告知您何时(a)对工作流进行了更新，但(b)尚未对此工作流执行停止/开始。

![](assets/d365-to-acs-icon-stop-with-changes.png)
