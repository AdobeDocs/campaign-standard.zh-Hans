---
title: 高级表达式编辑
description: 利用查询版向导，可定义高级表达式。
audience: automating
content-type: reference
topic-tags: filtering-data
context-tags: queryFilter,overview;audience,main
feature: Workflows
role: Data Architect
level: Experienced
exl-id: f11754fb-188e-4cae-bd5b-0dfbf74befb3
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 98%

---

# 高级表达式编辑{#advanced-expression-editing}

## 关于高级表达式编辑 {#about-advanced-expression-editing}

编辑表达式需要手动输入条件以形成规则。

利用此模式，可使用高级功能。利用这些函数，可处理用于执行特定查询（如处理日期、字符串、数字字段、排序等）的值。

在编辑表达式时，也可以使用工作流的事件变量。 有关更多信息，请参阅[使用事件变量自定义活动](../../automating/using/customizing-workflow-external-parameters.md)一节。

您可以编辑表达式，以：

* 通过添加规则时可用的 **[!UICONTROL Advanced mode]** 选项定义查询。

   ![](assets/expression_editor_2.png)

* 编辑工作流中的表达式。例如，向活动添加附加数据。
* 编辑可见性条件以定义编辑某个块在 HTML 内容编辑器中的显示方式。在这种情况下，表达式以 JavaScript 格式进行编辑，且不会提供高级函数作为标配。

## 编辑表达式 {#edit-an-expression}

利用高级表达式版，可手动定义专门对应于您需求的表达式。

编辑表达式可于创建电子邮件时在受众窗口中使用，也可于创建工作流时在查询活动中使用。

