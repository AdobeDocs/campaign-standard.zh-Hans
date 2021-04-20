---
solution: Campaign Standard
product: campaign
title: 数据模型
description: 了解数据模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '57'
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
                  <td>PK</td>
                  <td>False</td>
                  <td>字符串</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>ctx</td>
                  <td>False</td>
                  <td>项目</td>
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
                  <td>mobilePhone</td>
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