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
exl-id: 995da330-6c86-444b-86b2-61d887f37db4
source-git-commit: 8e6465e8334ea621b353b0a908e231b9093c58ce
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 0%

---

# 事务性事件改进 {#transactional-event-improvements}

>[!AVAILABILITY]
>
>这些功能当前仅适用于一组组织（有限可用性）。 有关更多信息，请联系您的Adobe代表。

目前，在Adobe Campaign Standard中，没有管理员安全组的用户无法访问、创建或发布事务事件，这会导致需要配置和发布事件但缺少管理员权限的业务用户出现问题。 此外，无法复制事务事件。

我们对事务型消息传递访问控制实施了以下改进：

* 新 **[!UICONTROL Role]**，调用 **MC用户**，以允许非管理员用户管理事务事件配置。 的 **MC用户** 角色授予这些用户访问、创建、发布和取消发布事务型事件和消息的能力。

* 执行投放（即每次编辑并再次发布事务型消息时创建的技术消息，或默认每月一次）现在设置为 **[!UICONTROL Organizational unit]** 创建事件的用户所属的安全组，而不是 **[!UICONTROL Organizational unit]** 的 **消息中心代理(mcExec)** 安全组。

* **管理员** 现在可以复制已发布的事务型事件以及具有 **MC用户** 角色，前提是它们位于相同的 **组织单位** 层级作为创建事件的用户。

## 分配MC用户角色 {#assign-role}

要分配 **MC用户** 对安全组的角色：

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

## 分配MC用户安全组 {#assign-group}

1. 在Admin Console中，选择 **产品** 选项卡。

1. 选择 **Adobe Campaign Standard** 然后选择您的实例。

1. 从 **产品配置文件** 列表，选择 **MC用户** 群组。

1. 单击 **添加用户** 并输入要添加到此产品配置文件的配置文件的名称、用户组或电子邮件地址。

1. 添加后，单击 **保存**.

添加到此的用户 **[!UICONTROL Security group]** 现在可以访问、创建和发布事务型事件和消息。

## 重复事务事件 {#duplicate-transactional-events}

具有 **管理员** 安全组<!--([Functional administrators](../../administration/using/users-management.md#functional-administrators)?)--> 现在，如果事件已 **发布**.

此外，非管理员用户 **MC用户** 角色现在可以访问事件配置，但其复制权限由 **组织单位** 他们属于。 如果当前用户和创建事件的用户属于同一组织单位层次结构，则允许复制。

例如，如果属于“法国销售”组织单位的用户创建事件配置：

* 组织单位为“Paris Sales”的另一用户将能够复制此事件，因为“Paris Sales”是“France Sales”组织单位的一部分。

* 但是，组织单位为“旧金山销售”的用户将无法这样做，因为“旧金山销售”位于“美国销售”组织单位下，该组织单位与“法国销售”组织单位分开。

要复制事件配置，请执行以下步骤。

1. 单击 **Adobe** 徽标，然后选择 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.

1. 将鼠标悬停在所选的已发布事件配置上，然后选择 **[!UICONTROL Duplicate element]** 按钮。

   ![](assets/message-center_duplicate-button.png)

   >[!CAUTION]
   >
   >您无法复制未发布的事件配置。 [了解详情](publishing-transactional-event.md)

1. 此时会自动显示重复的事件。 它包含的配置与您为原始事件定义的配置相同，但具有 **[!UICONTROL Draft]** 状态。

   ![](assets/message-center_duplicated-draft-event.png)

1. 将自动创建相应的事务型消息。 要访问它，请转到 **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_duplicated-message.png)

1. 打开新复制的消息。 它包含您为原始消息定义的相同设计，但具有 **[!UICONTROL Draft]** 状态，即使原始事务型消息已发布也是如此。

   ![](assets/message-center_duplicated-draft-message.png)

1. 您现在可以编辑和个性化此消息。 请参阅 [编辑事务型消息](../../channels/using/editing-transactional-message.md).

## 影响 {#impacts}

下表概述了这些改进的影响：

| 对象 | 在此更改之前 | 此更改之后 |
|:-: | :--: | :-:|
| 事务型事件 | 仅 **管理员** 安全组可以创建和发布事件。 | 的 **MC用户** 角色允许用户创建和发布事件。 |
| 事务型消息 | 事务型消息设置为 **组织单位** 的 **消息中心代理(mcExec)** 安全组。 | 事务型消息设置为 **组织单位** 创建事务性事件/消息的用户所属的安全组的。 |
| 执行投放 | 执行投放设置为 **组织单位** 的 **消息中心代理(mcExec)** 安全组。 | 执行投放设置为 **组织单位** 创建事务性事件/消息的用户所属的安全组的。 |
| 已发布的事务型事件 | 任何用户都无法进行复制。 | <ul><li>具有 **管理员** 安全组可以复制已发布的事件。</li> <li>具有 **MC用户** 角色可以复制已发布的事件，前提是它们位于相同的 **组织单位** 层级作为创建事件的用户。</li></ul> |


<!--Transactional Message Templates| Transactional Message templates are set to the Organizational unit **All**. | Transaction Message Template will be set to the **Organizational unit** of the security group to which the user creating the message template belongs.-->