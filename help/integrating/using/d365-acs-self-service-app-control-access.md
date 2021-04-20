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
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 0%

---


# 访问Adobe Campaign Standard与Microsoft Dynamics 365自助服务应用程序的集成

此配置将要求您与组织的Experience Cloud(EC)管理员合作。 这些是授予您访问自助服务集成应用程序界面所需的初始步骤。 访问该工具后，您将设置与数据的连接并配置Adobe Campaign与Microsoft Dynamics 365之间的数据流。

>[!NOTE]
>
>您需要联系Adobe代表并提供Adobe Campaign Standard组织和实例名称。 将记录一个票证以请求为您的组织启用集成应用程序。

## 添加产品用户档案

在本节中，您将学习如何授予对Adobe Campaign Standard与Microsoft Dynamics 365自助应用程序集成的访问权限。 对您在Adobe Experience Cloud中的组织具有访问权限的用户将无权访问集成自助应用程序，除非您按照以下步骤授予他们访问权限。

>[!IMPORTANT]
>
> 这些步骤要求在您的组织的Experience Cloud中具有&#x200B;**管理员**&#x200B;角色。


1. 浏览到https://experience.adobe.com/并登录Adobe Experience Cloud。
1. 访问&#x200B;**Admin Console**。

   ![](assets/do-not-localize/d365-to-acs-access-3.png)

1. 单击&#x200B;**[!UICONTROL Products]**&#x200B;访问您的Experience Cloud解决方案。

   ![](assets/do-not-localize/d365-to-acs-access-6.png)


   >[!IMPORTANT]
   >
   >本节中的其余步骤将针对您的每个活动实例（开发、文本、生产）执行。

1. 单击要配置的第一个实例。

   ![](assets/do-not-localize/d365-to-acs-access-6.png)

   实例页面应类似于：

   ![](assets/do-not-localize/d365-to-acs-access-8.png)

1. 单击&#x200B;**[!UICONTROL New Profile]**&#x200B;按钮并添加一个名为：**Campaign Standard- your-prod-instance-name - D365/ACS Integration**

   * 如果您在列表中看到此条目，则无需继续。 单击左侧菜单中的&#x200B;**Adobe Campaign Standard**&#x200B;并检查其他活动实例。

   * 确保将“your-prod-instance-name”替换为实例的实际名称。

1. 您可以将&#x200B;**[!UICONTROL Permission Group]**&#x200B;下拉列表保留为默认值。

1. 如果条目类似于以下内容，则单击&#x200B;**[!UICONTROL Done]**&#x200B;按钮。

   ![](assets/do-not-localize/d365-to-acs-access-14.png)

   新产品用户档案已添加。

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

## 授予用户{#add-users-to-profile}访问权限

在&#x200B;**[!UICONTROL Products]**&#x200B;页面中，选择您的活动实例，然后执行以下步骤：

1. 单击您之前创建的新用户档案: **Campaign Standard- your-prod-instance-name - D365/ACS Integration**

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

1. 单击&#x200B;**[!UICONTROL Developers]**&#x200B;选项卡。

   ![](assets/do-not-localize/d365-to-acs-access-18.png)

1. 单击&#x200B;**[!UICONTROL Add Developer]**&#x200B;按钮

1. 输入要添加的用户的姓名或电子邮件地址。  选择与用户匹配的结果。

   如果这是用户首次添加到组织，请输入详细信息。

1. 单击&#x200B;**[!UICONTROL Save]**&#x200B;进行确认。
