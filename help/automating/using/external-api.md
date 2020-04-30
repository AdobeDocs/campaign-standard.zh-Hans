---
title: 外部 API
description: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: externalAPI,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c59faa935663bf803ed97f30e45f9b4276b448b8

---


# 外部 API {#external-api}

## 说明 {#description}

![](assets/wf_externalAPI.png)

该 **[!UICONTROL External API]** 活动通过HTTP API调用从外部系 **统将数据引入** 工作流中 **** 。

外部系统端点可以是公共API端点、客户管理系统或无服务器应用程序实例(例如 [Adobe I/O Runtime](https://www.adobe.io/apis/experienceplatform/runtime.html))，以及一些类别。

>[!NOTE]
>
>出于安全原因，Campaign Standard中不支持使用JSSP。 如果需要执行代码，可以通过外部API活动调用Adobe I/O Runtime实例。

本活动的主要特点是：

* 能够将JSON格式的数据传递到第三方REST API端点
* 能够接收回JSON响应，将其映射到输出表，并向下游传递到其他工作流活动。
* 具有出站特定过渡的故障管理

### 从测试版过渡到GA {#from-beta-to-ga}

在Campaign Standard20.3版本中，外部API功能已将Trom Beta版本移至“一般可用性(GA)”。

>[!CAUTION]
>
>因此，如果您使用测试版外部API活动，则需要在所有工作流中用GA外部API活动替换它们。  使用External API测试版的工作流将从20.3版本开始停止工作。

替换外部API活动时，将新的外部API活动添加到工作流中，手动复制配置详细信息，然后删除旧活动。

>[!NOTE]
>
>您将无法复制标题值，因为这些值在活动中被遮罩。

接下来，在工作流中重新配置其他活动，这些活动指向和／或使用测试版外部API活动中的数据，以指向和／或使用新外部API中的数据。 活动示例：电子邮件投放(个性化字段)、扩充活动等

### 限制和护栏 {#guardrails}

为本活动设置了以下护栏：

* 50MB HTTP响应数据大小限制
* 请求超时为10分钟
* 不允许HTTP重定向
* 拒绝非HTTPS Url
* “接受：application/json”请求标题和“Content-Type:application/json&quot;响应头被允许

>[!CAUTION]
>
>请注意，该活动用于获取活动范围的数据(最新的优惠集、最新的得分等)，而不用于检索每个用户档案的特定信息，因为这会导致大量数据被传输。 如果用例要求使用此功能，建议使用“传输文 [件”活动](../../automating/using/transfer-file.md) 。


JSON的特定护栏已经到位：

* **JSON最大深度**:将可处理的自定义嵌套JSON的最大深度限制为10级。
* **JSON最大密钥长度**:将生成的内部密钥的最大长度限制为255。 此键与列ID关联。
* **允许的JSON最大重复密钥**: 将用作列ID的重复JSON属性名称的最大总数限制为150。


活动不支持JSON结构，因为：

* 将数组对象与其他非数组元素组合
* JSON数组对象嵌套在一个或多个中间数组对象中。


## 配置 {#configuration}

将活动拖放到 **[!UICONTROL External API]** 工作流中，然后打开活动以开始配置。

### 入站映射

入站映射是由以前的入站活动生成的临时表，该表将在UI中显示为JSON并发送。
根据此临时表，用户可以修改入站数据。

![](assets/externalAPI-inbound.png)

在“ **入站资源** ”下拉菜单中，您可以选择将创建临时表的查询活动。

“添 **加计数参数** ”复选框将为来自临时表的每行添加计数值。 请注意，此复选框仅在入站活动生成临时表时可用。

“入 **站列** ”部分允许用户添加入站过渡表中的任何字段。 所选列将是数据对象中的键。 JSON中的数据对象将是一个数组列表，其中包含入站过渡表中每行中选定列的数据。

通过 **自定义参数** 文本框，您可以添加有效的JSON，其中包含外部API需要的其他数据。 此附加数据将添加到生成的JSON中的params对象。

### 出站映射

此选项卡允许您定义API调 **用返回的** JSON示例结构。

![](assets/externalAPI-outbound.png)

JSON分析器设计为适应标准JSON结构模式类型，但有些例外。 标准模式的示例是：`{“data”:[{“key”:“value”}, {“key”:“value”},...]}`

示例JSON定义必须具有以 **下特征**:

* **数组元素** 必须包含第一级属性（不支持更深的级别）。
   **属性名称** ，将最终成为输出临时表的输出模式的列名称。
* **要捕获的JSON** 元素必须在JSON响应中处于10级或更低的嵌套级别。
* **列名称** ，定义基于“data”数组的第一个元素。
列定义（添加／删除）和属性的类型值可以在列定义选项卡中 **进行编辑** 。

**拼合复选框** 行为：

拼合复选框(默认：未选中)，以指示是否将JSON拼合到键／值映射。

* 禁用( **取消选中** )此复选框后，将分析示例JSON以查找数组对象。 用户需要提供API响应范例JSON格式的修剪版本，以便Adobe Campaign能够准确确定用户希望使用的数组。 在工作流创作时，将确定并记录嵌套数组对象的路径，以便在执行时使用它从从从API调用接收的JSON响应体访问该数组对象。

* 启用 **此复选框** （选中）后，示例JSON将被拼合，在提供的示例JSON中指定的所有属性将用于创建输出临时表的列，并显示在“列定义”选项卡上。 请注意，如果示例JSON中有任何数组对象，则这些数组对象的所有元素也将被拼合。


如果验 **证了分析**，则会显示一条消息，邀请您在“列定义”选项卡中自定义数据映射。 在其他情况下，会显示错误消息。

### 执行

通过此选项卡，可定义 **将向ACS发送数据的HTTPS端点** 。 如果需要，您可以在以下字段中输入身份验证信息。
![](assets/externalAPI-execution.png)

### 属性

通过此选项卡，您可 **以控制外部API活动** （如UI中显示的标签）上的常规属性。 内部ID不可自定义。

![](assets/externalAPI-properties.png)

### 列定义

>[!NOTE]
>
>当响应数据格式在“出站映 **射”选项卡中完成** 并验证后，将显示此选项卡。

“列定 **义** ”选项卡允许您精确指定每列的数据结构，以便导入不包含任何错误的数据，并使其与Adobe Campaign数据库中已存在的类型匹配以供将来操作。

![](assets/externalAPI-column.png)

例如，您可以更改列的标签，选择其类型（字符串、整数、日期等） 甚至指定错误处理。

有关详细信息，请参阅“加 [载文件](../../automating/using/load-file.md) ”部分。

### 过渡

通过此选项卡可激活 **出站过渡** 及其标签。 此特定过渡在超时或有效负 **荷超过** 数据大小限制时 **很有用**。

![](assets/externalAPI-transition.png)

### 执行选项

此选项卡在大多数工作流活动中都可用。 有关详细信息，请参阅 [活动属性部分](../../automating/using/executing-a-workflow.md#activity-properties) 。

![](assets/externalAPI-options.png)

## 故障排除

有两种类型的日志消息已添加到此新的工作流活动:信息和错误。 它们可以帮助您排除潜在问题。

### 信息

这些日志消息用于在执行工作流活动期间记录有关有用检查点的信息。 具体而言，以下日志消息用于记录首次尝试以及访问API的重试尝试（以及首次尝试失败的原因）。

<table> 
 <thead> 
  <tr> 
   <th> 消息格式<br /> </th> 
   <th> Example<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 调用API URL'%s'。</td> 
   <td> <p>调用API URL 'https://example.com/api/v1/web-coupon?count=2'。</p></td> 
  </tr> 
  <tr> 
   <td> 重试API URL“%s”，之前的尝试失败(“%s”)。</td> 
   <td> <p>重试API URL 'https://example.com/api/v1/web-coupon?count=2'，之前的尝试失败('HTTP - 401')。</p></td>
  </tr> 
  <tr> 
   <td> 从'%s'传输内容(%s / %s)。</td> 
   <td> <p>从“https://example.com/api/v1/web-coupon?count=2'”传输内容(1234 / 1234)。</p></td> 
  </tr>
 </tbody> 
</table>

### 错误

这些日志消息用于记录有关意外错误情况的信息，这些错误情况最终可能导致工作流活动失败。

<table> 
 <thead> 
  <tr> 
   <th> 代码——消息格式<br /> </th> 
   <th> Example<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> WKF-560250 —— 超出API请求正文限制(限制：'%d')。</td> 
   <td> <p>API请求正文超出限制(限制：5242880)。</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560239 —— 超出API响应限制(限制：'%d')。</td> 
   <td> <p>超出API响应限制(限制：5242880')。</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560245 —— 无法解析API URL(错误：'%d')。</td> 
   <td> <p>无法解析API URL(错误：'-2010')。</p>
   <p> 注意：当API URL失败验证规则时，将记录此错误。</p></td>
  </tr> 
  <tr>
   <td> WKF-560244 - API URL主机不能是“localhost”或IP地址文字(URL主机：'%s')。</td> 
   <td> <p>API URL主机不得为“localhost”或IP地址文本(URL主机：'localhost')。</p>
    <p>API URL主机不得为“localhost”或IP地址文本(URL主机：192.168.0.5”)。</p>
    <p>API URL主机不得为“localhost”或IP地址文本(URL主机：“[2001]”)。</p></td>
  </tr> 
  <tr> 
   <td> WKF-560238 - API URL必须是安全URL(https)(请求的URL:'%s')。</td> 
   <td> <p>API URL必须是安全URL(https)(请求的URL:'https://example.com/api/v1/web-coupon?count=2')。</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560249 —— 无法创建请求正文JSON。 添加“%s”时出错。</td> 
   <td> <p>无法创建请求正文JSON。 添加“params”时出错。</p>
    <p>无法创建请求正文JSON。 添加“data”时出错。</p></td>
  </tr> 
  <tr> 
   <td> WKF-560246 - HTTP头键错误(头键：'%s')。</td> 
   <td> <p>HTTP头键错误(头键：'%s')。</p>
   <p> 注意：当自定义头密钥根据 <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFC失败验证时，将记录此错误</a></p></td> 
  </tr>
 <tr> 
   <td> WKF-560248 —— 不允许HTTP头键(头键：'%s')。</td> 
   <td> <p>不允许HTTP头键(头键：“接受”)。</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560247 - AHTTP头值错误(头值：'%s')。</td> 
   <td> <p>HTTP头值错误(头值：'%s')。 </p>
    <p>注意：当自定义标头值根据 <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFC失败验证时，将记录此错误</a></p></td> 
  </tr> 
  <tr> 
   <td> WKF-560240 - JSON有效负荷有坏属性“%s”。</td> 
   <td> <p>JSON有效负荷有坏属性“blah”。</p></td>
  </tr> 
  <tr>
   <td> WKF-560241 —— 格式不正确的JSON或不可接受的格式。</td> 
   <td> <p>JSON格式不正确或格式不可接受。</p>
   <p>注意：此消息仅适用于从外部API解析响应主体，并在尝试验证响应主体是否符合本活动规定的JSON格式时记录。</p></td>
  </tr>
  <tr> 
   <td> WKF-560246 -活动失败(原因：'%s')。</td> 
   <td> <p>当由于HTTP 401错误响应而活动失败时-活动失败(原因：'HTTP - 401')</p>
        <p>当由于内部调用失败而导致活动失败时-活动失败(原因：“iRc - -Nn”)。</p>
        <p>当由于Content-Type标题无效而活动失败时。 -活动失败(原因：“Content-Type - application/html”)。</p></td> 
  </tr>
 </tbody> 
</table>

<!--
## Example: Managing coupons with External API Activity

This example illustrates how to **add coupon value** retrieving by a REST call to profiles and then sending an email containing these coupon values.

The workflow is presented as follows:

![](assets/externalAPI_activity_example1.png)

1. Drag and drop an **External API** activity
    1. Parse the JSON sample responsa as {"data":[{"code":"value"}]}.
    1. Add the **Rest endpoint URL** and define authentication setting if needed
    ![](assets/externalAPI_activity_example2.png)
    1. In the **column definition** tab, add a new column called **code** that will store the code value.
        ![](assets/externalAPI_activity_example3.png)
    1. Enabled an **outbound transition** to manage request failures.
1. Drag and drop a **Query** activity
    1. Configure the **Target** tab to query all the **@adobe.com** email. For different Query samples, refer to the [Query](../../automating/using/query.md) section.
    1. In the **additional data** tab, add a new column based on **rowId()** function. This additional column allows you to reconciliate coupon code with the profile ID..
        ![](assets/externalAPI_activity_example4.png)

        >[!NOTE]
        >
        >This reconciliation approach means that the profile query number is equal to the number of coupon values returned by the REST call.
1. Once this two activities are configured, drag and drop an **Enrichment** activity to associate coupon values with profiles.
    1. Select the previous Query activity in the **primarySet** field.
        ![](assets/externalAPI_activity_example5.png)
    1. Create a new relation in the **Advanced relations** tab, and add the following reconciliation criteria:
    1. **@expr1** coming grom the Query activity in the source expression field.
    1. **@lineNum** as an expression that returns the line number for each coupon value in the destination field.
        ![](assets/externalAPI_activity_example6.png)
        More information on the enrichment activity are available [here](../../automating/using/enrichment.md)

    1. The transition **Data Structure** will contain:
        ![](assets/externalAPI_activity_example7.png)
1. Finally drag and drop a **Send via Email** activity.
    You can modify your email template by adding the **code** personnalized field.

-->
