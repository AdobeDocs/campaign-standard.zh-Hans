---
solution: Campaign Standard
product: campaign
title: 导出列表
description: 'Adobe Campaign允许您直接从概述屏幕中导出列表显示的数据，以供将来使用。 '
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
translation-type: tm+mt
source-git-commit: 2a92600df01fd3c78a2b35c8034a2ce347e5c1d8
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 6%

---


# 导出列表{#exporting-lists}

Adobe Campaign允许您直接在文件中导出列表以供将来使用。 在文件中导出列表会在&#x200B;**[!UICONTROL Export audits]**&#x200B;菜单中生成日志条目。 有关导出审核的更多信息，请参阅[审核导出](../../administration/using/auditing-export-logs.md)一节。

![](assets/do-not-localize/how-to-video.png) [了解如何在视频中配置列表](#video)

导出列表选项默认允许导出最多100,000行，并由&#x200B;**Nms_ExportListLimit**&#x200B;选项定义。 此选项可由功能管理员管理，位于&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**&#x200B;菜单下。

对于具有&#x200B;**[!UICONTROL EXPORT (export)]**&#x200B;角色的用户，导出列表在具有&#x200B;**列表**&#x200B;模式视图的所有屏幕中都可用。

1. 转到您选择的&#x200B;**列表**&#x200B;屏幕。 例如，测试用户档案概述屏幕(**[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**)。
1. 检查屏幕是否处于&#x200B;**列表**&#x200B;模式。

   ![](assets/export_list_mode_switch.png)

1. 使用右上角的&#x200B;**[!UICONTROL Configure list]**&#x200B;按钮按要导出的顺序在列表中组织列。 除配置的列外，还将导出资源的主键。
1. 如果您喜欢，可以应用过滤器。 为此，请单击左上角的按钮以显示搜索窗格。

   如果从包含不同资源的列表进行导出，则必须应用过滤器，以便在列表中仅显示一种类型的资源。

1. 如果您喜欢，请对所选列进行排序。
1. 选择导出按钮![](assets/exportlistbutton.png)。

   将出现一个弹出窗口来确认导出。 确认导出后，文件会自动下载到您的计算机。

文件以CSV格式生成，扩展名为。TXT。 它根据导出的资源和导出日期命名。 例如：名称profileBase_20150426_120253.txt将应用于2015年4月26日12:02:53进行的用户档案导出。 它采用UTF-8格式进行编码。

数字值和日期会考虑执行导出的用户的本地时间（区域设置）。 例如：DD-MM-YYYY或MM-DD-YYYY。

要执行大于此值的导出，您必须创建专用工作流。 请参阅[Extract file](../../automating/using/extract-file.md)部分。

**示例**

以下示例是从以下定义的用户档案列表执行的导出：

* 显示的列（按顺序）:姓氏、名字、出生日期、电子邮件地址。
* 名称按字母顺序排序。

![](assets/export_list_example1.png)

生成的文件如下所示（对于前十条记录）:

```
Last name;First name;Birth date;Email;Zip code
Abalo;Patrick;11/11/1941 02:00:00;patrick.a@testmail.com;29200
Abasq;Joel;21/08/1977 02:00:00;abasq.joel@testmail.com;92160
Abernot;John;12/07/1963 01:00:00;john.abernot@testmail.com;78510
Abiven;Christian;16/03/1975 01:00:00;chris.a@mailtest.com;35000
Abouvier;Peter;02/07/1975 01:00:00;pabouvier@mailtest.com;94560
Accardi;Mike;22/06/1948 01:00:00;mike.accardi@mail.com;76400
Accremont;Frank;27/04/1947 01:00:00;accr.frank@mailtest.com;13500
Adam;Daniel;17/09/1953 01:00:00;danieladam@mail.com;17000
Adama;Pascal;22/01/1990 01:00:00;adapascal@mailtest.com;75012
Adama;Henry;22/09/1992 02:00:00;henry.adama@mail.com;64120
```

**相关主题：**

* [角色](../../administration/using/list-of-roles.md)
* [自定义列表](../../start/using/customizing-lists.md)

## 教程视频{#video}

此视频演示如何配置列表。

>[!VIDEO](https://video.tv.adobe.com/v/25288/?quality=12)

此处[提供其他Campaign Standard操作方法视频。](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hans)
