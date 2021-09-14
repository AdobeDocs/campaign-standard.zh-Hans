---
title: 数据模型
description: 了解数据模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 20dafd81-8546-450a-87a0-59a2509efb7a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 5%

---

# 访客(nms:visitor)

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
        <td>评论</td>
        <td>反向链接注释</td>
        <td>字符串(255)</td>
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
        <td>投放（投放）</td>
        <td>投放</td>
        <td>链接 </td>
        <td> </td>
    </tr>
    <tr>
        <td>deliveryId</td>
        <td>上次投放的ID</td>
        <td>整数 </td>
        <td> </td>
    </tr>
    <tr>
        <td>desc</td>
        <td>说明</td>
        <td>字符串(512)</td>
        <td> </td>
    </tr>
    <tr>
        <td>电子邮件</td>
        <td>电子邮件</td>
        <td>字符串(128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>externalId</td>
        <td>外部ID</td>
        <td>字符串(64)</td>
        <td> </td>
    </tr>
    <tr>
        <td>firstName</td>
        <td>名字</td>
        <td>字符串(30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>forwardUrl</td>
        <td>转发URL</td>
        <td>字符串(255)</td>
        <td> </td>
    </tr>
    <tr>
        <td>geoUnit(geoUnitBase)</td>
        <td>地理单位</td>
        <td>链接 </td>
        <td> </td>
    </tr>
    <tr>
        <td>lastModified</td>
        <td>上次修改时间</td>
        <td>日期 </td>
        <td> </td>
    </tr>
    <tr>
        <td>lastName</td>
        <td>姓氏</td>
        <td>字符串(50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>modifiedBy(userBase)</td>
        <td>修改者</td>
        <td>链接 </td>
        <td> </td>
    </tr>
    <tr>
        <td>orgUnit(orgUnitBase)</td>
        <td>组织单位</td>
        <td>链接 </td>
        <td> </td>
    </tr>
    <tr>
        <td>来源</td>
        <td>源</td>
        <td>枚举（字节） </td>
        <td>
            <ul>
            <li>未定义 — 未定义 — 0</li>
            <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>收件人（收件人）</td>
        <td>已识别的用户档案</td>
        <td>链接 </td>
        <td> </td>
    </tr>
    <tr>
        <td>recipientId</td>
        <td>配置文件ID</td>
        <td>整数 </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerEmail</td>
        <td>反向链接电子邮件</td>
        <td>字符串(128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerFirstName</td>
        <td>反向链接名字</td>
        <td>字符串(30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerId</td>
        <td>反向链接ID</td>
        <td>整数 </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerLastName</td>
        <td>反向链接姓氏</td>
        <td>字符串(50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerRcp（收件人）</td>
        <td>反向链接</td>
        <td>链接 </td>
        <td> </td>
    </tr>
    <tr>
        <td>title</td>
        <td>标签</td>
        <td>字符串(255)</td>
        <td> </td>
    </tr>
</table>

## 过滤器

按姓氏、名字或电子邮件（按文本）</p>

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
