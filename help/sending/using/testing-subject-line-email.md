---
title: Testing the subject line of an email
seo-title: Testing the subject line of an email
description: Testing the subject line of an email
seo-description: Discover how to define the subject line of an email in the Email Designer.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: 发送
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3fc0d9d7e90a31ffb34efc33d6f5c148ba5aac90

---

# 测试电子邮件的主题行 {#testing-a-subject}

要测试主题行，请执行以下步骤：

1. 创建或打开电子邮件。
1. Open the content and enter the subject of the email in the corresponding input field.
1. 单击 **[!UICONTROL Test subject]** 按钮以访问窗 **[!UICONTROL Test your subject line]** 口。 您仍可以从此窗口编辑主题。
1. 选择正确的模型以考虑开放率预测。 有多种型号可用，每种型号都对应于特定行业。
1. Click **[!UICONTROL Test]**.

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

* 您可以根据以前电子邮件的数据培训本地模型：

   * 如果您已在使用Adobe Campaign，将自动对本地模型进行培训，以了解您已发送的消息。
   * 如果您不熟悉Adobe Campaign，则可以从以前的系统/ESP中提取包含4列的CSV文件：日期、主题、发送、打开。 To do that, go to  &gt;  &gt;  &gt;  and follow the instructions provided on the successive screens. **[!UICONTROL Administration]****[!UICONTROL Channels]****[!UICONTROL Email]****[!UICONTROL Subject Line Import]** When the subject upload is complete, import a local model as described below. The local model is automatically trained with the data you uploaded.
   * If you are new to Adobe Campaign and cannot get a CSV file as described above, you can use a pre-trained model or wait until you have enough delivery data in your system to train a local model. The system will automatically determine whether your current data set contains enough data to recognize patterns and to train the model.

      >[!NOTE]
      >
      >There is no defined number of subject lines needed to train your own model. To be able to train it, the subject lines need to be varied and to have no duplicates. If there is not enough data to process, the system will not be able to train the model. You can only have one trained model on your instance.
   要培训本地模型，请从此处下载subjectLineTraining.xml [](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) ，然后使用包导入功 [](../../automating/using/managing-packages.md) 能将其上传到您的Adobe Campaign实例。 A technical workflow will automatically do the training for you.

   The first time you want to train a model, an administrator can force the  to start from the  &gt;  &gt;  menu.**[!UICONTROL SubjectLine Training workflow]****[!UICONTROL Administration]****[!UICONTROL Application settings]****[!UICONTROL Workflows]**

   Once a model has been uploaded and trained, the feature is automatically activated and a new option appears next to the subject line field of your messages.

   Then, the technical workflow will automatically continue to train your model every week.

* 您可以导入特定行业（医疗等）的预先培训的模型using the package import feature. [](../../automating/using/managing-packages.md)这些模型在此 [处可用](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) ，并且无法接受培训。

   上传模型后，该功能将自动激活，消息的主题行字段旁边将显示一个新选项。

>[!NOTE]
>
>导入和生成经过培训的模型只能由管理员执行。

可用的模型包括：

* 化妆品行业：subjectInsightComsetic.xml
* 超市业：subjectInsightSupermarket.xml
* 医疗行业：subjectInsightMedical.xml
* 培训模型：subjectlineTraining.xml。
