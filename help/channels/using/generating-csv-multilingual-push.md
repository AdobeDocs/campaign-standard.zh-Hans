---
solution: Campaign Standard
product: campaign
title: 为多语言推送通知生成CSV文件并Campaign Standard
description: 上传CSV文件以生成投放内容是支持多语言推送通知的功能。
audience: channels
content-type: reference
topic-tags: email-messages
feature: 推送
role: 业务从业者
level: 中间
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 0%

---


# 为多语言推送通知生成 CSV 文件{#generating-csv-multilingual-push}

上传CSV文件以生成投放内容是支持多语言推送通知的功能。 CSV文件的格式需要遵循某些准则，才能成功上传文件，从而能够创建投放。 以下几节介绍了文件格式及其注意事项。

## 文件格式{#file-format}

多语言推送需要CSV文件中包含14列：

1. title
1. messageBody
1. 声音
1. adge
1. deeplinkURI
1. 类别
1. iosMediaAttachmentURL
1. androidMediaAttachmentURL
1. isContentAvailable
1. isMutableContent
1. customFields
1. locale
1. 语言
1. silentPush

单击&#x200B;**[!UICONTROL Manage Content Variants]**&#x200B;窗口中的&#x200B;**[!UICONTROL Download a sample file]**，检查CSV示例。 有关详细信息，请参阅此[部分](../../channels/using/creating-a-multilingual-push-notification.md)。

* **title， messageBody， sound， badge， deplinkURI， 类别, iosMediaAttachmentURL， androidMediaAttachmentURL**:定期推送有效负荷内容。您需要以与创建推送投放类似的方式提供此信息。
* **自定义字段**:对自定义字段使用JSON格式，例如 `{"key1":"value1","key2":"value2"}`.有关自定义字段的示例，请参阅上面的示例文件。
* **isContentAvailable**:“内容可用”检查的标志，值1表示true，值0表示false。默认值为0。 如果将此列留空，该值将被视为0。
* **isMutableContent**:可变内容的标志，值1表示true，值0表示false。默认值为0。 如果将此列留空，该值将被视为0。
* **locale**:locale是语言变体的字段，例如“en_us”表示美语 — 英语，“fr_fr”表示法语 — 法语。
* **语言**:与区域设置关联的语言的名称。例如，如果区域设置为“en_us”，则语言的名称应为“English-United States”。
* **silentPush**:推送通知类型的标志。如果是常规推送通知，则值应为0。 如果是静默推送，则值应为1。 默认值为0。 如果将此列留空，该值将被视为0。

## 创建csv文件{#constraints-guideline-csv}的约束和准则

**每列的名称是固定的**。您应在CSV文件中包含每列的名称，如果不对内容使用任何列，请将其留空。

**“locale”和“language”列是必填项，值对于每行都是唯一的。**
此列的空值将导致文件上传失败。

**列的顺序很重要**。上载文件中的列顺序需要采用与示例文件相同的格式。

**引用列内容**。由于这是CSV（表示逗号分隔值）文件，因此必须引用包含逗号(,)的任何列内容。 例如，“你好，汤姆！”

**UTF-8编码对于国际字符是必需的。**

**如果按纯文本生成文件，则按“，”分隔每列。**

**变体不匹配。** 如果将内容块和目标受众用于特定语言，您需要在CSV文件中列表每种目标语言，否则发送投放时会出错。

## 在csv文件{#personalization-field-csv}中插入个性化字段

如果要使用个性化字段，应在文件中包含<span>标记。

要在messageBody中插入“firstName”个性化字段，消息必须为：

```
 "Hello <span class="nl-dce-field nl-dce-done"  data-nl-expr="/context/profile/firstName">First name</span>, this is message".
```

“firstName”字段由：

```
 <span class="nl-dce-field nl-dce-done" data-nl-expr="/context/profile/firstName">First name</span>
```

在范围中有两个必填属性：

* 一个是静态类。 无论您计划使用哪个个性化字段，它始终都是class=&quot;nl-dce-field nl-dce-done&quot;。

