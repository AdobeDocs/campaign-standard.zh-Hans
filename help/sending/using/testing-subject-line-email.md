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
source-git-commit: 7e61796376a14c279d38107905275172be0dd12d

---

# 测试电子邮件的主题行 {#testing-a-subject}

要测试主题行，请执行以下步骤：

1. 创建或打开电子邮件。
1. 打开内容，然后在相应的输入字段中输入电子邮件的主题。
1. 单击 **[!UICONTROL Test subject]** 按钮以访问窗 **[!UICONTROL Test your subject line]** 口。 您仍可以从此窗口编辑主题。
1. 选择正确的模型以考虑开放率预测。 有多种型号可用，每种型号都对应于特定行业。
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

* 您可以根据以前电子邮件的数据培训本地模型：

   * 如果您已在使用Adobe Campaign，将自动对本地模型进行培训，以了解您已发送的消息。
   * 如果您不熟悉Adobe Campaign，则可以从以前的系统/ESP中提取包含4列的CSV文件：日期，主题，打开，发送。 为此，请转到 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Subject Line Import]** ，然后按照连续屏幕上提供的说明操作。 主题上传完成后，请导入本地模型，如下所述。 本地模型会自动使用您上传的数据进行培训。
   * 如果您是Adobe Campaign的新用户，并且无法如上所述获得CSV文件，则可以使用预先培训的模型，或等到系统中有足够的交付数据来培训本地模型时再执行。 系统将自动确定当前数据集是否包含足够的数据来识别模式和训练模型。

      >[!NOTE]
      >
      >培训您自己的模型不需要定义的主题行数。 为了能够训练它，主题线必须是多样的，没有重复项。 如果没有足够的数据进行处理，系统就无法对模型进行训练。 实例上只能有一个经过培训的模型。
   要培训本地模型，请从此处下载subjectLineTraining.xml [](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) ，然后使用包导入功 [](../../automating/using/managing-packages.md) 能将其上传到您的Adobe Campaign实例。 技术工作流将自动为您完成培训。

   当您第一次要培训模型时，管理员可以从> **[!UICONTROL SubjectLine Training workflow]** >菜单强制开始模 **[!UICONTROL Administration]** 型 **[!UICONTROL Application settings]** 的操 **[!UICONTROL Workflows]** 作。

   上传并培训模型后，该功能将自动激活，消息的主题行字段旁边将显示一个新选项。

   然后，技术工作流将每周自动继续培训您的模型。

* 您可以导入特定行业（医疗等）的预先培训的模型使用包 [导入功能](../../automating/using/managing-packages.md) 。 要访问这些模型，请 [单击此处](https://support.neolane.net/webApp/extranetLogin) ，然后转 **[到下载中心]**。这些模型无法接受培训。

   上传模型后，该功能将自动激活，消息的主题行字段旁边将显示一个新选项。

>[!NOTE]
>
>导入和生成经过培训的模型只能由管理员执行。

可用的模型包括：

* 化妆品行业：subjectInsightComsetic.xml
* 超市业：subjectInsightSupermarket.xml
* 医疗行业：subjectInsightMedical.xml
* 培训模型：subjectlineTraining.xml。
