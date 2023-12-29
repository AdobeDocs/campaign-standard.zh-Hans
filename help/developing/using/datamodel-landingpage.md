---
title: 数据模型登录页面
description: 了解数据模型
audience: designing
content-type: reference
topic-tags: editing-sms-and-push-content
context-tags: delivery,smsContent,back
feature: Data Model
role: Developer
level: Experienced
exl-id: bd12a214-5998-4fb9-9f54-0c886067b58b
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '1817'
ht-degree: 7%

---

# landingPage (nms：landingPage)

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
         <td>additionaldata</td>
         <td>其他数据</td>
         <td>集合 </td>
         <td> </td>
      </tr>
      <tr>
         <td>其他语言</td>
         <td>其他语言</td>
         <td>项 </td>
         <td> </td>
      </tr>
      <tr>
         <td>allowNonIdentifiedTarget</td>
         <td>授权未识别的访客</td>
         <td>布尔值 </td>
         <td> </td>
      </tr>
      <tr>
         <td>品牌策略(brandingBase)</td>
         <td>品牌</td>
         <td>链接 </td>
         <td> </td>
      </tr>
      <tr>
         <td>内置</td>
         <td>内置应用程序对象</td>
         <td>布尔值 </td>
         <td> </td>
      </tr>
      <tr>
         <td>缓存</td>
         <td>缓存</td>
         <td>字符串 </td>
         <td> </td>
      </tr>
      <tr>
         <td>campaign (campaignBase)</td>
         <td>营销活动</td>
         <td>链接 </td>
         <td> </td>
      </tr>
      <tr>
         <td>closedlog</td>
         <td>“登陆页面已关闭”日志</td>
         <td>字符串 </td>
         <td> </td>
      </tr>
      <tr>
         <td>contextResourceType</td>
         <td>Contextresourcetype</td>
         <td>字符串 </td>
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
         <td>cryptKey</td>
         <td>AES加密密钥</td>
         <td>字符串(64)</td>
         <td> </td>
      </tr>
      <tr>
         <td>defaultlanguage</td>
         <td>默认语言</td>
         <td>枚举（字符串） (255)</td>
         <td>
            <ul>
               <li>希腊语 — el - el</li>
               <li>英语 — en - en</li>
               <li>中文 — zh - zh</li>
               <li>法语（法国） - fr_FR - fr_FR</li>
               <li>越南语 — vi - vi</li>
               <li>葡萄牙语（葡萄牙） - pt_PT - pt_PT</li>
               <li>意大利语（意大利） - it_IT - it_IT</li>
               <li>意大利语 — it - it</li>
               <li>荷兰语（比利时） - nl_BE - nl_BE</li>
               <li>挪威语（挪威） - no_NO - no_NO</li>
               <li>荷兰语（荷兰） — nl_NL - nl_NL</li>
               <li>阿拉伯语 — ar - ar</li>
               <li>英语（美国） - en_US - en_US</li>
               <li>爱尔兰语 — ga - ga</li>
               <li>捷克语 — cs - cs</li>
               <li>爱沙尼亚语 — et - et</li>
               <li>印度尼西亚语 — id - id</li>
               <li>西班牙语 — es - es</li>
               <li>俄语 — ru - ru</li>
               <li>荷兰语 — nl - nl</li>
               <li>瓦隆 — 瓦 — 瓦</li>
               <li>葡萄牙语 — pt - pt</li>
               <li>法语（比利时） - fr_BE - fr_BE</li>
               <li>拉脱维亚语 — lv - lv</li>
               <li>立陶宛语 — lt - lt</li>
               <li>泰语 — th -th</li>
               <li>英语（英国） — en_GB - en_GB</li>
               <li>法语 — fr - fr</li>
               <li>葡萄牙语（巴西） - pt_BR - pt_BR</li>
               <li>德语 — de - de</li>
               <li>丹麦语 — da - da</li>
               <li>芬兰语 — fi - fi</li>
               <li>匈牙利语 — hu - hu</li>
               <li>瑞典语（芬兰） — sv_FI - sv_FI</li>
               <li>日语 — ja - ja</li>
               <li>希伯来语 — he - he</li>
               <li>韩语 — ko - ko</li>
               <li>瑞典语 — sv - sv</li>
               <li>瑞典（瑞典语） - sv_SE - sv_SE</li>
               <li>斯洛伐克语 — sk - sk</li>
               <li>马耳他语 — mt - mt</li>
               <li>意大利语（瑞士） - it_CH - it_CH</li>
               <li>波兰语 — pl - pl</li>
               <li>斯洛文尼亚语 — sl - sl</li>
               <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>defaultOrigin（交付）</td>
         <td>流量源</td>
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
         <td>设计语言</td>
         <td>设计语言</td>
         <td>枚举（字符串） (255)</td>
         <td>
            <ul>
               <li>希腊语 — el - el</li>
               <li>英语 — en - en</li>
               <li>中文 — zh - zh</li>
               <li>法语（法国） - fr_FR - fr_FR</li>
               <li>越南语 — vi - vi</li>
               <li>葡萄牙语（葡萄牙） - pt_PT - pt_PT</li>
               <li>意大利语（意大利） - it_IT - it_IT</li>
               <li>意大利语 — it - it</li>
               <li>荷兰语（比利时） - nl_BE - nl_BE</li>
               <li>挪威语（挪威） - no_NO - no_NO</li>
               <li>荷兰语（荷兰） — nl_NL - nl_NL</li>
               <li>阿拉伯语 — ar - ar</li>
               <li>英语（美国） - en_US - en_US</li>
               <li>爱尔兰语 — ga - ga</li>
               <li>捷克语 — cs - cs</li>
               <li>爱沙尼亚语 — et - et</li>
               <li>印度尼西亚语 — id - id</li>
               <li>西班牙语 — es - es</li>
               <li>俄语 — ru - ru</li>
               <li>荷兰语 — nl - nl</li>
               <li>瓦隆 — 瓦 — 瓦</li>
               <li>葡萄牙语 — pt - pt</li>
               <li>法语（比利时） - fr_BE - fr_BE</li>
               <li>拉脱维亚语 — lv - lv</li>
               <li>立陶宛语 — lt - lt</li>
               <li>泰语 — th -th</li>
               <li>英语（英国） — en_GB - en_GB</li>
               <li>法语 — fr - fr</li>
               <li>葡萄牙语（巴西） - pt_BR - pt_BR</li>
               <li>德语 — de - de</li>
               <li>丹麦语 — da - da</li>
               <li>芬兰语 — fi - fi</li>
               <li>匈牙利语 — hu - hu</li>
               <li>瑞典语（芬兰） — sv_FI - sv_FI</li>
               <li>日语 — ja - ja</li>
               <li>希伯来语 — he - he</li>
               <li>韩语 — ko - ko</li>
               <li>瑞典语 — sv - sv</li>
               <li>瑞典（瑞典语） - sv_SE - sv_SE</li>
               <li>斯洛伐克语 — sk - sk</li>
               <li>马耳他语 — mt - mt</li>
               <li>意大利语（瑞士） - it_CH - it_CH</li>
               <li>波兰语 — pl - pl</li>
               <li>斯洛文尼亚语 — sl - sl</li>
               <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>动态服务</td>
         <td>动态服务</td>
         <td>布尔值 </td>
         <td> </td>
      </tr>
      <tr>
         <td>结束</td>
         <td>过期日期</td>
         <td>日期 </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorContextResourceType</td>
         <td>ErrorContextResourceType</td>
         <td>字符串 </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorPage</td>
         <td>错误页面</td>
         <td>项 </td>
         <td> </td>
      </tr>
      <tr>
         <td>geoUnit (geoUnitBase)</td>
         <td>地理单位</td>
         <td>链接 </td>
         <td> </td>
      </tr>
      <tr>
         <td>htmlPage</td>
         <td>页面</td>
         <td>集合 </td>
         <td> </td>
      </tr>
      <tr>
         <td>identificationByUrlParam</td>
         <td>通过URL参数标识</td>
         <td>布尔值 </td>
         <td> </td>
      </tr>
      <tr>
         <td>inactiveUrlRedirection</td>
         <td>重定向URL</td>
         <td>字符串(4096)</td>
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
         <td>作业</td>
         <td>作业</td>
         <td>集合 </td>
         <td> </td>
      </tr>
      <tr>
         <td>jobLogs</td>
         <td>日志</td>
         <td>集合 </td>
         <td> </td>
      </tr>
      <tr>
         <td>标签</td>
         <td>标签</td>
         <td>字符串(128)</td>
         <td> </td>
      </tr>
      <tr>
         <td>lastModified</td>
         <td>上次修改时间</td>
         <td>日期 </td>
         <td> </td>
      </tr>
      <tr>
         <td>loadingFilter (queryFilterBase)</td>
         <td>正在加载密钥</td>
         <td>链接 </td>
         <td> </td>
      </tr>
      <tr>
         <td>loadingFilterMapping</td>
         <td>加载键的参数</td>
         <td>集合 </td>
         <td> </td>
      </tr>
      <tr>
         <td>logicalStatus</td>
         <td>执行状态</td>
         <td>枚举（字符串） (255)</td>
         <td>
            <ul>
               <li>进行中 — 已开始 — 已开始</li>
               <li>编辑 — 版本 — 版本</li>
               <li>已完成 — 已完成 — 已完成</li>
               <li>警告 — 警告 — 警告</li>
               <li>错误 — 错误 — 错误</li>
               <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>messageaction</td>
         <td>开始发送消息</td>
         <td>布尔值 </td>
         <td> </td>
      </tr>
      <tr>
         <td>messageActionDelivery (deliveryMCTemplateBase)</td>
         <td>事务性消息</td>
         <td>链接 </td>
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
         <td>orgUnit (orgUnitBase)</td>
         <td>组织实体</td>
         <td>链接 </td>
         <td> </td>
      </tr>
      <tr>
         <td>预填充</td>
         <td>预载访客数据</td>
         <td>布尔值 </td>
         <td> </td>
      </tr>
      <tr>
         <td>program (programBase)</td>
         <td>项目</td>
         <td>链接 </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicUrl</td>
         <td>公共URL</td>
         <td>字符串 </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicationDate</td>
         <td>发布日期</td>
         <td>日期 </td>
         <td> </td>
      </tr>
      <tr>
         <td>reconciliationFilter (queryFilterBase)</td>
         <td>协调键</td>
         <td>链接 </td>
         <td> </td>
      </tr>
      <tr>
         <td>reconciliationFilterMapping</td>
         <td>协调密钥参数</td>
         <td>集合 </td>
         <td> </td>
      </tr>
      <tr>
         <td>reconciliationUpdateStrategy</td>
         <td>更新策略</td>
         <td>枚举（字节） </td>
         <td>
            <ul>
               <li>更新 — updateTarget - 1</li>
               <li>未授权 — 未授权 — 0</li>
               <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>服务(serviceBase)</td>
         <td>订阅服务</td>
         <td>链接 </td>
         <td> </td>
      </tr>
      <tr>
         <td>specificAction</td>
         <td>特定操作</td>
         <td>枚举（字节） </td>
         <td>
            <ul>
               <li>黑名单 — 黑名单 — 3</li>
               <li>无特定操作 — 无 — 0</li>
               <li>退订 — 退订 — 2</li>
               <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
               <li>订阅 — 订阅 — 1</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>开始</td>
         <td>部署日期</td>
         <td>日期 </td>
         <td> </td>
      </tr>
      <tr>
         <td>state</td>
         <td>状态</td>
         <td>枚举（字节） </td>
         <td>
            <ul>
               <li>编辑 — 编辑 — 0</li>
               <li>发布失败 — 失败 — 99</li>
               <li>已关闭 — 已关闭 — 20</li>
               <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
               <li>联机 — 已打开 — 10</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>targetresource</td>
         <td>定位维度</td>
         <td>字符串(255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>模板(landingPage)</td>
         <td>登陆页面模板</td>
         <td>链接 </td>
         <td> </td>
      </tr>
      <tr>
         <td>testUrl</td>
         <td>测试 URL</td>
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
               <li>服务器时区 — _server_ - _server_</li>
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
               <li>默认 — _inherit_ - _inherit_</li>
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
               <li>数据库的时区 — _wdbc_ - _wdbc_</li>
               <li>(GMT+06:30)仰光 — 亚洲_仰光 — 亚洲/仰光</li>
               <li>(GMT+11:00)马加丹，所罗门群岛，新喀里多尼亚 — 太平洋_瓜达尔卡纳尔 — 太平洋/瓜达尔卡纳尔</li>
               <li>(GMT+02:00)开罗 — 非洲_开罗 — 非洲/开罗</li>
               <li>(GMT+05:00)叶卡捷琳堡 — 亚洲_叶卡捷琳堡 — 亚洲/叶卡捷琳堡</li>
               <li>(GMT+08:00)伊尔库茨克 — 亚洲_伊尔库茨克 — 亚洲/伊尔库茨克</li>
               <li>(GMT+10:00)关岛，莫尔斯比港 — 太平洋关岛 — 太平洋/关岛</li>
               <li>(GMT-04:00)大西洋标准时间（加拿大） — 美洲_哈利法克斯 — 美洲/哈利法克斯</li>
               <li>(GMT)格林威治标准时间 — 格林威治标准时间 — 格林威治标准时间</li>
               <li>(GMT-04:00)拉巴斯 — 美洲_拉巴斯 — 美洲/拉巴斯</li>
               <li>操作员时区 — _login_ - _login_</li>
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
         <td>登陆页面</td>
         <td>字符串(255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingEnabled</td>
         <td>日志响应</td>
         <td>布尔值 </td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingUrlName</td>
         <td>跟踪 URL 名称</td>
         <td>字符串 </td>
         <td> </td>
      </tr>
      <tr>
         <td>类型</td>
         <td>类型</td>
         <td>枚举（字节） </td>
         <td>
            <ul>
               <li>通用 — 通用 — 0</li>
               <li>退订服务 — 退订 — 3</li>
               <li>黑名单 — 黑名单 — 4</li>
               <li>无效值 — __Invalid_value__ - __Invalid_value__</li>
               <li>收购 — 收购–1</li>
               <li>服务订购 — 订购 — 2</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>uuid</td>
         <td>安全性 ID</td>
         <td>字符串 </td>
         <td> </td>
      </tr>
      <tr>
         <td>webTrackingEnabled</td>
         <td>启用 Web 跟踪</td>
         <td>布尔值 </td>
         <td> </td>
      </tr>
   </table>

## 筛选器

按逻辑状态(byLogicalStatus)

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>state</td>
    <td>明细列表</td>
    </tr>
</table>

按名称或标签(byText)

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

按状态（按州）

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>state</td>
    <td>明细列表</td>
    </tr>
</table>

按定向资源(byTargetResource)

<table>
<tr>
<th>名称</th>
<th>类型</th>
</tr>
<tr>
<td>targetresource</td>
<td>字符串</td>
</tr>
</table>

包括高级登陆页面（含高级）

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>高级</td>
    <td>布尔值</td>
    </tr>
</table>

包括来自异类列表的连续投放（使用Continuous）

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

在给定时间段内存在（按日历）

<table>
        <tr>
        <th>名称</th>
        <th>类型</th>
        </tr>
        <tr>
        <td>startDate</td>
        <td>日期</td>
        </tr>
        <tr>
        <td>endDate</td>
        <td>日期</td>
        </tr>
    </table>

在指定期间发布（由Planning提供）

<table>
    <tr>
    <th>名称</th>
    <th>类型</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>日期</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>日期</td>
    </tr>
</table>
