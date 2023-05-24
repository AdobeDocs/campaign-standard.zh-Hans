---
title: DataModel服務
description: 瞭解資料模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: a326b38f-ca88-4a44-a7c2-b6e34497a364
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 40%

---

# 服務(nms：service)

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
                  <td>cusPrice</td>
                  <td>價格</td>
                  <td>整数 </td>
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
                  <td>history</td>
                  <td>订阅历史记录</td>
                  <td>集合 </td>
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
                  <td>limitedDuration</td>
                  <td>受限的持续时间</td>
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
                  <td>分項清單（位元） </td>
                  <td>
                     <ul>
                        <li>行動裝置（簡訊） — 簡訊 — 1</li>
                        <li>電子郵件 — 電子郵件 — 0</li>
                        <li>無效值 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>模式</td>
                  <td>模式</td>
                  <td>分項清單（位元） </td>
                  <td>
                     <ul>
                        <li>病毒性 — 病毒性 — 1</li>
                        <li>Newsletter — 電子報 — 0</li>
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
                  <td>公用標籤</td>
                  <td>服務標籤</td>
                  <td>字串(128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>開始</td>
                  <td>开始日期</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subLandingPage (landingPageSubscriptionBase)</td>
                  <td>訂閱登陸頁面</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenario (deliveryMCTemplateBase)</td>
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
                  <td>訂閱</td>
                  <td>订阅</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>目標資源</td>
                  <td>定位维度</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>範本（服務）</td>
                  <td>服务模板</td>
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
                  <td>服务</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubLandingPage (landingPageUnsubscriptionBase)</td>
                  <td>取消訂閱登陸頁面</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubScenario (deliveryMCTemplateBase)</td>
                  <td>退订确认</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubScenarioEventType</td>
                  <td>UnsubScenarioEventType</td>
                  <td>字符串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>validityDuration</td>
                  <td>有效期持续时间</td>
                  <td>数字 </td>
                  <td> </td>
               </tr>
            </table>

## 筛选器

在指定期間內可用（由Planning）

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

依管道型別（依管道）

<table>
<tr>
<th>名称</th>
<th>类型</th>
</tr>
<tr>
<td>頻道</td>
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

透過目標資源(byTargetResource)

<table>
<tr>
<th>名称</th>
<th>类型</th>
</tr>
<tr>
<td>目標資源</td>
<td>字符串</td>
</tr>
</table>
