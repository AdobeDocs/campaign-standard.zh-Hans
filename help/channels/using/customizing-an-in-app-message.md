---
title: 自定义应用程序内消息
description: 了解如何使用各种选项自定义应用程序内消息。
page-status-flag: never-activated
uuid: 1d9c08ed-4de5-440d-bf51-4a437eec67d5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: in-app-messaging
discoiquuid: c9c3e033-e319-447b-8d87-ff7dd4941876
context-tags: delivery,inAppContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1269ee2041e0857b077424ba7f50fbfa9519ae7b

---


# 自定义应用程序内消息{#customizing-an-in-app-message}

要微调应用程序内消息，Adobe Campaign允许您在设计应用程序内消息时访问一组高级选项。

通过应用程序内内容编辑器，您可以在两种应用程序内消息模式之间进行选择：

* [消息模板](#customizing-with-a-message-template):此模板允许您使用图像或视频以及操作按钮完全自定义应用程序内。
* [自定义消息](#customizing-with-a-custom-html-message):通过此模板可导入自定义HTML。

![](assets/inapp_customize_1.png)

>[!NOTE]
>
> 仅Android API 19及更高版本支持应用程序内消息渲染。

**相关主题：**

* [发送应用程序内消息](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)
* [应用程序内报告](../../reporting/using/in-app-report.md)
* [实施本地通知跟踪](https://helpx.adobe.com/campaign/kb/local-notification-tracking.html)

## 使用消息模板进行自定义 {#customizing-with-a-message-template}

### 布局 {#layout}

下拉 **[!UICONTROL Layout]** 框为您提供了四个不同的选项，可根据您的消息需求进行选择：

* **[!UICONTROL Full page]**:此类布局覆盖受众设备的整个屏幕。

   它支持媒体（图像、视频）、文本和按钮组件。

* **[!UICONTROL Large modal]**:此布局显示在大型警报样式窗口中，您的应用程序仍在后台可见。

   它支持媒体（图像、视频）、文本和按钮组件。

* **[!UICONTROL Small modal]**:此布局显示为一个小的警报类型窗口，您的应用程序仍在后台可见。

   它支持媒体（图像、视频）、文本和按钮组件。

* **[!UICONTROL Alert]**:此类布局将作为本机操作系统警报消息显示。

   它只能支持文本和按钮组件。

* **[!UICONTROL Local notification]**:此类布局显示为横幅消息。

   它只能支持声音、文本和目标。 有关本地通知的详细信息，请参 [阅自定义本地通知消息类型](#customizing-a-local-notification-message-type)。

每种类型的布局都可以在不同的设备(如手机、平板电脑、平台（如Android或iOS）上预览，并可在内容编辑器的右窗口中显示方向（如横向或纵向）。

![](assets/inapp_customize_4.png)

### Media {#media}

通过 **[!UICONTROL Media]** 此下拉框，您可以向应用程序内消息中添加媒体，为最终用户创建引人入胜的体验。

1. 在图像和 **[!UICONTROL Media Type]** 视频之间选择您的内容。
1. 对于媒 **[!UICONTROL Image]** 体类型，请根据支持的格 **[!UICONTROL Media URL]** 式在字段中输入URL。

   如果需要，您还可以输入到设备脱 **[!UICONTROL Bundled image]** 机时可用的路径。

   ![](assets/inapp_customize_5.png)

1. 对于介 **[!UICONTROL Video]** 质类型，请在字段中输入您的 **[!UICONTROL Media URL]** URL。

   然后，输入在 **[!UICONTROL Video poster]** 观众设备上下载视频时要使用的内容，或直到用户点击播放按钮。

   ![](assets/inapp_customize_6.png)

### 文本 {#text}

如果需要，您还可以向应用程序内消息中添加消息标题和内容。 为了更好地个性化您的应用程序内消息，您可以向内容中添加不同的个性化字段、内容块和动态文本。

1. 在下 **[!UICONTROL Text]** 拉框中，在字段中添加标 **[!UICONTROL Message title]** 题。

   ![](assets/inapp_customize_9.png)

1. 在字段中添加您的 **[!UICONTROL Message content]** 内容。
1. 要进一步个性化您的文本，请单击 ![](assets/edit_darkgrey-24px.png) 该图标以添加个性化字段。

   ![](assets/inapp_customize_8.png)

1. 键入消息内容并根据需要添加个性化字段。

   For more information on personalization field, refer to this [section](../../designing/using/personalization.md#inserting-a-personalization-field).

   ![](assets/inapp_customize_10.png)

1. 在预览窗口中检查您的消息内容。

   ![](assets/inapp_customize_11.png)

### 按钮 {#buttons}

您最多可以向应用程序内消息添加两个按钮。

1. 在下 **[!UICONTROL Buttons]** 拉框中，输入类别中第一个按钮的文 **[!UICONTROL Primary]** 本。

   ![](assets/inapp_customize_12.png)

1. 选择两个操作中的哪 **[!UICONTROL Dismiss]** 个， **[!UICONTROL Redirect]** 并将分配给您的主按钮。
1. 在类别 **[!UICONTROL Secondary]** 中，根据需要，通过输入文本向应用程序内添加第二个按钮。
1. 选择与第二个按钮关联的操作。
1. 如果选择了该 **[!UICONTROL Redirect]** 操作，请在字段中输入Web URL或深层 **[!UICONTROL Destination URL]** 链接。

   ![](assets/inapp_customize_13.png)

1. 在字段中输入您的Web URL或 **[!UICONTROL Destination URL]** 深层链接(如果您选择了操 **[!UICONTROL Redirect]** 作)
1. 在预览窗口中或通过单击“预览”按钮检查您的消息内容。

   请参阅预 [览应用程序内消息页](#previewing-the-in-app-message) 。

   ![](assets/inapp_customize_11.png)

### 设置 {#settings}

1. 在类别 **[!UICONTROL Settings]** 中，选择浅色和深色之间的背景色。
1. 选择显示或不显示带有选项的关闭按 **[!UICONTROL Show close button]** 钮，以为用户提供一种关闭应用程序内消息的方式。
1. 选择按钮对齐方式是水平还是垂直于选 **[!UICONTROL Button alignment]** 项。
1. 选择您的应用程序内消息在几秒钟后是否可以自动消失。

   ![](assets/inapp_customize_7.png)

## 自定义本地通知消息类型 {#customizing-a-local-notification-message-type}

本地通知只能由应用程序在特定时间触发，具体取决于事件。 他们会提醒用户，即使没有访问Internet，应用程序中也会发生一些事情。
要了解如何跟踪本地通知，请参阅此 [页](https://helpx.adobe.com/campaign/kb/local-notification-tracking.html)。

要自定义本地通知，请执行以下操作：

1. 在您的页 **[!UICONTROL Content]** 面中，选 **[!UICONTROL Local notification]** 择类别中 **[!UICONTROL Layout]** 的

   ![](assets/inapp_customize_17.png)

1. 在类 **[!UICONTROL Text]** 别下，键入 **[!UICONTROL Message title]** 和 **[!UICONTROL Message content]**。

   ![](assets/inapp_customize_18.png)

1. 在类别 **[!UICONTROL Advanced option]** 下的字段中，选 **[!UICONTROL Wait to display]** 择触发事件后，您的本地通知将在屏幕上显示多长时间（以秒为单位）。
1. 在字 **[!UICONTROL Sound]** 段中，输入接收本地通知时由移动设备播放的声音文件的文件名（扩展名为）。

   如果文件是在手机应用程序包中定义的，则在发送通知时播放声音文件。 否则，将播放设备的默认音效。

   ![](assets/inapp_customize_19.png)

1. 指定一个目标，以在用户与字段中的本地通知交互时重定向 **[!UICONTROL Deeplink URL]** 用户。
1. 要以键值对的形式在有效负荷中传递自定义数据，您可以向本地通知添加自定义字段。 在类 **[!UICONTROL Custom fields]** 别中，单击按 **[!UICONTROL Create an element]** 钮。
1. 然后输 **[!UICONTROL Keys]** 入与每 **[!UICONTROL Values]** 个键关联的键。

   请注意，自定义字段的处理和用途完全取决于移动应用程序。

1. 在类别 **[!UICONTROL Apple options]** 中，填写字段以添 **[!UICONTROL Category]** 加一个类别ID，以执行自定义操作（如果Apple移动应用程序提供）。

## 使用自定义HTML消息进行自定义 {#customizing-with-a-custom-html-message}

>[!NOTE]
>
>自定义HTML消息不支持内容个性化。

该模 **[!UICONTROL Custom message]** 式允许您直接导入一个预配置的HTML消息。

为此，您只需从计算机中拖放或选择文件即可。

您的文件必须具有特定的布局，单击“下载示例文件” **选项即可找到该布局** 。

![](assets/inapp_customize_16.png)

您还可以找到在Adobe Campaign中成功导入的自定义HTML要求列表。

![](assets/inapp_customize_3.png)

导入HTML后，您可以在预览窗口中找到不同设备上的文件预览。

## 预览应用程序内消息 {#previewing-the-in-app-message}

在发送应用程序内消息之前，您可以测试测试配置文件以检查目标受众在收到您的分发时将看到什么。

1. Click the **[!UICONTROL Preview]** button.

   ![](assets/inapp_sending_2.png)

1. 单击该 **[!UICONTROL Select a test profile]** 按钮并选择其中一个测试配置文件以开始预览分发。 For more information on test profiles, refer to this [section](../../audiences/using/managing-test-profiles.md).
1. 在Android、iPhone手机甚至平板电脑等不同设备上查看您的消息。 您还可以检查您的个性化字段是否正在检索正确的数据。

   ![](assets/inapp_sending_3.png)

1. 您现在可以发送消息，并通过传送报告衡量其影响。 For more on reporting, refer to [this section](../../reporting/using/in-app-report.md).

