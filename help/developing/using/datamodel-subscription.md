---
title: 数据模型
description: 了解数据模型
uuid: 99277e46-e4f7-49a9-ba27-b878780f90da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
discoiquuid: 6e21db35-daf9-4edb-977a-6ef606db0e4d
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 订阅事件(nms:rtEvent)

## 对象描述

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
        <td>物料 </td>
        <td> </td>
    </tr>
    <tr>
        <td>电子邮件</td>
        <td>电子邮件</td>
        <td>string(128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>emailFormat</td>
        <td>电子邮件格式</td>
        <td>明细列表（字节） </td>
        <td>
            <ul>
            <li>文本——文本- 1</li>
            <li>HTML - html - 2</li>
            <li>无效值- __Invalid_value__ - __Invalid_value__</li>
            <li>未知——未知- 0</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>eventHistoId</td>
        <td>存档事件ID</td>
        <td>整数 </td>
        <td> </td>
    </tr>
    <tr>
        <td>移动电话</td>
        <td>移动号码</td>
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

通过电子邮件（通过电子邮件）

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

按状态或类型（按状态或类型）

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