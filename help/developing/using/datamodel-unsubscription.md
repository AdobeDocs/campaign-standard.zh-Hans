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
source-wordcount: '53'
ht-degree: 5%

---


# 退订事件(nms:rtEvent)

## 对象描述

<table>
               <tr>
                  <th>名称</th>
                  <th>只读</th>
                  <th>类型</th>
                  <th>必需</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>False</td>
                  <td>字符串</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>ctx</td>
                  <td>False</td>
                  <td>物料</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>电子邮件</td>
                  <td>False</td>
                  <td>字符串</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>emailFormat</td>
                  <td>False</td>
                  <td>明细列表</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>移动电话</td>
                  <td>False</td>
                  <td>字符串</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>serverUrl</td>
                  <td>True</td>
                  <td>字符串</td>
                  <td>False</td>
               </tr>
            </table>

## 过滤器

byEmail

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

byStatusOrType

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