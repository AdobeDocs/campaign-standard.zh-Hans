---
title: DataModel退订事件
description: 了解数据模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 508361d1-6a0b-4476-a058-4162fb3e8d5e
TQID: https://experienceleague.adobe.com/VuhZ3s5VTH3MFPuqzr18GBMmyaPxD2uQEdJAsMIOlf0
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 54
ht-degree: 59%

---

# 退订事件(nms:rtEvent)

## 对象说明

<table>
               <tr>
                  <th>名称</th>
                  <th>只读</th>
                  <th>类型</th>
                  <th>必填</th>
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
                  <td>真</td>
                  <td>字符串</td>
                  <td>假</td>
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
