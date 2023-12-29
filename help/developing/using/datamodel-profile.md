---
title: 数据模型配置文件
description: 了解数据模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 652c22a5-7fff-4d08-9396-f0b292aaca76
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '1392'
ht-degree: 10%

---

# 个人资料(nms：recipient)

## 对象说明

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
                  <td>appSubscription</td>
                  <td>应用程序订阅</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>birthDate</td>
                  <td>出生日期</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>黑名单</td>
                  <td>不再联系（通过任何渠道）</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListEmail</td>
                  <td>不再电子邮件联系</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListFax</td>
                  <td>不再传真联系</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListMobile</td>
                  <td>不再通过短信联系</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPhone</td>
                  <td>不再电话联系</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPostMail</td>
                  <td>不再直邮联系</td>
                  <td>布尔值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPushnotification</td>
                  <td>不再通过推送通知联系</td>
                  <td>布尔值 </td>
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
                  <td>创建时间</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy (userBase)</td>
                  <td>创建者</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cryptedId</td>
                  <td>加密ID</td>
                  <td>字符串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusHobbieslink (cusHobbies)</td>
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
                  <td>域</td>
                  <td>电子邮件域</td>
                  <td>字符串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>电子邮件</td>
                  <td>电子邮件</td>
                  <td>字符串(128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailFormat</td>
                  <td>电子邮件格式</td>
                  <td>枚举（字节） </td>
                  <td>
                     <ul>
                        <li>文本 — 文本 — 1</li>
                        <li>HTML- html - 2</li>
                        <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
                        <li>未知 — 未知 — 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>emailStatus (addressStatus)</td>
                  <td>有关电子邮件的信息</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>excludeLogs</td>
                  <td>排除日志</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>externalId</td>
                  <td>外部资源Id</td>
                  <td>string(100) </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>传真</td>
                  <td>传真</td>
                  <td>字符串(32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>名字</td>
                  <td>名字</td>
                  <td>字符串(30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>性别</td>
                  <td>性别</td>
                  <td>枚举（字节） </td>
                  <td>
                     <ul>
                        <li>未指定 — 未知 — 0</li>
                        <li>男 — 男 — 1</li>
                        <li>女 — 女 — 2</li>
                        <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
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
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>姓氏</td>
                  <td>姓氏</td>
                  <td>字符串(50)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>位置</td>
                  <td>位置</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>日志</td>
                  <td>投放日志</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>中间名</td>
                  <td>中间名</td>
                  <td>字符串(30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>移动电话</td>
                  <td>移动</td>
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
                  <td>电话</td>
                  <td>电话</td>
                  <td>字符串(32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>位置</td>
                  <td>位置</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>邮政地址</td>
                  <td>邮政地址</td>
                  <td>项 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>salutation</td>
                  <td>标题</td>
                  <td>string (20)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink（状态）</td>
                  <td>状态</td>
                  <td>链接 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subHisto</td>
                  <td>订阅历史记录</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>订阅</td>
                  <td>订阅</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>缩略图</td>
                  <td>缩略图</td>
                  <td>字符串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>时区</td>
                  <td>时区</td>
                  <td>枚举（字符串）(64)</td>
                  <td>
                     <ul>
                        <li>(GMT-02:00)中大西洋 — 大西洋_南佐治亚 — 大西洋/南佐治亚</li>
                        <li>(GMT+02:00)安曼 — 亚洲_安曼 — 亚洲/安曼</li>
                        <li>(GMT-03:00)布拉西 — 美洲_圣保罗 — 美洲/圣保罗</li>
                        <li>(GMT+06:00)阿斯塔纳，达卡 — 亚洲_达卡 — 亚洲/达卡</li>
                        <li>(GMT+06:00)新西伯利亚 — 亚洲_新西伯利亚 — 亚洲/新西伯利亚</li>
                        <li>(GMT+02:00)温得和克 — 非洲_温得和克 — 非洲/温得和克</li>
                        <li>(GMT+04:00)高加索，埃里温 — 亚洲_埃里温 — 亚洲/埃里温</li>
                        <li>(GMT-04:00)马瑙斯 — 美洲_马瑙斯 — 美洲/马瑙斯</li>
                        <li>(GMT+03:30)德黑兰市 — 亚洲_德黑兰 — 亚洲/德黑兰</li>
                        <li>(GMT+12:00)奥克兰，惠灵顿 — 太平洋_奥克兰 — 太平洋/奥克兰</li>
                        <li>(GMT+02:00)耶路撒冷 — 亚洲_耶路撒冷 — 亚洲/耶路撒冷</li>
                        <li>(GMT+03:00)莫斯科，圣彼得堡，伏尔加格勒 — 欧洲_莫斯科 — 欧洲/莫斯科</li>
                        <li>(GMT+09:30)阿德莱德 — 澳大利亚_阿德莱德 — 澳大利亚/阿德莱德</li>
                        <li>(GMT+10:00)堪培拉，墨尔本，悉尼 — 澳大利亚_堪培拉 — 澳大利亚/堪培拉</li>
                        <li>(GMT+08:00)珀斯 — 澳大利亚珀斯 — 澳大利亚/珀斯</li>
                        <li>(GMT+09:00)雅库茨克 — 亚洲_雅库茨克 — 亚洲/雅库茨克</li>
                        <li>(GMT-10:00)夏威夷 — 太平洋_檀香山 — 太平洋/檀香山</li>
                        <li>(GMT+04:00)巴库 — 亚洲_巴库 — 亚洲/巴库</li>
                        <li>(GMT+10:00)符拉迪沃斯托克 — 亚洲_符拉迪沃斯托克 — 亚洲/符拉迪沃斯托克</li>
                        <li>(GMT+09:00)首尔 — 亚洲_首尔 — 亚洲/首尔</li>
                        <li>(GMT+01:00)萨拉热窝，斯科普列，索菲亚，华沙，萨格勒布 — 欧洲_萨拉热窝 — 欧洲/萨拉热窝</li>
                        <li>(GMT+04:00)阿布扎比，马斯喀特 — 亚洲_马斯喀特 — 亚洲/马斯喀特</li>
                        <li>(GMT+08:00)吉隆坡、新加坡 — 亚洲_吉隆坡 — 亚洲/吉隆坡</li>
                        <li>(GMT+09:00)大阪，札幌，东京 — 亚洲_东京 — 亚洲/东京</li>
                        <li>(GMT+10:00)布里斯班 — 澳大利亚_布里斯班 — 澳大利亚/布里斯班</li>
                        <li>(GMT+05:30)斯里哈亚瓦登尼普拉 — 亚洲_科伦坡 — 亚洲/科伦坡</li>
                        <li>(GMT+02:00)哈拉雷，比勒陀利亚 — 非洲_哈拉雷 — 非洲/哈拉雷</li>
                        <li>(GMT+08:00)乌兰巴托 — 亚洲_乌兰巴托 — 亚洲/乌兰巴托</li>
                        <li>(GMT-02:00)格林威治标准时间减2小时 — Gmt_m2 - Etc/GMT+2</li>
                        <li>(GMT-03:00)格林威治标准时间减3小时 — Gmt_m3 - Etc/GMT+3</li>
                        <li>(GMT-01:00)格林威治标准时间减1小时 — Gmt_m1 - Etc/GMT+1</li>
                        <li>(GMT-06:00)格林威治标准时间减6小时 — Gmt_m6 - Etc/GMT+6</li>
                        <li>(GMT-07:00)格林威治标准时间减7小时 — Gmt_m7 - Etc/GMT+7</li>
                        <li>(GMT-04:00)格林威治标准时间减4小时 — Gmt_m4 - Etc/GMT+4</li>
                        <li>(GMT)卡萨布兰卡 — 非洲_卡萨布兰卡 — 非洲/卡萨布兰卡</li>
                        <li>(GMT+05:30)加尔各答，金奈，孟买，新德里 — 亚洲_加尔各答 — 亚洲/加尔各答</li>
                        <li>(GMT-11:00)格林威治标准时间减11小时 — Gmt_m11 - Etc/GMT+11</li>
                        <li>(GMT-09:00)格林威治标准时间减9小时 — Gmt_m9 - Etc/GMT+9</li>
                        <li>(GMT-03:30)纽芬兰 — 美洲_圣约翰 — 美洲/圣约翰</li>
                        <li>(GMT+03:00)格林威治标准时间加3小时 — Gmt_p3 - Etc/GMT-3</li>
                        <li>(GMT-04:30)加拉加斯 — 美洲_加拉加斯 — 美洲/加拉加斯</li>
                        <li>(GMT+01:00)阿姆斯特丹，柏林，伯尔尼，罗马，斯德哥尔摩，维也纳 — 欧洲_柏林 — 欧洲/柏林</li>
                        <li>(GMT-07:00)奇瓦瓦，拉巴斯，马萨特兰 — 美洲_奇瓦瓦 — 美洲/奇瓦瓦</li>
                        <li>(GMT+03:00)内罗毕 — 非洲_内罗毕 — 非洲/内罗毕</li>
                        <li>(GMT-04:00)亚松森 — 美洲_亚松森 — 美洲/亚松森</li>
                        <li>(GMT+03:00)巴格达 — 亚洲_巴格达 — 亚洲/巴格达</li>
                        <li>(GMT-10:00)格林威治标准时间减10小时 — Gmt_m10 - Etc/GMT+10</li>
                        <li>(GMT-03:00)格陵兰 — 美洲_戈特哈布 — 美洲/戈特哈布</li>
                        <li>(GMT+02:00)达马斯 — 亚洲_大马士革 — 亚洲/大马士革</li>
                        <li>(GMT-11:00)萨摩亚 — 太平洋_萨摩亚 — 太平洋/萨摩亚</li>
                        <li>(GMT-05:00)波哥大，利马，基多 — 美洲_波哥大 — 美洲/波哥大</li>
                        <li>(GMT+01:00)布鲁塞尔，哥本哈根，马德里，巴黎 — 欧洲_巴黎 — 欧洲/巴黎</li>
                        <li>(GMT+08:00)北京，重庆，香港，乌鲁木齐 — 亚洲_上海 — 亚洲/上海</li>
                        <li>(GMT+12:00)斐济 — 太平洋_斐济 — 太平洋/斐济</li>
                        <li>(GMT+02:00)雅典，伊斯坦布尔，明斯克 — 欧洲_雅典 — 欧洲/雅典</li>
                        <li>(GMT+04:00)第比利斯 — 亚洲_第比利斯 — 亚洲/第比利斯</li>
                        <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
                        <li>(GMT+05:45)加德满都 — 亚洲_加德满都 — 亚洲/加德满都</li>
                        <li>(GMT-05:00)印第安纳州（东部） — 美洲_印第安纳波利斯 — 美洲/印第安纳波利斯</li>
                        <li>(GMT-01:00)佛得角群岛 — 大西洋_佛得角 — 大西洋/佛得角</li>
                        <li>(GMT+04:00)路易港 — 印度洋_毛里求斯 — 印度洋/毛里求斯</li>
                        <li>(GMT+08:00)台北 — 亚洲_台北 — 亚洲/台北</li>
                        <li>(GMT+06:30)仰光 — 亚洲_仰光 — 亚洲/仰光</li>
                        <li>(GMT+11:00)马加丹，所罗门群岛，新喀里多尼亚 — 太平洋_瓜达尔卡纳尔 — 太平洋/瓜达尔卡纳尔</li>
                        <li>(GMT+02:00)开罗 — 非洲_开罗 — 非洲/开罗</li>
                        <li>(GMT+05:00)叶卡捷琳堡 — 亚洲_叶卡捷琳堡 — 亚洲/叶卡捷琳堡</li>
                        <li>(GMT+08:00)伊尔库茨克 — 亚洲_伊尔库茨克 — 亚洲/伊尔库茨克</li>
                        <li>(GMT+10:00)关岛，莫尔斯比港 — 太平洋关岛 — 太平洋/关岛</li>
                        <li>(GMT-04:00)大西洋标准时间（加拿大） — 美洲_哈利法克斯 — 美洲/哈利法克斯</li>
                        <li>(GMT)格林威治标准时间 — 格林威治标准时间 — 格林威治标准时间</li>
                        <li>默认 — 无 — 无</li>
                        <li>(GMT-04:00)拉巴斯 — 美洲_拉巴斯 — 美洲/拉巴斯</li>
                        <li>(GMT-06:00)瓜达拉哈拉，墨西哥，蒙特雷 — 美洲_墨西哥城 — 美洲/墨西哥城</li>
                        <li>(GMT+09:30)达尔文 — 澳大利亚_达尔文 — 澳大利亚/达尔文</li>
                        <li>(GMT-05:00)东部标准时间（美国和加拿大） — 美洲_纽约 — 美洲/纽约</li>
                        <li>(GMT-05:00)格林威治标准时间减5小时 — Gmt_m5 - Etc/GMT+5</li>
                        <li>(GMT+05:00)伊斯兰堡，卡拉奇，塔肯特 — 亚洲_卡拉奇 — 亚洲/卡拉奇</li>
                        <li>(GMT+03:00)科韦特，利雅德 — 亚洲_利雅得 — 亚洲/利雅得</li>
                        <li>(GMT-08:00)格林威治标准时间减8小时 — Gmt_m8 - Etc/GMT+8</li>
                        <li>(GMT-01:00)亚速尔群岛 — 大西洋_亚速尔群岛 — 大西洋/亚速尔群岛</li>
                        <li>(GMT+07:00)曼谷，河内，雅加达 — 亚洲_曼谷 — 亚洲/曼谷</li>
                        <li>(GMT)蒙罗维亚 — 非洲_蒙罗维亚 — 非洲/蒙罗维亚</li>
                        <li>(GMT-09:00)阿拉斯加 — 美洲_安克雷奇 — 美洲/安克雷奇</li>
                        <li>(GMT+01:00)贝尔格莱德，布拉迪斯拉发，布达佩斯，卢布尔雅那，布拉格 — 欧洲_贝尔格莱德 — 欧洲/贝尔格莱德</li>
                        <li>(GMT)雷克雅未克 — 大西洋_雷克雅未克 — 大西洋/雷克雅未克</li>
                        <li>(GMT+02:00)布加勒斯特 — 欧洲_布加勒斯特 — 欧洲/布加勒斯特</li>
                        <li>(GMT+05:00)格林威治标准时间加5小时 — Gmt_p5 - Etc/GMT-5</li>
                        <li>(GMT+04:00)格林威治标准时间加4小时 — Gmt_p4 - Etc/GMT-4</li>
                        <li>(GMT+07:00)格林威治标准时间加7小时 — Gmt_p7 - Etc/GMT-7</li>
                        <li>(GMT+06:00)格林威治标准时间加6小时 — Gmt_p6 - Etc/GMT-6</li>
                        <li>(GMT+01:00)格林威治标准时间加1小时 — Gmt_p1 - Etc/GMT-1</li>
                        <li>(GMT-08:00)太平洋（美国和加拿大） — 美洲_洛杉矶 — 美洲/洛杉矶</li>
                        <li>(GMT+02:00)格林威治标准时间加2小时 — Gmt_p2 - Etc/GMT-2</li>
                        <li>(GMT+07:00)克拉斯诺亚尔斯克 — 亚洲_克拉斯诺亚尔斯克 — 亚洲/克拉斯诺亚尔斯克</li>
                        <li>(GMT+09:00)格林威治标准时间加9小时 — Gmt_p9 - Etc/GMT-9</li>
                        <li>(GMT+08:00)格林威治标准时间加8小时 — Gmt_p8 - Etc/GMT-8</li>
                        <li>(GMT+10:00)霍巴特 — 澳大利亚_霍巴特 — 澳大利亚/霍巴特</li>
                        <li>(GMT+13:00)努库阿洛法 — 太平洋_汤加塔布 — 太平洋/汤加塔布</li>
                        <li>(GMT-06:00)中美洲 — 美洲_里贾纳 — 美洲/里贾纳</li>
                        <li>(GMT-03:00)布宜诺斯艾利斯，卡宴，福塔莱萨 — 美洲_布宜诺斯艾利斯 — 美洲/布宜诺斯艾利斯</li>
                        <li>(GMT-07:00)落基山脉（美国和加拿大） — 美洲_丹佛 — 美洲/丹佛</li>
                        <li>(GMT+01:00)中非 — 西部 — 非洲_罗安达 — 非洲/罗安达</li>
                        <li>(GMT+02:00)赫尔辛基，基辅，里加，索菲亚，塔林，维尔纽斯 — 欧洲_赫尔辛基 — 欧洲/赫尔辛基</li>
                        <li>(GMT)格林尼治标准时间：都柏林，爱丁堡，里斯本，伦敦 — 欧洲_伦敦 — 欧洲/伦敦</li>
                        <li>(GMT-07:00)亚利桑那 — 美洲_凤凰城 — 美洲/凤凰城</li>
                        <li>(GMT+02:00)贝鲁特 — 亚洲_贝鲁特 — 亚洲/贝鲁特</li>
                        <li>(GMT+04:30)喀布尔 — 亚洲_喀布尔 — 亚洲/喀布尔</li>
                        <li>(GMT-06:00)中心（美国和加拿大） — 美洲_芝加哥 — 美洲/芝加哥</li>
                        <li>(GMT+11:00)格林威治标准时间加11小时 — Gmt_p11 - Etc/GMT-11</li>
                        <li>(GMT+10:00)格林威治标准时间加10小时 — Gmt_p10 - Etc/GMT-10</li>
                        <li>(GMT+13:00)格林威治标准时间加13小时 — Gmt_p13 - Etc/GMT-13</li>
                        <li>(GMT+12:00)格林威治标准时间加12小时 — Gmt_p12 - Etc/GMT-12</li>
                        <li>(GMT-04:00)圣地亚哥 — 美洲_圣地亚哥 — 美洲/圣地亚哥</li>
                        <li>(GMT-03:00)蒙得维的亚 — 美洲_蒙得维的亚 — 美洲/蒙得维的亚</li>
                        <li>(GMT-04:00)库亚巴 — 美洲_库亚巴 — 美洲/库亚巴</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>标题</td>
                  <td>用户档案</td>
                  <td>字符串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>跟踪</td>
                  <td>跟踪日志</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
            </table>


## 筛选器


生日（生日）

<table>
<tr>
<th>名称</th>
<th>类型</th>
</tr>
<tr>
<td>includeStart</td>
<td>布尔值</td>
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
<td>endDay</td>
<td>日期</td>
</tr>
<tr>
<td>精度</td>
<td>明细列表</td>
</tr>
<tr>
<td>相对值</td>
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
<td>布尔值</td>
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

按电子邮件（按电子邮件）

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

按名称或电子邮件(byText)

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

按静态受众(byStaticAudience)

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

个人资料（个人资料）

<table>
<tr>
<th>名称</th>
<th>类型</th>
</tr>
<tr>
<td>个人资料</td>
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
