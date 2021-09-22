---
title: Campaign Standard Mobile 指南
description: 进一步了解Adobe Campaign Standard中移动投放的一般准则，例如如何配置移动应用程序或创建推送通知和应用程序内消息。
audience: channels
content-type: reference
topic-tags: mobile-guide
feature: Overview
role: User
level: Beginner
source-git-commit: e583ba4e93b16389be9d06c4b7fa8eebf4ee3cfc
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 23%

---

# 移动渠道快速入门 {#mobile-guide}

<table style="table-layout:fixed">
<tr>
<td><img src="assets/do-not-localize/config_push.png" width="60px"><p>了解如何配置移动应用程序以发送推送通知</br><a href="#configuration-push">单击此处</a></p></td>
<td><img src="assets/do-not-localize/config_inapp.png" width="60px"><p>了解如何为应用程序内消息配置移动应用程序</br><a href="#configuring-mobile-app">单击此处</a></p></td>
</tr>
<tr>
<td><img src="assets/do-not-localize/push2.png" width="60px"><p>了解有关如何创建推送通知的更多信息</br><a href="#create-push">单击此处</a></p></td>
<td><img src="assets/do-not-localize/inapp.png" width="60px"><p>了解如何创建应用程序内消息</br><a href="#create-inapp">单击此处</a></p></td></tr>
</table>

## 关于移动交付 {#about-mobile}

Adobe Campaign允许您在各种渠道上创建和发送个性化消息，并通过专用报告衡量其有效性。

借助Adobe Campaign Standard，您可以通过三个不同渠道发送移动投放：

* 短信，请参见关于短信消息一节。
* 推送通知，请参见关于推送通知一节。
* 应用程序内消息，在关于应用程序内消息部分中显示。

## 为推送通知配置移动应用程序 {#configuration-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>使用Adobe Experience Platform SDK配置移动应用程序</strong></p>
    </div>
    <p>要发送应用程序内消息和推送通知，需要利用Adobe Experience Platform SDK在Adobe Campaign中设置您的移动应用程序。</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>单击此处</strong></a>以了解更多信息。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>了解Campaign Standard推送通知有效载荷结构</strong></p>
    </div>
    <p>详细了解成功从Adobe Campaign Standard将推送通知发送到应用程序时，移动应用程序中接收的有效载荷的结构。</br><a href="../../administration/using/push-payload.md"><strong>单击此处</strong></a>以了解更多信息。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>实施本地通知跟踪</strong></p>
    </div>
    <p>单击此处了解如何确保正确实施本地通知跟踪。 </br><a href="../../administration/using/local-tracking.md"><strong>单击此处</strong></a>以了解更多信息。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>实施推送跟踪</strong></p>
    </div>
    <p>了解如何确保在iOS和Android上正确实施推送通知跟踪。</br><a href="../../administration/using/push-tracking.md"><strong>单击此处</strong></a>以了解更多信息。</p>
    <br>
  </td>
</tr>
</table>

## 为应用程序内消息配置移动应用程序 {#configuring-mobile-app}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>使用Adobe Experience Platform SDK配置移动应用程序</strong></p>
    </div>
    <p>要发送应用程序内消息和推送通知，需要利用Adobe Experience Platform SDK在Adobe Campaign中设置您的移动应用程序。</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>单击此处</strong></a>以了解更多信息。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>使用Adobe Experience Platform SDK支持的移动使用案例</strong></p>
    </div>
    <p>进一步了解Adobe Campaign Standard中使用Adobe Experience Platform SDK支持的移动使用案例。</br><a href="../../administration/using/supported-mobile-use-cases.md"><strong>单击此处</strong></a>以了解更多信息。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>配置Adobe Experience Platform Launch规则以支持Adobe Campaign Standard用例</strong></p>
    </div>
    <p><a href="../../administration/using/configuring-rules-launch.md"><strong>单击</strong></a> 此处以在Adobe Experience Platform Launch中开始创建数据元素和规则，以将PII和其他数据从移动应用程序发送到Adobe Campaign Standard。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>实施本地通知跟踪</strong></p>
    </div>
    <p>单击此处了解如何确保正确实施本地通知跟踪。 </br><a href="../../administration/using/local-tracking.md"><strong>单击此处</strong></a>以了解更多信息。</p>
    <br>
  </td>
</tr>
</table>

