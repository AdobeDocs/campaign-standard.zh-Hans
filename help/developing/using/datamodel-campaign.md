---
title: DataModel营销活动
description: 了解数据模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: a63fe730-a6b2-4ae0-93da-9f8ee7824c9f
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 33%

---

# 营销活动(nms：campaign)

## 对象说明

<table>
               <tr>
                  <th>名称</th>
                  <th>标签</th>
                  <th>类型（长度）</th>
                  <th>明细列表值</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>主资源ID</td>
                  <td>字符串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>活动</td>
                  <td>活动</td>
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
                  <td>已创建</td>
                  <td>创建时间</td>
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
                  <td>desc</td>
                  <td>说明</td>
                  <td>字符串(512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>持续时间</td>
                  <td>营销活动持续时间</td>
                  <td>数字 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>结束</td>
                  <td>结束日期</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>地理单位</td>
                  <td>链接 </td>
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
                  <td>modifiedBy (userBase)</td>
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
                  <td>orgUnit (orgUnitBase)</td>
                  <td>组织实体</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>program (programBase)</td>
                  <td>项目</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>实时报告</td>
                  <td>实时报表</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>开始</td>
                  <td>开始日期</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>状态</td>
                  <td>状态</td>
                  <td>枚举（字节） </td>
                  <td>
                     <ul>
                        <li>已开始 — 已开始 — 1</li>
                        <li>编辑 — 版本 — 0</li>
                        <li>已完成 — 已完成 — 2</li>
                        <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>模板（营销活动）</td>
                  <td>营销活动模板</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>缩略图</td>
                  <td>缩略图</td>
                  <td>字符串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>标题</td>
                  <td>营销活动</td>
                  <td>字符串(255)</td>
                  <td> </td>
               </tr>
            </table>

## 筛选器

按逻辑状态(byLogicalStatus)

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>state</td>
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
</table>

按期间（按期间）

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

按状态（按州）

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>state</td>
    <td>明细列表</td>
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

在给定期间计划（按计划）

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
