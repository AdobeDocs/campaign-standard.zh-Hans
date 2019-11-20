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
source-git-commit: c7e83d7d5130ce93b880e4835e634dad03504ebb

---


# 服务(nms:service)

## 对象描述

<table>
               <tr>
                  <th>名称</th>
                  <th>标签</th>
                  <th>类型（长度）</th>
                  <th>枚举值</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>主资源ID</td>
                  <td>字符串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>builtIn</td>
                  <td>内置应用程序对象</td>
                  <td>布尔值 </td>
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
                  <td>cusPrice</td>
                  <td>价格</td>
                  <td>整数 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>desc</td>
                  <td>说明</td>
                  <td>string(512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>end</td>
                  <td>结束日期</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit(geoUnitBase)</td>
                  <td>地理单位</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>历史</td>
                  <td>订阅历史记录</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>是外部资源</td>
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
                  <td>limitedDuration</td>
                  <td>有限持续时间</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>日期</td>
                  <td>日期(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>渠道</td>
                  <td>枚举（字节） </td>
                  <td>
                     <ul>
                        <li>移动(SMS)- sms - 1</li>
                        <li>电子邮件——电子邮件- 0</li>
                        <li>无效值- __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>模式</td>
                  <td>模式</td>
                  <td>枚举（字节） </td>
                  <td>
                     <ul>
                        <li>病毒——病毒-1</li>
                        <li>新闻稿——新闻稿- 0</li>
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
                  <td>orgUnit(orgUnitBase)</td>
                  <td>组织单位</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>publicLabel</td>
                  <td>服务标签</td>
                  <td>string(128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>开始</td>
                  <td>开始日期</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subLandingPage(landingPageSubscriptionBase)</td>
                  <td>订阅登录页</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenario(deliveryMCTemplateBase)</td>
                  <td>订阅确认</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenarioEventType</td>
                  <td>SubScenarioEventType</td>
                  <td>字符串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>订阅</td>
                  <td>订阅</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>targetResource</td>
                  <td>定位维度</td>
                  <td>string(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>模板（服务）</td>
                  <td>服务模板</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>缩略图</td>
                  <td>缩略图</td>
                  <td>string(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>标题</td>
                  <td>服务</td>
                  <td>string(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>nimcastLandingPage(landingPageUnsubscriptionBase)</td>
                  <td>取消订阅登录页面</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>nimmacScenario(deliveryMCTemplateBase)</td>
                  <td>取消订阅确认</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>nimbusScenarioEventType</td>
                  <td>NimmicScenarioEventType</td>
                  <td>字符串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>validityDuration</td>
                  <td>有效期</td>
                  <td>数字 </td>
                  <td> </td>
               </tr>
            </table>

## 滤镜

在给定时间段内可用（按计划）

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
</table>

通过定位资源(byTargetResource)

<table>
<tr>
<th>名称</th>
<th>类型</th>
</tr>
<tr>
<td>targetResource</td>
<td>字符串</td>
</tr>
</table>