---
title: DataModel交付
description: 了解数据模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: aea3e72d-8e89-46c7-a796-bf856414c654
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 27%

---

# 投放(nms：delivery)

## 对象说明

<table>
               <tr>
                  <th>名称</th>
                  <th>标签</th>
                  <th>类型（长度）</th>
                  <th>明细列表值</th>
               </tr>
               <tr>
                  <td>FCP</td>
                  <td>校样</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>主资源ID</td>
                  <td>字符串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>abTesting</td>
                  <td>A/B 测试</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>高级</td>
                  <td>高级交付</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>advancedParameters</td>
                  <td>高级参数</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>aemContents</td>
                  <td>Adobe Experience Manager内容</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>警报消息</td>
                  <td>警告消息</td>
                  <td>字符串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>警报模式</td>
                  <td>警告类型</td>
                  <td>字符串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>附件</td>
                  <td>附加文件</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>品牌策略(brandingBase)</td>
                  <td>品牌</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>broadLogs</td>
                  <td>投放日志</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>内置</td>
                  <td>内置应用程序对象</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>campaign (campaignBase)</td>
                  <td>营销活动</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cmsAccount (extAccountAEMBase)</td>
                  <td>Adobe Experience Manager帐户</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>命令</td>
                  <td>命令</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>内容</td>
                  <td>内容</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>contentSource</td>
                  <td>内容源</td>
                  <td>枚举（字节） </td>
                  <td>
                     <ul>
                        <li>Adobe Experience Manager - aem - 1</li>
                        <li>Adobe Campaign - campaign - 0</li>
                        <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>contextResourceType</td>
                  <td>资源类型</td>
                  <td>字符串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>已创建</td>
                  <td>已创建</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy (userBase)</td>
                  <td>创建者</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>deliverymode</td>
                  <td>投放模式</td>
                  <td>枚举（字节） </td>
                  <td>
                     <ul>
                        <li>批量交付 — 批量 — 1</li>
                        <li>中间源 — 中间源 — 4</li>
                        <li>描述 — 描述性 — 2</li>
                        <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
                        <li>外部 — 外部 — 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>deliveryProvider (extAccountBase)</td>
                  <td>路由</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>desc</td>
                  <td>说明</td>
                  <td>字符串(512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailPreview</td>
                  <td>电子邮件预览</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>excludeLogs</td>
                  <td>排除日志</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>排除项</td>
                  <td>排除原因</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>执行</td>
                  <td>投放执行参数</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>executionType</td>
                  <td>执行类型</td>
                  <td>枚举（字节） </td>
                  <td>
                     <ul>
                        <li>唯一 — 一次 — 0</li>
                        <li>连续 — 连续 — 1</li>
                        <li>消息中心 — messageCenter - 2</li>
                        <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>forecastlogs</td>
                  <td>预测日志</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>地理单位</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>hasAttachments</td>
                  <td>添加附加文件</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>图标</td>
                  <td>图标</td>
                  <td>枚举（字节） </td>
                  <td>
                     <ul>
                        <li>事务性电子邮件 — emailLightning - 60</li>
                        <li>传真 — 传真 — 4</li>
                        <li>移动设备（短信） — 短信 — 1</li>
                        <li>定期电子邮件 — emailRefresh - 30</li>
                        <li>直邮 — 纸张 — 3</li>
                        <li>电话 — 电话 — 2</li>
                        <li>其他 — 其他–120</li>
                        <li>定期短信 — smsRefresh - 31</li>
                        <li>移动应用程序 — pushNotification - 40</li>
                        <li>事务性短信 — smsLightning - 61</li>
                        <li>电子邮件 — 电子邮件 — 0</li>
                        <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>是外部资源</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isMaster</td>
                  <td>母版</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isTemplate</td>
                  <td>模板</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>迭代</td>
                  <td>投放</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>作业</td>
                  <td>作业</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>jobLogs</td>
                  <td>日志</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>kpi</td>
                  <td>指标</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>标签</td>
                  <td>标签</td>
                  <td>字符串(128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>上次修改时间</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>logicalStatus</td>
                  <td>执行状态</td>
                  <td>枚举（字符串） (255)</td>
                  <td>
                     <ul>
                        <li>进行中 — 已开始 — 已开始</li>
                        <li>编辑 — 版本 — 版本</li>
                        <li>已完成 — 已完成 — 已完成</li>
                        <li>警告 — 警告 — 警告</li>
                        <li>错误 — 错误 — 错误</li>
                        <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>mailParameters</td>
                  <td>电子邮件标头参数</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>日期</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>映射(deliveryMapping)</td>
                  <td>目标映射</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>master (deliveryBase)</td>
                  <td>主实例</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>masterKpi</td>
                  <td>主指示器</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>渠道</td>
                  <td>枚举（字节） </td>
                  <td>
                     <ul>
                        <li>传真 — 传真 — 4</li>
                        <li>移动设备（短信） — 短信 — 1</li>
                        <li>电子邮件 — 电子邮件 — 0</li>
                        <li>电话 — 电话 — 2</li>
                        <li>直邮 — 纸张 — 3</li>
                        <li>移动应用程序 — pushNotification - 40</li>
                        <li>其他 — 其他–120</li>
                        <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>修改人</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>name</td>
                  <td>ID</td>
                  <td>字符串(64)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>offerManagement</td>
                  <td>选件管理</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>组织实体</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>父项(deliveryBase)</td>
                  <td>父项投放</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>优先级</td>
                  <td>投放优先级</td>
                  <td>枚举（字节） </td>
                  <td>
                     <ul>
                        <li>高 — 高 — 20</li>
                        <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
                        <li>正常 — 正常 — 10</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>program (programBase)</td>
                  <td>项目</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>验证</td>
                  <td>验证</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotificationPreview</td>
                  <td>推送通知预览</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushnotificationParameters</td>
                  <td>PushNotification参数</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>实时报告</td>
                  <td>实时报表</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>resourceVersion</td>
                  <td>资源版本</td>
                  <td>字符串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>功能区消息</td>
                  <td>功能区消息</td>
                  <td>字符串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>方案</td>
                  <td>投放模板参数</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>计划</td>
                  <td>投放计划</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsParameters</td>
                  <td>短信参数</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsPreview</td>
                  <td>短信预览</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>状态</td>
                  <td>状态</td>
                  <td>枚举（字节） </td>
                  <td>
                     <ul>
                        <li>开始挂起 — startPending - 51</li>
                        <li>准备投放 — 准备就绪 — 45</li>
                        <li>重试挂起 — 重试挂起 — 61</li>
                        <li>正在进行重试 — retryInProgress - 62</li>
                        <li>失败 — 失败 — 87</li>
                        <li>进行中 — 已开始 — 55</li>
                        <li>定位待定 — targetPrepPending - 11</li>
                        <li>Personalization待处理 — messagePrepPending - 21</li>
                        <li>已暂停 — 已暂停 — 75</li>
                        <li>编辑 — 版本 — 0</li>
                        <li>已完成 — 已完成 — 95</li>
                        <li>正在进行计数 — targetSelection - 12</li>
                        <li>已完成消息 — messageReady - 25</li>
                        <li>Personalization或计数失败 — preparationError - 37</li>
                        <li>已停止 — 已取消 — 85</li>
                        <li>正在进行Personalization — 消息准备 — 22</li>
                        <li>Target ready - targetReady - 15</li>
                        <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
                        <li>正在进行仲裁 — targetArbitration - 13</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>目标</td>
                  <td>投放目标群体</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>模板(deliveryTemplateSummary)</td>
                  <td>投放模板</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>缩略图</td>
                  <td>投放缩略图</td>
                  <td>字符串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>标题</td>
                  <td>投放</td>
                  <td>字符串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>跟踪</td>
                  <td>跟踪参数</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingLogs</td>
                  <td>跟踪日志</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingUrls</td>
                  <td>跟踪的 URL</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>triggerMessage</td>
                  <td>交易型消息的参数</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>类型(typologyBase)</td>
                  <td>类型</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>工作流(workflowBase)</td>
                  <td>定位工作流</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflowstatus</td>
                  <td>工作流状态</td>
                  <td>枚举（字符串） (255)</td>
                  <td>
                     <ul>
                        <li>进行中 — 已开始 — 已开始</li>
                        <li>编辑 — 版本 — 版本</li>
                        <li>已完成 — 已完成 — 已完成</li>
                        <li>警告 — 警告 — 警告</li>
                        <li>错误 — 错误 — 错误</li>
                        <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
            </table>

## 过滤器

按渠道类型(byChannel)

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>渠道</td>
    <td>明细列表</td>
    </tr>
</table>

按执行类型(byExecutionType)

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>executionType</td>
    <td>明细列表</td>
    </tr>
</table>

按逻辑状态(byLogicalStatus)

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>状态</td>
    <td>明细列表</td>
    </tr>
</table>

按名称或标签(byText)

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>文本</td>
    <td>字符串</td>
    </tr>
    <tr>
    <td>mc</td>
    <td>字符串</td>
    </tr>
</table>

按期间（按期间）

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>时间段</td>
    <td>字符串</td>
    </tr>
</table>

按期间(byStartPeriod)

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>日期</td>
    </tr>
    <tr>
    <td>时间段</td>
    <td>字符串</td>
    </tr>
</table>

按发布状态(byPublicationStatus)

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>pStatus</td>
    <td>明细列表</td>
    </tr>
</table>

按状态（按州）

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>状态</td>
    <td>明细列表</td>
    </tr>
</table>

跟进消息(showFollowup)

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>后续活动</td>
    <td>布尔值</td>
    </tr>
</table>

包括高级投放（含高级）

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>高级</td>
    <td>布尔值</td>
    </tr>
</table>

包括来自异类列表的连续投放（使用Continuous）

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>withContinuous</td>
    <td>布尔值</td>
    </tr>
</table>

包括验证(withFCP)

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>withFCP</td>
    <td>布尔值</td>
    </tr>
</table>

在指定期间计划（按Planning）

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>日期</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>日期</td>
    </tr>
</table>

在给定时间段内存在（按日历）

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>日期</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>日期</td>
    </tr>
</table>

显示开箱即用(showOob)

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>oob</td>
    <td>布尔值</td>
    </tr>
</table>
