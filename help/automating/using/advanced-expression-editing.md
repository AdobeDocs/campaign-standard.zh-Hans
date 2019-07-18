---
title: 高级表达式编辑
seo-title: 高级表达式编辑
description: 高级表达式编辑
seo-description: 查询版本向导允许您定义高级表达式。
page-status-flag: 从未激活
uuid: a635f999-27ce-41e0-a88 c-8a3882 e31 efe
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 筛选数据
discoiquuid: 4375153c-0621-4d4c-bcfci-66d157 f04 f6 c
context-tags: queryFilter，概述；受众，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Advanced expression editing{#advanced-expression-editing}

## About advanced expression editing {#about-advanced-expression-editing}

编辑表达式涉及手动输入条件以构成规则。

此模式允许您使用高级函数。这些函数允许您操作用于执行特定查询的值，如处理日期、字符串、数字字段、排序等。

编辑表达式时也可以使用事件变量。For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

您可以编辑表达式，以便：

* Define a query, via the **[!UICONTROL Advanced mode]** option which is available when a rule is added.

   ![](assets/expression_editor_2.png)

* 在工作流中编辑表达式。例如，为活动添加其他数据。
* 编辑可见性条件以定义如何显示HTML内容编辑器中的块。在这种情况下，将以JavaScript格式编辑表达式，但不会将高级函数用作标准。

## Edit an expression {#edit-an-expression}

高级表达式版本可让您手动定义一个特定于您的需求的表达式。

在创建工作流时，可以在创建电子邮件或在查询活动中使用“受众”窗口时使用编辑表达式。

1. Access the expression editing window via one of the methods detailed in the [About advanced expression editing](../../automating/using/advanced-expression-editing.md#about-advanced-expression-editing) section. 它涉及以下元素：

   * 定义表达式的输入字段。
   * The list of available fields that can be used in the expression and correspond to the targeting dimension of the query (see [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)).
   * 可用函数列表，按类别排序。
   ![](assets/expression_editor_1.png)

1. 通过直接在相应字段中输入表达式或使用可用字段和函数的列表来编辑表达式。

   双击某个字段或表达式可将其添加到放置光标的表达式。

   可以使用工作流的事件变量来构建表达式。For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

1. 根据需要为您的规则提供特定名称。输入的名称将在查询编辑器工作区中显示为规则名称。

编辑表达式可让您根据需要个性化受众表达式以定位您的人群。

**相关主题：**

* [表达式语法](../../automating/using/advanced-expression-editing.md#expression-syntax)
* [函数列表](../../automating/using/list-of-functions.md)

## Expression Syntax {#expression-syntax}

### Standard syntax {#standard-syntax}

标准表达式由一个或多个符合以下语法元素的条件组成：

* Each condition takes the form of **&lt;value1&gt; &lt;comparison operator&gt; &lt;value2&gt;** whereby:

   * **&lt; value1&gt;** 是一个字段或函数。For example **@created** for the date a profile was created or **Year(@created)** for the year a profile was created.
   * **&lt;比较运算符&gt;** 是 [比较运算符](../../automating/using/advanced-expression-editing.md#comparison-operators) 部分中列出的操作符之一。This operator defines the comparison method between **&lt;value1&gt;** and **&lt;value2&gt;**.
   * **&lt; value2&gt;** 是一个字段、一个函数或手动输入的值。
   >[!NOTE]
   >
   >**&lt; value1&gt;** 和 **&lt; value2&gt;** 类型数据必须相同。For example, if **&lt;value1&gt;** is a date, then **&lt;value2&gt;** must also be a date.

* 如果您希望使用多个条件，可以使用逻辑运算符组合它们。

   * **[!UICONTROL AND]**：两种条件相交。
   * **[!UICONTROL OR]**：两种条件相结合。

例如：

```
Year(@created) = Year(GetDate()) AND Month(@created) = Month(GetDate())
```

在此示例中，创建日期处于当前月份和年的配置文件为目标。

### JavaScript syntax {#javascript-syntax}

定义HTML内容编辑器文本类型块的可见性条件时，必须使用JavaScript类型语法的表达式。

JavaScript表达式由一个或多个条件组成，它们使用以下语法元素：

* Each condition takes the form of **&lt;context&gt; &lt;comparison operator&gt; &lt;value2&gt;** whereby:

   * **&lt; context&gt;** 是一个字段或一个允许您指定上下文的函数。For example **context.profile.@email** for a profile's email address or **context.profile.firstName.length()** for the number of characters of a profile's first name.
   * **&lt;比较运算符&gt;** 是 [比较运算符](../../automating/using/advanced-expression-editing.md#comparison-operators) 部分中列出的操作符之一。This operator defines the comparison method between **&lt;context&gt;** and **&lt;value2&gt;**.
   * **&lt; value2&gt;** 是一个字段、一个函数或手动输入的值。
   >[!NOTE]
   **&lt; context&gt;** 和 **&lt; value2&gt;** 类型数据必须相同。For example, if **&lt;context&gt;** is a date, then **&lt;value2&gt;** must also be a date.

* 如果您希望使用多个条件，可以使用逻辑运算符组合它们。

   * **[!UICONTROL &&]**：两种条件相交。
   * **[!UICONTROL ||]**：两种条件相结合。

例如：

```
context.profile.age > 21 && context.profile.firstName.length() > 0
```

In this example, profiles older than 21 years of age and whose first name has been provided (symbolized by the fact that the **firstName** field contains at least one character).

## Comparison operators {#comparison-operators}

对于某些规则，查询编辑器允许您选择一个值来定义条件。

条件必须使用下列运算符之一链接到值。

<table> 
 <thead> 
  <tr> 
   <th> Operator<br /> </th> 
   <th> Standard syntax<br /> </th> 
   <th> JavaScript syntax<br /> </th> 
   <th> Description<br /> </th> 
   <th> Example<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <span class="uicontrol">等于</span><br /> </td> 
   <td> =<br /> </td> 
   <td> ==<br /> </td> 
   <td> The first value must be completely identical to the second value.<br /> </td> 
   <td> <strong>@ lastName= Martin</strong> 检索姓氏为“Martin”的配置文件，但只有这些相同字符。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">大于</span><br /> </td> 
   <td> &gt;<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> The first value must categorically be more than the second value.<br /> </td> 
   <td> <strong>@ age&gt;50</strong> 检索年龄大于“50”、因此“51”、“52”等配置文件。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">小于</span><br /> </td> 
   <td> &lt;<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> The first value must categorically be less than the second value.<br /> </td> 
   <td> <strong>@ created&lt; aysago(100)</strong> 检索在不超过100天前在数据库中创建的所有配置文件。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">大于或等于</span><br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> The first value must be more than or equal to the second value.<br /> </td> 
   <td> <strong>@ age&gt;=30</strong> 检索30年以上的配置文件。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">小于或等于</span><br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> The first value must be less than or equal to the second value.<br /> </td> 
   <td> <strong>@ age&lt;=60</strong> 检索60或更少的配置文件。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">不同的 </span><br /> </td> 
   <td> !=<br /> </td> 
   <td> !=<br /> </td> 
   <td> The first value must be different from the second value.<br /> </td> 
   <td> <strong>@语言！= English</strong> retrieves profiles that have not been defined as English speaking.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">包含</span><br /> </td> 
   <td> IN<br /> </td> 
   <td> N/A<br /> </td> 
   <td> The first value must contain the second value.<br /> </td> 
   <td> <strong>@域in mail</strong>.此处，返回所有具有“邮件”值的域名。Consequently, the 'gmail.com' domain name will make up part of the returned results.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">赞一样</span><br /> </td> 
   <td> LIKE<br /> </td> 
   <td> N/A<br /> </td> 
   <td> <span class="uicontrol">类似</span> 于 <span class="uicontrol">包含</span> 运算符的非常相似。It lets you insert a <span class="uicontrol">%</span> wild card character in the value that is being searched.<br /> </td> 
   <td> <strong>@ LastName LIKE Mart%n</strong>.Here, the substitution character <strong>%</strong> serves as a "joker" to find the name "Martin" in the hypothetical case that the spelling is not correct.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">不像</span><br /> </td> 
   <td> NOT<br /> </td> 
   <td> N/A<br /> </td> 
   <td> Is similar to <span class="uicontrol">Like</span>. 它允许您不恢复输入的值。Here too, the entered value must contain the <span class="uicontrol">%</span> wild card character.<br /> </td> 
   <td> <strong>@ lastName NOT Smi%h</strong>.此处，收件人对应于名称“Smi%h”(sith Smith，etc)。are not returned as a result.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">为空</span><br /> </td> 
   <td> IS NULL<br /> </td> 
   <td> N/A<br /> </td> 
   <td> The first value must correspond to an empty value.<br /> </td> 
   <td> <strong>@ MobilePhone IS NULL</strong> 检索未提供手机号码的所有配置文件。<br /> </td> 
  </tr> 
 </tbody> 
</table>

