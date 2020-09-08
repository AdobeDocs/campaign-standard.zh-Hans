---
title: 数据模型
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
source-git-commit: 1f15e28bed22e3defb29f16875fcf4c07f4af5a3
workflow-type: tm+mt
source-wordcount: '1204'
ht-degree: 1%

---


# 营销历史(nms:history)

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
                  <td>年龄</td>
                  <td>年龄</td>
                  <td>整数 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>birthDate</td>
                  <td>出生日期</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackList</td>
                  <td>不再联系(由任何渠道)</td>
                  <td>布尔 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListEmail</td>
                  <td>不再通过电子邮件联系</td>
                  <td>布尔 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListFax</td>
                  <td>不再通过传真联系</td>
                  <td>布尔 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListMobile</td>
                  <td>不再通过SMS联系</td>
                  <td>布尔 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPhone</td>
                  <td>不再通过电话联系</td>
                  <td>布尔 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPostalMail</td>
                  <td>不再通过直邮联系</td>
                  <td>布尔 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPushnotification</td>
                  <td>不再通过推送通知进行联系</td>
                  <td>布尔 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countBroadLogEvents</td>
                  <td>CountBroadLogEvents</td>
                  <td>整数 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countSubHistoEvents</td>
                  <td>CountSubHistoEvents</td>
                  <td>整数 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>国家／地区（国家／地区）</td>
                  <td>国家／地区</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countryIsoA2</td>
                  <td>ISO A2代码</td>
                  <td>字符串(2)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>已创建</td>
                  <td>已创建</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy(userBase)</td>
                  <td>创建者</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusHobbieslink(cusHespoias)</td>
                  <td>CusHobbieslink</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusLastTransactionDate</td>
                  <td>上次交易日期</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusTransactionslink</td>
                  <td>交易</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>电子邮件</td>
                  <td>电子邮件</td>
                  <td>string(128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>事件</td>
                  <td>异构资源</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>传真</td>
                  <td>传真</td>
                  <td>字符串(32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>firstName</td>
                  <td>名字</td>
                  <td>字符串(30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>性别</td>
                  <td>性别</td>
                  <td>明细列表（字节） </td>
                  <td>
                     <ul>
                        <li>未指定——未知- 0</li>
                        <li>男——男- 1</li>
                        <li>女——女- 2</li>
                        <li>无效值- __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>是外部资源</td>
                  <td>布尔 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>kpiAndChart</td>
                  <td>KpiAndChart</td>
                  <td>物料 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>上次修改时间</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastName</td>
                  <td>姓氏</td>
                  <td>字符串(50)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>位置</td>
                  <td>位置</td>
                  <td>物料 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>middleName</td>
                  <td>中间名</td>
                  <td>字符串(30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>minBroadLogEvents</td>
                  <td>MinBroadLogEvents</td>
                  <td> </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>minSubHistoEvents</td>
                  <td>MinSubHistoEvents</td>
                  <td> </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>移动电话</td>
                  <td>手机</td>
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
                  <td>电话</td>
                  <td>电话</td>
                  <td>字符串(32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>问候语</td>
                  <td>标题</td>
                  <td>字符串(20)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink（状态）</td>
                  <td>州</td>
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
                  <td>时区</td>
                  <td>时区</td>
                  <td>明细列表（字符串）(64)</td>
                  <td>
                     <ul>
                        <li>(GMT-02:00)中大西洋——大西洋_南_格鲁吉亚——大西洋／南_格鲁吉亚</li>
                        <li>(GMT+02:00)安曼——亚洲_安曼——亚洲／安曼</li>
                        <li>(GMT-03:00)布拉西——美国圣保罗——美国／圣保罗</li>
                        <li>(GMT+06:00)阿斯塔纳，达卡——亚洲_达卡——亚洲／达卡</li>
                        <li>(GMT+06:00)新西伯利亚——亚洲_新西伯利亚——亚洲／新西伯利亚</li>
                        <li>(GMT+02:00)温得和克——非洲_温得和克——非洲／温得和克</li>
                        <li>(GMT+04:00)高加索，埃里温——亚洲_埃里温——亚洲／埃里温</li>
                        <li>(GMT-04:00)马瑙斯——美国_马瑙斯——美国／马瑙斯</li>
                        <li>(GMT+03:30)德黑兰——亚洲_德黑兰——亚洲／德黑兰</li>
                        <li>(GMT+12:00)奥克兰，惠灵顿——太平洋——奥克兰——太平洋／奥克兰</li>
                        <li>(GMT+02:00)耶路撒冷——亚洲_耶路撒冷——亚洲／耶路撒冷</li>
                        <li>(GMT+03:00)莫斯科，圣彼得堡，伏尔加格勒——欧洲_莫斯科——欧洲／莫斯科</li>
                        <li>(GMT+09:30)阿德莱德——澳大利亚_阿德莱德——澳大利亚／阿德莱德</li>
                        <li>(GMT+10:00)堪培拉，墨尔本，悉尼——澳大利亚_堪培拉——澳大利亚／堪培拉</li>
                        <li>(GMT+08:00)珀斯——澳大利亚_珀斯——澳大利亚／珀斯</li>
                        <li>(GMT+09:00)雅库茨克——亚洲_雅库茨克——亚洲／雅库茨克</li>
                        <li>(GMT-10:00)哈瓦伊——太平洋_檀香山——太平洋／檀香山</li>
                        <li>(GMT+04:00)巴库——亚洲_巴库——亚洲／巴库</li>
                        <li>(GMT+10:00)符拉迪沃斯托克——亚洲_符拉迪沃斯托克——亚洲／符拉迪沃斯托克</li>
                        <li>(GMT+09:00)首尔——亚洲_首尔——亚洲／首尔</li>
                        <li>(GMT+01:00)萨拉热窝，斯科普列，索非亚，华沙，萨格勒布——欧洲_萨拉热窝——欧洲／萨拉热窝</li>
                        <li>(GMT+04:00)阿布扎比，马斯喀特——亚洲_马斯喀特——亚洲／马斯喀特</li>
                        <li>(GMT+08:00)吉隆坡，新加坡——亚洲_吉隆坡——亚洲／吉隆坡</li>
                        <li>(GMT+09:00)大坂，札幌，东京——亚洲_东京——亚洲／东京</li>
                        <li>(GMT+10:00)布里斯班——澳大利亚_布里斯班——澳大利亚／布里斯班</li>
                        <li>(GMT+05:30)斯里哈亚华登尼普拉——亚洲_科伦坡——亚洲／科伦坡</li>
                        <li>(GMT+02:00)哈拉雷，比勒陀利亚——非洲_哈拉雷——非洲／哈拉雷</li>
                        <li>(GMT+08:00)乌兰巴托——亚洲_乌兰巴托——亚洲／乌兰巴托</li>
                        <li>(GMT-02:00)格林威治平均时间减2小时- Gmt_m2 - Etc/GMT+2</li>
                        <li>(GMT-03:00)格林威治平均时间减3小时- Gmt_m3 - Etc/GMT+3</li>
                        <li>(GMT-01:00)格林威治平均时间减1小时- Gmt_m1 - Etc/GMT+1</li>
                        <li>(GMT-06:00)格林威治平均时间减6小时- Gmt_m6 - Etc/GMT+6</li>
                        <li>(GMT-07:00)格林威治平均时间减7小时- Gmt_m7 - Etc/GMT+7</li>
                        <li>(GMT-04:00)格林威治平均时间减4小时- Gmt_m4 - Etc/GMT+4</li>
                        <li>(GMT)卡萨布兰卡——非洲_卡萨布兰卡——非洲／卡萨布兰卡</li>
                        <li>(GMT+05:30)加尔各答，钦奈，孟买，新德里——亚洲_加尔各答——亚洲／加尔各答</li>
                        <li>(GMT-11:00)格林威治平均时间减11小时- Gmt_m11 - Etc/GMT+11</li>
                        <li>(GMT-09:00)格林威治平均时间减9小时- Gmt_m9 - Etc/GMT+9</li>
                        <li>(GMT-03:30)纽芬兰——美国圣约翰——美国／圣约翰</li>
                        <li>(GMT+03:00)格林威治平均时间加3小时- Gmt_p3 - Etc/GMT-3</li>
                        <li>(GMT-04:30)加拉加斯——美洲_加拉加斯——美洲／加拉加斯</li>
                        <li>(GMT+01:00)阿姆斯特丹，柏林，伯尔尼，罗马，斯德哥尔摩，维也纳——欧洲_柏林——欧洲／柏林</li>
                        <li>(GMT-07:00)奇瓦瓦，拉巴斯，马萨特兰——美国_奇瓦瓦——美国／奇瓦瓦</li>
                        <li>(GMT+03:00)内罗毕——非洲_内罗毕——非洲／内罗毕</li>
                        <li>(GMT-04:00)亚松森——美国_亚松森——美国／亚松森</li>
                        <li>(GMT+03:00)巴格达德——亚洲_巴格达——亚洲／巴格达</li>
                        <li>(GMT-10:00)格林威治平均时间减10小时- Gmt_m10 - Etc/GMT+10</li>
                        <li>(GMT-03:00)格陵兰——美洲_戈德萨布——美洲／戈德萨布</li>
                        <li>(GMT+02:00)达马斯——亚洲_大马士革——亚洲／大马士革</li>
                        <li>(GMT-11:00)萨摩亚——太平洋_萨摩亚——太平洋／萨摩亚</li>
                        <li>(GMT-05:00)波哥大，利马，基多——美国_波哥大——美国／波哥大</li>
                        <li>(GMT+01:00)布鲁塞尔，哥本哈根，马德里，巴黎——欧洲_巴黎——欧洲／巴黎</li>
                        <li>(GMT+08:00)北京，重庆，香港，乌鲁木齐——亚洲_上海——亚洲／上海</li>
                        <li>(GMT+12:00)菲吉——太平洋_斐济——太平洋／斐济</li>
                        <li>(GMT+02:00)雅典，伊斯坦布尔，明斯克——欧洲_雅典——欧洲／雅典</li>
                        <li>(GMT+04:00)第比利斯——亚洲_第比利斯——亚洲／第比利斯</li>
                        <li>无效值- __Invalid_value__ - __Invalid_value__</li>
                        <li>(GMT+05:45)加德满都——亚洲_加德满都——亚洲／加德满都</li>
                        <li>(GMT-05:00)印第安纳州（东部）-美国_印第安纳波利斯——美国／印第安纳波利斯</li>
                        <li>(GMT-01:00)佛得角群岛——大西洋_佛得角——大西洋／佛得角</li>
                        <li>(GMT+04:00)路易港——印度_毛里求斯——印度／毛里求斯</li>
                        <li>(GMT+08:00)台北——亚洲_台北——亚洲／台北</li>
                        <li>(GMT+06:30)仰光——亚洲_仰光——亚洲／仰光</li>
                        <li>(GMT+11:00)马加丹，所罗门群岛，新喀里多尼亚——太平洋——瓜达卡纳尔——太平洋／瓜达卡纳尔</li>
                        <li>(GMT+02:00)开罗——非洲_开罗——非洲／开罗</li>
                        <li>(GMT+05:00)叶卡捷琳堡——亚洲_叶卡捷琳堡——亚洲／叶卡捷琳堡</li>
                        <li>(GMT+08:00)伊尔库茨克——亚洲_伊尔库茨克——亚洲／伊尔库茨克</li>
                        <li>(GMT+10:00)关岛，莫尔兹比港——太平洋_关岛——太平洋／关岛</li>
                        <li>(GMT-04:00)大西洋标准时间（加拿大）- America_Halifax - America/Halifax</li>
                        <li>(GMT)格林威治时间- GMT - GMT</li>
                        <li>默认——无——无</li>
                        <li>(GMT-04:00)拉巴斯——美国_拉巴斯——美国／拉巴斯</li>
                        <li>(GMT-06:00)瓜达拉哈拉，墨西哥，蒙特雷——美洲_墨西哥_城——美洲／墨西哥_城</li>
                        <li>(GMT+09:30)达尔文——澳大利亚_达尔文——澳大利亚／达尔文</li>
                        <li>(GMT-05:00)东部（美国和加拿大）- America_New_York - America/New_York</li>
                        <li>(GMT-05:00)格林威治平均时间减5小时- Gmt_m5 - Etc/GMT+5</li>
                        <li>(GMT+05:00)伊斯兰堡，卡拉奇，大其木——亚洲_卡拉奇——亚洲／卡拉奇</li>
                        <li>(GMT+03:00)科韦特，里亚德——亚洲_利雅得——亚洲／利雅得</li>
                        <li>(GMT-08:00)格林威治平均时间减8小时- Gmt_m8 - Etc/GMT+8</li>
                        <li>(GMT-01:00)亚速尔群岛——大西洋_亚速尔群岛——大西洋／亚速尔群岛</li>
                        <li>(GMT+07:00)曼谷，河内，雅加达——亚洲_曼谷——亚洲／曼谷</li>
                        <li>(GMT)蒙罗维亚——非洲_蒙罗维亚——非洲／蒙罗维亚</li>
                        <li>(GMT-09:00)阿拉斯加——美国_安克拉治——美国／安克拉治</li>
                        <li>(GMT+01:00)贝尔格莱德，布拉迪斯拉发，布达佩斯，卢布尔雅那，布拉格——欧洲_贝尔格莱德——欧洲／贝尔格莱德</li>
                        <li>(GMT)雷克雅未克——大西洋_雷克雅未克——大西洋／雷克雅未克</li>
                        <li>(GMT+02:00)布卡斯特——欧洲_布加勒斯特——欧洲／布加勒斯特</li>
                        <li>(GMT+05:00)格林威治平均时间加5小时- Gmt_p5 - Etc/GMT-5</li>
                        <li>(GMT+04:00)格林威治平均时间加4小时- Gmt_p4 - Etc/GMT-4</li>
                        <li>(GMT+07:00)格林威治平均时间加7小时- Gmt_p7 - Etc/GMT-7</li>
                        <li>(GMT+06:00)格林威治平均时间加6小时- Gmt_p6 - Etc/GMT-6</li>
                        <li>(GMT+01:00)格林威治平均时间加1小时- Gmt_p1 - Etc/GMT-1</li>
                        <li>(GMT-08:00)太平洋（美国和加拿大）- America_Los_Angeles - America/Los_Angeles</li>
                        <li>(GMT+02:00)格林威治平均时间加2小时- Gmt_p2 - Etc/GMT-2</li>
                        <li>(GMT+07:00)克拉斯诺亚尔斯克——亚洲_克拉斯诺亚尔斯克——亚洲／克拉斯诺亚尔斯克</li>
                        <li>(GMT+09:00)格林威治平均时间加9小时- Gmt_p9 - Etc/GMT-9</li>
                        <li>(GMT+08:00)格林威治平均时间加8小时- Gmt_p8-Etc/GMT-8</li>
                        <li>(GMT+10:00)霍巴特——澳大利亚_霍巴特——澳大利亚／霍巴特</li>
                        <li>(GMT+13:00)努库阿洛法——太平洋_通加塔普——太平洋／通加塔普</li>
                        <li>(GMT-06:00)中美洲——美国_里贾纳——美国／里贾纳</li>
                        <li>(GMT-03:00)布宜诺斯艾利斯，卡宴，福塔雷萨——美洲_布宜诺斯艾利斯——美洲／布宜诺斯艾利斯</li>
                        <li>(GMT-07:00)洛矶山脉（美国和加拿大）-美国_丹佛——美国／丹佛</li>
                        <li>(GMT+01:00)中非——西非——罗安达——非洲／罗安达</li>
                        <li>(GMT+02:00)赫尔辛基，基辅，里加，索非亚，塔林，维尔纽斯——欧洲_赫尔辛基——欧洲／赫尔辛基</li>
                        <li>(GMT)格林威治平均时间：都柏林、爱丁堡、里斯本、伦敦——欧洲_伦敦——欧洲／伦敦</li>
                        <li>(GMT-07:00)亚利桑那——美国_菲尼克斯——美国／菲尼克斯</li>
                        <li>(GMT+02:00)贝鲁特——亚洲_贝鲁特——亚洲／贝鲁特</li>
                        <li>(GMT+04:30)喀布尔——亚洲_喀布尔——亚洲／喀布尔</li>
                        <li>(GMT-06:00)中心（美国和加拿大）- America_Chicago - America/Chicago</li>
                        <li>(GMT+11:00)格林威治平均时间加11小时- Gmt_p11 - Etc/GMT-11</li>
                        <li>(GMT+10:00)格林威治平均时间加10小时- Gmt_p10 - Etc/GMT-10</li>
                        <li>(GMT+13:00)格林威治平均时间加13小时- Gmt_p13 - Etc/GMT-13</li>
                        <li>(GMT+12:00)格林威治平均时间加12小时- Gmt_p12 - Etc/GMT-12</li>
                        <li>(GMT-04:00)圣地亚哥——美国_圣地亚哥——美国／圣地亚哥</li>
                        <li>(GMT-03:00)蒙得维的亚——美国_蒙得维的亚——美国／蒙得维的亚</li>
                        <li>(GMT-04:00)库亚巴——美国_库亚巴——美国／库亚巴</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>标题</td>
                  <td>用户档案</td>
                  <td>string(255)</td>
                  <td> </td>
               </tr>
            </table>

## 过滤器

生日（生日）

<table>
<tr>
<th>名称</th>
<th>类型</th>
</tr>
<tr>
<td>includeStart</td>
<td>布尔</td>
</tr>
<tr>
<td>previousUnitsValue</td>
<td>整数</td>
</tr>
<tr>
<td>nextUnitsValue</td>
<td>整数</td>
</tr>
<tr>
<td>结束日</td>
<td>日期</td>
</tr>
<tr>
<td>精度</td>
<td>明细列表</td>
</tr>
<tr>
<td>relativeValue</td>
<td>字符串</td>
</tr>
<tr>
<td>月</td>
<td>日期</td>
</tr>
<tr>
<td>运算符</td>
<td>明细列表</td>
</tr>
<tr>
<td>includeEnd</td>
<td>布尔</td>
</tr>
<tr>
<td>endMonth</td>
<td>日期</td>
</tr>
<tr>
<td>类型</td>
<td>明细列表</td>
</tr>
<tr>
<td>天</td>
<td>日期</td>
</tr>
</table>

通过电子邮件（通过电子邮件）

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

按键(byKeysProfile)

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

按姓名或电子邮件（按文本）

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

按静态受众（按StaticAudience）

<table>
<tr>
<th>名称</th>
<th>类型</th>
</tr>
<tr>
<td>受众</td>
<td>链接</td>
</tr>
</table>

已单击(hasClickedDelivery)

<table>
<tr>
<th>名称</th>
<th>类型</th>
</tr>
<tr>
<td>投放</td>
<td>链接</td>
</tr>
</table>

已打开(hasOpenedDelivery)

<table>
<tr>
<th>名称</th>
<th>类型</th>
</tr>
<tr>
<td>投放</td>
<td>链接</td>
</tr>
</table>

用户档案(用户档案)

<table>
<tr>
<th>名称</th>
<th>类型</th>
</tr>
<tr>
<td>用户档案</td>
<td>链接</td>
</tr>
</table>

已接收(hasReceivedDelivery)

<table>
<tr>
<th>名称</th>
<th>类型</th>
</tr>
<tr>
<td>投放</td>
<td>链接</td>
</tr>
</table>

订阅者（订阅者）

<table>
<tr>
<th>名称</th>
<th>类型</th>
</tr>
<tr>
<td>服务</td>
<td>链接</td>
</tr>
</table>