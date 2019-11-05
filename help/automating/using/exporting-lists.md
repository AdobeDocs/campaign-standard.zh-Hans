---
title: 导出列表
description: 'Adobe Campaign允许您直接将概览屏幕中显示为列表的数据导出到文件中以供将来使用。 '
page-status-flag: 从未激活
uuid: c64fe706-bd6e-4746-958e-f94226f4e2cb
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 导入和导出数据
discoiquuid: 12c874da-435f-44b6-a3c8-873301e177cc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 导出列表{#exporting-lists}

Adobe Campaign允许您直接将列表导出到文件中以供将来使用。 导出文件中的列表会在菜单中生成日志 **[!UICONTROL Export audits]** 条目。 有关导出审核的详细信息，请参阅“审核 [导出](../../administration/using/auditing-export-logs.md) ”一节。

导出列表选项默认允许导出最多100,000行，并由 **Nms_ExportListLimit选项定义** 。 此选项可由功能管理员在&gt; **[!UICONTROL Administration]****[!UICONTROL Application settings]** &gt;菜单 **[!UICONTROL Options]** 下管理。

对于具有该角色的用户，导出列表在具有“列 **表** ”模式视图的所有屏幕中都 **[!UICONTROL EXPORT (export)]** 可用。

1. 转到您选择的“列 **表** ”屏幕。 例如，测试配置文件概述屏幕( **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Test profiles]** )。
1. 检查屏幕是否处于“列 **表** ”模式。

   ![](assets/export_list_mode_switch.png)

1. 按您希望使用右上角的按钮导出列表中的列的 **[!UICONTROL Configure list]** 顺序组织列。 除了配置的列外，还将导出资源的主键。
1. 如果您喜欢，可以应用过滤器。 为此，请单击左上角的按钮以显示搜索窗格。

   如果从包含不同资源的列表中进行导出，则必须应用筛选器，以便列表中只显示一种类型的资源。

1. 如果您喜欢，请对所选列进行排序。
1. 选择导出按钮 ![](assets/exportlistbutton.png)。

   此时将显示一个用于确认导出的弹出窗口。 确认导出后，文件会自动下载到您的计算机。

文件以CSV格式生成，除非导出在iOS中执行，在这种情况下，生成的文件采用TXT格式。 它根据导出的资源和导出日期命名。 例如：name profileBase_20150426_120253.csv将应用于2015年4月26日12:02:53进行的配置文件导出。 它采用UTF-8格式进行编码。

数字值和日期考虑执行导出的用户的本地时间（区域设置）。 例如：DD-MM-YYYY或MM-DD-YYYY。

要执行大于此值的导出，您必须创建专用工作流。 请参阅“解 [压文件](../../automating/using/extract-file.md) ”部分。

**示例**

以下示例是从以下定义的配置文件列表中执行的导出：

* 显示列（按顺序）:姓、名、出生日期、电子邮件地址。
* 名称按字母顺序排序。

![](assets/export_list_example1.png)

生成的文件如下（前十条记录）所示：

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
* [配置列表视频](https://helpx.adobe.com/campaign/kt/acs/using/acs-configuring-a-list-feature-video-setup.html)

