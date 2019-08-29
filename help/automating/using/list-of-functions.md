---
title: 函数列表
seo-title: 函数列表
description: 函数列表
seo-description: 查询编辑工具允许您使用高级函数进行复杂过滤。
page-status-flag: 从未激活
uuid: fd50fc99-1e7a-479b-beb7-1f419 d419 d46
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 筛选数据
discoiquuid: cdbe962-1c59-4cd8-b29 e-36aa2562 fac6
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 83be3f22f3508248f2a4666080a7207998093dc3

---


# 函数列表{#list-of-functions}

## 关于函数 {#about-functions}

查询编辑工具允许您使用高级函数进行复杂过滤。为此，工具调色板包含可在工作区中使用的 **[!UICONTROL Expression]** 元素。有关此元素的详细信息，请参阅 [特定部分](../../automating/using/advanced-expression-editing.md)。

此元素允许您手动输入条件。您可以在此使用在以下部分中定义的函数。

有几种函数类型可用，具体取决于所需的结果和操作数据的类型：

* 日期
* Geomarketing
* 数值
* 其他函数
* 集合
* 字符串处理
* 排序

## 日期 {#dates}

日期函数用于处理日期或时间值。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名称</strong><br /> </td> 
   <td> <strong>描述</strong><br /> </td> 
   <td> <strong>语法</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>加载天数</strong><br /> </td> 
   <td> 将天数添加到某个日期<br /> </td> 
   <td> addDays(&lt; date&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>加载项</strong><br /> </td> 
   <td> 向某个日期添加多个小时<br /> </td> 
   <td> addStudio(&lt; date&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>添加分钟数</strong><br /> </td> 
   <td> 向日期添加几分钟<br /> </td> 
   <td> addMin分钟(&lt; date&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>addMonthly</strong><br /> </td> 
   <td> 添加几个月到一个日期<br /> </td> 
   <td> addMonthly(&lt; date&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>addSeconds</strong><br /> </td> 
   <td> 向日期添加几秒数<br /> </td> 
   <td> addSeconds(&lt; date&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>addAnys</strong><br /> </td> 
   <td> 添加多年的日期<br /> </td> 
   <td> addAnys(&lt; date&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>仅限DateOnly</strong><br /> </td> 
   <td> 仅返回日期(在00：00时)<br /> </td> 
   <td> dateOnly(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Day</strong><br /> </td> 
   <td> 返回表示日期日期的数字<br /> </td> 
   <td> Day(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>第一年</strong><br /> </td> 
   <td> 返回一个数字，表示日期中的一天<br /> </td> 
   <td> Dayofyear(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Daysago</strong><br /> </td> 
   <td> 返回当前日期减去n天<br /> </td> 
   <td> Daysago(&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysaGoint</strong><br /> </td> 
   <td> 返回当前日期减去n天(作为整数yyyymmdd)<br /> </td> 
   <td> daysagoint(&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysDiff</strong><br /> </td> 
   <td> 两个日期之间的天数<br /> </td> 
   <td> daysDiff(&lt;结束日期&gt;，&lt;开始日期&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Daysed</strong><br /> </td> 
   <td> 返回日期中的天数<br /> </td> 
   <td> Daysed(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>getDate</strong><br /> </td> 
   <td> 返回服务器的当前系统日期<br /> </td> 
   <td> getDate()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>小时</strong><br /> </td> 
   <td> 返回日期的小时<br /> </td> 
   <td> 小时(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HoursDiff</strong><br /> </td> 
   <td> 返回两个日期之间的小时数<br /> </td> 
   <td> hoursDiff(&lt;结束日期&gt;，&lt;开始日期&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LocalToOutc</strong><br /> </td> 
   <td> 将本地日期和时间转换为UTC<br /> </td> 
   <td> localToC(&lt; date&gt;，&lt; Time Zone&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>分钟</strong><br /> </td> 
   <td> 返回日期的分钟数<br /> </td> 
   <td> 分钟(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>targesDiff</strong><br /> </td> 
   <td> 返回两个日期之间的分钟数<br /> </td> 
   <td> sociesDiff(&lt;结束日期&gt;，&lt;开始日期&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>月</strong><br /> </td> 
   <td> 返回表示日期月份的数字<br /> </td> 
   <td> 月(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Monthsago</strong><br /> </td> 
   <td> 返回与当前日期对应的日期减去n个月<br /> </td> 
   <td> MonthSago(&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsDiff</strong><br /> </td> 
   <td> 返回两个日期之间的月数<br /> </td> 
   <td> monthSDiff(&lt;结束日期&gt;，&lt;开始日期&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthSales</strong><br /> </td> 
   <td> 返回日期的几个月内的年龄<br /> </td> 
   <td> Monthed(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>第二个</strong><br /> </td> 
   <td> 返回日期的秒数<br /> </td> 
   <td> 第二个(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>旧版</strong><br /> </td> 
   <td> 返回最早的日期 </td> 
   <td> Listest(&lt; Date&gt;，&lt; Date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>searchDiff</strong><br /> </td> 
   <td> 返回两个日期之间的秒数<br /> </td> 
   <td> searchDiff(&lt;结束日期&gt;，&lt;开始日期&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>分时段</strong><br /> </td> 
   <td> 从日期中减去天数<br /> </td> 
   <td> 分时段(&lt; date&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>子时间</strong><br /> </td> 
   <td> 从一个日期减去多个小时<br /> </td> 
   <td> subhours(&lt; date&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>分时段</strong><br /> </td> 
   <td> 从日期中减去分钟数<br /> </td> 
   <td> subMinds(&lt; date&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>子月份</strong><br /> </td> 
   <td> 从日期中减去多个月<br /> </td> 
   <td> subMonth(&lt; date&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>sub秒</strong><br /> </td> 
   <td> 从日期中减去秒数<br /> </td> 
   <td> subSeconds(&lt; date&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>年子年</strong><br /> </td> 
   <td> 从日期中减去多年<br /> </td> 
   <td> subyear(&lt; date&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDate</strong><br /> </td> 
   <td> 将日期+时间转换为日期<br /> </td> 
   <td> toDate(&lt; date+ time&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>toDateTime</strong><br /> </td> 
   <td> 将字符串转换为日期+时间<br /> </td> 
   <td> toDateTime(&lt; string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>todateTimeWithTimeZone</strong><br /> </td> 
   <td> 将字符串转换为日期+时区。<br /> 示例：todateTimeWithTimeZone(“2019-02-1908：09：00”，“亚洲/德黑兰”)<br /> </td> 
   <td> topDateTimeWithTimeZone(&lt; string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>截断日期</strong><br /> </td> 
   <td> 将日期+时间舍入到最近的秒数<br /> </td> 
   <td> 截断日期(@ lastModified，&lt;秒&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>截断数据</strong><br /> </td> 
   <td> 将日期+时间舍入为秒表示的给定精度<br /> </td> 
   <td> thendateTZ(&lt; date&gt;，&lt;秒&gt;，&lt;时区&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>截断1/4</strong><br /> </td> 
   <td> 将日期舍入到季度<br /> </td> 
   <td> 截断(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>截断时间</strong><br /> </td> 
   <td> 将时间部分四舍五入到最接近的秒数<br /> </td> 
   <td> thenTime(&lt; date&gt;，&lt;秒&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>截断Week</strong><br /> </td> 
   <td> 将日期舍入到周<br /> </td> 
   <td> 截断Week(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>截断年份</strong><br /> </td> 
   <td> 将日期+时间舍入到每年的月日<br /> </td> 
   <td> 截断年份(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>工作日</strong><br /> </td> 
   <td> 返回表示日期中一周中一天的数字<br /> </td> 
   <td> 工作日(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>年</strong><br /> </td> 
   <td> 返回表示日期年份的数字<br /> </td> 
   <td> 年(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>月和月</strong><br /> </td> 
   <td> 返回表示日期和月份月份的数字<br /> </td> 
   <td> earandMonth(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>yeArsDiff</strong><br /> </td> 
   <td> 返回两个日期之间的年数<br /> </td> 
   <td> yeArsDiff(&lt;结束日期&gt;，&lt;开始日期&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YeArsed</strong><br /> </td> 
   <td> 返回日期中的年份<br /> </td> 
   <td> eArardsed(&lt; date&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Geomarketing {#geomarketing}

地理营销功能用于操纵地理价值。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名称</strong><br /> </td> 
   <td> <strong>描述</strong><br /> </td> 
   <td> <strong>语法</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>距离</strong><br /> </td> 
   <td> 返回longitude和纬度定义的两点之间的距离(以度表示)<br /> </td> 
   <td> 距离(&lt; Publisher A&gt;、&lt; Latitude A&gt;、&lt; Publisher B&gt;、&lt; Latitude B&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 数字 {#numerical}

数值函数用于将文本转换为数字。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名称</strong><br /> </td> 
   <td> <strong>描述</strong><br /> </td> 
   <td> <strong>语法</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Abs</strong><br /> </td> 
   <td> 返回数字的绝对值<br /> </td> 
   <td> Abs(&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ceil</strong><br /> </td> 
   <td> 返回大于或等于一个数字的最低整数<br /> </td> 
   <td> CEIL(&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Floor</strong><br /> </td> 
   <td> 返回大于或等于一个数字的最大整数<br /> </td> 
   <td> Floor(&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>最大程度</strong><br /> </td> 
   <td> 返回两个数字中的更多<br /> </td> 
   <td> 最大(&lt;号1&gt;，&lt;号2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>最少</strong><br /> </td> 
   <td> 返回两个数字中的较小<br /> </td> 
   <td> 最少(&lt;号1&gt;，&lt;号2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mod</strong><br /> </td> 
   <td> 返回n1by n的整数部分的其余部分<br /> </td> 
   <td> MoD(&lt;号1&gt;，&lt;号2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>百分比</strong><br /> </td> 
   <td> 返回表示为百分比的两个数字的比率<br /> </td> 
   <td> 百分比(&lt;号1&gt;，&lt;号2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>随机</strong><br /> </td> 
   <td> 返回随机值<br /> </td> 
   <td> 随机()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>圆形</strong><br /> </td> 
   <td> 将数字舍入n小数点<br /> </td> 
   <td> round(&lt; number&gt;，&lt;小数位数&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sign</strong><br /> </td> 
   <td> 返回数字的符号<br /> </td> 
   <td> Sign(&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>touble</strong><br /> </td> 
   <td> 将整数转换为浮点<br /> </td> 
   <td> toDouble(&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInt64</strong><br /> </td> 
   <td> 将浮动内容转换为64位整数<br /> </td> 
   <td> ToInt64(&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInteger</strong><br /> </td> 
   <td> 将浮动内容转换为整数<br /> </td> 
   <td> toInteger(&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Trunc</strong><br /> </td> 
   <td> 截断n到n小数点<br /> </td> 
   <td> Trunc(&lt; n1&gt;，&lt; n2&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 其他人 {#others}

此表包含其余的函数。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名称</strong><br /> </td> 
   <td> <strong>描述</strong><br /> </td> 
   <td> <strong>语法</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>案例</strong><br /> </td> 
   <td> 如果验证条件，则返回值1。否则，返回值2<br /> </td> 
   <td> case(&lt;条件&gt;，&lt; value1&gt;)，否则(&lt; value2&gt;))<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Clearbit</strong><br /> </td> 
   <td> 删除值中的标记<br /> </td> 
   <td> clearbit(&lt;标识符&gt;，&lt; flag&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Coalesce</strong><br /> </td> 
   <td> 如果值为零或null，则返回值2，否则返回值1<br /> </td> 
   <td> Coalesce(&lt; value1&gt;，&lt; value2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Decode</strong><br /> </td> 
   <td> 返回值为值1= value2，否则返回4<br /> </td> 
   <td> 解码(&lt; value1&gt;，&lt; value2&gt;，&lt; value3&gt;，&lt; value4&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>其它</strong><br /> </td> 
   <td> 返回值1(只能用作案例函数的参数)<br /> </td> 
   <td> 其他(&lt; value1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>getEmailDomain</strong><br /> </td> 
   <td> 从电子邮件地址提取域<br /> </td> 
   <td> getEmailDomain(&lt; value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>getMirrorURL</strong><br /> </td> 
   <td> 检索镜像页面服务器的URL<br /> </td> 
   <td> getMirrorURL(&lt; value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>iIF</strong><br /> </td> 
   <td> 如果表达式为true，则返回值1，否则返回值2<br /> </td> 
   <td> iIF(&lt;条件&gt;，&lt; value1&gt;，&lt; value2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>isBitSet</strong><br /> </td> 
   <td> 指示标志是否位于值中<br /> </td> 
   <td> isBitSet(&lt;标识符&gt;，&lt; flag&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>isemptyString</strong><br /> </td> 
   <td> 如果字符串为空，则返回值2，否则返回值3<br /> </td> 
   <td> isEmptyString(&lt; string&gt;，&lt; value2&gt;，&lt; value3&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Nonull</strong><br /> </td> 
   <td> 如果参数为NULL，则返回空字符串<br /> </td> 
   <td> null(&lt; value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowID</strong><br /> </td> 
   <td> 返回行号<br /> </td> 
   <td> RowID<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>setBit</strong><br /> </td> 
   <td> 强制在值中使用标记<br /> </td> 
   <td> setBit(&lt;标识符&gt;，&lt; flag&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Toboolean</strong><br /> </td> 
   <td> 将数字转换为Boolean<br /> </td> 
   <td> topOolean(&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>When</strong><br /> </td> 
   <td> 如果验证表达式，则返回值1。否则，返回值2(只能用作案例函数的参数)<br /> </td> 
   <td> when(&lt; condition&gt;，&lt; value1&gt;)<br /> </td> 
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
   <td> <strong>描述</strong><br /> </td> 
   <td> <strong>语法</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull2</strong><br /> </td> 
   <td> 指示所有参数均为非空且不为空<br /> </td> 
   <td> allnonNull2(&lt; string&gt;，&lt; string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull3</strong><br /> </td> 
   <td> 指示所有参数均为非空且不为空<br /> </td> 
   <td> allnonNull(&lt; string&gt;、&lt; string&gt;、&lt; string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ASCII</strong><br /> </td> 
   <td> 返回字符串中第一个字符的ASCII值<br /> </td> 
   <td> ASCII(&lt;字符串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Char</strong><br /> </td> 
   <td> 返回与“n”ASCII代码对应的字符<br /> </td> 
   <td> 字符(&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Charindex</strong><br /> </td> 
   <td> 返回字符串中字符串的位置<br /> </td> 
   <td> 字符串(&lt;字符串&gt;，&lt;字符串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DataLength</strong><br /> </td> 
   <td> 返回字符串中字符的数量<br /> </td> 
   <td> datalLength(&lt; String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>getLine</strong><br /> </td> 
   <td> 返回字符串的nth(从到n)行<br /> </td> 
   <td> getLine(&lt; string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ifequals</strong><br /> </td> 
   <td> 返回第三个参数(如果前两个参数相等，否则返回最后一个参数)<br /> </td> 
   <td> iFeQuals(&lt; string&gt;、&lt; string&gt;、&lt; string&gt;、&lt; string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>isMemonull</strong><br /> </td> 
   <td> 指示作为参数传递的memo是否为空<br /> </td> 
   <td> isMemonDull(&lt; Memo&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JXPublish</strong><br /> </td> 
   <td> 模拟作为参数传递的两个字符串。将在返回值的每个字符串之间添加一个空格。<br /> </td> 
   <td> JXPublish(&lt; string&gt;，&lt; string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords3</strong><br /> </td> 
   <td> 模拟作为参数传递的三个字符串。将在返回值的每个字符串之间添加一个空格。<br /> </td> 
   <td> JXPublish3(&lt; string&gt;、&lt; string&gt;、&lt; string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LPad</strong><br /> </td> 
   <td> 返回左侧完整的字符串<br /> </td> 
   <td> LPad(&lt;字符串&gt;，&lt; number&gt;，&lt; carbacre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Left</strong><br /> </td> 
   <td> 返回字符串的第n个字符<br /> </td> 
   <td> Left(&lt; string&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>长度</strong><br /> </td> 
   <td> 返回字符串长度<br /> </td> 
   <td> 长度(&lt;字符串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>更低</strong><br /> </td> 
   <td> 返回小写字符串<br /> </td> 
   <td> 更低(&lt;字符串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Lt修剪</strong><br /> </td> 
   <td> 删除字符串左侧的空格<br /> </td> 
   <td> L修剪(&lt; string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Md5Digest</strong><br /> </td> 
   <td> 返回字符串MD键的十六进制表示形式<br /> </td> 
   <td> Md摘要(&lt;字符串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MemoMinclude</strong><br /> </td> 
   <td> 指定备忘录是否包含作为参数传递的字符串<br /> </td> 
   <td> MemoMinclude(&lt; memo&gt;，&lt; string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RPad</strong><br /> </td> 
   <td> 在右侧返回完整的字符串<br /> </td> 
   <td> RPad(&lt; string&gt;，&lt; number&gt;，&lt;字符&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>替换时间</strong><br /> </td> 
   <td> 用字符串(第个参数)中的另一个字符串值(第个参数)替换指定字符串(第个参数)值的所有实例<br /> </td> 
   <td> 替换(&lt; String&gt;、&lt; String&gt;、&lt; String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Right</strong><br /> </td> 
   <td> 返回字符串的最后n个字符<br /> </td> 
   <td> 右(&lt;字符串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>R修剪</strong><br /> </td> 
   <td> 删除字符串右侧的空格<br /> </td> 
   <td> R修剪(&lt;字符串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha256Digest</strong><br /> </td> 
   <td> 为给定UTF字符串计算标准 <strong>SHA256</strong> 哈希哈希<br /> </td> 
   <td> Sha256摘要(&lt; String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha384Digest</strong><br /> </td> 
   <td> 为给定UTF字符串计算标准 <strong>SHA384</strong> 哈希<br /> </td> 
   <td> Sha384摘要(&lt; String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha512Digest</strong><br /> </td> 
   <td> 为给定UTF字符串计算标准 <strong>SHA512</strong> 哈希值<br /> </td> 
   <td> Sha512摘要(&lt; String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Smart Smart</strong><br /> </td> 
   <td> 返回大写字母中每个单词的第一个字母的字符串<br /> </td> 
   <td> 智能(&lt;字符串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>子字符串</strong><br /> </td> 
   <td> 从字符串的字符n处提取子字符串，长度为n2<br /> </td> 
   <td> subString(&lt; string&gt;，&lt; offset&gt;，&lt; length&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>tointlString</strong><br /> </td> 
   <td> 将数字转换为字符串<br /> </td> 
   <td> tointlString(&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>toString</strong><br /> </td> 
   <td> 将数字转换为字符串<br /> </td> 
   <td> toString(&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>上一页</strong><br /> </td> 
   <td> 返回大写字母中的字符串<br /> </td> 
   <td> 上限(&lt;字符串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLink</strong><br /> </td> 
   <td> 返回作为参数传递的链接的外键(如果其他两个参数相等)<br /> </td> 
   <td> VirtualLink(&lt; number&gt;，&lt; number&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLinkStr</strong><br /> </td> 
   <td> 返回作为参数传递的链接的外键(文本)键(如果其他两个参数相等)<br /> </td> 
   <td> VirtualLinkStr(&lt; string&gt;，&lt; number&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_aescribcC解密</strong><br /> </td> 
   <td> 用HEX格式(第个参数)中的键(<strong></strong>第个参数)和HEX格式的初始化矢量(3rd参数)解密HEX格式的加密值(第个参数)<br /> </td> 
   <td> encryption_aescribcC解密(&lt; String&gt;、&lt; String&gt;、&lt; String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_ aescribcEncrypt</strong><br /> </td> 
   <td> 使用AES算法(CBC块模式)使用一个字符串(第一个参数)加密一个字符串(第一个参数)和一个初始化矢量(第三个参数)。关键和初始化矢量必须以十六进制表示形式给出(从 <strong>\ x</strong>开始)。如果没有 <strong>\ x</strong>，结果将采用十六进制。<br /> 请注意，密钥大小可以是128位、192位、256位(16、24、32、32位字符)，但建议您使用与关键长度相同的256位和randomized IV。<br /> </td> 
   <td> encryption_ aescribcEncrypt(&lt; String&gt;，&lt; String&gt;，&lt; String&gt;)<br /> 例如：encryption_ aescribcEncrypt(johndoe@example.com，“<strong>\ x0123456789 ABCDEF012345689 ABCDEF</strong>”，“<strong>\ x0123456789 ABCDEFEDCBC9886543210</strong>”<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 集合 {#aggregates}

集合函数仅在从工作流的活动 [中添加其他数据](../../automating/using/query.md#enriching-data) 时才可用 **[!UICONTROL Query]** 。

聚合函数用于在一组值上执行计算。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名称</strong><br /> </td> 
   <td> <strong>描述</strong><br /> </td> 
   <td> <strong>语法</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>平均</strong>平均<br /> </td> 
   <td> 返回数字列中的平均值。<br /> </td> 
   <td> 平均(&lt; value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>计数</strong>、计数(NULL除外)<br /> </td> 
   <td> 计算列中的非空值。<br /> </td> 
   <td> 计数(&lt; value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Countal</strong>，全部计数<br /> </td> 
   <td> 计算所有值(包括空值和重复项)。<br /> </td> 
   <td> countle()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>独立</strong>、独特计数<br /> </td> 
   <td> 计算列中的非空值和不同值。<br /> </td> 
   <td> CountIndicated(&lt; value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Max</strong>，Max<br /> </td> 
   <td> 返回数值、字符串或日期列中的最大值。<br /> </td> 
   <td> Max(&lt; value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Min</strong>，Min<br /> </td> 
   <td> 返回数值、字符串或日期列中的最小值。<br /> </td> 
   <td> Min(&lt; value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sum</strong>、Sum<br /> </td> 
   <td> 返回数值列中的值总和。<br /> </td> 
   <td> Sum(&lt; value&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 表示形式 {#representation}

表示函数用于排序值。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名称</strong><br /> </td> 
   <td> <strong>描述</strong><br /> </td> 
   <td> <strong>语法</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Desc</strong><br /> </td> 
   <td> 应用降序排序<br /> </td> 
   <td> Desc(&lt; value1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>orderBy</strong><br /> </td> 
   <td> 在分区内对结果进行排序<br /> </td> 
   <td> orderBy(&lt; value1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>分区依据</strong><br /> </td> 
   <td> 分区在表上的查询结果<br /> </td> 
   <td> sectionBy(&lt; value1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowNum</strong><br /> </td> 
   <td> 根据表分区和排序顺序生成行号。MySQL不支持此函数<br /> </td> 
   <td> rowNum(compontionBy&gt;)、orderBy(&lt; value1&gt;))<br /> </td> 
  </tr> 
 </tbody> 
</table>

