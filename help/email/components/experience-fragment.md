---
title: 電子郵件體驗片段元件
description: 電子郵件體驗片段元件可讓內容作者在其內容中放置體驗片段變化版本，同時支援本地化內容結構。
role: Architect, Developer, Admin, User
exl-id: 861c1fd1-6d6d-426c-a338-a558326fe16e
index: false
source-git-commit: eb77567dc32cccb81a9fc131493d11fb55b7e93b
workflow-type: ht
source-wordcount: '865'
ht-degree: 100%

---


# 電子郵件體驗片段元件 {#email-experience-fragment-component}

電子郵件體驗片段元件可讓內容作者在其內容中放置體驗片段變化版本，同時支援本地化內容結構。

## 用途 {#usage}

電子郵件體驗片段元件可讓內容作者從現有的體驗片段變化版本中選取，並將其放置到內容中。體驗片段是同時包含內容和版面的內容群組，並可跨管道重複使用。

* 該元件的屬性可在[設定對話框](#configure-dialog)中定義。
* 將元件新增至內容時，可在[設計對話框](#design-dialog)中定義預設值。

電子郵件體驗片段元件支援本地化網站結構。

## 版本和相容性 {#version-and-compatibility}

電子郵件體驗片段元件的目前版本為 v1，此版本於 2022 年 10 月隨著電子郵件核心元件 X 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 相容 | - | - |

如需「電子郵件核心元件」版本和發行版本的進一步詳細資訊，請參閱[電子郵件核心元件版本](/help/email/versions.md)文件。

## 本地化網站結構支援 {#localized-site-structure}

電子郵件體驗片段元件可適應本地化的網站結構，並根據內容的本地化呈現適當的體驗片段。為此，體驗片段必須符合以下條件。

* 電子郵件體驗片段元件已新增至[頁面範本](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/templates.html?lang=zh-Hant)。
* 該範本用於建立新內容頁面，此頁面是 `/content/<site>` 以下的本地化結構的一部分。
* 在內容頁面上參考的體驗片段屬於 `/content/experience-fragments` 以下的本地化體驗結構的一部分，遵循與 `/content/<site>` 以下的網站相同的模式，包括使用相同的元件名稱。

在這種情況下，與目前頁面具有相同本地化 ([語言、Blueprint 或即時副本](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/reusing-content/msm-and-translation.html?lang=zh-Hant)) 的片段將當作範本的一部分呈現。

此行為僅限新增至範本的電子郵件體驗片段元件。新增到個別內容頁面的體驗片段元件將轉譯在元件中設定的精確體驗片段轉譯。

* 如需體驗片段元件本地化功能的運作方式範例，請參閱[下一章節](#example)。
* 如需核心元件的本地化功能如何搭配運作的範例，請參閱[核心元件頁面的本地化功能](/help/get-started/localization.md)。

### 範例 {#example}

假設您的內容看起來像這樣：

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

請注意，`/content/experience-fragments/wknd` 下的結構會反映 `/content/wknd` 的結構。

在此案例中，如果電子郵件體驗片段元件 `/content/experience-fragments/wknd/us/en/footerTextXf` 放置在範本上，根據該範本建立的本地化頁面將自動轉譯與本地化內容頁面對應的本地化體驗片段。

因此，如果您導覽至 `/content/wknd/ch/de` 底下使用相同範本的內容頁面，將會轉譯 `/content/experience-fragments/wknd/ch/de/footerTextXf` 而非 `/content/experience-fragments/wknd/us/en/footerTextXf`。

### 遞補 {#fallback}

電子郵件體驗片段元件會嘗試依照以下順序尋找對應的本地化元件。

1. 首先嘗試尋找語言根。
1. 如果未找到，則會嘗試尋找 Blueprint。
1. 如果未找到，則會嘗試尋找即時副本。
1. 如果找不到，則預設為元件中設定的體驗片段。

## 技術詳細資訊 {#technical-details}

閱讀最新的[體驗片段元件的相關技術文件](https://www.adobe.com/go/aem_cmp_xf_v1_tw)。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件。](/help/developing/overview.md)

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者選取應在該內容中轉譯的體驗片段變化版本。

![電子郵件體驗片段元件的編輯對話框](/help/email/assets/email-experience-fragment-edit.png)

使用&#x200B;**開啟選取對話框**&#x200B;按鈕開啟元件選擇器，選擇要新增至內容頁面的體驗片段元件變化版本。

如果您將電子郵件體驗片段元件新增至範本，只要體驗片段完成本地化，該元件便會自動進行本地化，因此在頁面呈現的內容可能與您明確選取的元件有所差異。如需詳細資訊，[請參閱以上範例](#example)。

您也可以定義 **ID**。此選項允許控制 HTML 中元件的唯一識別碼。

* 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的內容找到該 ID。
* 若已指定 ID，則作者應確保其為唯一識別碼。
* 變更該 ID 會對 CSS 產生影響。

### 樣式索引標籤 {#styles-tab-edit}

電子郵件體驗片段元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

使用下拉式清單，選取想要套用至元件的樣式。在編輯對話框中所做的選取，與從元件工具列中選擇具有相同效果。

元件樣式必須在[設計對話框](#design-dialog)中設定，才能使用該索引標籤。

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可為使用電子郵件體驗片段元件的內容作者定義可用選項，以及在放置電子郵件體驗片段元件時所設定的預設值。

### 樣式索引標籤 {#styles-tab}

電子郵件體驗片段元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
