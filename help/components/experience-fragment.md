---
title: 體驗片段元件
description: 體驗片段元件可讓內容作者將體驗片段變數新增至頁面。
role: Architect, Developer, Admin, User
exl-id: 103f729a-084d-4b6a-a239-d8ef8902eb95
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 1%

---

# 體驗片段元件{#experience-fragment-component}

核心元件體驗片段元件可讓內容作者在支援本地化網站結構的同時，將體驗片段變化放置在頁面上。

## 使用狀況 {#usage}

核心元件體驗片段元件可讓內容作者從現有體驗片段變化中選取，並將一個變數放在內容頁面上。 體驗片段元件也支援本地化的網站結構。

* 可在[configure dialog](#configure-dialog)中定義元件的屬性。
* 將元件新增至頁面時的預設值，可在[設計對話方塊](#design-dialog)中定義。

## 本地化網站結構支援 {#localized-site-structure}

體驗片段元件可適用於本地化的網站結構，並根據頁面的本地化來轉譯適當的體驗片段。 若要這麼做，體驗片段必須符合下列條件。

* 體驗片段元件會新增至範本。
* 該範本用於建立新內容頁面，該頁面是`/content/<site>`下方本地化結構的一部分。
* 內容頁面上參考的體驗片段屬於`/content/experience-fragments`下方的本地化體驗片段結構的一部分，其模式與`/content/<site>`下的網站相同，包括使用相同的元件名稱。

在此情況下，與目前頁面具有相同本地化（語言、藍圖或即時副本）的片段將轉譯為範本的一部分。

此行為僅限於新增至範本的體驗片段元件。 新增至個別內容頁面的體驗片段元件將呈現元件中設定的確切體驗片段轉譯。

* 如需體驗片段元件本地化功能如何運作的範例，請參閱[下方的](#example)一節。
* 如需核心元件本地化功能如何搭配運作的範例，請參閱核心元件頁面[本地化功能頁面](/help/get-started/localization.md)。

### 範例 {#example}

假設您的內容如下所示：

```
/content
+-- experience-fragments
   \-- wknd
      +-- language-masters
      +-- us
         +-- en
            +-- footerTextXf
            \-- headerTextXf
         \-- es
            +-- footerTextXf
            \-- headerTextXf
      \-- ch
         +-- de
            +-- footerTextXf
            \-- headerTextXf
         +-- fr
            +-- footerTextXf
            \-- headerTextXf
         \-- it
            +-- footerTextXf
            \-- headerTextXf
+-- wknd
   +-- language-masters
   +-- us
      +-- en
      \-- es
   +-- ch
      +-- de
      +-- fr
      \-- it
+-- wknd-events
\-- wknd-shop
```

請注意，`/content/experience-fragments/wknd`下的結構鏡像了`/content/wknd`的結構。

在此案例中，如果體驗片段元件`/content/experience-fragments/wknd/us/en/footerTextXf`放置在範本上，根據該範本建立的本地化頁面會自動呈現與本地化內容頁面相對應的本地化體驗片段。

因此，如果您導覽至使用相同範本的`/content/wknd/ch/de`下的內容頁面，將會呈現`/content/experience-fragments/wknd/ch/de/footerTextXf`而非`/content/experience-fragments/wknd/us/en/footerTextXf`。

### 備援 {#fallback}

體驗片段元件會嘗試依下列順序尋找對應的本地化元件。

1. 首先，它會嘗試尋找語言根。
1. 如果找不到，它會嘗試尋找藍圖。
1. 如果找不到，則會嘗試尋找即時副本。
1. 如果找不到，則預設為元件中設定的體驗片段。

## 版本與相容性 {#version-and-compatibility}

目前的體驗片段元件版本為v1，已於2019年9月隨核心元件2.6.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗體驗片段元件，並查看其設定選項以及HTML和JSON輸出的範例，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_xf)。

## 技術詳細資訊 {#technical-details}

如需體驗片段元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_xf_v1)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

設定對話方塊可讓內容作者選取應在頁面上呈現的體驗片段變化。

![體驗片段元件的編輯對話方塊](/help/assets/experience-fragment-edit.png)

使用&#x200B;**開啟選取對話方塊**&#x200B;按鈕，開啟元件選取器以選擇要新增至內容頁面的體驗片段元件變異。

如果您將體驗片段元件新增至範本，請注意，如果體驗片段已本地化，則會自動本地化，因此頁面上呈現的內容可能會與您明確選取的元件有所不同。 [如需詳細資](#example) 訊，請參閱上方範例。

您也可以定義&#x200B;**ID**。 此選項可控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一標識符。

* 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
* 若已指定ID，則作者應負責確認其唯一。
* 變更ID可能會影響CSS、JS和資料層追蹤。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義內容作者可用的選項，這些內容作者使用體驗片段元件，以及放置體驗片段元件時設定的預設值。

### 樣式標籤 {#styles-tab}

體驗片段元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
