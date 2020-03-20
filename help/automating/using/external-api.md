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
source-git-commit: 8f3c8f9a167f11ba5ded2be34a50b52edeeb6412

---


# 外部 API {#external-api}

## 说明 {#description}

![](assets/wf_externalAPI.png)

该活 **[!UICONTROL External API]** 动通过 **REST API调用从外部系统将** 数据引入 **工作流中** 。

REST端点可以是客户管理系统、 [](https://www.adobe.io/apis/experienceplatform/runtime.html) Adobe I/O Runtime实例或Experience Cloud REST端点（数据平台、Target、Analytics、Campaign等）。

>[!NOTE]
>
>出于安全原因，Campaign Standard不支持使用JSSP。 如果需要执行代码，可以通过外部API活动调用Adobe I/O Runtime实例。

>[!IMPORTANT]
>
>此功能目前处于测试阶段。 在开始使用外部API活动之前，您需要接受使用协议。 请注意，由于Adobe尚未以商业方式发布此测试版功能，因此Adobe Client Care不支持它，它可能包含错误，可能无法与其他已发布功能一样正常工作。

本活动的主要特点是：

* 能够将JSON格式的数据传递到第三方REST API端点
* 能够接收回JSON响应，将其映射到输出表，并传递到下游的其他工作流活动。
* 具有出站特定转移的故障管理

为此活动设置了以下护栏：

* 50MB HTTP响应数据大小限制
* 请求超时为10分钟
* 不允许HTTP重定向
* 拒绝非HTTPS Url
* “接受：application/json”请求标题和“Content-Type:application/json&quot;响应头被允许

>[!CAUTION]
>
>请注意，此活动用于获取营销活动范围的数据（最新的优惠信息集、最新得分等）不是检索每个配置文件的特定信息，因为这可能会导致传输大量数据。 如果用例要求这样做，建议使用“传输文 [件”活动](../../automating/using/transfer-file.md) 。

## 配置 {#configuration}

将活动拖放到 **[!UICONTROL External API]** 您的工作流中，然后打开活动以启动配置。

### 入站映射

入站映射是由以前的入站活动生成的临时表，该活动将在UI中显示为JSON并发送。
根据此临时表，用户可以修改入站数据。

![](assets/externalAPI-inbound.png)

通过 **入站资源下拉框** ，您可以选择将创建临时表的查询活动。

“添 **加计数参数** ”复选框将为来自临时表的每行提供一个计数值。 请注意，此复选框仅在入站活动生成临时表时可用。

“入 **站列** ”部分允许用户添加入站过渡表中的任何字段。 所选列将是数据对象中的键。 JSON中的数据对象将是一个数组列表，其中包含入站过渡表中每行中选定列的数据。

通过 **自定义参数** 文本框，您可以添加有效的JSON，其中包含外部API需要的其他数据。 此附加数据将添加到生成的JSON中的params对象。

### 出站映射

此选项卡允许您定义API调 **用返回的** JSON示例结构。

![](assets/externalAPI-outbound.png)

JSON结构模式为： `{“data”:[{“key”:“value”}, {“key”:“value”},...]}`

示例JSON定义必须具有以 **下特征**:

* **data** 是JSON中的必需属性名称，“data”的内容是JSON数组。
* **数组元素** 必须包含第一级属性（不支持更深的级别）。
   **属性名称** ，最终将成为输出临时表的输出架构的列名称。
* **列名称** ，定义基于“data”数组的第一个元素。
列定义（添加／删除）和属性的类型值可以在列定义选项卡中 **进行编辑** 。

如果验 **证了分析** ，则会显示一条消息，邀请您在“列定义”选项卡中自定义数据映射。 在其他情况下，会显示错误消息。

### 执行

通过此选项卡，可定义 **将向ACS发送数据的HTTPS端点** 。 如果需要，您可以在以下字段中输入身份验证信息。
![](assets/externalAPI-execution.png)

### 属性

通过此选项卡，您可 **以控制外部** API活动的常规属性，如UI中显示的标签。 内部ID不可自定义。

![](assets/externalAPI-properties.png)

### 列定义

>[!NOTE]
>
>当响应数据格式在“出站映 **射”选项卡中完成** 并验证后，将显示此选项卡。

列定 **义** (Column definition)选项卡允许您精确指定每列的数据结构，以便导入不包含任何错误的数据，并使其与Adobe Campaign数据库中已存在的类型相匹配，以便将来执行操作。

![](assets/externalAPI-column.png)

例如，您可以更改列的标签，选择其类型（字符串、整数、日期等） 甚至指定错误处理。

有关详细信息，请参阅“加 [载文件](../../automating/using/load-file.md) ”部分。

### 过渡

通过此选项卡可激活出站 **过渡** 及其标签。 此特定过渡在超时或有效负 **荷超过** 数据大小限制时 **很有用**。

![](assets/externalAPI-transition.png)

### 执行选项

此选项卡在大多数工作流活动中都可用。 有关详细信息，请参阅“活 [动属性](../../automating/using/executing-a-workflow.md#activity-properties) ”部分。

![](assets/externalAPI-options.png)

## 故障排除

有两种类型的日志消息已添加到此新的工作流活动：信息和错误。 它们可以帮助您排除潜在问题。

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
   <td> WKF-560246 —— 活动失败(原因：'%s')。</td> 
   <td> <p>当由于HTTP 401错误响应导致活动失败时——活动失败(原因：'HTTP - 401')</p>
        <p>当由于内部调用失败而导致活动失败时——活动失败(原因：“iRc - -Nn”)。</p>
        <p>当活动因内容类型标题无效而失败时。 -活动失败(原因：“Content-Type - application/html”)。</p></td> 
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
