---
title: 事务型消息传递权限
description: 了解链接到事务事件的权限。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
hide: true
hidefromtoc: true
feature: Transactional Messaging
role: User
level: Intermediate
source-git-commit: d7e0912dd7d19a1f5dd2172235f28a40e130cac1
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 0%

---

# 事务型消息传递权限 {#transactional-message-permission}

目前，在Adobe Campaign Standard中，没有管理员安全组的用户无法访问、创建或发布事件，这会导致需要配置和发布事件但缺少管理员权限的业务用户出现问题。

我们对事务型消息传递访问控制实施了以下改进：

* 新 **[!UICONTROL Role]**，调用 **MC用户**，以允许非管理员用户管理事务事件。 的 **MC用户** 角色授予这些用户访问、创建、发布和取消发布事务型事件和消息的能力。

* 子投放现在设置为 **[!UICONTROL Organizational unit]** 创建消息模板的用户所属的安全组，而不是 **[!UICONTROL Organizational unit]** 的 **消息中心代理(mcExec)** 安全组。

* 默认 **消息中心执行(mcExec)** 收集事务性消息传递子投放的促销活动现在设置为组织单位 **全部** 允许所有用户查看子投放的报告。

要分配 **MC用户** 角色：

1. 新建 **[!UICONTROL Security group]** 或更新现有变量。 [了解详情](../../administration/using/managing-groups-and-users.md)。

1. 单击 **[!UICONTROL Create element]** 为安全组分配角色。

   ![](assets/event_access_1.png)

1. 选择MC用户 **[!UICONTROL Role]** 单击 **[!UICONTROL Confirm]**.

   >[!IMPORTANT]
   >
   > 在将MC用户角色分配给操作员时要谨慎地继续，因为这允许他们取消发布事件。

   ![](assets/event_access_2.png)

1. 配置完毕后，单击 **[!UICONTROL Save]**.

链接到此链接的用户 **[!UICONTROL Security group]** 现在可以访问、创建和发布事务型事件和消息。

下表概述了此功能对访问控制的影响：

| 对象 | 在此更改之前 | 此更改之后 |
|:-: | :--: | :-:|
| 消息中心执行(mcExec)营销活动 | **消息中心执行(mcExec)** 营销活动设置为 **消息中心代理(mcExec)** 安全组。 | **消息中心执行(mcExec)** 营销活动设置为组织单位 **全部** 以允许所有子投放与此营销活动关联。</br> 所有用户都将能够查看子投放的报告，但对投放内容仅具有只读访问权限。 |
| 子投放 | 子投放将设置为 **组织单位** 的 **消息中心代理(mcExec)** 安全组。 | 子投放将设置为 **组织单位** 创建消息模板的用户所属的安全组的。 |
| 消息模板 | 消息模板设置为 **组织单位** 的&#x200B;**消息中心代理(mcExec)** 安全组。 | 消息模板将设置为 **组织单位** 创建消息模板的用户所属的安全组的。 |
| 事务型事件 | 仅 **管理员** 安全组可以创建和发布事件。 | 的 **MC用户** 角色允许用户创建和发布事件。 |
| 事务型消息模板 | 事务型消息模板设置为组织单位 **全部**. | 交易消息模板将设置为 **组织单位** 创建消息模板的用户所属的安全组的。 |