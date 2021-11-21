---
title: 导出列表
description: 'Adobe Campaign允许您将概述屏幕中显示为列表的数据直接导出到文件中，以供将来使用。 '
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: b39ce1f6-0c5b-4270-86a1-b79c49cd199c
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 6%

---

# 导出列表{#exporting-lists}

Adobe Campaign允许您直接在文件中导出列表供将来使用。 在文件中导出列表时，会在 **[!UICONTROL Export audits]** 菜单。 有关导出审核的更多信息，请参阅[审核导出](../../administration/using/auditing-export-logs.md)一节。

![](assets/do-not-localize/how-to-video.png) [了解如何在视频中配置列表](#video)

默认情况下，导出列表选项允许导出最多100,000行，具体行数由 **Nms_ExportListLimit** 选项。 功能管理员可在 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** 菜单。

在具有 **列表** 模式视图，对于具有 **[!UICONTROL EXPORT (export)]** 角色。

1. 转到您选择的 **列表** 屏幕。 例如，测试用户档案概述屏幕( **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]** )。
1. 检查屏幕是否位于 **列表** 模式。

   ![](assets/export_list_mode_switch.png)

1. 按照要使用导出列表中的列的顺序，组织列表中的列 **[!UICONTROL Configure list]** 按钮。 除了配置的列之外，资源的主键也将导出。
1. 如果需要，可以应用过滤器。 为此，请单击左上角的按钮以显示搜索窗格。

   如果从包含不同资源的列表进行导出，则必须应用过滤器，以便列表中仅显示一种类型的资源。

1. 如果需要，请对所选列进行排序。
1. 选择导出按钮 ![](assets/exportlistbutton.png).

   将显示一个弹出窗口以确认导出。 确认导出后，文件将自动下载到您的计算机。

文件以CSV格式生成，扩展名为.TXT。 它将根据导出的资源和导出日期命名。 例如：名称profileBase_20150426_120253.txt将应用于2015年4月26日12时执行的配置文件导出:02:53. 它采用UTF-8格式进行编码。

数值和日期考虑执行导出的用户的本地时间（区域设置）。 例如：DD-MM-YYYY或MM-DD-YYYY。

要执行大于此范围的导出，您必须创建专用工作流。 请参阅 [提取文件](../../automating/using/extract-file.md) 中。

**示例**

以下示例是从下面定义的用户档案列表中执行的导出：

* 显示的列（按顺序）：姓氏、名字、出生日期、电子邮件地址。
* 名称按字母顺序排序。

![](assets/export_list_example1.png)

生成的文件如下（对于前十条记录）：

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

以下视频演示了如何配置列表。

>[!VIDEO](https://video.tv.adobe.com/v/25288/?quality=12)

提供了其他Campaign Standard操作方法视频 [此处](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hans).