* 另一个是数据 — nl-expr，它是个性化领域的路径。 例如，如果您从UI中插入“firstName”个性化字段，则导航路径将是&#x200B;**[!UICONTROL Context (context)]** > **[!UICONTROL Profile (profile)]** > **[!UICONTROL First name (firstName)]**（如下图所示）。 在这种情况下，路径将

   ```
   /context/profile/firstName. data-nl-expr="/context/profile/firstName".
   ```

![](assets/multilingual_push_2.png)

## 区域设置和语言名称{#locale-language-names}

支持以下语言：

| locale | 语言 |
|:-:|:-:|
| af_za | 南非语 |
| sq_al | 阿尔巴尼亚 — 阿尔巴尼亚 |
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
| hy_am | 亚美尼亚 — 亚美尼亚 |
| az_az | 阿塞拜疆 — 阿塞拜疆 |
| be_by | 白俄罗斯 — 白俄罗斯 |
| bs_ba | 波斯尼亚 — 波斯尼亚 |
| bg_bg | 保加利亚 — 保加利亚 |
| ca_es | 加泰罗尼亚语 — 西班牙 |
| zh_cn | 简体中文 — 中国 |
| zh_sg | 简体中文 — 新加坡 |
| zh_hk | 繁体中文 — 中国香港特别行政区 |
| zh_tw | 繁体中文 — 台湾地区 |
| hr_hr | 克罗地亚 — 克罗地亚 |
| cs_cz | 捷克 — 切希亚 |
| da_dk | 丹麦语 — 丹麦 |
| nl_be | 荷兰语 — 比利时 |
| nl_nl | 荷兰 — 荷兰 |
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
| hu_hu | 匈牙利 — 匈牙利 |
| is_is | 冰岛语 — 冰岛 |
| id_id | 印度尼西亚 — 印度尼西亚 |
| it_it | 意大利语 — 意大利 |
| it_ch | 意大利语 — 瑞士 |
| ja_jp | 日语 — 日本 |
| kn_in | 卡纳达 — 印度 |
| kk_kz | 哈萨克语 — 哈萨克斯坦 |
| ko_kr | 韩语 — 韩国 |
| lv_lv | 拉脱维亚 — 拉脱维亚 |
| lt_lt | 立陶宛 — 立陶宛 |
| mk_mk | 马其顿 — 马其顿 |
| ms_my | 马来语 — 马来西亚 |
| mr_in | 马拉地 — 印度 |
| no_no | 挪威语 — 挪威 |
| pl_pl | 波兰 — 波兰 |
| pt_br | 葡萄牙语 — 巴西 |
| pt_pt | 葡萄牙语 — 葡萄牙 |
| pa_in | 旁遮普语 — 印度 |
| ro_md | 罗马尼亚语 — 摩尔多瓦 |
| ro_ro | 罗马尼亚语 — 罗马尼亚 |
| ru_kz | 俄语 — 哈萨克斯坦 |
| ru_ru | 俄语 — 俄罗斯 |
| ru_ua | 俄语 — 乌克兰 |
| a_in | 梵语 — 印度 |
| sr_ba | 塞尔维亚 — 波斯尼亚 |
| sr_rs | 塞尔维亚 — 塞尔维亚 |
| sk_sk | 斯洛伐克 — 斯洛伐克 |
| sl_si | 斯洛文尼亚 — 斯洛文尼亚 |
| es_ar | 西班牙语 — 阿根廷 |
| es_bo | 西班牙语 — 玻利维亚 |
| es_cl | 西班牙语 — 智利 |
| es_co | 西班牙语 — 哥伦比亚 |
| es_cr | 西班牙语 — 哥斯达黎加 |
| es_do | 西班牙语 — 多米尼加共和国 |
| es_ec | 西班牙语 — 厄瓜多尔 |
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
| tt_ru | 塔塔尔语 — 俄语 |
| te_in | 泰卢古 — 印度 |
| th_th | 泰语 — 泰国 |
| tr_cy | 土耳其语 — 塞浦路斯 |
| tr_tr | 土耳其语 — 土耳其 |
| uk_ua | 乌克兰语 — 乌克兰 |
| ur_in | 乌尔都 — 印度 |
| ur_pk | 乌尔都 — 巴基斯坦 |
| vi_vn | 越南 — 越南 |
