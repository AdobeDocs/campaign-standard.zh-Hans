---
title: DataModel
description: 了解数据模型
uuid: 99277e46-e4f7-49a9-ba27-b878780f90da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
discoiquuid: 6e21db35-daf9-4edb-977a-6ef606db0e4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 13ad7e616b51ae0fa0804db02f15120a636b7603

---


# 交付（nms：交付）

## 对象描述

<table>
               <tr>
                  <th>名称</th>
                  <th>标签</th>
                  <th>类型（长度）</th>
                  <th>枚举值</th>
               </tr>
               <tr>
                  <td>FCP</td>
                  <td>证明</td>
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
                  <td>A/B测试</td>
                  <td>项目 </td>
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
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>aemContents</td>
                  <td>Adobe Experience manager内容</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMessage</td>
                  <td>警告消息</td>
                  <td>字符串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMode</td>
                  <td>警告类型</td>
                  <td>字符串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>附件</td>
                  <td>附加的文件</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>品牌(brandingBase)</td>
                  <td>品牌</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>broadLogs</td>
                  <td>交付日志</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>builtIn</td>
                  <td>内置应用程序对象</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>campaign(campaignBase)</td>
                  <td>营销活动</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cmsAccount(extAccountAEMBase)</td>
                  <td>Adobe Experience manager客户</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>命令</td>
                  <td>命令</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>内容</td>
                  <td>内容</td>
                  <td>项目 </td>
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
                        <li>无效值- __Invalid_value__ - __Invalid_value__</li>
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
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy(userBase)</td>
                  <td>创建者</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>deliveryMode</td>
                  <td>交付模式</td>
                  <td>枚举（字节） </td>
                  <td>
                     <ul>
                        <li>批量交付——批量- 1</li>
                        <li>中间采购——中间采购- 4</li>
                        <li>说明——描述性- 2</li>
                        <li>无效值- __Invalid_value__ - __Invalid_value__</li>
                        <li>外部——外部- 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>deliveryProvider(extAccountBase)</td>
                  <td>路由</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>desc</td>
                  <td>说明</td>
                  <td>string(512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailPreview</td>
                  <td>电子邮件预览</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>excludeLogs</td>
                  <td>排除日志</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>排除</td>
                  <td>排除原因</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>执行</td>
                  <td>交付执行参数</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>executionType</td>
                  <td>执行类型</td>
                  <td>枚举（字节） </td>
                  <td>
                     <ul>
                        <li>唯一——一次- 0</li>
                        <li>连续——连续- 1</li>
                        <li>消息中心——消息中心- 2</li>
                        <li>无效值- __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>forecastLogs</td>
                  <td>ForecastLog</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit(geoUnitBase)</td>
                  <td>地理单位</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>hasAttachments</td>
                  <td>添加附加的文件</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>图标</td>
                  <td>图标</td>
                  <td>枚举（字节） </td>
                  <td>
                     <ul>
                        <li>交易电子邮件- emailLightning - 60</li>
                        <li>传真——传真- 4</li>
                        <li>移动(SMS)- sms - 1</li>
                        <li>循环电子邮件- emailRefresh - 30</li>
                        <li>直邮——纸张- 3</li>
                        <li>电话——电话- 2</li>
                        <li>其他——其他- 120</li>
                        <li>重复的SMS - smsRefresh - 31</li>
                        <li>移动应用程序- pushNotification - 40</li>
                        <li>交易SMS - smsLightning - 61</li>
                        <li>电子邮件——电子邮件- 0</li>
                        <li>无效值- __Invalid_value__ - __Invalid_value__</li>
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
                  <td>交付</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>工作</td>
                  <td>作业</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>jobLogs</td>
                  <td>日志</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>kpi</td>
                  <td>指标</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>标签</td>
                  <td>标签</td>
                  <td>string(128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>上次修改时间</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>logicalStatus</td>
                  <td>执行状态</td>
                  <td>枚举（字符串）(255)</td>
                  <td>
                     <ul>
                        <li>进行中——开始——开始</li>
                        <li>编辑——版本——版本</li>
                        <li>完成——完成——完成</li>
                        <li>警告——警告——警告</li>
                        <li>错误——错误——错误</li>
                        <li>无效值- __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>mailParameters</td>
                  <td>电子邮件标题参数</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>日期</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>映射(deliveryMapping)</td>
                  <td>目标映射</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>master(deliveryBase)</td>
                  <td>主实例</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>masterKpi</td>
                  <td>主指示器</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>渠道</td>
                  <td>枚举（字节） </td>
                  <td>
                     <ul>
                        <li>传真——传真- 4</li>
                        <li>移动(SMS)- sms - 1</li>
                        <li>电子邮件——电子邮件- 0</li>
                        <li>电话——电话- 2</li>
                        <li>直邮——纸张- 3</li>
                        <li>移动应用程序- pushNotification - 40</li>
                        <li>其他——其他- 120</li>
                        <li>无效值- __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>modifiedBy(userBase)</td>
                  <td>修改者</td>
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
                  <td>优惠管理</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit(orgUnitBase)</td>
                  <td>组织单位</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>parent(deliveryBase)</td>
                  <td>父交付</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>优先级</td>
                  <td>交付优先级</td>
                  <td>枚举（字节） </td>
                  <td>
                     <ul>
                        <li>高——高- 20</li>
                        <li>无效值- __Invalid_value__ - __Invalid_value__</li>
                        <li>正常——正常- 10</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>program(programBase)</td>
                  <td>计划</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>校样</td>
                  <td>校样</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotificationPreview</td>
                  <td>推送通知预览</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushnotificationParameters</td>
                  <td>PushNotification参数</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>实时报告</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>resourceVersion</td>
                  <td>资源版本</td>
                  <td>string(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ribbonMessage</td>
                  <td>功能区消息</td>
                  <td>字符串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>场景</td>
                  <td>交付模板参数</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>调度</td>
                  <td>交付计划</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsParameters</td>
                  <td>SMS参数</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsPreview</td>
                  <td>SMS预览</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>状态</td>
                  <td>状态</td>
                  <td>枚举（字节） </td>
                  <td>
                     <ul>
                        <li>开始等待——开始待定- 51</li>
                        <li>随时可送货——随时可用- 45</li>
                        <li>重试等待——重试等待- 61</li>
                        <li>重试进行中- retryInProgress - 62</li>
                        <li>失败——失败- 87</li>
                        <li>进行中——开始- 55</li>
                        <li>定位待定- targetPrepPending - 11</li>
                        <li>待定个性化- messagePrepingPending - 21</li>
                        <li>暂停——暂停- 75</li>
                        <li>编辑——版本- 0</li>
                        <li>完成——完成- 95</li>
                        <li>正在计数——目标选择- 12</li>
                        <li>消息已完成- messageReady - 25</li>
                        <li>个性化或计数失败- preparationError - 37</li>
                        <li>已停止——已取消- 85</li>
                        <li>正在进行的个性化——消息准备- 22</li>
                        <li>目标就绪——目标就绪- 15</li>
                        <li>无效值- __Invalid_value__ - __Invalid_value__</li>
                        <li>正在进行的仲裁——目标仲裁- 13</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>目标</td>
                  <td>交付目标人数</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>模板(deliveryTemplateSummary)</td>
                  <td>交付模板</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>缩略图</td>
                  <td>交付缩略图</td>
                  <td>string(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>标题</td>
                  <td>交付</td>
                  <td>string(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>跟踪</td>
                  <td>跟踪参数</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingLogs</td>
                  <td>跟踪日志</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingUrl</td>
                  <td>跟踪的URL</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>triggerMessage</td>
                  <td>事务消息的参数</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>类型学（类型学基础）</td>
                  <td>类型学</td>
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
                  <td>workflowStatus</td>
                  <td>工作流状态</td>
                  <td>枚举（字符串）(255)</td>
                  <td>
                     <ul>
                        <li>进行中——开始——开始</li>
                        <li>编辑——版本——版本</li>
                        <li>完成——完成——完成</li>
                        <li>警告——警告——警告</li>
                        <li>错误——错误——错误</li>
                        <li>无效值- __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
            </table>

## 滤镜

按渠道类型（按渠道）

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>通道</td>
    <td>枚举</td>
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
    <td>枚举</td>
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
    <td>枚举</td>
    </tr>
</table>

按名称或标签（按文本）

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
    <td>timePeriod</td>
    <td>字符串</td>
    </tr>
</table>

按期间（按开始期间）

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>timePeriod</td>
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
    <td>枚举</td>
    </tr>
</table>

按状态（按状态）

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>状态</td>
    <td>枚举</td>
    </tr>
</table>

跟进消息(showFolcoup)

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>跟进</td>
    <td>布尔值</td>
    </tr>
</table>

包括高级提交(withAdvanced)

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

包括来自异构列表的连续提交(withContinuous)

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

包含校样（使用FCP）

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

在给定期间内计划（按计划）

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>date</td>
    </tr>
</table>

在给定期间（按日历）提供

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>date</td>
    </tr>
</table>

现成显示(showOob)

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