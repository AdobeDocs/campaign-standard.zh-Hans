---
title: 发行说明 2020
description: 本页列表所有2020版Adobe Campaign标准。
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
source-git-commit: f4c6b74d9b80d80befed65d853cf82b32084c49d

---


# 发行说明 2020{#release-notes-2020}

[发布计划](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) |控 [制面板版本](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) |文 [档更新](../../rn/using/documentation-updates.md) |先 [前发行说明](../../rn/using/release-notes-2019.md) |已弃 [用功能](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

## 版本20.2 - 2020年4月 {#release-20-2---april-2020}

**新增内容?**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Azure Blob集成</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Azure Blob存储连接器现在可用于使用传输文件工作流活动将数据导入或 <strong>导出到Adobe Campaign</strong> 。 </p>
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
   <td> <p>除了测试用户档案，您现在还可以在真正的目标用户档案上测试电子邮件。 这允许您获得用户档案将收到的消息的精确表示形式： 自定义字段、动态和个性化信息，包括工作流的其他数据等。 </p>
    <p>有关详细信息，请参阅详 <a href="../../sending/using/testing-messages-using-target.md">细文档</a> 和教 <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html">程视频</a>。 </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>新功能将于4月在活动控制面板中发布，包括Google TXT记录管理、数据库空间监控和电子邮件警报。 有关这些功能的详细信息，请参 [阅控制面板发行说明](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html)。

**改进**

* 事务消息用户体验得到增强，界面一致性得到提高。 [阅读更多](../../channels/using/about-transactional-messaging.md)
* Campaign Standard现在允许您使用来自验证的额外数据将工作流发送给测试用户档案。
* 外部API活动的护栏已更新。 [阅读更多](../../automating/using/external-api.md)

**Email Designer增强功能**

* 修复了在个性化图像上多次点击时影响逃逸的问题。
* 修复了复制动态文本组件时可能导致复制黄行的问题。 (CAMP-41249)
* 修复了在表级而不是div级定义填充时Outlook中填充的问题。
* 修复了在切换到HTML模式时导致图像宽度被修改的问题。 (CAMP-41116)
* 修复了在为图标提供替代文本时无法访问社交媒体组件的问题。 (CAMP-41345)
* 修复了在电子邮件设 `<br>` 计器中使用复制粘贴时导致显示可见标记的问题。
* 修复了在从HTML内容切换为纯文本后，导致HTML标记显示在电子邮件中的问题。 (CAMP-41138)
* 修复了仅定义一个边框时无法呈现按钮的问题。
* 修复了HTML缩进中导致电子邮件页脚向左移动的问题。 (CAMP-40987)
* 修复了在切换为纯文本模式时，导致在纯文本内容中复制HTML中定义的集合属性的个性化字段的问题。 (CAMP-40365)
* 修复了阻止链接插入选定文本段的问题。 (CAMP-41406)
* 修复了在查询编辑器中选择时区时导致日期更改的问题。 (CAMP-38277)

**其他更改**

* 现 **在，KPI与Adobe Analytics** 现成工作流程的协调将运行到当前日期，而不是运行一天。
* MCPNS不支持将APNS和APNS-SANDBOX作为平台添加到应用程序中。 在Adobe Campaign标准版中成功添加证书后，您现在无法再重新更改设置，因为只能向MCPNS应用程序添加一个APNS平台（生产平台或沙箱）。

**Experience Platform集成**

>[!NOTE]
>
>Campaign Standard中的Adobe Experience Platform功能目前处于测试阶段，如有频繁更新，恕不另行通知。 请参阅详细文档： [Experience Platform Data Connector](../../developing/using/aep-about-data-connector.md), [受众目标](../../audiences/using/aep-about-audience-destinations-service.md)

* 在工作流日志中，每10分钟显示一次活动，该记录现在显示当前正在运行的作业已处理的记录数。
* 修复了导入从用户档案库删除的Adobe Experience Platform时可能发生的问题。
* 修复了工作流日志中显示导入记录总数结果不正确的问题。

**修补程序**

* 修复了在别名字 **段中添加空格** （然后创建新行项）时，可 **能出现的** “扩充”工作流活动问题。 (CAMP-39229)
* 修复了在发送用户档案消息时，每个测试验证都可以定位的问题。
* 修复了取消发布和删除事件配置后发生的问题。 [阅读更多](../../administration/using/configuring-transactional-messaging.md#deleting-an-event)
* 修复了在对工作流进 **行更改** 时“保存”按钮消失的问题。
* 修复了在隐私请求处理后在活动中手动删除隐私请求时的问题，该问题导致与请求关联的数据即使在清除后也无法被删除。
* 修复了在预览或发送包含特殊字符的消息时可能发生的问题。
* 修复了在执行具有多个入站工作流的活动时，在过渡中可能发生的问题。
* 修复了阻止标准用户在工作流订阅或投放中将“目标到应用程序”用作查询维的问题。 (CAMP-37618)

## 版本20.1.4 - 2020年2月 {#release-20-1-4---february-2020}

* 修复了在现有受众上打 **开读取工作流** 活动时的问题。 (CAMP-41002)

## 版本20.1.3 - 2020年2月 {#release-20-1-3---february-2020}

* 修复了CAMP-39273在20.1中引入的使用漏洞的客户回归问题。 39273营被归还。

## 版本20.1.2 - 2020年2月 {#release-20-1-2---february-2020}

**Email Designer增强功能**

* 修复了在修补过期片段并保存内容时在其中添加HTML标记元素的问题。 (CAMP-40685)
* 修复了在使用动态内容时添加空间的问题。 (CAMP-40605)
* 修复了配置事务性电子邮件模板时的问题。 (CAMP-40604)

## 版本20.1 - 2020年2月 {#release-20-1---february-2020}

**新增内容?**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Adobe Experience Platform Data Connector（测试版）</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Experience Platform Data Connector现在与Adobe Standard集成。 您可以将XTK数据(以活动摄取的数据)映射到Adobe Experience Platform数据模型(XDM)，从而使活动数据在Adobe Experience Platform上可用。 </p>
    <p>请注意，此功能仅适用于Azure上托管的客户。 有关激活此功能的功能和条件的详细信息，请参 <a href="../../developing/using/aep-about-data-connector.md">阅详细文</a> 档 <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">和操作方法视频</a>。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>受众目标（测试版） </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>受众目标允许您从Adobe Experience Platform共享细分到Adobe Campaign。</p>
    <p>请注意，此功能仅适用于Azure上托管的客户。 有关激活此功能的功能和条件的详细信息，请参 <a href="../../audiences/using/aep-about-audience-destinations-service.md">阅详细文</a> 档 <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html">和操作方法视频</a>。 </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**改进**

* 增强的MTA的全球可用性： 消息(包括事务性消息)现在由Adobe Campaign增强型MTA发送，该MTA提供了升级的发送基础结构，可改进发送能力、吞吐量和弹回处理。 [阅读更多](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)

* 时区管理已得到增强。 您现在可以为整个 [工作流定义](../../automating/using/building-a-workflow.md) 特定时区。 选定的时区将应用于工作流的所有活动。 现在，接口中（在日志中以及选择时区后）显示为操作员或服务器配置的时区信息。 (CAMP-37672)

* Campaign StandardAPI现在允许您在使用大表时通过向调用URL添 `_forcePagination=true` 加参数来执行分页。 [阅读更多](../../api/using/pagination.md)

* 投放日志ID（每个日志的唯一标识符）现在在所有投放日志的定位维度和跟踪日志资源中可用。 例如，这允许在导出时识别发送或跟踪日志。 [阅读更多](../../automating/using/exporting-logs.md)

**Email Designer增强功能**

* 在创建受众时添加了缺失的必填文本说明。
* 修复了在旧版电子邮件编 **辑器的向导** 中单击“更改内容”按钮时的问题。
* 修复了阻止标头与服务摘要报告中的内容对齐的问题。 (CAMP-38103)
* 修复了在不影响主题行其余部分的情况下阻止动态内容变体被删除的问题。 (CAMP-40096)
* 修复了在主题行上使用B变体时的A/B测试问题。 (CAMP-40327)
* 修复了使用上传HTML导入功能时无法拖放文件的问题。 (CAMP-39326)
* 修复了阻止您从文本编辑器复制和粘贴文本的问题。 (CAMP-39028)
* 修复了阻止显示单词建议的问题。 (CAMP-38970)
* 修复了阻止用户保存片段的问题。 (ATU-2447)
* 修复了阻止动态结构复制的问题。 (CAMP-38367)
* 修复了在复制时动态内容无法保留条件的问题。 (CAMP-39051)

**其他更改**

* “准备失败的投放”过滤器现在考虑投放的创建日期，而不是上次修改日期。
* 管理员安全组的组织单元不能再更改。
* 创建用户档案时，现在必须填写“组织单位”字段。
* 现在，仅当删除了事件和关联到Experience Cloud的事务模板时，才能删除Experience Cloud触发器。
* Adobe Creative SDK已停用。 现在，在Campaign Standard中已弃用它。 请参阅已 [弃用和已删除的功](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)能页。


**修补程序**

* 修复了执行删除隐私请求时阻止在排除日志中删除用户数据的问题。 (CAMP-39003)
* 修复了在容器元素中调整文本大小时导致辅助功能问题的问题。
* 修复了阻止用户忽略在营销活动中悬停时显示的日历弹出窗口的问题。
* 修复了活动中显 **[!UICONTROL External API]** 示按钮的问 **[!UICONTROL Confirm]** 题，即使未修改任何数据也是如此。
* 修复了对具有不同活动 **[!UICONTROL Union]** 维度的查询使用目标时的问题。 过渡数据只显示主集定位维度中的记录。 (CAMP-36831)
* 修复了在特定活动中使用上下文(例如 **[!UICONTROL Reconciliation]** 两个入站活动，其中一个是排除活动)时可能导致错误的问题。 (CAMP-37490)
* 修复了在选择和更新测试用户档案时可能发生的性能问题。 (CAMP-37976)
* 修复了通过登陆页订阅或取消订阅时可能显示错误页面的问题。 (CAMP-37771)
* 修复了以zip格式上传内容时发生的问题，该问题在HTML中引用了PNG文件，其扩展名为大写字母。 (CAMP-37913)
* 修复了在向投放添加测试用户档案时无法发送应用程序内消息的问题。
* 修复了外部API工作流活动错误，该错误在链接到扩充活动时失败。
* 修复了可能导致SMS消息状态显示不正确的问题。
* 修复了自定义资源导致重复条目显示在不同API端点下的问题。
* 修复了在发布后登陆页无法使用的问题。 (CAMP-38695)
* 修复了显示来自两个不同资源的交叉过渡的数据时发生的错误。 (CAMP-38974)
* 修复了导致明细列表中的投放模板值设置不正确的问题。 (CAMP-38388)
* 修复了电子邮件批量投放错误，该错误将投放状态显示为“待定”，将“已发送”状态显示为“已完成”。 (CAMP-35355)
* 修复了在动态报告中错误地显示发送者域的错误。 (CAMP-33123)
* 修复了在动态退订中导致报告计数不一致的问题。 (CAMP-39949)
* 修复了发送应用程序内消息时地址无法显示在发送日志屏幕中的问题。
* 修复了SMS发送日志无法用正确数量的弹回进行更新的问题。 (CAMP-38395)
* 修复了允许应用程序订阅发布呼叫更新推送通知令牌的漏洞。 (CAMP-39273)
