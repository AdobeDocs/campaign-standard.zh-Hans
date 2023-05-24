---
title: 資料模型種子成員
description: 瞭解資料模型
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

# 種子成員(nms：seedMember)

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
                  <td>國家/地區</td>
                  <td>国家/地区</td>
                  <td>链接 </td>
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
                  <td>emailRender</td>
                  <td>电子邮件渲染</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>傳真</td>
                  <td>传真</td>
                  <td>字串(32)</td>
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
                  <td>為外部資源</td>
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
                  <td>字串(256)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobileApp</td>
                  <td>移动应用程序</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>行動電話</td>
                  <td>手机</td>
                  <td>字串(32)</td>
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
                  <td>字串(64)</td>
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
                  <td>電話</td>
                  <td>电话</td>
                  <td>字串(32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>證明</td>
                  <td>验证</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotification</td>
                  <td>推送通知</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>registrationToken</td>
                  <td>注册令牌</td>
                  <td>字串(256)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sampleData</td>
                  <td>样本数据</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>簡訊</td>
                  <td>手机</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink (state)</td>
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
                  <td>縮圖</td>
                  <td>缩略图</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>title</td>
                  <td>测试配置文件</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>補漏白</td>
                  <td>陷印</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
            </table>

## 筛选器

依事件型別(byEventType)

<table>
        <tr>
        <th>名称</th>
        <th>类型</th>
        </tr>
        <tr>
        <td>事件型別</td>
        <td>字符串</td>
        </tr>
    </table>

依名稱或標籤(byText)

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

依使用狀況（依使用狀況）

<table>
        <tr>
        <th>名称</th>
        <th>类型</th>
        </tr>
        <tr>
        <td>補漏白</td>
        <td>布尔值</td>
        </tr>
        <tr>
        <td>emailRender</td>
        <td>布尔值</td>
        </tr>
        <tr>
        <td>證明</td>
        <td>布尔值</td>
        </tr>
    </table>

測試設定檔（設定檔）

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
