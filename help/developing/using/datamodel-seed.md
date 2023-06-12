---
title: 数据模型种子成员
description: 了解数据模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 9b522c84-e296-47c7-9588-2e5ed08ab631
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 47%

---

# 种子成员(nms：seedMember)

## 对象描述

<table>
               <tr>
                  <th>名称</th>
                  <th>标签</th>
                  <th>类型（长度）</th>
                  <th>明细列表值</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>主资源ID</td>
                  <td>字符串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>国家/地区</td>
                  <td>国家/地区</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>已创建</td>
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
                  <td>电子邮件渲染</td>
                  <td>电子邮件渲染</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>传真</td>
                  <td>传真</td>
                  <td>字符串(32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>地理单位</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>是外部资源</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>上次修改时间</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>位置</td>
                  <td>位置</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>marketingCloudId</td>
                  <td>MARKETING CLOUDID</td>
                  <td>字符串(256)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobileApp</td>
                  <td>移动应用程序</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>移动电话</td>
                  <td>手机</td>
                  <td>字符串(32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>修改者</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>name</td>
                  <td>ID</td>
                  <td>字符串(64)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>nms_recipient</td>
                  <td>用户档案</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>nms_rtEvent</td>
                  <td>Event</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>组织实体</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>电话</td>
                  <td>电话</td>
                  <td>字符串(32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>证明</td>
                  <td>验证</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>推送通知</td>
                  <td>推送通知</td>
                  <td>字符串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>registrationtoken</td>
                  <td>注册令牌</td>
                  <td>字符串(256)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sampledata</td>
                  <td>样本数据</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>短信</td>
                  <td>手机</td>
                  <td>字符串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink（状态）</td>
                  <td>状态</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>targetdata</td>
                  <td>扩展</td>
                  <td>字符串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>缩略图</td>
                  <td>缩略图</td>
                  <td>字符串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>title</td>
                  <td>测试配置文件</td>
                  <td>字符串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>陷印</td>
                  <td>陷印</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
            </table>

## 筛选器

按事件类型(byEventType)

<table>
        <tr>
        <th>名称</th>
        <th>类型</th>
        </tr>
        <tr>
        <td>事件类型</td>
        <td>字符串</td>
        </tr>
    </table>

按名称或标签(byText)

<table>
        <tr>
        <th>名称</th>
        <th>类型</th>
        </tr>
        <tr>
        <td>text</td>
        <td>字符串</td>
        </tr>
    </table>

按使用情况（按使用情况）

<table>
        <tr>
        <th>名称</th>
        <th>类型</th>
        </tr>
        <tr>
        <td>陷印</td>
        <td>布尔值</td>
        </tr>
        <tr>
        <td>电子邮件渲染</td>
        <td>布尔值</td>
        </tr>
        <tr>
        <td>证明</td>
        <td>布尔值</td>
        </tr>
    </table>

测试配置文件（配置文件）

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>seedMember</td>
    <td>链接</td>
    </tr>
</table>
