---
title: DataModel订阅事件
description: 了解数据模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: cf0fac4e-59fd-4d6e-a411-41361f45938d
TQID: 'https://experienceleague.adobe.com/XssYu0sntbeCRq1uNe6MhztLtISXoJiOefIOnjqIaoQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: a1681cd8-6b2e-4955-9113-33b5f7a22b8c
    internal-label: Data model architecture
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 33%
---
# 订阅事件(nms:rtEvent)

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
        <td>ctx</td>
        <td>事件上下文</td>
        <td>项 </td>
        <td> </td>
    </tr>
    <tr>
        <td>电子邮件</td>
        <td>电子邮件</td>
        <td>字符串(128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>emailFormat</td>
        <td>电子邮件格式</td>
        <td>枚举（字节） </td>
        <td>
            <ul>
            <li>文本 — 文本 — 1</li>
            <li>HTML - html - 2</li>
            <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
            <li>未知 — 未知 — 0</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>eventHistoId</td>
        <td>已存档事件ID</td>
        <td>整数 </td>
        <td> </td>
    </tr>
    <tr>
        <td>移动电话</td>
        <td>手机号码</td>
        <td>字符串(32)</td>
        <td> </td>
    </tr>
    <tr>
        <td>serverUrl</td>
        <td>ServerUrl</td>
        <td>字符串 </td>
        <td> </td>
    </tr>
</table>

## 过滤器

按电子邮件（按电子邮件）

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>电子邮件</td>
    <td>字符串</td>
    </tr>
</table>

按状态或类型(byStatusOrType)

<table>
        <tr>
        <th>名称</th>
        <th>类型</th>
        </tr>
        <tr>
        <td>状态</td>
        <td>明细列表</td>
        </tr>
        <tr>
        <td>类型</td>
        <td>字符串</td>
        </tr>
    </table>