1. 有关访问表达式编辑窗口的方法详情，请参阅[关于高级表达式编辑](../../automating/using/advanced-expression-editing.md#about-advanced-expression-editing)一节。其中涉及以下元素：

   * 定义表达式的输入字段。
   * 可在表达式中使用并对应于查询中定向维度的可用字段清单（请参阅[定向维度和资源](../../automating/using/query.md#targeting-dimensions-and-resources)）。
   * 可用函数的列表，按类别排序。

   ![](assets/expression_editor_1.png)

1. 通过直接在相应字段中输入表达式以编辑表达式，或通过使用一系列可用字段和函数以编辑表达式。

   双击某个字段或表达式，可将其添加到光标所在的表达式中。

   可以使用工作流的事件变量来构建表达式。有关更多信息，请参阅[使用事件变量自定义活动](../../automating/using/customizing-workflow-external-parameters.md)一节。

1. 根据需要为规则指定一个特定名称。输入的名称将作为规则名称，显示在查询编辑器工作区中。

通过编辑表达式，您可以个性化受众表达式，以根据需要定向群体。

**相关主题：**

* [表达式语法](../../automating/using/advanced-expression-editing.md#expression-syntax)
* [函数列表](../../automating/using/list-of-functions.md)

## 表达式语法 {#expression-syntax}

### 标准语法 {#standard-syntax}

标准表达式由一个或多个符合以下语法元素的条件组成：

* 每个条件都采用 **&lt;value1> &lt;comparison operator> &lt;value2>** 的形式，其中：

   * **&lt;value1>** 是字段或函数例如 **@created** 对应于创建用户档案的日期，而 **Year(@created)** 对应于创建用户档案的年份。
   * **&lt;comparison operator>** 是 [Comparison operators](../../automating/using/advanced-expression-editing.md#comparison-operators) 部分中列出的运算符之一。此运算符用于定义 **&lt;value1>** 和 **&lt;value2>** 之间的比较方法。
   * **&lt;value2>** 是手动输入的字段、函数或值。

   >[!NOTE]
   >
   >**&lt;value1>** 和 **&lt;value2>** 类型数据必须相同。例如，如果 **&lt;value1>** 是日期，则 **&lt;value2>** 也必须是日期。

* 如果要使用多个条件，则可使用逻辑运算符将它们组合在一起。

   * **[!UICONTROL AND]**：两个条件相交。
   * **[!UICONTROL OR]**：两个条件相并。

例如：

```
Year(@created) = Year(GetDate()) AND Month(@created) = Month(GetDate())
```

在本例中，需要定向创建日期为当前月份和年份的用户档案。

### JavaScript 语法 {#javascript-syntax}

在定义 HTML 内容编辑器的文本类型块的可见性条件时，必须使用 JavaScript 类型语法的表达式。

JavaScript 表达式由一个或多个条件组成，其中使用了以下语法元素：

* 每个条件都采用 **&lt;context> &lt;comparison operator> &lt;value2>** 的形式，其中：

   * **&lt;context>** 是用于指定上下文的字段或函数。例如 **context.profile.@email** 对应于用户档案的电子邮件地址，而 **context.profile.firstName.length()** 对应于用户档案名字的字符数。
   * **&lt;comparison operator>** 是 [Comparison operators](../../automating/using/advanced-expression-editing.md#comparison-operators) 部分中列出的运算符之一。此运算符用于定义 **&lt;context>** 和 **&lt;value2>** 之间的比较方法。
   * **&lt;value2>** 是手动输入的字段、函数或值。

   >[!NOTE]
   **&lt;context>** 和 **&lt;value2>** 类型数据必须相同。例如，如果 **&lt;context>** 是日期，则 **&lt;value2>** 也必须是日期。

* 如果要使用多个条件，则可使用逻辑运算符将它们组合在一起。

   * **[!UICONTROL &&]**：两个条件相交。
   * **[!UICONTROL ||]**：两个条件相并。

例如：

```
context.profile.age > 21 && context.profile.firstName.length() > 0
```

在本例中，就是 21 岁以上并且提供了名字的用户档案（以 **firstName** 字段至少包 含一个字符为标志）。

## 比较运算符 {#comparison-operators}

对于某些规则，利用查询编辑器，可选择一个值以定义条件。

条件必须通过使用下列运算符之一，链接到值。

<table> 
 <thead> 
  <tr> 
   <th> 运算符<br /> </th> 
   <th> 标准语法<br /> </th> 
   <th> JavaScript 语法<br /> </th> 
   <th> 说明<br /> </th> 
   <th> 示例<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <span class="uicontrol">等于</span> <br /> </td> 
   <td> =<br /> </td> 
   <td> ==<br /> </td> 
   <td> 第一个值必须与第二个值完全相同。<br /> </td> 
   <td> <strong>@lastName = Martin</strong> 可检索姓氏为“Martin”的用户档案，且只检索与其相同的字符。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">大于</span> <br /> </td> 
   <td> &gt;<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> 第一个值必须绝对大于第二个值。<br /> </td> 
   <td> <strong>@age &gt; 50</strong> 可检索年龄超过“50”（比如“51”、“52”等）的用户档案。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">小于</span> <br /> </td> 
   <td> &lt;<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> 第一个值必须绝对小于第二个值。<br /> </td> 
   <td> <strong>@created &lt; DaysAgo(100)</strong> 可检索之前 100 天（不含第 100 天）内在数据库中创建的所有用户档案。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">大于或等于</span> <br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> 第一个值必须大于或等于第二个值。<br /> </td> 
   <td> <strong>@age &gt;= 30</strong> 可检索年龄为 30 岁或更大的用户档案。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">小于或等于</span> <br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> 第一个值必须小于或等于第二个值。<br /> </td> 
   <td> <strong>@age &lt;= 60</strong> 可检索年龄为 60 岁或更小的用户档案。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">不同 </span> <br /> </td> 
   <td> !=<br /> </td> 
   <td> !=<br /> </td> 
   <td> 第一个值必须不同于第二个值。<br /> </td> 
   <td> <strong>@language ! = English</strong> 可检索尚未定义为可使用英语的用户档案。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">包含</span> <br /> </td> 
   <td> IN<br /> </td> 
   <td> N/A<br /> </td> 
   <td> 第一个值必须包含第二个值。<br /> </td> 
   <td> <strong>@domain IN mail</strong>。此处，结果中会返回所有具有“mail”值的域名。因此，“gmail.com”域名也将构成返回结果的一部分。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">相似</span> <br /> </td> 
   <td> LIKE<br /> </td> 
   <td> N/A<br /> </td> 
   <td> <span class="uicontrol">相似</span>与<span class="uicontrol">包含</span>运算符非常相似。利用该运算符，可在搜索的值中插 入 <span class="uicontrol">%</span> 通配符。<br /> </td> 
   <td> <strong>@lastName LIKE Mart%n</strong>。在此，替换字符 <strong>%</strong> 将用作“绝招”，在假设拼写不正确的情况下查找名称“Martin”。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">不相似</span> <br /> </td> 
   <td> NOT<br /> </td> 
   <td> N/A<br /> </td> 
   <td> 与 <span class="uicontrol">相似</span>相同。不能用于取回输入的值。在本例中，输入的值也必须包含 <span class="uicontrol">%</span> 个通配符字段。<br /> </td> 
   <td> <strong>@lastName NOT Smi%h</strong>。此处，不会返回与名称“Smi%h”（代表 Smith 等）对应的收件人作为结果。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">为空</span> <br /> </td> 
   <td> IS NULL<br /> </td> 
   <td> N/A<br /> </td> 
   <td> 第一个值必须对应于空值。<br /> </td> 
   <td> <strong>@mobilePhone IS NULL</strong> 可检索尚未提供手机号码的所有用户档案。<br /> </td> 
  </tr> 
 </tbody> 
</table>
