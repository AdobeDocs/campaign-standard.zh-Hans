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
source-git-commit: c7e83d7d5130ce93b880e4835e634dad03504ebb

---


# 种子成员(nms:seedMember)

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
                  <td>国家／地区（国家／地区）</td>
                  <td>国家／地区</td>
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
                  <td>createdBy(userBase)</td>
                  <td>创建者</td>
                  <td>链接 </td>
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
                  <td>emailRendering</td>
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
                  <td>geoUnit(geoUnitBase)</td>
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
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>marketingCloudId</td>
                  <td>Marketing Cloud ID</td>
                  <td>string(256)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobileApp</td>
                  <td>移动应用程序</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>移动</td>
                  <td>字符串(32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>modifiedBy(userBase)</td>
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
                  <td>个人资料</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>nms_rtEvent</td>
                  <td>活动</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit(orgUnitBase)</td>
                  <td>组织单位</td>
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
                  <td>证明</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotification</td>
                  <td>推送通知</td>
                  <td>string(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>registrationToken</td>
                  <td>注册令牌</td>
                  <td>string(256)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sampleData</td>
                  <td>样本数据</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sms</td>
                  <td>移动</td>
                  <td>string(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink（状态）</td>
                  <td>州</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>targetData</td>
                  <td>扩展</td>
                  <td>字符串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>缩略图</td>
                  <td>缩略图</td>
                  <td>string(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>标题</td>
                  <td>测试配置文件</td>
                  <td>string(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>陷阱</td>
                  <td>陷印</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
            </table>

## 滤镜

按事件类型(byEventType)

<table>
        <tr>
        <th>名称</th>
        <th>类型</th>
        </tr>
        <tr>
        <td>eventType</td>
        <td>字符串</td>
        </tr>
    </table>

按名称或标签（按文本）

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

按使用（按使用）

<table>
        <tr>
        <th>名称</th>
        <th>类型</th>
        </tr>
        <tr>
        <td>陷阱</td>
        <td>布尔值</td>
        </tr>
        <tr>
        <td>emailRendering</td>
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