---
title: 导出/导入自定义资源
description: 本教程介绍如何导出和导入自定义资源包。
audience: automating
content-type: reference
topic-tags: data-management-activities
feature: Workflows
role: Data Architect
level: Experienced
exl-id: f8e7eb96-9541-4d28-9d8d-f06af822debd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 100%

---

# 导出/导入自定义资源 {#exporting-importing-custom-resources}

本教程介绍如何将自定义资源包从开发环境导出并导入到制作环境。

此示例针对链接到 Adobe Campaign 的功能管理员。

先决条件包括：

* **一个或多个可用且已发布的自定义资源**。

  此外，您必须为这些资源定义具有唯一性的密钥，因为不会导出资源包中的自动主密钥。因此，该资源可以具有主密钥和附加唯一密钥，以保证记录的唯一性。
* **创建和导出资源包**&#x200B;所需的权限。

其他资源：

* [管理资源包](../../automating/using/managing-packages.md)
* [部署资源包：工作原理](../../developing/using/data-model-concepts.md)
* [添加或扩展资源](../../developing/using/key-steps-to-add-a-resource.md)

## 导出结构 {#exporting-the-structure}

在本节中，我们将执行第一个资源包导出，该资源包中详细介绍了自定义资源数据的物理结构。

此示例包含两个自定义资源：**Products** 和 **Orders**。

1. 转到 **[!UICONTROL Administration]** / **[!UICONTROL Deployment]** / **[!UICONTROL Package exports]** 菜单。

   我们将创建新的资源包，以导出使用两个自定义资源“Products”和“Orders”进行了筛选的 **[!UICONTROL Custom resource (cusResource)]**。

1. 在 **[!UICONTROL Package exports]** 页面中，单击 **[!UICONTROL Create]** 以创建新资源包。
1. 填写标签，然后单击 **[!UICONTROL Create element]**。

   ![](assets/cusresources_export1.png)

1. 搜索并选择 **[!UICONTROL Custom resource (cusResource)]**。

   ![](assets/cusresources_export2.png)

1. 在筛选条件中选择 **Products** 和 **Orders** 这两个资源，以配置 **[!UICONTROL Custom resource]** 的详细信息。

   确保更改逻辑运算符。必须将该值设置为 **OR**，以便将产品资源和订单资源的结构集成到资源包中。

   ![](assets/cusresources_export3.png)

1. 确认并保存资源包定义。

您现在可以单击 **[!UICONTROL Start export]**。

![](assets/cusresources_export4.png)

生成的资源包位于“Downloads”文件夹中。Zip 文件的名称是随机生成的。您可以为其重新命名。

## 导出数据 {#exporting-the-data}

通过第二次导出，可导出 **Products** 和 **Orders** 自定义资源的数据。

根据与结构导出相同的导出类型，您将创建另一个包含数据的资源包。

1. 在 **[!UICONTROL Package exports]** 页面中，单击 **[!UICONTROL Create]** 以创建新资源包。
1. 使用 **[!UICONTROL Export data of my resources]** 填写标签，然后单击 **[!UICONTROL Export content]** 选项卡中的 **[!UICONTROL Create element]**。
1. 搜索并选择 **Products** 资源。

   ![](assets/cusresources_exportdata1.png)

1. 将高级&#x200B;**筛选条件**&#x200B;配置为 **@Label IS NOT NULL**。

   ![](assets/cusresources_exportdata2.png)

1. 查看计数。

   ![](assets/cusresources_exportdata3.png)

1. 对 **Orders** 自定义资源重复相同的操作。

   ![](assets/cusresources_exportdata4.png)

1. 确认并保存资源包定义。

您现在可以单击 **[!UICONTROL Start export]**。

![](assets/cusresources_exportdata5.png)

生成的资源包位于“Downloads”文件夹中。Zip 文件的名称是随机生成的。您可以为其重新命名。

## 导入结构 {#importing-the-structure}

### 导入资源包 {#importing-the-structure-package}

1. 连接到要导入新创建资源包的&#x200B;**目标实例**。
1. 转到 **[!UICONTROL Administration]** / **[!UICONTROL Deployment]** / **[!UICONTROL Package imports]** 菜单，创建新资源包以导入来自第一次导出的文件。
1. 将&#x200B;**结构文件**&#x200B;拖放到为此目的而提供的区域中。可接受的格式为 ZIP 或 XML。

   ![](assets/cusresources_import2.png)

1. 修改标签，例如 **Import structure**，然后单击 **[!UICONTROL Save]**。
1. 单击 **[!UICONTROL Start import]**。

   ![](assets/cusresources_import3.png)

### 发布 {#publish-structure}

1. 转到 **[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Publication]** 菜单。
1. 单击 **[!UICONTROL Prepare publication]**，然后单击 **[!UICONTROL Publish]** 以使用来自新自定义资源的数据更新实例。
1. 对应于所安装资源包的菜单项，将插入到 **[!UICONTROL Client data]** 菜单中。

   ![](assets/cusresources_import1.png)

## 导入数据 {#importing-the-data}

在本节中，我们将&#x200B;**导入数据**，这些数据会链接到上一步中安装到实例上的资源包。

与上一步相同，此步骤分为两个部分：导入资源包和发布。

### 导入资源包 {#importing-the-data-package}

1. 转到 **[!UICONTROL Administration]** / **[!UICONTROL Deployment]** / **[!UICONTROL Package imports]** 菜单，创建新资源包以导入包含数据的文件。
1. 将数据文件拖放到为此目的而提供的区域中。可接受的格式为 ZIP 或 XML。
1. 修改标签，例如“Import data”，然后单击 **[!UICONTROL Save]**。
1. 单击 **[!UICONTROL Start import]**。

   ![](assets/cusresources_importdata.png)

### 发布 {#publish-data}

1. 转到 **[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Publication]** 菜单。
1. 单击 **[!UICONTROL Prepare publication]**，然后单击 **[!UICONTROL Publish]** 以使用来自自定义资源的数据更新实例。
