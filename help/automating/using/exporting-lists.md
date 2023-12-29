---
title: 导出列表
description: Adobe Campaign允许您直接从概述屏幕中将显示为列表的数据导出到文件中，以供将来使用。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: b39ce1f6-0c5b-4270-86a1-b79c49cd199c
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 5%

---

# 导出列表{#exporting-lists}

Adobe Campaign允许您直接将列表导出到文件中以供将来使用。 导出文件中的列表会在中生成日志条目 **[!UICONTROL Export audits]** 菜单。 有关导出审核的更多信息，请参阅[审核导出](../../administration/using/auditing-export-logs.md)一节。

![](assets/do-not-localize/how-to-video.png) [了解如何在视频中配置列表](#video)

默认情况下，导出列表选项允许导出最多100,000行，具体行数由 **Nms_ExportListLimit** 选项。 功能管理员可通过 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** 菜单。

导出列表适用于所有具有 **列表** 模式视图，适用于具有下列参数的用户： **[!UICONTROL EXPORT (export)]** 角色。

1. 转到您选择的 **列表** 屏幕。 例如，测试用户档案概述屏幕( **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]** )。
1. 检查屏幕是否位于 **列表** 模式。

   ![](assets/export_list_mode_switch.png)

1. 使用按您想要导出的顺序组织列表中的列 **[!UICONTROL Configure list]** 按钮，在右上角。 除了已配置的列之外，还将导出资源的主键。
1. 如果需要，可以应用过滤器。 为此，请单击左上角的按钮以显示搜索窗格。

   如果从包含不同资源的列表执行导出，则必须应用过滤器，以便列表中只显示一种类型的资源。

1. 如果您愿意，可以对您选择的列进行排序。
1. 选择导出按钮 ![](assets/exportlistbutton.png).

   此时将显示一个弹出窗口，用于确认导出。 确认导出后，文件将自动下载到您的计算机。

该文件以CSV格式生成，扩展名为.TXT。 根据导出的资源和导出日期进行命名。 例如：名称profileBase_20150426_120253.txt将应用于2015年4月26日12点执行的配置文件导出:02:53. 它采用UTF-8格式编码。

数值和日期会考虑执行导出的用户的本地时间（区域设置）。 例如：DD-MM-YYYY或MM-DD-YYYY。

要执行大于此值的导出，您必须创建一个专用工作流。 请参阅 [提取文件](../../automating/using/extract-file.md) 部分。

**示例**

以下示例是从下面定义的配置文件列表中执行的导出：

* 显示的列（按顺序）：姓氏、名字、出生日期、电子邮件地址。
* 名称按字母顺序排序。

![](assets/export_list_example1.png)

生成的文件（对于前10条记录）如下所示：

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

## 教程视频 {#video}

本视频说明如何配置列表。

>[!VIDEO](https://video.tv.adobe.com/v/25288/?quality=12)

提供了其他Campaign Standard操作方法视频 [此处](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hans).
