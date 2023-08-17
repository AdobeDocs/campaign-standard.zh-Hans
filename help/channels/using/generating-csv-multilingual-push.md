---
title: 为带有Campaign Standard的多语言推送通知生成CSV文件
description: 上传CSV文件以生成内容以进行投放是一项用于支持多语言推送通知的功能。
audience: channels
content-type: reference
topic-tags: email-messages
feature: Push
role: User
level: Intermediate
exl-id: bd9ec3f9-e047-42dc-ab64-9fb274cb4656
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 0%

---

# 为多语言推送通知生成 CSV 文件{#generating-csv-multilingual-push}

上传CSV文件以生成内容以进行投放是一项用于支持多语言推送通知的功能。 CSV文件的格式需要遵循特定准则才能成功上传文件，从而能够创建投放。 以下各节介绍文件格式及其注意事项。

## 文件格式 {#file-format}

多语言推送在CSV文件中需要14列：

1. title
1. messagebody
1. 声音
1. adge
1. deeplinkURI
1. 类别
1. iOS媒体附件URL
1. androidMediaAttachmentURL
1. isContentAvailable
1. isMutableContent
1. customField
1. 区域设置
1. 语言
1. silentPush

通过单击 **[!UICONTROL Download a sample file]** 在 **[!UICONTROL Manage Content Variants]** 窗口。 有关更多信息，请参阅此 [部分](../../channels/using/creating-a-multilingual-push-notification.md).

* **title， messageBody，声音，徽章， deeplinkURI，类别， iosMediaAttachmentURL， androidMediaAttachmentURL**：常规推送有效负荷内容。 您需要在创建推送投放时以类似的方式提供此信息。
* **自定义字段**：对自定义字段使用JSON格式，例如 `{"key1":"value1","key2":"value2"}`. 有关自定义字段的示例，请参阅上面的示例文件。
* **isContentAvailable**：标记表示内容可用检查，值1表示真，值0表示假。 默认值为0。 如果将此列留空，则将该值视为0。
* **isMutableContent**：标记可变内容，值1表示true，值0表示false。 默认值为0。 如果将此列留空，则将该值视为0。
* **区域设置**：区域设置是语言变体的字段，例如，“en_us”表示美国英语，“fr_fr”表示法语 — 法语。
* **语言**：与区域设置关联的语言的名称。 例如，如果locale为“en_us”，则语言名称应为“English-United States”。
* **silentPush**：表示推送通知类型的标记。 如果是常规推送通知，则值应为0。 如果是静默推送，则值应为1。 默认值为0。 如果将此列留空，则将该值视为0。

## 创建csv文件的约束和准则 {#constraints-guideline-csv}

**每列的名称都是固定的**.
您应在CSV文件中包括每列的名称，如果不对内容使用任何列，则将其留空。

**“locale”和“language”列是必填的，并且每行的值都是唯一的。**
此列的空值将导致文件上传失败。

**列的顺序很重要**. 上传文件中列的顺序需要遵循与示例文件相同的格式。

**引用列内容**. 由于这是一个CSV（表示逗号分隔值）文件，因此必须引用包含逗号(，)的任何列内容。 例如，“你好，汤姆！”

**国际字符需要UTF-8编码。**

**如果以纯文本生成文件，请用“，”分隔各列。**

**变量不匹配。** 如果您使用内容块并以特定语言定位受众，则需要在CSV文件中列出每种目标语言，否则在发送投放时将收到错误。

## 在csv文件中插入个性化字段 {#personalization-field-csv}

如果要使用个性化字段，您应包括 <span> 标记之前。

要在messageBody中插入“firstName”个性化字段，消息需要是：

```
 "Hello <span class="nl-dce-field nl-dce-done"  data-nl-expr="/context/profile/firstName">First name</span>, this is message".
```

“firstName”字段由以下内容表示：

```
 <span class="nl-dce-field nl-dce-done" data-nl-expr="/context/profile/firstName">First name</span>
```

在范围中，有两个必需属性：

