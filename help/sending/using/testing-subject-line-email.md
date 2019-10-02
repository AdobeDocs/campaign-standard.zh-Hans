---
title: 测试电子邮件的主题行
seo-title: 测试电子邮件的主题行
description: 测试电子邮件的主题行
seo-description: Discover how to define the subject line of an email in the Email Designer.
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
source-git-commit: 8b85bbad7458286252a2900ce730288f6e52442e

---

# 测试主题 {#testing-a-subject}

要测试主题行，请执行以下步骤：

1. 创建或打开电子邮件。
1. 打开内容，然后在相应的输入字段中输入电子邮件的主题。
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
* **彩色词**:在测试主题时，以绿色突出显示的单词是对增加打开率预测贡献最大的单词。 Words highlighted in red are the words that contribute the least to increasing the open rate prediction. If you add or remove words in the subject, highlighted words will change.
* **Categories and word suggestions: Towards the lower part of the window, a number of relevant categories for the selected model are displayed.** These categories are sorted by order of importance and they allow you to see whether your subject contains words that are associated with it via a check symbol. Each category contains a set of suggested words that could be used in your subject to make it more relevant and increase the open rate. These words are the words that are used the most often in a given category.

>[!NOTE]
>
>Personalization fields and punctuation marks are stripped from the subject analysis. In the case of dynamic/conditional text, all variants are considered as one subject line.

![](assets/predictive_subject_line_example.png)

## Importing models {#importing-models}

By default, there is no model running on your Adobe Campaign server. There are two ways to get a model and activate the feature:

* You can train a local model from the data of your previous email messages:

   * If you are already using Adobe Campaign, the local model will be automatically trained on the messages that you have already sent.
   * If you are new to Adobe Campaign, you can extract a CSV file from your previous system/ESP that contains 4 columns: date, subject, sent, opens. 为此，请转到 **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Email]** &gt; **[!UICONTROL Subject Line Import]** ，然后按照连续屏幕上提供的说明操作。 主题上传完成后，请导入本地模型，如下所述。 The local model is automatically trained with the data you uploaded.
   * 如果您是Adobe Campaign的新用户，并且无法如上所述获得CSV文件，则可以使用预先培训的模型，或等到系统中有足够的交付数据来培训本地模型时再执行。 系统将自动确定当前数据集是否包含足够的数据来识别模式和训练模型。

      >[!NOTE]
      >
      >培训您自己的模型不需要定义的主题行数。 为了能够训练它，主题线必须是多样的，没有重复项。 如果没有足够的数据进行处理，系统就无法对模型进行训练。 实例上只能有一个经过培训的模型。
   要培训本地模型，请从此处下载subjectLineTraining.xml [](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) ，然后使用包导入功 [](../../automating/using/managing-packages.md) 能将其上传到您的Adobe Campaign实例。 技术工作流将自动为您完成培训。

   当您第一次要培训模型时，管理员可以从&gt; **[!UICONTROL SubjectLine Training workflow]** &gt;菜单强制开始模 **[!UICONTROL Administration]** 型 **[!UICONTROL Application settings]** 的操 **[!UICONTROL Workflows]** 作。

   上传并培训模型后，该功能将自动激活，消息的主题行字段旁边将显示一个新选项。

   然后，技术工作流将每周自动继续培训您的模型。

* 您可以导入特定行业（医疗等）的预先培训的模型使用包 [导入功能](../../automating/using/managing-packages.md) 。 这些模型在此 [处可用](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) ，并且无法接受培训。

   上传模型后，该功能将自动激活，消息的主题行字段旁边将显示一个新选项。

>[!NOTE]
>
>导入和生成经过培训的模型只能由管理员执行。

可用的模型包括：

* 化妆品行业：subjectInsightComsetic.xml
* 超市业：subjectInsightSupermarket.xml
* 医疗行业：subjectInsightMedical.xml
* 培训模型：subjectlineTraining.xml。