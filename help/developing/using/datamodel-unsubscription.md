---
title: DataModel取消訂閱事件
description: 瞭解資料模型
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

# 取消訂閱事件(nms：rtEvent)

## 物件說明

<table>
               <tr>
                  <th>名称</th>
                  <th>唯讀</th>
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
                  <td>電子郵件格式</td>
                  <td>假</td>
                  <td>分項清單</td>
                  <td>假</td>
               </tr>
               <tr>
                  <td>行動電話</td>
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
        <td>分項清單</td>
        </tr>
        <tr>
        <td>类型</td>
        <td>字符串</td>
        </tr>
    </table>