## 创建推送通知 {#create-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>准备和发送推送通知</strong></p>
    </div>
    <p><a href="../../channels/using/preparing-and-sending-a-push-notification.md"><strong>此处</strong></a> 了解如何准备推送通知，以及如何将其发送给目标受众。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>自定义推送通知</strong></p>
    </div>
    <p>要优化投放，可在设计推送通知时使用Adobe Campaign访问一组选项。</br><a href="../../channels/using/customizing-a-push-notification.md"><strong>单击此处</strong></a>以了解更多信息。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>创建多语言推送通知</strong></p>
    </div>
    <p>根据用户首选的语言和区域发送消息，以个性化推送通知内容。</br><a href="../../channels/using/creating-a-multilingual-push-notification.md"><strong>单击此处</strong></a>以了解更多信息。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>显示 Adobe Campaign Standard 推送通知中的图像</strong></p>
    </div>
    <p><a href="../../administration/using/image-push-notification.md"><strong>以</strong></a> 下了解如何在iOS设备上显示Adobe Campaign推送通知中的图像。</p>
    <br>
  </td>
</tr>
</table>

## 创建应用程序内消息 {#create-inapp}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>准备和发送应用程序内消息</strong></p>
    </div>
    <p><a href="../../channels/using/preparing-and-sending-an-in-app-message.md"><strong>以</strong></a> 下内容了解如何准备应用程序内消息，以及如何将其发送给目标受众。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>自定义应用程序内消息</strong></p>
    </div>
    <p>要优化投放，可在设计应用程序内消息时通过Adobe Campaign访问一组高级选项。</br><a href="../../channels/using/customizing-an-in-app-message.md"><strong>单击此处</strong></a>以了解更多信息。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>自定义本地通知消息类型</strong></p>
    </div>
    <p>本地通知只能由应用程序在特定时间根据事件触发。</br><a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type"><strong>单击此处</strong></a>以了解更多信息。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>应用程序内报告</strong></p>
    </div>
    <p>应用程序内报表提供与应用程序内投放相关的详细信息。</br><a href="../../reporting/using/in-app-report.md"><strong>单击此处</strong></a>以了解更多信息。</p>
    <br>
  </td>
</tr>
</table>

## 创建短信消息 {#create-sms}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>创建短信消息</strong></p>
    </div>
    <p>创建短信投放与创建常规电子邮件非常相似。</br>以下详 <a href="../../channels/using/creating-an-sms-message.md"><strong>细</strong></a> 步骤介绍了特定于此渠道的配置。</br></p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>自定义短信消息
</strong></p>
    </div>
    <p>要优化投放，可在设计短信消息时使用Adobe Campaign访问一组高级选项。</br><a href="../../channels/using/sms-and-push-content-editor-interface.md"><strong>单击此处以了解更多信息。</br><a href="../../channels/using/sms-and-push-content-editor-interface.md"><strong></p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>管理传入的短信</strong></p>
    </div>
    <p>当用户档案回复通过Campaign发送的短信消息时，您可以配置自动发回给他的消息以及要执行的操作。自定义本地通知消息类型</br><a href="../../channels/using/managing-incoming-sms.md"><strong>单击此处了解更多信息。</br><a href="../../channels/using/managing-incoming-sms.md"><strong></p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>短信报告</strong></p>
    </div>
    <p>短信报表提供了有关短信投放的详细信息，如投放率和跳出率。</br><a href="../../reporting/using/sms-report.md"><strong>单击此处</strong></a>以了解更多信息。</p>
    <br>
  </td>
</tr>
</table>

## 移动故障诊断 {#mobile-troubleshooting}

以下页面将帮助您解决在Adobe Campaign Classic中使用移动交付时最常见的问题。

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>推送通知常见问题解答</strong></p>
    </div>
    <p><a href="../../channels/using/about-push-notifications.md#push-faq"><strong>单击此处以了解更多信息。</p>
  </td>
  <td>
    <div>
    <p><strong>Adobe Launch Synchronization 常见问题解答</strong></p>
    </div>
    <p><a href="../../channels/using/in-app-faq.md"><strong>单击此处以了解更多信息。</p>
  </td>
  <td>
    <div>
    <p><strong>应用程序内常见问题解答</strong></p>
    </div>
    <p><a href="../../administration/using/syncwithlaunch-faq.md"><strong>单击此处以了解更多信息。</p>
  </td>
</tr>
</table>


