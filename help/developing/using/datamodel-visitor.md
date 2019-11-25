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
source-git-commit: 6263623a5a8999c475255709a7d0150437e68c0b

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
        <td>引介评论</td>
        <td>string(255)</td>
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
        <td>交付（交付）</td>
        <td>交付</td>
        <td>链接 </td>
        <td> </td>
    </tr>
    <tr>
        <td>deliveryId</td>
        <td>上次传送的ID</td>
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
        <td>电子邮件</td>
        <td>电子邮件</td>
        <td>string(128)</td>
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
        <td>转发url</td>
        <td>string(255)</td>
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
        <td>date </td>
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
            <li>未定义——未定义- 0</li>
            <li>无效值- __Invalid_value__ - __Invalid_value__</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>收件人（收件人）</td>
        <td>已识别的配置文件</td>
        <td>链接 </td>
        <td> </td>
    </tr>
    <tr>
        <td>recipientId</td>
        <td>个人资料ID</td>
        <td>整数 </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerEmail</td>
        <td>反向链接电子邮件</td>
        <td>string(128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerFirstName</td>
        <td>引用名</td>
        <td>字符串(30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerId</td>
        <td>参照ID</td>
        <td>整数 </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerLastName</td>
        <td>引用姓氏</td>
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
        <td>标题</td>
        <td>标签</td>
        <td>string(255)</td>
        <td> </td>
    </tr>
</table>

## 滤镜

按姓、名或电子邮件（按文本）</p>

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