---
title: 个性化电子邮件主题行
seo-title: 个性化电子邮件主题行
description: 个性化电子邮件主题行
seo-description: 您可以个性化电子邮件的主题，还可以尝试不同主题行并评估其打开率。
page-status-flag: 从未激活
uuid: 345b5f4b-8e2c-4f8e-bce7-3e9 b40 a44932
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 设计
content-type: reference
topic-tags: 个性化内容
discoiquuid: f7a5e935-54cf-422e-8459-27221409a200
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# 个性化电子邮件主题行{#personalizing-the-subject-line-of-an-email}

## 个性化电子邮件主题 {#personalizing-an-email-subject}

必须使用邮件主题来准备和发送消息。

>[!NOTE]
>
>如果主题行为空，则会在邮件功能板中和电子邮件设计器中显示警告。

要配置电子邮件主题，请转到电子邮件设计器主页 **[!UICONTROL Properties]** 的选项卡(可通过主页图标访问)并填写章节 **[!UICONTROL Subject]** 。

![](assets/email_designer_subject.png)

您还可以单击相应的图标，将个性化字段、内容块和动态内容添加到主题行。

**相关主题：**

* [插入个性化字段](../../designing/using/inserting-a-personalization-field.md)
* [添加内容块](../../designing/using/adding-a-content-block.md)
* [在电子邮件中定义动态内容](../../designing/using/defining-dynamic-content-in-an-email.md)

## 预测主题行 {#predictive-subject-line}

在编辑电子邮件时，您可以尝试不同主题行，并在发送之前获得对其打开率的评估。

默认情况下禁用此功能。导入第一个模型时，将启用该功能。模型是特定行业特定的培训数据集的结果。模型允许系统在提交新主题行时预测电子邮件的打开率。

>[!NOTE]
>
>此功能适用于电子邮件以及仅包含英语内容的数据库。培训模型将不一致，如果您的实例包含其他语言的电子邮件，则会导致错误的结果。仅当实例中已经有一个模型时，允许您测试主题的选项才可见。

### 测试主题 {#testing-a-subject}

要测试主题行，请执行以下操作：

1. 创建或打开电子邮件。
1. 打开内容并在相应的输入字段中输入电子邮件主题。
1. 单击 **[!UICONTROL Test subject]** 按钮可访问 **[!UICONTROL Test your subject line]** 窗口。您仍可以从此窗口编辑主题。
1. 选择正确的模型以考虑打开率预测。有一些模型可用，每个模型对应特定行业。
1. Click **[!UICONTROL Test]**.

然后分析您的主题。

>[!NOTE]
>
>如果主题行过短，则无法分析该主题，并显示一条错误消息。

系统会计算一些指示器，并显示一组工具以帮助您：

* **预测的打开率**：此图表为您提供了电子邮件所能达到的最新主题的开放率理念。
* **主题长度**：此指示器可让您查看主题的当前长度是否正确，或者其是否需要较长或更短。
* **彩色字词**：测试主题时，绿色突出显示的词语是提高打开率预测最重要的词语。以红色突出显示的词语是提高打开率预测最少的词语。如果您在主题中添加或删除单词，高亮显示的单词将会更改。
* **类别和单词建议**：在窗口的下半部分，会显示选定模型的许多相关类别。这些类别按重要性顺序排序，它们允许您查看主题是否包含通过复选符号与之关联的词语。每个类别包含一组建议的词语，这些词语可用于您的主题，使其更具相关性并提高打开率。这些词语是给定类别中使用最频繁的词语。

>[!NOTE]
>
>个性化字段和标点符号会从主题分析中删除。对于动态/条件文本，所有变体都被视为一个主题行。

![](assets/predictive_subject_line_example.png)

### 导入模型 {#importing-models}

默认情况下，Adobe Campaign服务器上没有运行的模型。有两种方法可获取模型并激活该功能：

* 您可以通过先前电子邮件的数据培训本地模型：

   * 如果您已经在使用Adobe Campaign，则将自动对已发送的消息进行本地模型培训。
   * 如果您是Adobe Campaign的新用户，则可以从上一个包含列的系统/ESP中提取CSV文件：date、subject、send、open.要执行此操作，请转到 **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Email]** &gt; **[!UICONTROL Subject Line Import]** 并按照连续屏幕上提供的说明操作。当主题上传完成时，请导入本地模型，如下所述。本地模型会自动使用您上传的数据进行培训。
   * 如果您是Adobe Campaign的新用户并且无法获得上述CSV文件，则可以使用预培训模型或等到您的系统中有足够的交付数据来培训本地模型。系统将自动确定当前数据集是否包含足够的数据来识别模式和培训模型。

      >[!NOTE]
      >
      >培训自己的模型没有定义的主题行数量。要进行培训，主题行需要各种不同的内容，不会重复。如果没有足够的数据处理，系统将无法培训模型。您只能在实例上有一个受过培训的模型。
   要培训本地模型，请从 [此处下载subjectLineTraining.xml](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) ，然后使用 [包导入](../../automating/using/managing-packages.md) 功能将其上载到Adobe Campaign实例。技术工作流程将自动为您完成培训。

   第一次要培训模型时，管理员可以强制 **[!UICONTROL SubjectLine Training workflow]** 从 **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Workflows]** 菜单开始。

   上传和培训模型后，该功能会自动激活，并在邮件的主题行字段旁边显示一个新选项。

   然后，技术工作流程将自动每周培训您的模型。

* 您可以导入特定于特定行业(医疗等)的预培训模型。使用 [包导入](../../automating/using/managing-packages.md) 功能。这些模型在 [此处](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) 可用，无法进行培训。

   上传模型后，该功能会自动激活，并且消息的主题行字段旁边会显示一个新选项。

>[!NOTE]
>
>导入和生成培训模型只能由管理员执行。

可使用的模型有：

* 化妆品行业：subjectInsightCosmetic.xml
* 超市行业：subjectInsightSupermarket.xml
* 医疗行业：subjectInsightMedical.xml
* 要培训的模型：searchTineTraining. xml。

**相关主题：**

* [使用Adobe Sensei预测优化主题行](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Createcompellingcontenttailoredtoeveryindividual)
