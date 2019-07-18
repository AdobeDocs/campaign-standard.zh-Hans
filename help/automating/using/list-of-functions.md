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
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# List of functions{#list-of-functions}

## About functions {#about-functions}

查询编辑工具允许您使用高级函数进行复杂过滤。To do this, the tool palette contains the **[!UICONTROL Expression]** element that you can use in the workspace. Further information on this element is detailed in a [specific section](../../automating/using/advanced-expression-editing.md).

此元素允许您手动输入条件。您可以在此使用在以下部分中定义的函数。

有几种函数类型可用，具体取决于所需的结果和操作数据的类型：

* 日期
* Geomarketing
* 数值
* 其他函数
* 集合
* 字符串处理
* 排序

## Dates {#dates}

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
   <td> Adds a number of days to a date<br /> </td> 
   <td> AddDays(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>加载项</strong><br /> </td> 
   <td> Adds a number of hours to a date<br /> </td> 
   <td> AddHours(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>添加分钟数</strong><br /> </td> 
   <td> Adds a number of minutes to a date<br /> </td> 
   <td> AddMinutes(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>addMonthly</strong><br /> </td> 
   <td> Adds a number of months to a date<br /> </td> 
   <td> AddMonths(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>addSeconds</strong><br /> </td> 
   <td> Adds a number of seconds to a date<br /> </td> 
   <td> AddSeconds(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>addAnys</strong><br /> </td> 
   <td> Adds a number of years to a date<br /> </td> 
   <td> AddYears(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>仅限DateOnly</strong><br /> </td> 
   <td> Returns the date only (with time at 00:00)<br /> </td> 
   <td> DateOnly(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Day</strong><br /> </td> 
   <td> Returns the number representing the day of the date<br /> </td> 
   <td> Day(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>第一年</strong><br /> </td> 
   <td> Returns a number representing the day in the year of the date<br /> </td> 
   <td> DayOfYear(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Daysago</strong><br /> </td> 
   <td> Returns the current date minus n days<br /> </td> 
   <td> DaysAgo(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysaGoint</strong><br /> </td> 
   <td> Returns the current date minus n days (as an integer yyyymmdd)<br /> </td> 
   <td> DaysAgoInt(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysDiff</strong><br /> </td> 
   <td> Number of days between two dates<br /> </td> 
   <td> DaysDiff(&lt;end date&gt;, &lt;start date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Daysed</strong><br /> </td> 
   <td> Returns the age in days of a date<br /> </td> 
   <td> DaysOld(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>getDate</strong><br /> </td> 
   <td> Returns the current system date of the server<br /> </td> 
   <td> GetDate()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>小时</strong><br /> </td> 
   <td> Returns the hour of the date<br /> </td> 
   <td> Hour(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HoursDiff</strong><br /> </td> 
   <td> Returns the number of hours between two dates<br /> </td> 
   <td> HoursDiff(&lt;end date&gt;, &lt;start date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LocalToOutc</strong><br /> </td> 
   <td> Converts a local date and time to UTC<br /> </td> 
   <td> LocalToUTC(&lt;date&gt;, &lt;Time Zone&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>分钟</strong><br /> </td> 
   <td> Returns the minutes of the date<br /> </td> 
   <td> Minute(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>targesDiff</strong><br /> </td> 
   <td> Returns the number of minutes between two dates<br /> </td> 
   <td> MinutesDiff(&lt;end date&gt;, &lt;start date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>月</strong><br /> </td> 
   <td> Returns the number representing the month of the date<br /> </td> 
   <td> Month(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Monthsago</strong><br /> </td> 
   <td> Returns the date corresponding to the current date minus n months<br /> </td> 
   <td> MonthsAgo(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsDiff</strong><br /> </td> 
   <td> Returns the number of months between two dates<br /> </td> 
   <td> MonthsDiff(&lt;end date&gt;, &lt;start date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthSales</strong><br /> </td> 
   <td> Returns the age in months of a date<br /> </td> 
   <td> MonthsOld(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>第二个</strong><br /> </td> 
   <td> Returns the seconds of the date<br /> </td> 
   <td> Second(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>旧版</strong><br /> </td> 
   <td> 返回最早的日期 </td> 
   <td> Oldest(&lt;Date&gt;, &lt;Date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>searchDiff</strong><br /> </td> 
   <td> Returns the number of seconds between two dates<br /> </td> 
   <td> SecondsDiff(&lt;end date&gt;, &lt;start date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>分时段</strong><br /> </td> 
   <td> Subtracts a number of days from a date<br /> </td> 
   <td> SubDays(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>子时间</strong><br /> </td> 
   <td> Subtracts a number of hours from a date<br /> </td> 
   <td> SubHours(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>分时段</strong><br /> </td> 
   <td> Subtracts a number of minutes from a date<br /> </td> 
   <td> SubMinutes(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>子月份</strong><br /> </td> 
   <td> Subtracts a number of months from a date<br /> </td> 
   <td> SubMonths(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>sub秒</strong><br /> </td> 
   <td> Subtracts a number of seconds from a date<br /> </td> 
   <td> SubSeconds(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>年子年</strong><br /> </td> 
   <td> Subtracts a number of years from a date<br /> </td> 
   <td> SubYears(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDate</strong><br /> </td> 
   <td> Converts a date + time as a date<br /> </td> 
   <td> ToDate(&lt;date + time&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>toDateTime</strong><br /> </td> 
   <td> Converts a string to a date + time<br /> </td> 
   <td> ToDateTime(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>todateTimeWithTimeZone</strong><br /> </td> 
   <td> 将字符串转换为日期+时区。<br /> 示例：todateTimeWithTimeZone(“2019-02-1908：09：00”，“亚洲/德黑兰”)<br /> </td> 
   <td> ToDateTimeWithTimezone(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>截断日期</strong><br /> </td> 
   <td> Rounds a date+time to the nearest second<br /> </td> 
   <td> TruncDate(@lastModified, &lt;number of seconds&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>截断数据</strong><br /> </td> 
   <td> Rounds a date + time to a given precision expressed in seconds<br /> </td> 
   <td> TruncDateTZ(&lt;date&gt;, &lt;number of seconds&gt;, &lt;time zone&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>截断1/4</strong><br /> </td> 
   <td> Rounds a date off to the quarter<br /> </td> 
   <td> TruncQuarter(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>截断时间</strong><br /> </td> 
   <td> Rounds the time part up to the nearest second<br /> </td> 
   <td> TruncTime(&lt;date&gt;, &lt;number of seconds&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>截断Week</strong><br /> </td> 
   <td> Rounds a date off to the week<br /> </td> 
   <td> TruncWeek(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>截断年份</strong><br /> </td> 
   <td> Rounds a date + time to January 1st of the year<br /> </td> 
   <td> TruncYear(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>工作日</strong><br /> </td> 
   <td> Returns the number representing the day in the week of the date<br /> </td> 
   <td> WeekDay(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>年</strong><br /> </td> 
   <td> Returns the number representing the year of the date<br /> </td> 
   <td> Year(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>月和月</strong><br /> </td> 
   <td> Returns the number representing the year and month of the date<br /> </td> 
   <td> YearAndMonth(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>yeArsDiff</strong><br /> </td> 
   <td> Returns the number of years between the two dates<br /> </td> 
   <td> YearsDiff(&lt;end date&gt;, &lt;start date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YeArsed</strong><br /> </td> 
   <td> Returns the age in years of a date<br /> </td> 
   <td> YearsOld(&lt;date&gt;)<br /> </td> 
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
   <td> Returns the distance in kilometers between two points defined by their longitude and latitude (expressed in degrees)<br /> </td> 
   <td> Distance(&lt;Longitude A&gt;, &lt;Latitude A&gt;, &lt;Longitude B&gt;, &lt;Latitude B&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Numerical {#numerical}

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
   <td> Returns the absolute value of a number<br /> </td> 
   <td> Abs(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ceil</strong><br /> </td> 
   <td> Returns the lowest integer greater than or equal to a number<br /> </td> 
   <td> Ceil(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Floor</strong><br /> </td> 
   <td> Returns the greatest integer greater than or equal to a number<br /> </td> 
   <td> Floor(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>最大程度</strong><br /> </td> 
   <td> Returns the greater of two numbers<br /> </td> 
   <td> Greatest(&lt;number 1&gt;, &lt;number 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>最少</strong><br /> </td> 
   <td> Returns the smaller of two numbers<br /> </td> 
   <td> Least(&lt;number 1&gt;, &lt;number 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mod</strong><br /> </td> 
   <td> Returns the remainder of the integer division from n1 by n2<br /> </td> 
   <td> Mod(&lt;number 1&gt;, &lt;number 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>百分比</strong><br /> </td> 
   <td> Returns the ratio of two numbers expressed as a percentage<br /> </td> 
   <td> Percent(&lt;number 1&gt;, &lt;number 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>随机</strong><br /> </td> 
   <td> Returns the random value<br /> </td> 
   <td> Random()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>圆形</strong><br /> </td> 
   <td> Rounds off a number to n decimals<br /> </td> 
   <td> Round(&lt;number&gt;, &lt;number of decimals&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sign</strong><br /> </td> 
   <td> Returns the sign of the number<br /> </td> 
   <td> Sign(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>touble</strong><br /> </td> 
   <td> Converts an integer to a float<br /> </td> 
   <td> ToDouble(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInt64</strong><br /> </td> 
   <td> Converts a float to a 64 bit integer<br /> </td> 
   <td> ToInt64(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInteger</strong><br /> </td> 
   <td> Converts a float to an integer<br /> </td> 
   <td> ToInteger(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Trunc</strong><br /> </td> 
   <td> Truncates n1 to n2 decimals<br /> </td> 
   <td> Trunc(&lt;n1&gt;, &lt;n2&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Others {#others}

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
   <td> 如果验证条件，则返回值1。Otherwise, returns value 2<br /> </td> 
   <td> Case(When(&lt;condition&gt;, &lt;value 1&gt;), Else(&lt;value 2&gt;))<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Clearbit</strong><br /> </td> 
   <td> Deletes the Flag in the value<br /> </td> 
   <td> ClearBit(&lt;identifier&gt;, &lt;flag&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Coalesce</strong><br /> </td> 
   <td> Returns value 2 if value 1 is zero or null, otherwise returns value 1<br /> </td> 
   <td> Coalesce(&lt;value 1&gt;, &lt;value 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Decode</strong><br /> </td> 
   <td> Returns value 3 is value 1 = value 2, otherwise returns 4<br /> </td> 
   <td> Decode(&lt;value 1&gt;, &lt;value 2&gt;, &lt;value 3&gt;, &lt;value 4&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>其它</strong><br /> </td> 
   <td> Returns value 1 (may only be used as a parameter of the case function)<br /> </td> 
   <td> Else(&lt;value 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>getEmailDomain</strong><br /> </td> 
   <td> Extracts the domain from an email address<br /> </td> 
   <td> GetEmailDomain(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>getMirrorURL</strong><br /> </td> 
   <td> Retrieves the URL of the mirror page server<br /> </td> 
   <td> GetMirrorURL(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>iIF</strong><br /> </td> 
   <td> Returns value 1 if the expression is true, otherwise returns value 2<br /> </td> 
   <td> Iif(&lt;condition&gt;, &lt;value 1&gt;, &lt;value 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>isBitSet</strong><br /> </td> 
   <td> Indicates whether the Flag is in the value<br /> </td> 
   <td> IsBitSet(&lt;identifier&gt;, &lt;flag&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>isemptyString</strong><br /> </td> 
   <td> Returns value 2 if the string is empty, otherwise returns value 3<br /> </td> 
   <td> IsEmptyString(&lt;string&gt;, &lt;value 2&gt;, &lt;value 3&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Nonull</strong><br /> </td> 
   <td> Returns the empty string if the argument is NULL<br /> </td> 
   <td> NoNull(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowID</strong><br /> </td> 
   <td> Returns the line number<br /> </td> 
   <td> RowId<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>setBit</strong><br /> </td> 
   <td> Forces the Flag in the value<br /> </td> 
   <td> SetBit(&lt;identifier&gt;, &lt;flag&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>setVar</strong><br /> </td> 
   <td> Sets a variable<br /> </td> 
   <td> SetVar(&lt;variable&gt;, &lt;expression&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Toboolean</strong><br /> </td> 
   <td> Converts a number into a Boolean<br /> </td> 
   <td> ToBoolean(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>When</strong><br /> </td> 
   <td> 如果验证表达式，则返回值1。Otherwise, returns value 2 (may only be used as a parameter of the case function)<br /> </td> 
   <td> When(&lt;condition&gt;, &lt;value 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>newUUID</strong><br /> </td> 
   <td> Returns a new UUID.<br /> </td> 
   <td> newUUID<br /> </td> 
  </tr> 
 </tbody> 
</table>

## String {#string}

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
   <td> Indicates if all parameters are non-null and not empty<br /> </td> 
   <td> AllNonNull2(&lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull3</strong><br /> </td> 
   <td> Indicates if all parameters are non-null and not empty<br /> </td> 
   <td> AllNonNull3(&lt;string&gt;, &lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ASCII</strong><br /> </td> 
   <td> Returns the ASCII value of the first character in the string<br /> </td> 
   <td> Ascii(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Char</strong><br /> </td> 
   <td> Returns the character corresponding to the 'n' ASCII code<br /> </td> 
   <td> Char(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Charindex</strong><br /> </td> 
   <td> Returns the position of string 2 in string 1<br /> </td> 
   <td> Charindex(&lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DataLength</strong><br /> </td> 
   <td> Returns the number of characters in a string<br /> </td> 
   <td> DataLength(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>getLine</strong><br /> </td> 
   <td> Returns the nth (from 1 to n) line of the string<br /> </td> 
   <td> GetLine(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ifequals</strong><br /> </td> 
   <td> Returns the third parameter if the first two parameters are equal otherwise returns the last parameter<br /> </td> 
   <td> IfEquals(&lt;string&gt;, &lt;string&gt;, &lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>isMemonull</strong><br /> </td> 
   <td> Indicates if the memo passed as a parameter is null<br /> </td> 
   <td> IsMemoNull(&lt;Memo&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JXPublish</strong><br /> </td> 
   <td> 模拟作为参数传递的两个字符串。A space is added between each string in the returned value.<br /> </td> 
   <td> JuxtWords(&lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords3</strong><br /> </td> 
   <td> 模拟作为参数传递的三个字符串。A space is added between each string in the returned value.<br /> </td> 
   <td> JuxtWords3(&lt;string&gt;, &lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LPad</strong><br /> </td> 
   <td> Returns the completed string on the left<br /> </td> 
   <td> LPad(&lt;string&gt;, &lt;number&gt;, &lt;caractère&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Left</strong><br /> </td> 
   <td> Returns the first n characters of the string<br /> </td> 
   <td> Left(&lt;string&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>长度</strong><br /> </td> 
   <td> Returns the string length<br /> </td> 
   <td> Length(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>更低</strong><br /> </td> 
   <td> Returns the string in lowercase<br /> </td> 
   <td> Lower(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Lt修剪</strong><br /> </td> 
   <td> Removes spaces to the left of the string<br /> </td> 
   <td> Ltrim(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Md5Digest</strong><br /> </td> 
   <td> Returns an hexadecimal representation of the MD5 key of a string<br /> </td> 
   <td> Md5Digest(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MemoMinclude</strong><br /> </td> 
   <td> Specifies whether the memo contains the string passed as a parameter<br /> </td> 
   <td> MemoContains(&lt;memo&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RPad</strong><br /> </td> 
   <td> Returns the completed string on the right<br /> </td> 
   <td> RPad(&lt;string&gt;, &lt;number&gt;, &lt;character&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>替换时间</strong><br /> </td> 
   <td> Replaces all occurrences of a specified string (2nd parameter) value with another string value (3rd parameter) in a string (1st parameter)<br /> </td> 
   <td> Replace(&lt;String&gt;, &lt;String&gt;, &lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Right</strong><br /> </td> 
   <td> Returns the last n characters of the string<br /> </td> 
   <td> Right(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>R修剪</strong><br /> </td> 
   <td> Removes spaces to the right of the string<br /> </td> 
   <td> Rtrim(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha256Digest</strong><br /> </td> 
   <td> Calculates the standard <strong>SHA256</strong> hash for a given UTF8 string<br /> </td> 
   <td> Sha256Digest(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha384Digest</strong><br /> </td> 
   <td> Calculates the standard <strong>SHA384</strong> hash for a given UTF8 string<br /> </td> 
   <td> Sha384Digest(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha512Digest</strong><br /> </td> 
   <td> Calculates the standard <strong>SHA512</strong> hash for a given UTF8 string<br /> </td> 
   <td> Sha512Digest(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Smart Smart</strong><br /> </td> 
   <td> Returns the string with the first letter of each word in capitals<br /> </td> 
   <td> Smart(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>子字符串</strong><br /> </td> 
   <td> Extracts the sub-string starting at character n1 of the string and with a length of n2<br /> </td> 
   <td> Substring(&lt;string&gt;, &lt;offset&gt;, &lt;length&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>tointlString</strong><br /> </td> 
   <td> Converts the number to a string<br /> </td> 
   <td> ToIntlString(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>toString</strong><br /> </td> 
   <td> Converts the number to a string<br /> </td> 
   <td> ToString(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>上一页</strong><br /> </td> 
   <td> Returns the string in capitals<br /> </td> 
   <td> Upper(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLink</strong><br /> </td> 
   <td> Returns the foreign key of a link passed as a parameter if the other two parameters are equal<br /> </td> 
   <td> VirtualLink(&lt;number&gt;, &lt;number&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLinkStr</strong><br /> </td> 
   <td> Returns the foreign (text) key of a link passed as a parameter if the other two parameters are equal<br /> </td> 
   <td> VirtualLinkStr(&lt;string&gt;, &lt;number&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_aescribcC解密</strong><br /> </td> 
   <td> Decrypts an encrypted value in HEX format with "<strong>x</strong>" prefix (1st parameter) using a key in HEX format (2nd parameter) and an initialization vector in HEX format (3rd parameter)<br /> </td> 
   <td> encryption_aescbcDecrypt(&lt;String&gt;, &lt;String&gt;, &lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_ aescribcEncrypt</strong><br /> </td> 
   <td> 使用AES算法(CBC块模式)使用一个字符串(第一个参数)加密一个字符串(第一个参数)和一个初始化矢量(第三个参数)。The key and the initialization vector must be given in a hexadecimal representation (starting with <strong>\x</strong>). The result will be in hexadecimal without the <strong>\x</strong>.<br /> 请注意，密钥大小可以是128位、192位、256位(16、24、32、32位字符)，但建议您使用与关键长度相同的256位和randomized IV。<br /> </td> 
   <td> encryption_aescbcEncrypt(&lt;String&gt;, &lt;String&gt;, &lt;String&gt;)<br /> For example: encryption_aescbcEncrypt(johndoe@example.com, "<strong>\x0123456789ABCDEF0123456789ABCDEF</strong>", "<strong>\x0123456789ABCDEFFEDCBA9876543210</strong>")<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Aggregates {#aggregates}

The aggregation functions are only available when [adding additional data](../../automating/using/query.md#enriching-data) from a workflow's **[!UICONTROL Query]** activity.

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
   <td> Returns the average in a numerical column.<br /> </td> 
   <td> Avg(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>计数</strong>、计数(NULL除外)<br /> </td> 
   <td> Counts the non-null values in a column.<br /> </td> 
   <td> Count(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Countal</strong>，全部计数<br /> </td> 
   <td> Counts all of the values (including null values and duplicates).<br /> </td> 
   <td> CountAll()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>独立</strong>、独特计数<br /> </td> 
   <td> Counts the non-null, distinct values in a column.<br /> </td> 
   <td> Countdistinct(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Max</strong>，Max<br /> </td> 
   <td> Returns the maximum value in a numerical, string, or date column.<br /> </td> 
   <td> Max(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Min</strong>，Min<br /> </td> 
   <td> Returns the minimum value in a numerical, string, or date column.<br /> </td> 
   <td> Min(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sum</strong>、Sum<br /> </td> 
   <td> Returns the sum of the values in a numerical column.<br /> </td> 
   <td> Sum(&lt;value&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Representation {#representation}

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
   <td> Applies a descending sort<br /> </td> 
   <td> Desc(&lt;value 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>orderBy</strong><br /> </td> 
   <td> Sorts the result within the partition<br /> </td> 
   <td> OrderBy(&lt;value 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>分区依据</strong><br /> </td> 
   <td> Partitions the result of a query on a table<br /> </td> 
   <td> PartitionBy(&lt;value 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowNum</strong><br /> </td> 
   <td> 根据表分区和排序顺序生成行号。This function is not supported for MySQL<br /> </td> 
   <td> RowNum(PartitionBy(&lt;value 1&gt;), OrderBy(&lt;value 1&gt;))<br /> </td> 
  </tr> 
 </tbody> 
</table>

