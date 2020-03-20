---
title: 测试电子邮件的主题行
description: 了解如何在电子邮件设计器中定义电子邮件的主题行。
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6f89b420f0f98c13da1bfff8f9b1b29e015aef89

---

# 测试电子邮件的主题行 {#testing-a-subject}


## 关于预测主题行 {#about-predictive-subject-line}

在编辑电子邮件时，您可以尝试不同的主题行并在发送电子邮件之前获得其打开率的估计。

默认情况下，此功能处于禁用状态。 在导入第一个模型时启用它。 模型是特定于特定行业的培训数据集的结果。 模型允许系统在提交新的主题行时预测电子邮件的打开率。

>[!NOTE]
>
>此功能适用于电子邮件和仅包含英语内容的数据库。 如果您的实例包含其他语言的电子邮件，则经过培训的模型将不一致，并会导致错误的结果。 仅当实例上已有模型可用时，才会显示用于测试主题的选项。

有关导入模型的详细信息，请参阅此 [部分](#importing-models)。

## 测试主题行 {#testing-subject-line}

要测试主题行，请执行以下步骤：

1. 创建或打开电子邮件。
1. 打开内容，然后在相应的输入字段中输入电子邮件的主题。
1. 单击 **[!UICONTROL Test subject]** 按钮以访问窗 **[!UICONTROL Test your subject line]** 口。 您仍可以从此窗口编辑主题。
1. 选择正确的模型以考虑开放率预测。 有多种型号可用，每种型号都对应于特定行业。 有关使用模型的更多信息，请参阅此 [部分](#importing-models)。
1. 单击 **[!UICONTROL Test]**.

然后，将分析您的主题。

>[!NOTE]
>
>如果主题行过短，则无法分析它并显示错误消息。

将计算多个指示器并显示一组工具，以帮助您：

* **预计开放率**:此图表可让您了解电子邮件及其当前主题的打开率。
* **主题长度**:此指示器可让您查看主题的当前长度是否正确，或者它需要更长还是更短。
* **彩色词**:在测试主题时，以绿色突出显示的单词是对增加打开率预测贡献最大的单词。 以红色突出显示的词是对增加开放率预测贡献最小的词。 如果在主题中添加或删除单词，高亮显示的单词将会更改。
* **类别和字词建议**:向窗口的下部显示选定模型的多个相关类别。 这些类别按重要性顺序排序，它们允许您查看主题是否包含通过检查符号与其关联的词。 每个类别都包含一组建议单词，这些单词可用于您的主题中，以使其更相关并提高开放率。 这些单词是在给定类别中使用最频繁的单词。

>[!NOTE]
>
>个性化字段和标点符号会从主题分析中去除。 对于动态／条件文本，所有变体都被视为一个主题行。

![](assets/predictive_subject_line_example.png)

## 导入模型 {#importing-models}

默认情况下，Adobe Campaign服务器上没有运行的模型。 有两种方法可获取模型并激活特征：

* 您可以根据以前电子邮件的数据培训本地模型。
* 您可以导入特定行业（医疗等）的预先培训的模型使用包 [导入功能](../../automating/using/managing-packages.md) 。

### 培训本地模型 {#training-local-model}

* 如果您已在使用Adobe Campaign，将自动对本地模型进行培训，以了解您已发送的消息。
* 如果您不熟悉Adobe Campaign，则可以从以前的系统/ESP中提取包含4列的CSV文件：日期，主题，打开，发送。 要执行此操作，请转到 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Subject Line Import]** ，然后按照连续屏幕上提供的说明操作。 主题上传完成后，请导入本地模型，如下所述。 本地模型会自动使用您上传的数据进行培训。
* 如果您是Adobe Campaign的新用户，并且无法如上所述获得CSV文件，则可以使用预先培训过的模型 [](#pre-trained-models) ，或等到系统中有足够的交付数据来培训本地模型时再执行。 系统将自动确定当前数据集是否包含足够的数据来识别模式和训练模型。

>[!NOTE]
>
>培训您自己的模型不需要定义的主题行数。 有关此问题的详细信息，请参 [阅疑难解答](#troubleshooting)。
>
>实例上只能有一个经过培训的模型。

要培训本地模型，请执行以下操作：
1. 从此处下载subjectLineTraining.xml [](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) ，然后使用包导 [](../../automating/using/managing-packages.md) 入功能将其上传到Adobe Campaign实例。 技术工作流将自动为您完成培训。
1. 当您第一次要培训模型时，管理员可以从> **[!UICONTROL SubjectLine Training workflow]** >菜单强制开始模 **[!UICONTROL Administration]** 型 **[!UICONTROL Application settings]** 的操 **[!UICONTROL Workflows]** 作。
1. 上传并培训模型后，该功能将自动激活，消息的主题行字段旁边将显示一个新选项。
1. 然后，技术工作流将每周自动继续培训您的模型。

### 导入预先培训的模型 {#pre-trained-models}

要访问这些模型，请单 [击此处](https://support.neolane.net/webApp/extranetLogin) ，然后转到 **[!UICONTROL Download Center]**。 使用包 [导入功能](../../automating/using/managing-packages.md) ，将模型上传到Adobe Campaign实例。

可用的模型包括：

* 化妆品行业：subjectInsightComsetic.xml
* 超市业：subjectInsightSupermarket.xml
* 医疗行业：subjectInsightMedical.xml
* 培训模型：subjectlineTraining.xml。

这些模型不能被训练。

上传模型后，该功能将自动激活，消息的主题行字段旁边将显示一个新选项。

>[!NOTE]
>
>导入和生成经过培训的模型只能由管理员执行。

## 故障排除 {#troubleshooting}

预测主题行是一个机器学习过程，它考虑了您上传的所有主题行及其未结率。 这样，系统就可以在提交新的主题行时预测电子邮件的打开率。

为了能够培训您自己的模型，无论用于培训模型的主题行数量如何，主题行都必须不同且不得重复。

主题线的质量至关重要。 如果没有足够的质量数据进行处理，或者如果所有以前的主题行过于相似，系统将无法对模型进行培训，您可能会收到一条错误消息。 这意味着您现有的记录集不允许提供可靠的预测建议。

在这种情况下，您应查看所上传的数据，并确保主题行的变化足够多，以便有效地培训模型。

<!--Some clients have reported this issue: I have had the subject line training workflow running for about a year now.  It has trained on 883 records and I am still seeing the message "The existing dataset is not enough to generate a model."  I do get an error in the workflow every time it runs "XML-110009 Unable to find the element 'runwf' of path '/' (document with schema 'serverConf')".

For this, campaign takes the subject line as training data and tries to come up with significant enough model to predict open rate with 95% confidence.

The 400 subject line number is mention with at least and is only indicative, model generation will also depend on quality of these lines.

It may happen that even 10k subject lines don't lead to model generation if they are too similar.

It means that it can be case that you don't have enough subject lines to generate the model and it is giving this error.

If you are getting an error/warning message, it means that your existing set of records is not enough for the predictive subject module to give a high confidence suggestion.

Adobe recommends reviewing the data you are uploading as the similarity of the subject lines might be the issue.-->
