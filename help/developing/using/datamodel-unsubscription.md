---
title: DataModel退订事件
description: 了解数据模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 508361d1-6a0b-4476-a058-4162fb3e8d5e
TQID: 'https://experienceleague.adobe.com/VuhZ3s5VTH3MFPuqzr18GBMmyaPxD2uQEdJAsMIOlf0'
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
source-wordcount: '54'
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