* 一个是静态类。 无论您计划使用哪个个性化字段，它都始终为class=&quot;nl-dce-field nl-dce-done&quot;。

* 另一种是data-nl-expr，它是个性化字段的路径。 例如，如果您从UI插入“firstName”个性化字段，则导航路径将为 **[!UICONTROL Context (context)]** > **[!UICONTROL Profile (profile)]** > **[!UICONTROL First name (firstName)]** （如下图所示）。 在这种情况下，路径将为

  ```
  /context/profile/firstName. data-nl-expr="/context/profile/firstName".
  ```

![](assets/multilingual_push_2.png)

## 区域设置和语言名称 {#locale-language-names}

支持以下语言：

| 区域设置 | 语言 |
|:-:|:-:|
| af_za | 南非荷兰语 — 南非 |
| sq_al | 阿尔巴尼亚语 — 阿尔巴尼亚 |
| ar_dz | 阿拉伯语 — 阿尔及利亚 |
| ar_bh | 阿拉伯语 — 巴林 |
| ar_iq | 阿拉伯语 — 伊拉克 |
| ar_il | 阿拉伯语 — 以色列 |
| ar_jo | 阿拉伯语 — 约旦 |
| ar_kw | 阿拉伯语 — 科威特 |
| ar_lb | 阿拉伯语 — 黎巴嫩 |
| ar_ma | 阿拉伯语 — 摩洛哥 |
| ar_om | 阿拉伯语 — 阿曼 |
| ar_qa | 阿拉伯语 — 卡塔尔 |
| ar_sa | 阿拉伯语 — 沙特阿拉伯 |
| ar_sy | 阿拉伯语 — 叙利亚 |
| ar_tn | 阿拉伯语 — 突尼斯 |
| ar_ae | 阿拉伯语 — 阿拉伯联合酋长国 |
| ar_ye | 阿拉伯语 — 也门 |
| hy_am | 亚美尼亚语 — 亚美尼亚 |
| az_az | 阿塞拜疆语 — 阿塞拜疆 |
| be_by | 白俄罗斯语 — 白俄罗斯 |
| bs_ba | 波斯尼亚语 — 波斯尼亚 |
| bg_bg | 保加利亚语 — 保加利亚 |
| ca_es | 加泰罗尼亚语 — 西班牙 |
| zh_cn | 中文（简体） — 中国 |
| zh_sg | 中文（简体） — 新加坡 |
| zh_hk | 中文（繁体） — 中国香港特别行政区 |
| zh_tw | 中文（繁体） — 台湾地区 |
| hr_hr | 克罗地亚语 — 克罗地亚 |
| cs_cz | 捷克语 — 捷克语 |
| da_dk | 丹麦语 — 丹麦 |
| nl_be | 荷兰语 — 比利时 |
| nl_nl | 荷兰语 — 荷兰 |
| en_au | 英语 — 澳大利亚 |
| en_bz | 英语 — 伯利兹 |
| en_ca | 英语 — 加拿大 |
| en_in | 英语 — 印度 |
| en_ie | 英语 — 爱尔兰 |
| en_jm | 英语 — 牙买加 |
| en_nz | 英语 — 新西兰 |
| en_ph | 英语 — 菲律宾 |
| en_za | 英语 — 南非 |
| en_tt | 英语 — 特立尼达和多巴哥 |
| en_gb | 英语 — 英国 |
| en_us | 英语 — 美国 |
| en_zw | 英语 — 津巴布韦 |
| et_ee | 爱沙尼亚语 — 爱沙尼亚 |
| fi_fi | 芬兰语 — 芬兰 |
| fr_be | 法语 — 比利时 |
| fr_ca | 法语 — 加拿大 |
| fr_fr | 法语 — 法国 |
| fr_lu | 法语 — 卢森堡 |
| fr_ch | 法语 — 瑞士 |
| de_at | 德语 — 奥地利 |
| de_de | 德语 — 德国 |
| de_lu | 德语 — 卢森堡 |
| de_ch | 德语 — 瑞士 |
| el_cy | 希腊语 — 塞浦路斯 |
| el_gr | 希腊语 — 希腊 |
| gu_in | 古吉拉特语 — 印度 |
| he_il | 希伯来语 — 以色列 |
| hi_in | 印地语 — 印度 |
| hu_hu | 匈牙利语 — 匈牙利 |
| is_is | 冰岛语 — 冰岛 |
| id_id | 印度尼西亚语 — 印度尼西亚 |
| it_it | 意大利语 — 意大利 |
| it_ch | 意大利语 — 瑞士 |
| ja_jp | 日语 — 日本 |
| kn_in | 卡纳达语 — 印度 |
| kk_kz | 哈萨克语 — 哈萨克斯坦 |
| ko_kr | 韩语 — 韩国 |
| lv_lv | 拉脱维亚语 — 拉脱维亚 |
| lt_lt | 立陶宛语 — 立陶宛 |
| mk_mk | 马其顿语 — 马其顿 |
| ms_my | 马来语 — 马来西亚 |
| mr_in | 马拉地语 — 印度 |
| no_no | 挪威语 — 挪威 |
| pl_pl | 波兰语 — 波兰 |
| pt_br | 葡萄牙语 — 巴西 |
| pt_pt | 葡萄牙语 — 葡萄牙 |
| pa_in | 旁遮普语 — 印度 |
| ro_md | 罗马尼亚语 — 摩尔多瓦 |
| ro_ro | 罗马尼亚语 — 罗马尼亚 |
| ru_kz | 俄语 — 哈萨克斯坦 |
| ru_ru | 俄语 — 俄罗斯 |
| ru_ua | 俄语 — 乌克兰 |
| a_in | 梵语 — 印度 |
| sr_ba | 塞尔维亚语 — 波斯尼亚 |
| sr_rs | 塞尔维亚语 — 塞尔维亚 |
| sk_sk | 斯洛伐克语 — 斯洛伐克 |
| sl_si | 斯洛文尼亚语 — 斯洛文尼亚 |
| es_ar | 西班牙语 — 阿根廷 |
| es_bo | 西班牙语 — 玻利维亚 |
| es_cl | 西班牙语 — 智利 |
| es_co | 西班牙语 — 哥伦比亚 |
| es_cr | 西班牙语 — 哥斯达黎加 |
| es_do | 西班牙语 — 多米尼加共和国 |
| es_ec | 西班牙语 — 厄瓜多尔尔 |
| es_sv | 西班牙语 — 萨尔瓦多 |
| es_gt | 西班牙语 — 危地马拉 |
| es_hn | 西班牙语 — 洪都拉斯 |
| es_mx | 西班牙语 — 墨西哥 |
| es_ni | 西班牙语 — 尼加拉瓜 |
| es_pa | 西班牙语 — 巴拿马 |
| es_py | 西班牙语 — 巴拉圭 |
| es_pe | 西班牙语 — 秘鲁 |
| es_pr | 西班牙语 — 波多黎各 |
| es_es | 西班牙语 — 西班牙 |
| es_uy | 西班牙语 — 乌拉圭 |
| es_ve | 西班牙语 — 委内瑞拉 |
| sw_ke | 斯瓦希里语 — 肯尼亚 |
| sv_fi | 瑞典语 — 芬兰 |
| sv_se | 瑞典语 — 瑞典 |
| ta_in | 泰米尔语 — 印度 |
| tt_ru | 鞑靼语 — 俄语 |
| te_in | 泰卢固语 — 印度 |
| th_th | 泰语 — 泰国 |
| tr_cy | 土耳其语 — 塞浦路斯 |
| tr_tr | 土耳其语 — 土耳其 |
| uk_ua | 乌克兰语 — 乌克兰 |
| ur_in | 乌尔都语 — 印度 |
| ur_pk | 乌尔都语 — 巴基斯坦 |
| vi_vn | 越南语 — 越南 |
