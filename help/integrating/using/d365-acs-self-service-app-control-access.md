---
title: 访问Adobe Campaign Standard与Dynamics 365自助服务应用程序的集成
description: Adobe Campaign Standard与Dynamics 365自助服务应用程序集成
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 44b59f56-99be-41ae-af8d-76272bb94d18
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 0%

---

# 访问Adobe Campaign Standard与Microsoft Dynamics 365自助服务应用程序的集成

此配置将要求您与Experience Cloud(EC)管理员一起为您的组织工作。 这些是授予您访问自助服务集成应用程序界面所需的初始步骤。 访问该工具后，您将设置与数据的连接，并配置Adobe Campaign和Microsoft Dynamics 365之间的数据流。

>[!NOTE]
>
>您需要联系Adobe代表并提供Adobe Campaign Standard组织和实例名称。 系统将记录一个票证，以请求为您的组织启用集成应用程序。

## 添加产品配置文件

在此部分中，您将了解如何授予对Adobe Campaign Standard与Microsoft Dynamics 365自助服务应用程序集成的访问权限。 对您在Adobe Experience Cloud中的组织拥有访问权限的用户将无权访问集成自助服务应用程序，除非您按照以下步骤授予他们访问权限。

>[!IMPORTANT]
>
> 这些步骤需要 **管理员** 角色。

1. 浏览https://experience.adobe.com/并登录Adobe Experience Cloud。
1. 访问 **Admin Console**.

   ![](assets/do-not-localize/d365-to-acs-access-3.png)

1. 单击 **[!UICONTROL Products]** 以访问您的Experience Cloud解决方案。

   ![](assets/do-not-localize/d365-to-acs-access-6.png)


   >[!IMPORTANT]
   >
   >此部分中的其余步骤将针对您的每个Campaign实例（开发、文本、生产）执行。

1. 单击要配置的第一个实例。

   ![](assets/do-not-localize/d365-to-acs-access-6.png)

   实例页面应如下所示：

   ![](assets/do-not-localize/d365-to-acs-access-8.png)

1. 单击 **[!UICONTROL New Profile]** 按钮，并添加新条目，名为： **Campaign Standard- your-prod-instance-name - D365/ACS集成**

   * 如果您在列表中看到此条目，则无需继续。 单击 **Adobe Campaign Standard** ，并检查其他Campaign实例。

   * 确保将“your-prod-instance-name”替换为实例的实际名称。

1. 您可以离开 **[!UICONTROL Permission Group]** 默认值的下拉列表。

1. 如果您的条目类似于以下内容，请单击 **[!UICONTROL Done]** 按钮。

   ![](assets/do-not-localize/d365-to-acs-access-14.png)

   已添加新产品配置文件。

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

## 授予用户访问权限 {#add-users-to-profile}

从 **[!UICONTROL Products]**  页面，选择您的Campaign实例并按照以下步骤操作：

1. 单击您之前创建的新配置文件：  **Campaign Standard- your-prod-instance-name - D365/ACS集成**

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

1. 单击 **[!UICONTROL Developers]** 选项卡。

   ![](assets/do-not-localize/d365-to-acs-access-18.png)

1. 单击 **[!UICONTROL Add Developer]** 按钮

1. 输入要添加的用户的名称或电子邮件地址。  选择与用户匹配的结果。

   如果这是用户首次添加到组织，请输入详细信息。

1. 单击 **[!UICONTROL Save]** 确认。
