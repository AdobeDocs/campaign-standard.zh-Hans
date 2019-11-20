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


# 订阅事件(nms:rtEvent)

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
        <td>ctx</td>
        <td>活动上下文</td>
        <td>项目 </td>
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
        <td>枚举（字节） </td>
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
        <td>存档的活动ID</td>
        <td>整数 </td>
        <td> </td>
    </tr>
    <tr>
        <td>mobilePhone</td>
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

## 滤镜

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
        <td>枚举</td>
        </tr>
        <tr>
        <td>type</td>
        <td>字符串</td>
        </tr>
    </table>