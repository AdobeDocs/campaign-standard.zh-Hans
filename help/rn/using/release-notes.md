---
title: 最新版本
description: 本页列出了Adobe Campaign Standard的所有最新版本。
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
source-git-commit: e119ee1dc605b4f0ca48cd79fcdf2ad38d6b1440

---


# 最新版本{#latest-release}

[发布计划](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) |控 [制面板版本](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) |文 [档更新](../../rn/using/documentation-updates.md) |先 [前发行说明](../../rn/using/release-notes-2019.md) |已弃 [用功能](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

## 版本20.1 - 2020年2月 {#release-20-1---february-2020}

**有什么新增功能？**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Adobe Experience Platform Data Connector（测试版）</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Experience Platform Data Connector现已与Adobe Campaign Standard集成。 您可以通过将XTK数据（在Campaign中摄取的数据）映射到Adobe Experience Platform数据模型(XDM)，在Adobe Experience Platform上提供Campaign数据。 </p>
    <p>请注意，此功能仅适用于Azure上托管的客户。 有关激活此功能的功能和条件的详细信息，请参 <a href="../../administration/using/aep-about-data-connector.md">阅详细文档</a><a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">和操作方法视频</a>。</p>
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
   <td> <p>受众目标允许您将Adobe Experience Platform中的细分共享到Adobe Campaign。</p>
    <p>请注意，此功能仅适用于Azure上托管的客户。 有关激活此功能的功能和条件的详细信息，请参 <a href="../../audiences/using/aep-about-audience-destinations-service.md">阅详细文档</a><a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html">和操作方法视频</a>。 </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**改进**

* 增强的MTA的全球可用性：消息（包括交易消息）现在由Adobe Campaign增强型MTA发送，它提供了升级的发送基础结构，可改进交付性、吞吐量和弹回处理。 [阅读更多](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)

* 时区管理已得到增强。 您现在可以为整个 [工作流定义](../../automating/using/building-a-workflow.md) 特定时区。 选定的时区将应用于工作流的所有活动。 现在，有关为操作员或服务器配置的时区的信息显示在界面中（在日志中和选择时区后）。 (CAMP-37672)

* 现在，通过向调用URL添加参数，Campaign Standard API允许您在使用大表时 `_forcePagination=true` 执行分页。 [阅读更多](../../api/using/pagination.md)

* 交付日志ID（每个日志的唯一标识符）现在在所有定位维的交付日志和跟踪日志资源中可用。 这允许在导出时识别发送或跟踪日志。 [阅读更多](../../automating/using/exporting-logs.md)

**Email Designer增强功能**

* 添加了在创建受众时缺少的必填文本说明。
* 修复了在旧版电子邮件编辑器的 **向导中单击** “更改内容”按钮时的问题。
* 修复了阻止标题与服务摘要报告中的内容对齐的问题。 (CAMP-38103)
* 修复了在不影响主题行其余部分的情况下无法删除动态内容变体的问题。 (CAMP-40096)
* 修复了在主题行上使用B变体时的A/B测试问题。 (CAMP-40327)
* 修复了在使用上传HTML导入功能时无法拖放文件的问题。 (CAMP-39326)
* 修复了阻止您从文本编辑器复制和粘贴文本的问题。 (CAMP-39028)
* 修复了阻止显示单词建议的问题。 (CAMP-38970)
* 修复了阻止用户保存片段的问题。 (ATU-2447)

**其他更改**

* “准备失败的提交”过滤器现在考虑提交的创建日期而不是上次修改日期。
* 管理员安全组的组织单位不能再更改。
* 创建配置文件时，现在必须填写“组织单位”字段。
* 现在，仅当删除活动和与其关联的事务模板时，才能删除Experience Cloud触发器。

**修补程序**

* 修复了执行删除隐私请求时阻止在排除日志中删除用户数据的问题。 (CAMP-39003)
* 修复了在容器元素中调整文本大小时导致辅助功能问题的问题。
* 修复了阻止用户忽略在营销活动中悬停时显示的日历弹出窗口的问题。
* 修复了活动中显 **[!UICONTROL External API]**示按钮的问题，即使未修**[!UICONTROL Confirm]** 改任何数据也是如此。
* 修复了在具有不同目标维 **[!UICONTROL Union]**度的查询上使用活动时的问题。 过渡数据只显示主集的定位维度中的记录。 (CAMP-36831)
* 修复了在特定上下文中使用活动（例如，两个入站活动，其中一个是排除活动）时，可能导致错误的问题。 **[!UICONTROL Reconciliation]**(CAMP-37490)
* 修复了在选择和更新测试配置文件时可能发生的性能问题。 (CAMP-37976)
* 修复了通过登录页面订阅或取消订阅时可能显示错误页面的问题。 (CAMP-37771)
* 修复了以zip格式上传内容时发生的问题，该问题在HTML中引用PNG文件，其扩展名为大写字母。 (CAMP-37913)
* 修复了在将测试配置文件添加到分发时无法发送应用程序内消息的问题。
* 修复了外部API工作流活动在链接到丰富化活动时失败的错误。
* 修复了可能导致SMS消息状态显示错误的问题。
* 修复了自定义资源导致重复条目显示在不同API端点下的问题。
* 修复了登录页面在发布后不可用的问题。 (CAMP-38695)
* 修复了显示来自两个不同资源的交叉点过渡的数据时出现的错误。 (CAMP-38974)
* 修复了导致分发模板中的枚举值设置错误的问题。 (CAMP-38388)
* 修复了电子邮件批量提交时出错，该错误将提交状态显示为“待定”，将“已发送”状态显示为“已完成”。 (CAMP-35355)
* 修复了在动态报告中错误地显示发送者域的错误。 (CAMP-33123)
* 修复了在动态报表中导致取消订阅计数不一致的问题。 (CAMP-39949)
* 修复了发送应用程序内消息时地址无法显示在发送日志屏幕中的问题。
* 修复了SMS发送日志无法用正确数量的弹回进行更新的问题。 (CAMP-38395)
