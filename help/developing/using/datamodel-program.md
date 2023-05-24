---
title: 資料模型程式
description: 瞭解資料模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: b05dc67a-6447-4d22-99f2-8a14a0ee46d2
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 36%

---

# 程式(nms：program)

## 物件說明

<table>
               <tr>
                  <th>名称</th>
                  <th>标签</th>
                  <th>型別（長度）</th>
                  <th>明细列表值</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>主要資源ID</td>
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
                  <td>buildIn</td>
                  <td>内置应用程序对象</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>已建立</td>
                  <td>已创建</td>
                  <td>date </td>
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
                  <td>字串(512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>結束</td>
                  <td>结束日期</td>
                  <td>date </td>
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
                  <td>為外部資源</td>
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
                  <td>label</td>
                  <td>标签</td>
                  <td>字串(128)</td>
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
                  <td>分項清單（字串） (255)</td>
                  <td>
                     <ul>
                        <li>進行中 — 已開始 — 已開始</li>
                        <li>編輯 — 版本 — 版本</li>
                        <li>已完成 — 已完成 — 已完成</li>
                        <li>警告 — 警告 — 警告</li>
                        <li>錯誤 — 錯誤 — 錯誤</li>
                        <li>無效值 — __Invalid_value__ - __Invalid_value__</li>
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
                  <td>字串(64)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>组织实体</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>父級(programBase)</td>
                  <td>父級計畫</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>即時報表</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>開始</td>
                  <td>开始日期</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>状态</td>
                  <td>状态</td>
                  <td>分項清單（位元） </td>
                  <td>
                     <ul>
                        <li>開始 — 開始 — 1</li>
                        <li>編輯 — 版本 — 0</li>
                        <li>已完成 — 已完成 — 2</li>
                        <li>無效值 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>範本（方案）</td>
                  <td>計畫範本</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>縮圖</td>
                  <td>缩略图</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>title</td>
                  <td>项目</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
            </table>

## 筛选器

依邏輯狀態(byLogicalStatus)

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>state</td>
    <td>分項清單</td>
    </tr>
</table>

依名稱或標籤(byText)

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>文字</td>
    <td>字符串</td>
    </tr>
</table>

按期間（按期間）

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
    <td>時間週期</td>
    <td>字符串</td>
    </tr>
</table>

包含來自異質清單的連續傳遞（使用Continuous）

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

包含子程式(withParent)

<table>
        <tr>
        <th>名称</th>
        <th>类型</th>
        </tr>
        <tr>
        <td>withParent</td>
        <td>布尔值</td>
        </tr>
    </table>

僅限合格的父項（合格父項）

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>方案</td>
    <td>链接</td>
    </tr>
</table>

為指定期間計畫（由Planning）

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

在指定期間內存在（依行事曆）

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
