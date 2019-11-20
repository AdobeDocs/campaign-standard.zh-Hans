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


# 程序(nms:program)

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
                  <td>活动</td>
                  <td>活动</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>builtIn</td>
                  <td>内置应用程序对象</td>
                  <td>布尔值 </td>
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
                  <td>end</td>
                  <td>结束日期</td>
                  <td>date </td>
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
                  <td>isTemplate</td>
                  <td>模板</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>标签</td>
                  <td>标签</td>
                  <td>string(128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>上次修改时间</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>logicalStatus</td>
                  <td>执行状态</td>
                  <td>枚举（字符串）(255)</td>
                  <td>
                     <ul>
                        <li>进行中——开始——开始</li>
                        <li>编辑——版本——版本</li>
                        <li>完成——完成——完成</li>
                        <li>警告——警告——警告</li>
                        <li>错误——错误——错误</li>
                        <li>无效值- __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
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
                  <td>orgUnit(orgUnitBase)</td>
                  <td>组织单位</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>parent(programBase)</td>
                  <td>父程序</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>实时报告</td>
                  <td>项目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>开始</td>
                  <td>开始日期</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>状态</td>
                  <td>状态</td>
                  <td>枚举（字节） </td>
                  <td>
                     <ul>
                        <li>开始——开始- 1</li>
                        <li>编辑——版本- 0</li>
                        <li>完成——完成- 2</li>
                        <li>无效值- __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>模板（程序）</td>
                  <td>计划模板</td>
                  <td>链接 </td>
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
                  <td>计划</td>
                  <td>string(255)</td>
                  <td> </td>
               </tr>
            </table>

## 滤镜

按逻辑状态(byLogicalStatus)

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>状态</td>
    <td>枚举</td>
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

按期间（按期间）

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>timePeriod</td>
    <td>字符串</td>
    </tr>
</table>

包括来自异构列表的连续提交(withContinuous)

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>withContinuous</td>
    <td>布尔值</td>
    </tr>
</table>

包括子程序(withParent)

<table>
        <tr>
        <th>名称</th>
        <th>类型</th>
        </tr>
        <tr>
        <td>withParent</td>
        <td>布尔值</td>
        </tr>
    </table>

仅限合格的父母（合格的父母）

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>程序</td>
    <td>链接</td>
    </tr>
</table>

在给定期间内计划（按计划）

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>date</td>
    </tr>
</table>

在给定期间（按日历）提供

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>date</td>
    </tr>
</table>