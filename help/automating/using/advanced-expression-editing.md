---
title: 高级表达式编辑
description: 查询版向导允许您定义高级表达式。
page-status-flag: 从未激活
uuid: a635f999-27ce-41e0-a88c-8a3882e31efe
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 过滤数据
discoiquuid: 4375153c-0621-4d4c-bfcc-66d157f04f6c
context-tags: queryFilter，概述；audience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 高级表达式编辑{#advanced-expression-editing}

## 关于高级表达式编辑 {#about-advanced-expression-editing}

编辑表达式需要手动输入条件以形成规则。

此模式允许您使用高级功能。 这些函数允许您处理用于执行特定查询的值，如操作日期、字符串、数字字段、排序等。

编辑表达式时也可以使用事件变量。 有关此内容的详细信息，请参阅使 [用事件变量自定义活动](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) 。

您可以编辑表达式，以便：

* 通过添加规则时 **[!UICONTROL Advanced mode]** 可用的选项定义查询。

   ![](assets/expression_editor_2.png)

* 在工作流中编辑表达式。 例如，向活动添加其他数据。
* 编辑可见性条件以定义HTML内容编辑器中块的显示方式。 在这种情况下，表达式将以JavaScript格式进行编辑，并且不提供将高级函数作为标准使用。

## 编辑表达式 {#edit-an-expression}

高级表达式版本允许您手动定义一个与您的需求特别对应的表达式。

编辑表达式可在创建电子邮件时在“受众”窗口中使用，也可以在创建工作流时在查询活动中使用。

1. 通过“关于高级表达式编辑”部分中详细介绍的方法之一 [访问表达式编辑窗口](../../automating/using/advanced-expression-editing.md#about-advanced-expression-editing) 。 它涉及以下元素：

   * 在其中定义表达式的输入字段。
   * 可用字段列表，可在表达式中使用并与查询的定位维对应(请参阅定 [位维和资源](../../automating/using/query.md#targeting-dimensions-and-resources))。
   * 可用函数列表，按类别排序。
   ![](assets/expression_editor_1.png)

1. 通过直接在相应字段中输入表达式或使用可用字段和函数列表来编辑表达式。

   双击字段或表达式可将其添加到放置光标的表达式中。

   可以使用工作流的事件变量构建表达式。 有关此内容的详细信息，请参阅使 [用事件变量自定义活动](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) 。

1. 根据需要为规则指定一个特定名称。 输入的名称将作为规则名称显示在查询编辑器工作区中。

通过编辑表达式，您可以个性化“受众”表达式以根据需要定位受众。

**相关主题：**

* [表达式语法](../../automating/using/advanced-expression-editing.md#expression-syntax)
* [功能列表](../../automating/using/list-of-functions.md)

## 表达式语法 {#expression-syntax}

### 标准语法 {#standard-syntax}

标准表达式由一个或多个条件组成，这些条件与以下语法元素相关：

* 每个条件都采用 **&lt;value1&gt; &lt;comparison operator&gt; &lt;value2&gt;的形式，据此** :

   * **&lt;value1&gt;** 是字段或函数。 例如 **,@created** for the date a profile was created or **Year(@created)** for the year a profile was created.
   * **&lt;comparison operator&gt;** 是“比较”运算符部分中列出的 [运算符之一](../../automating/using/advanced-expression-editing.md#comparison-operators) 。 此运算符定义 **&lt;value1&gt;和****&lt;value2&gt;之间的比较方法**。
   * **&lt;value2&gt;** 是手动输入的字段、函数或值。
   >[!NOTE]
   >
   >&lt; **value1&gt;** 和 **** &lt;value2&gt;类型数据必须相同。 例如，如果 **&lt;value1&gt;是日期** ，则 **&lt;value2&gt;** 也必须是日期。

* 如果要使用多个条件，可以使用逻辑运算符将它们组合在一起。

   * **[!UICONTROL AND]**:两个条件相交。
   * **[!UICONTROL OR]**:两个条件结合在一起。

例如：

```
Year(@created) = Year(GetDate()) AND Month(@created) = Month(GetDate())
```

在此示例中，目标是创建日期在当前月份和年份的配置文件。

### JavaScript语法 {#javascript-syntax}

定义HTML内容编辑器的文本类型块的可见性条件时，必须使用具有JavaScript类型语法的表达式。

JavaScript表达式由一个或多个条件组成，它们使用以下语法元素：

* 每个条件都采用 **&lt;context&gt; &lt;comparison operator&gt; &lt;value2&gt;的形式，据此** :

   * **&lt;context&gt;** 是允许您指定上下文的字段或函数。 例如， **context.profile。@email** （针对配置文件的电子邮件地址）或 **context.profile.firstName.length()** （针对配置文件名的字符数）。
   * **&lt;comparison operator&gt;** 是“比较”运算符部分中列出的 [运算符之一](../../automating/using/advanced-expression-editing.md#comparison-operators) 。 此运算符定义 **&lt;context&gt;和****&lt;value2&gt;之间的比较方法**。
   * **&lt;value2&gt;** 是手动输入的字段、函数或值。
   >[!NOTE]
   &lt; **context&gt;****** 和&lt;value2&gt;类型数据必须相同。 例如，如果 **&lt;context&gt;** is a date，则 **&lt;value2&gt;** assuble be date.

* 如果要使用多个条件，可以使用逻辑运算符将它们组合在一起。

   * **[!UICONTROL &&]**:两个条件相交。
   * **[!UICONTROL ||]**:两个条件结合在一起。

例如：

```
context.profile.age > 21 && context.profile.firstName.length() > 0
```

在此示例中，提供了21岁以上且其名字的配置文件(以 **firstName** 字段至少包含一个字符为例)。

## 比较运算符 {#comparison-operators}

对于某些规则，查询编辑器允许您选择一个值来定义条件。

条件必须通过使用下列运算符之一链接到值。

<table> 
 <thead> 
  <tr> 
   <th> 运算符<br /> </th> 
   <th> 标准语法<br /> </th> 
   <th> JavaScript语法<br /> </th> 
   <th> 说明<br /> </th> 
   <th> Example<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <span class="uicontrol">等于</span><br /> </td> 
   <td> =<br /> </td> 
   <td> ==<br /> </td> 
   <td> 第一个值必须与第二个值完全相同。<br /> </td> 
   <td> <strong>@lastName = Martin</strong> 将检索其姓氏为“Martin”的配置文件，只检索这些相同的字符。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">大于</span><br /> </td> 
   <td> &gt;<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> 第一个值必须绝对大于第二个值。<br /> </td> 
   <td> <strong>@age &gt; 50</strong> 可检索早于“50”、“51”、“52”等的配置文件。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">小于</span><br /> </td> 
   <td> &lt;<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> 第一个值必须绝对小于第二个值。<br /> </td> 
   <td> <strong>@created &lt; DaysAgo(100)</strong> 检索在不到100天前的数据库中创建的所有配置文件。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">大于或等于</span><br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> 第一个值必须大于或等于第二个值。<br /> </td> 
   <td> <strong>@age &gt;= 30</strong> 可检索年龄在30岁及以上的档案。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">小于或等于</span><br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> 第一值必须小于或等于第二值。<br /> </td> 
   <td> <strong>@age &lt;= 60</strong> 可检索年龄在60岁或以下的配置文件。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">不同 </span><br /> </td> 
   <td> !=<br /> </td> 
   <td> !=<br /> </td> 
   <td> 第一个值必须不同于第二个值。<br /> </td> 
   <td> <strong>@language != English</strong> 将检索尚未定义为英语的配置文件。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">包含</span><br /> </td> 
   <td> IN<br /> </td> 
   <td> N/A<br /> </td> 
   <td> 第一个值必须包含第二个值。<br /> </td> 
   <td> <strong>@domain IN mail</strong>。 此处，结果中将返回所有具有“mail”值的域名。 因此，“gmail.com”域名将构成返回结果的一部分。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">喜欢</span><br /> </td> 
   <td> LIKE<br /> </td> 
   <td> N/A<br /> </td> 
   <td> <span class="uicontrol">Like</span> 与Contains运算符非 <span class="uicontrol">常相似</span> 。 它允许您在所搜 <span class="uicontrol">索的值中</span> ，插入%通配符。<br /> </td> 
   <td> <strong>@lastName LIKE Mart%n</strong>。 在此处，替换字符 <strong>%</strong> 用作“小丑”，在拼写不正确的假设情况下查找名称“Martin”。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">不喜欢</span><br /> </td> 
   <td>  NOT<br /> </td> 
   <td> N/A<br /> </td> 
   <td> 与“喜欢”类 <span class="uicontrol">似</span>。 它不允许您恢复输入的值。 在此，输入的值也必须包含 <span class="uicontrol">%</span> 通配符。<br /> </td> 
   <td> <strong>@lastName不是Smi%h</strong>。 此处，收件人与名称“Smi%h”（so Smith，等）对应不返回。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">为空</span><br /> </td> 
   <td> 为空<br /> </td> 
   <td> N/A<br /> </td> 
   <td> 第一个值必须与空值对应。<br /> </td> 
   <td> <strong>@mobilePhone IS NULL</strong> 将检索其手机号码尚未提供的所有配置文件。<br /> </td> 
  </tr> 
 </tbody> 
</table>

