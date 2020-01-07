---
title: 功能列表
description: 查询编辑工具允许您使用高级功能执行复杂过滤。
page-status-flag: never-activated
uuid: fd50fc99-1e7a-479b-beb7-1f246b419d46
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: filtering-data
discoiquuid: 3cdbe962-1c59-4cd8-b29e-36aa2562fac6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fa9d2be71b4bbf5eceadbd1835db324618f9529c

---


# 功能列表{#list-of-functions}

## 关于函数 {#about-functions}

查询编辑工具允许您使用高级功能执行复杂过滤。 为此，工具调板包含可在工 **[!UICONTROL Expression]**作区中使用的元素。 有关此元素的详细信息，请参阅特[定部分](../../automating/using/advanced-expression-editing.md)。

此元素允许您手动输入条件。 您可以在此处使用以下部分中定义的函数。

根据所需的结果和操作数据的类型，可以使用几种功能类型：

* 日期
* Geomarketing
* 数值
* 其他函数
* 聚合
* 字符串处理
* 排序

## 日期 {#dates}

日期函数用于操作日期或时间值。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
   <td> <strong>语法</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddDays</strong><br /> </td> 
   <td> 向日期添加天数<br /> </td> 
   <td> AddDays(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddHours</strong><br /> </td> 
   <td> 向日期添加小时数<br /> </td> 
   <td> AddHours(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddMinutes</strong><br /> </td> 
   <td> 向日期添加分钟数<br /> </td> 
   <td> AddMinutes(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddMonths</strong><br /> </td> 
   <td> 将月数添加到日期<br /> </td> 
   <td> AddMonths(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddSeconds</strong><br /> </td> 
   <td> 向日期添加秒数<br /> </td> 
   <td> AddSeconds(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddYears</strong><br /> </td> 
   <td> 在日期中添加年数<br /> </td> 
   <td> AddYears(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>仅日期</strong><br /> </td> 
   <td> 仅返回日期（时间为00:00）<br /> </td> 
   <td> DateOnly(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>日</strong><br /> </td> 
   <td> 返回表示日期的数字<br /> </td> 
   <td> Day(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>年度日</strong><br /> </td> 
   <td> 返回表示日期年中某天的数字<br /> </td> 
   <td> DayOfYear(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysAgo</strong><br /> </td> 
   <td> 返回当前日期减n天<br /> </td> 
   <td> DaysAgo(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysAgoInt</strong><br /> </td> 
   <td> 返回当前日期减去n天（作为整数yyyymmdd）<br /> </td> 
   <td> DaysAgoInt(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysDiff</strong><br /> </td> 
   <td> 两个日期之间的天数<br /> </td> 
   <td> DaysDiff（&lt;结束日期&gt;, &lt;开始日期&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysOld</strong><br /> </td> 
   <td> 返回日期的年龄（以天为单位）<br /> </td> 
   <td> DaysOld(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetDate</strong><br /> </td> 
   <td> 返回服务器的当前系统日期<br /> </td> 
   <td> GetDate()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>小时</strong><br /> </td> 
   <td> 返回日期的小时<br /> </td> 
   <td> Hour(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>小时差异</strong><br /> </td> 
   <td> 返回两个日期之间的小时数<br /> </td> 
   <td> HoursDiff（&lt;结束日期&gt;, &lt;开始日期&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LocalToUTC</strong><br /> </td> 
   <td> 将本地日期和时间转换为UTC<br /> </td> 
   <td> LocalToUTC（&lt;date&gt;, &lt;时区&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>分钟</strong><br /> </td> 
   <td> 返回日期的分钟数<br /> </td> 
   <td> Minute(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MinutesDiff</strong><br /> </td> 
   <td> 返回两个日期之间的分钟数<br /> </td> 
   <td> MinutesDiff（&lt;结束日期&gt;, &lt;开始日期&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>月</strong><br /> </td> 
   <td> 返回表示日期月份的数字<br /> </td> 
   <td> Month(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>数月前</strong><br /> </td> 
   <td> 返回与当前日期相应的日期减去n个月<br /> </td> 
   <td> MonthsAgo(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsDiff</strong><br /> </td> 
   <td> 返回两个日期之间的月份数<br /> </td> 
   <td> MonthsDiff（&lt;结束日期&gt;, &lt;开始日期&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsOld</strong><br /> </td> 
   <td> 返回日期的月份数<br /> </td> 
   <td> MonthsOld(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>第二</strong><br /> </td> 
   <td> 返回日期的秒数<br /> </td> 
   <td> Second(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>最旧</strong><br /> </td> 
   <td> 返回最旧的日期 </td> 
   <td> 最旧（&lt;日期&gt;, &lt;日期&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SecondsDiff</strong><br /> </td> 
   <td> 返回两个日期之间的秒数<br /> </td> 
   <td> SecondsDiff（&lt;结束日期&gt;, &lt;开始日期&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubDays</strong><br /> </td> 
   <td> 从日期减去天数<br /> </td> 
   <td> SubDays(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>小时数</strong><br /> </td> 
   <td> 从日期减去小时数<br /> </td> 
   <td> SubHours(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>子分钟</strong><br /> </td> 
   <td> 从日期减去分钟数<br /> </td> 
   <td> SubMinutes(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>子月份</strong><br /> </td> 
   <td> 从日期减去月数<br /> </td> 
   <td> SubMonths(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>子秒</strong><br /> </td> 
   <td> 从日期减去秒数<br /> </td> 
   <td> SubSeconds(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>子年</strong><br /> </td> 
   <td> 从日期减去数年<br /> </td> 
   <td> SubYears(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDate</strong><br /> </td> 
   <td> 将日期+时间转换为日期<br /> </td> 
   <td> ToDate(&lt;date + time&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDateTime</strong><br /> </td> 
   <td> 将字符串转换为日期+时间<br /> </td> 
   <td> ToDateTime(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDateTimeWithTimezone</strong><br /> </td> 
   <td> 将字符串转换为日期+时区。<br /> 示例：ToDateTimeWithTimezone(“2019-02-19 08:09:00”,“Asia/Dehran”)<br /> </td> 
   <td> ToDateTimeWithTimezone(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncDate</strong><br /> </td> 
   <td> 将日期+时间舍入到最近的第二个<br /> </td> 
   <td> TruncDate（@lastModified, &lt;秒数&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncDateTZ</strong><br /> </td> 
   <td> 将日期+时间舍入为以秒为单位的给定精度<br /> </td> 
   <td> TruncDateTZ（&lt;date&gt;, &lt;秒数&gt;, &lt;时区&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncQuarter</strong><br /> </td> 
   <td> 将日期舍入到季度<br /> </td> 
   <td> TruncQuarter(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncTime</strong><br /> </td> 
   <td> 将时间部分舍入到最近的第二个<br /> </td> 
   <td> TruncTime（&lt;date&gt;, &lt;秒数&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncWeek</strong><br /> </td> 
   <td> 将日期舍入到周<br /> </td> 
   <td> TruncWeek(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncYear</strong><br /> </td> 
   <td> 将日期+时间舍入到年度的1月1日<br /> </td> 
   <td> TruncYear(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>WeekDay</strong><br /> </td> 
   <td> 返回表示日期周中某天的数字<br /> </td> 
   <td> WeekDay(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>年</strong><br /> </td> 
   <td> 返回表示日期年份的数字<br /> </td> 
   <td> Year(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>年和月</strong><br /> </td> 
   <td> 返回表示日期的年份和月份的数字<br /> </td> 
   <td> YearAndMonth(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearsDiff</strong><br /> </td> 
   <td> 返回两个日期之间的年数<br /> </td> 
   <td> YearsDiff（&lt;结束日期&gt;, &lt;开始日期&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearsOld</strong><br /> </td> 
   <td> 返回日期的年龄<br /> </td> 
   <td> YearsOld(&lt;date&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Geomarketing {#geomarketing}

该几何营销函数用于操作地理值。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
   <td> <strong>语法</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>距离</strong><br /> </td> 
   <td> 返回两个点之间的距离（以公里为单位），这两个点由其经度和纬度定义（以度表示）<br /> </td> 
   <td> 距离（&lt;经度A&gt;、&lt;经度A&gt;、&lt;经度B&gt;、&lt;经度B&gt;）<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 数字 {#numerical}

数值函数用于将文本转换为数字。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
   <td> <strong>语法</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Abs</strong><br /> </td> 
   <td> 返回数字的绝对值<br /> </td> 
   <td> Abs(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ceil</strong><br /> </td> 
   <td> 返回大于或等于数字的最低整数<br /> </td> 
   <td> Ceil(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Floor</strong><br /> </td> 
   <td> 返回小于或等于一个数字的最大整数<br /> </td> 
   <td> Floor(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>最伟大</strong><br /> </td> 
   <td> 返回两个数字中的较大者<br /> </td> 
   <td> 最大（&lt;数字1&gt;, &lt;数字2&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>最少</strong><br /> </td> 
   <td> 返回两个数字中的较小者<br /> </td> 
   <td> 最少（&lt;数字1&gt;, &lt;数字2&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mod</strong><br /> </td> 
   <td> 返回从n1除以n2的整数除的余数<br /> </td> 
   <td> Mod(&lt;number 1&gt;, &lt;number 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>百分比</strong><br /> </td> 
   <td> 返回以百分比表示的两个数字的比率<br /> </td> 
   <td> Percent(&lt;number 1&gt;, &lt;number 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>随机</strong><br /> </td> 
   <td> 返回随机值<br /> </td> 
   <td> Random()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>圆形</strong><br /> </td> 
   <td> 将数字舍入为n小数<br /> </td> 
   <td> Round（&lt;number&gt;, &lt;小数&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>签名</strong><br /> </td> 
   <td> 返回数字的符号<br /> </td> 
   <td> Sign(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDouble</strong><br /> </td> 
   <td> 将整数转换为浮点<br /> </td> 
   <td> ToDouble(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInt64</strong><br /> </td> 
   <td> 将浮点数转换为64位整数<br /> </td> 
   <td> ToInt64(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInteger</strong><br /> </td> 
   <td> 将浮点转换为整数<br /> </td> 
   <td> ToInteger(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Trunc</strong><br /> </td> 
   <td> 截断n1到n2小数<br /> </td> 
   <td> Trunc(&lt;n1&gt;, &lt;n2&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 其他 {#others}

此表包含剩余的可用函数。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
   <td> <strong>语法</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>案例</strong><br /> </td> 
   <td> 如果条件已验证，则返回值1。 否则，返回值2<br /> </td> 
   <td> Case(When(&lt;condition&gt;, &lt;value 1&gt;), Else(&lt;value 2&gt;))<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ClearBit</strong><br /> </td> 
   <td> 删除值中的标记<br /> </td> 
   <td> ClearBit(&lt;identifier&gt;, &lt;flag&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Coalesce</strong><br /> </td> 
   <td> 如果值1为零或null，则返回值2，否则返回值1<br /> </td> 
   <td> Coalesce(&lt;value 1&gt;, &lt;value 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>解码</strong><br /> </td> 
   <td> 返回值3是值1 =值2，否则返回4<br /> </td> 
   <td> Decode(&lt;value 1&gt;, &lt;value 2&gt;, &lt;value 3&gt;, &lt;value 4&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Else</strong><br /> </td> 
   <td> 返回值1（只能用作case函数的参数）<br /> </td> 
   <td> Else(&lt;value 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetEmailDomain</strong><br /> </td> 
   <td> 从电子邮件地址提取域<br /> </td> 
   <td> GetEmailDomain(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetMirrorURL</strong><br /> </td> 
   <td> 检索镜像页面服务器的URL<br /> </td> 
   <td> GetMirrorURL(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>If</strong><br /> </td> 
   <td> 如果表达式为true，则返回值1，否则返回值2<br /> </td> 
   <td> Iif(&lt;condition&gt;, &lt;value 1&gt;, &lt;value 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsBitSet</strong><br /> </td> 
   <td> 指示标记是否在值中<br /> </td> 
   <td> IsBitSet(&lt;identifier&gt;, &lt;flag&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsEmptyString</strong><br /> </td> 
   <td> 如果字符串为空，则返回值2，否则返回值3<br /> </td> 
   <td> IsEmptyString(&lt;string&gt;, &lt;value 2&gt;, &lt;value 3&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>NoNull</strong><br /> </td> 
   <td> 如果参数为NULL，则返回空字符串<br /> </td> 
   <td> NoNull(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowId</strong><br /> </td> 
   <td> 返回行号<br /> </td> 
   <td> RowId<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SetBit</strong><br /> </td> 
   <td> 强制值中的标记<br /> </td> 
   <td> SetBit(&lt;identifier&gt;, &lt;flag&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToBoolean</strong><br /> </td> 
   <td> 将数字转换为布尔值<br /> </td> 
   <td> ToBoolean(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>何时</strong><br /> </td> 
   <td> 如果验证了表达式，则返回值1。 否则，返回值2（只能用作case函数的参数）<br /> </td> 
   <td> When(&lt;condition&gt;, &lt;value 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>newUUID</strong><br /> </td> 
   <td> 返回新的UUID。<br /> </td> 
   <td> newUUID<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 字符串 {#string}

字符串函数用于操作一组字符串。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
   <td> <strong>语法</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull2</strong><br /> </td> 
   <td> 指示所有参数是否为非null且不为空<br /> </td> 
   <td> AllNonNull2(&lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull3</strong><br /> </td> 
   <td> 指示所有参数是否为非null且不为空<br /> </td> 
   <td> AllNonNull3(&lt;string&gt;, &lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ASCII</strong><br /> </td> 
   <td> 返回字符串中第一个字符的ASCII值<br /> </td> 
   <td> Ascii(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Char</strong><br /> </td> 
   <td> 返回与“n”ASCII代码对应的字符<br /> </td> 
   <td> Char(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Charindex</strong><br /> </td> 
   <td> 返回字符串1中字符串2的位置<br /> </td> 
   <td> Charindex(&lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DataLength</strong><br /> </td> 
   <td> 返回字符串中的字符数<br /> </td> 
   <td> DataLength(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetLine</strong><br /> </td> 
   <td> 返回字符串的n（从1到n）行<br /> </td> 
   <td> GetLine(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IfEquals</strong><br /> </td> 
   <td> 如果前两个参数相等，则返回第三个参数，否则返回最后一个参数<br /> </td> 
   <td> IfEquals(&lt;string&gt;, &lt;string&gt;, &lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsMemoNull</strong><br /> </td> 
   <td> 指示作为参数传递的备忘录是否为null<br /> </td> 
   <td> IsMemoNull(&lt;Memo&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords</strong><br /> </td> 
   <td> 将作为参数传递的两个字符串截断。 返回值中的每个字符串之间都会添加一个空格。<br /> </td> 
   <td> JuxtWords(&lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords3</strong><br /> </td> 
   <td> 将作为参数传递的三个字符串截断。 返回值中的每个字符串之间都会添加一个空格。<br /> </td> 
   <td> JuxtWords3(&lt;string&gt;, &lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LPad</strong><br /> </td> 
   <td> 返回左边已完成的字符串<br /> </td> 
   <td> LPad(&lt;string&gt;, &lt;number&gt;, &lt;caractère&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>左侧</strong><br /> </td> 
   <td> 返回字符串的前n个字符<br /> </td> 
   <td> Left(&lt;string&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>长度</strong><br /> </td> 
   <td> 返回字符串长度<br /> </td> 
   <td> Length(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>低</strong><br /> </td> 
   <td> 以小写形式返回字符串<br /> </td> 
   <td> Lower(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ltrim</strong><br /> </td> 
   <td> 删除字符串左侧的空格<br /> </td> 
   <td> Ltrim(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Md5Digest</strong><br /> </td> 
   <td> 返回字符串MD5键的十六进制表示形式<br /> </td> 
   <td> Md5Digest(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>备忘录包含</strong><br /> </td> 
   <td> 指定备忘录是否包含作为参数传递的字符串<br /> </td> 
   <td> MemoContains(&lt;memo&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RPad</strong><br /> </td> 
   <td> 返回右侧的已完成字符串<br /> </td> 
   <td> RPad(&lt;string&gt;, &lt;number&gt;, &lt;character&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>替换</strong><br /> </td> 
   <td> 将指定字符串（第2个参数）值的所有出现替换为字符串中的另一个字符串值（第3个参数）（第1个参数）<br /> </td> 
   <td> Replace(&lt;String&gt;, &lt;String&gt;, &lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>右</strong><br /> </td> 
   <td> 返回字符串的最后n个字符<br /> </td> 
   <td> Right(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rtrim</strong><br /> </td> 
   <td> 删除字符串右侧的空格<br /> </td> 
   <td> Rtrim(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha256Digest</strong><br /> </td> 
   <td> 计算给定 <strong>UTF8字符串的标准</strong> SHA256哈希<br /> </td> 
   <td> Sha256Digest(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha384Digest</strong><br /> </td> 
   <td> 计算给定 <strong>UTF8字符串的标准</strong> SHA384哈希<br /> </td> 
   <td> Sha384Digest(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha512Digest</strong><br /> </td> 
   <td> 计算给定 <strong>UTF8字符串的标准</strong> SHA512哈希<br /> </td> 
   <td> Sha512Digest(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>智能</strong><br /> </td> 
   <td> 返回带每个单词的第一个字母大写的字符串<br /> </td> 
   <td> Smart(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>子字符串</strong><br /> </td> 
   <td> 提取从字符串的字符n1开始且长度为n2的子字符串<br /> </td> 
   <td> 子字符串(&lt;string&gt;, &lt;offset&gt;, &lt;length&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToIntlString</strong><br /> </td> 
   <td> 将数字转换为字符串<br /> </td> 
   <td> ToIntlString(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToString</strong><br /> </td> 
   <td> 将数字转换为字符串<br /> </td> 
   <td> ToString(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>上</strong><br /> </td> 
   <td> 返回大写字符串<br /> </td> 
   <td> Upper(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLink</strong><br /> </td> 
   <td> 如果其他两个参数相等，则返回作为参数传递的链接的外键<br /> </td> 
   <td> VirtualLink(&lt;number&gt;, &lt;number&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLinkStr</strong><br /> </td> 
   <td> 如果其他两个参数相等，则返回作为参数传递的链接的外键（文本）<br /> </td> 
   <td> VirtualLinkStr(&lt;string&gt;, &lt;number&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_aescbcDecrypt</strong><br /> </td> 
   <td> 使用HEX格式（第2个参数）的密钥和HEX格式（第3个参数）的初始化矢量，以“<strong>x</strong>”前缀（第1个参数）以HEX格式解密加密值<br /> </td> 
   <td> encryption_aescbcDecrypt(&lt;String&gt;, &lt;String&gt;, &lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_aescbcEncrypt</strong><br /> </td> 
   <td> 使用AES算法（CBC块模式）使用密钥（第2个参数）和初始化矢量（第3个参数）对字符串（第1个参数）进行加密。 密钥和初始化矢量必须以十六进制表示形式提供(以 <strong>\x开头</strong>)。 结果将以十六进制表示，不带 <strong>\x</strong>。<br /> 请注意，密钥大小可以是128位、192位、256位（16、24、32个十六进制字符），但建议您使用256位和与密钥长度相同的随机IV。<br /> </td> 
   <td> encryption_aescbcEncrypt(&lt;String&gt;, &lt;String&gt;, &lt;String&gt;)<br /> ，例如：encryption_aescbcEncrypt(johndoe@example.com, "<strong>\x0123456789ABCDEF0123456789ABCDEF</strong>", "<strong>\x0123456789ABCDEFCba9876543210</strong>”)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 聚合 {#aggregates}

只有在从工作流的活动中添 [加其他数据时](../../automating/using/query.md#enriching-data) ，聚合函数才 **[!UICONTROL Query]**可用。

集合函数用于对一组值执行计算。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
   <td> <strong>语法</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>平均</strong>，平均<br /> </td> 
   <td> 返回数字列中的平均值。<br /> </td> 
   <td> Avg(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>计数</strong>、计数（NULL除外）<br /> </td> 
   <td> 计算列中的非空值。<br /> </td> 
   <td> Count(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>全部计数</strong>，全部计数<br /> </td> 
   <td> 计算所有值（包括空值和重复值）。<br /> </td> 
   <td> CountAll()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Countdistinct</strong>, Distinct计数<br /> </td> 
   <td> 计算列中非空的不同值。<br /> </td> 
   <td> Countdistinct(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Max</strong>, Max<br /> </td> 
   <td> 返回数字、字符串或日期列中的最大值。<br /> </td> 
   <td> Max(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>闵</strong>、敏<br /> </td> 
   <td> 返回数字、字符串或日期列中的最小值。<br /> </td> 
   <td> Min(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sum</strong>, Sum<br /> </td> 
   <td> 返回数值列中值的和。<br /> </td> 
   <td> Sum(&lt;value&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 表示法 {#representation}

表示函数用于对值进行排序。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
   <td> <strong>语法</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Desc</strong><br /> </td> 
   <td> 应用降序排序<br /> </td> 
   <td> Desc(&lt;value 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>OrderBy</strong><br /> </td> 
   <td> 对分区内的结果进行排序<br /> </td> 
   <td> OrderBy(&lt;value 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>分区依据</strong><br /> </td> 
   <td> 将查询结果分区到表<br /> </td> 
   <td> PartitionBy(&lt;value 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowNum</strong><br /> </td> 
   <td> 基于表分区和排序序列生成行号。 MySQL不支持此函数<br /> </td> 
   <td> RowNum(PartitionBy(&lt;value 1&gt;), OrderBy(&lt;value 1&gt;))<br /> </td> 
  </tr> 
 </tbody> 
</table>

