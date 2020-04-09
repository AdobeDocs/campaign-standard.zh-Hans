---
title: 最新版本
description: 本页列表了所有最新版本的Adobe Campaign标准版。
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2646aa9ad60805a4dedc6b8a1f91c16f6e1b438d

---


# 最新版本{#latest-release}

[发布计划](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) |控 [制面板版本](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) |文 [档更新](../../rn/using/documentation-updates.md) |先 [前发行说明](../../rn/using/release-notes-2019.md) |已弃 [用功能](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

[单击此处](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU) ，直接在您的收件箱中订阅发布通知并获取有关Adobe Experience Cloud最新版本的详细信息。

## 20.2版- 2020年4月 {#release-20-2---april-2020}

**新增内容?**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Azure Blob集成</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Azure Blob存储连接器现在可用于使用传输文件工作流活动将数据导入或导出 <strong>到Adobe Campaign</strong> 。 </p>
    <p>有关详细信息，请参阅详 <a href="../../administration/using/external-accounts.md#microsoft-azure-external-account">细文档</a>。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>使用目标用户档案进行电子邮件测试</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>除了测试用户档案，您现在还可以在真正的目标用户档案上测试电子邮件。 这允许您获得用户档案将收到的消息的精确表示形式：自定义字段、动态和个性化信息，包括来自工作流的其他数据等。 </p>
    <p>有关详细信息，请参阅详细 <a href="../../sending/using/testing-messages-using-target.md">文档</a> 和教 <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html">程视频</a>。 </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>新功能将于4月在活动控制面板中发布，包括Google TXT记录管理、数据库空间监控和电子邮件警报。 有关这些功能的详细信息，请参阅控 [制面板发行说明](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html)。

**改进**

* 事务消息传递用户体验得到增强，界面一致性得到提高。 [阅读更多](../../channels/using/about-transactional-messaging.md)
* Campaign Standard现在允许您使用来自工作流的其他数据将验证发送到测试用户档案。
* 外部API活动的护栏已更新。 [阅读更多](../../automating/using/external-api.md)

**Email Designer增强功能**

* 修复了在个性化图像上多次单击时影响逃逸的问题。
* 修复了复制动态文本组件时可能导致复制黄行的问题。 (CAMP-41249)
* 修复了在表级而不是div级定义填充时Outlook中的填充问题。
* 修复了在切换到HTML模式时导致图像宽度被修改的问题。 (CAMP-41116)
* 修复了在为图标提供替代文本时无法访问社交媒体组件的问题。 (CAMP-41345)
* 修复了在电子邮件设 `<br>` 计器中使用复制粘贴时显示可见标记的问题。
* 修复了在从HTML内容切换为纯文本后，导致HTML标记显示在电子邮件中的问题。 (CAMP-41138)
* 修复了仅定义一个边框时无法呈现按钮的问题。
* 修复了HTML缩进中导致Microsoft Outlook中电子邮件的页脚向左移动的问题。 (CAMP-40987)
* 修复了在切换到纯文本模式时，导致在纯文本内容中复制HTML中定义的集合属性的个性化字段的问题。 (CAMP-40365)
* 修复了阻止链接插入选定文本段的问题。 (CAMP-41406)
* 修复了在查询编辑器中选择时区时导致日期更改的问题。 (CAMP-38277)

**其他更改**

* 现 **在，KPI与Adobe Analytics** 现成工作流程的协调功能将运行到当前日期，而不是运行一天。
* MCPNS不支持将APNS和APNS-SANDBOX作为平台添加到应用程序中。 在Adobe Campaign标准版中成功添加证书后，您现在无法再更改回设置，因为只能向MCPNS应用程序添加一个APNS平台（生产或沙箱）。

**Experience Platform集成**

>[!NOTE]
>
>Campaign Standard中的Adobe Experience Platform功能目前处于测试阶段，可能会在不另行通知的情况下频繁更新。 请参阅详细文档：Experience Platform Data Connector [,](../../administration/using/aep-about-data-connector.md)[受众目标](../../audiences/using/aep-about-audience-destinations-service.md)

* 在工作流日志中，每10分钟显示一次，活动现在显示当前正在运行的作业已处理的记录数。
* 修复了导入从数据库删除的Adobe Experience Platform用户档案时可能发生的问题。
* 修复了工作流日志中的一个问题，该问题可能导致导入记录总数显示错误结果。

**修补程序**

* 修复了扩充工作 **流活动的一个问题，该问题在别名字段中添加空格时可能会发生，****** 该字段随后创建了一个新行项。 (CAMP-39229)
* 修复了发送用户档案消息时每个测试验证都可以定位的问题。
* 修复了在取消发布和删除事件配置后发生的问题。 [阅读更多](../../administration/using/configuring-transactional-messaging.md#deleting-an-event)
* 修复了在对工作流进行 **更改时** ,“保存”按钮消失的问题。
* 修复了在隐私请求处理后在活动中手动删除该请求时，即使在清除后，也无法删除与该请求关联的数据的问题。
* 修复了在预览或发送包含Adobe Experience Manager特殊字符的消息时可能发生的问题。
* 修复了在执行具有多个入站工作流的活动时，在过渡中可能发生的问题。