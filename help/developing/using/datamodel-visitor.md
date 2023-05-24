---
title: DataModel訪客
description: 瞭解資料模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 20dafd81-8546-450a-87a0-59a2509efb7a
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 42%

---

# 訪客(nms：visitor)

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
        <td>評論</td>
        <td>推荐人评论</td>
        <td>字串(255)</td>
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
        <td>傳遞（傳遞）</td>
        <td>投放</td>
        <td>链接 </td>
        <td> </td>
    </tr>
    <tr>
        <td>deliveryId</td>
        <td>上次傳遞的ID</td>
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
        <td>电子邮件</td>
        <td>电子邮件</td>
        <td>字串(128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>externalId</td>
        <td>外部 ID</td>
        <td>字串(64)</td>
        <td> </td>
    </tr>
    <tr>
        <td>名字</td>
        <td>名字</td>
        <td>字串(30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>forwardUrl</td>
        <td>转发 url</td>
        <td>字串(255)</td>
        <td> </td>
    </tr>
    <tr>
        <td>geoUnit (geoUnitBase)</td>
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
        <td>姓氏</td>
        <td>姓氏</td>
        <td>字串(50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>modifiedBy (userBase)</td>
        <td>修改者</td>
        <td>链接 </td>
        <td> </td>
    </tr>
    <tr>
        <td>orgUnit (orgUnitBase)</td>
        <td>组织实体</td>
        <td>链接 </td>
        <td> </td>
    </tr>
    <tr>
        <td>來源</td>
        <td>来源</td>
        <td>分項清單（位元） </td>
        <td>
            <ul>
            <li>未定義 — 未定義 — 0</li>
            <li>無效值 — __Invalid_value__ - __Invalid_value__</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>收件者</td>
        <td>已識別的設定檔</td>
        <td>链接 </td>
        <td> </td>
    </tr>
    <tr>
        <td>recipientId</td>
        <td>配置文件 ID</td>
        <td>整数 </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerEmail</td>
        <td>推荐人邮箱</td>
        <td>字串(128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerFirstName</td>
        <td>推荐人名字</td>
        <td>字串(30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerId</td>
        <td>反向連結ID</td>
        <td>整数 </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerLastName</td>
        <td>推荐人姓氏</td>
        <td>字串(50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerRcp (recipient)</td>
        <td>反向链接</td>
        <td>链接 </td>
        <td> </td>
    </tr>
    <tr>
        <td>title</td>
        <td>标签</td>
        <td>字串(255)</td>
        <td> </td>
    </tr>
</table>

## 筛选器

依姓氏、名字或電子郵件(byText)</p>

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
