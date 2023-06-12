---
title: DataModel退订事件
description: 了解数据模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 508361d1-6a0b-4476-a058-4162fb3e8d5e
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 58%

---

# 退订事件(nms：rtEvent)

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
                  <td>假</td>
                  <td>字符串</td>
                  <td>假</td>
               </tr>
               <tr>
                  <td>ctx</td>
                  <td>假</td>
                  <td>项</td>
                  <td>假</td>
               </tr>
               <tr>
                  <td>电子邮件</td>
                  <td>假</td>
                  <td>字符串</td>
                  <td>假</td>
               </tr>
               <tr>
                  <td>emailFormat</td>
                  <td>假</td>
                  <td>明细列表</td>
                  <td>假</td>
               </tr>
               <tr>
                  <td>移动电话</td>
                  <td>假</td>
                  <td>字符串</td>
                  <td>假</td>
               </tr>
               <tr>
                  <td>serverUrl</td>
                  <td>True</td>
                  <td>字符串</td>
                  <td>假</td>
               </tr>
            </table>

## 筛选器

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
