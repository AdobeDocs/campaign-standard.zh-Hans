---
title: 导出列表
seo-title: 导出列表
description: 导出列表
seo-description: 'Adobe Campaign允许您将数据显示为概览屏幕中直接显示的列表，供将来使用。 '
page-status-flag: 从未激活
uuid: c64fe706-bd6 e-4746-958e-f97226 f4 e2 cb
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 导入和导出数据
discoiquuid: 12c874da-435f-44b6-a3 c8-873301e177 cc
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Exporting lists{#exporting-lists}

Adobe Campaign允许您将列表直接导出到文件中供将来使用。Exporting a list in a file generates a log entry in the **[!UICONTROL Export audits]** menu. For more information on export audits, refer to the [Auditing exports](../../administration/using/auditing-export-logs.md) section.

The export list option allows you to export a maximum of 100,000 lines by default and defined by the **Nms_ExportListLimit** option. This option can be managed by the functional administrator, under the **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]** menu.

Export list is available in all the screens that have a **List** mode view, for users with the **[!UICONTROL EXPORT (export)]** role.

1. Go to your chosen **List** screen. For example, the test profile overview screen ( **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Test profiles]** ).
1. Check that the screen is in **List** mode.

   ![](assets/export_list_mode_switch.png)

1. Organize the columns in the list in the order that you want to export them using the **[!UICONTROL Configure list]** button, in the top right corner. 除了配置的列之外，资源的主要键也将导出。
1. 如果您喜欢，可以应用过滤器。为此，单击左上角的按钮以显示搜索窗格。

   如果从包含不同资源的列表中执行导出，则必须应用过滤器，以便仅在列表中显示一种类型的资源。

1. 如果喜欢，请对选定的列排序。
1. Select the export button ![](assets/exportlistbutton.png).

   将显示一个弹出窗口，确认导出。确认导出后，文件会自动下载到您的计算机。

文件以CSV格式生成，除非在iOS中执行导出，在这种情况下，生成的文件采用TXT格式。它是根据导出的资源和导出日期命名的。例如：名为ProFileBase_20150426_120253.csv的名称将应用于在2015年月26日下午12：02：53执行的配置文件导出。它采用UTF-8格式进行编码。

数值和日期考虑执行导出的用户的本地时间(区域设置)。例如：DD-MM-YYYY或MM-DD-YYYY。

要执行大于此操作的导出，您必须创建专用工作流。Refer to the [Extract file](../../automating/using/extract-file.md) section.

**示例**

以下示例是从以下定义的配置文件列表执行的导出：

* 显示的列(按顺序)：姓氏、名字、出生日期、电子邮件地址。
* 名称按字母顺序排序。

![](assets/export_list_example1.png)

生成的文件如下所示(对于前十个记录)：

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

