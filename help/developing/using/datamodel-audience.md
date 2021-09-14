---
title: 数据模型
description: 了解数据模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 53da6c4e-d4fb-4677-acff-744e3eb10960
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 6%

---

# 受众(nms:audience)

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
                  <td>aamMappingId</td>
                  <td>Audience Manager映射ID</td>
                  <td>字符串(100)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>amcDataSource(amcDataSourceBase)</td>
                  <td>AMC数据源</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceData</td>
                  <td>预览选定群体</td>
                  <td>收藏集 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceDataSchema</td>
                  <td>数据模式</td>
                  <td>字符串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceMetadata</td>
                  <td>AudienceMetadata</td>
                  <td>字符串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>collectLineNumber</td>
                  <td>使用行号作为ID</td>
                  <td>布尔 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>count</td>
                  <td>计数</td>
                  <td>整数 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countDate</td>
                  <td>计数日期</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countPreview</td>
                  <td>CountPreview</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>已创建</td>
                  <td>已创建</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy(userBase)</td>
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
                  <td>doNotPersist</td>
                  <td>不要将此作业历史化</td>
                  <td>布尔 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>errorLimit</td>
                  <td>中止前出错</td>
                  <td>整数 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>expirationDate</td>
                  <td>过期时间</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit(geoUnitBase)</td>
                  <td>地理单位</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>hasSchema</td>
                  <td>HasSchema</td>
                  <td>布尔 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isAMC</td>
                  <td>Adobe Marketing Cloud受众</td>
                  <td>布尔 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>是外部资源</td>
                  <td>布尔 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>jobLogs</td>
                  <td>日志</td>
                  <td>收藏集 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>label</td>
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
                  <td>rejectFilename</td>
                  <td>拒绝文件</td>
                  <td>字符串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sharedAudience</td>
                  <td>共享受众的名称</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>来源</td>
                  <td>来源</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sourceId</td>
                  <td>源Id</td>
                  <td>整数 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>title</td>
                  <td>受众</td>
                  <td>字符串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>type</td>
                  <td>类型</td>
                  <td>枚举（字符串）(100)</td>
                  <td>
                     <ul>
                        <li>查询 — 查询 — 查询</li>
                        <li>列表 — 列表 — 列表</li>
                        <li>文件 — 文件 — 文件</li>
                        <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>where</td>
                  <td>查询定义</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>工作流（工作流）</td>
                  <td>工作流</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
            </table>

## 过滤器

通过筛选维度(byFilteringResource)

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>filteringResource</td>
    <td>字符串</td>
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

按类型（按类型）

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>type</td>
    <td>明细列表</td>
    </tr>
    <tr>
    <td>isAMC</td>
    <td>字符串</td>
    </tr>
</table>
