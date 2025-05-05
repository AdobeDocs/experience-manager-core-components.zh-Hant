---
title: 電子郵件體驗片段元件
description: 電子郵件體驗片段元件可讓內容作者在其內容中放置體驗片段變數，同時支援當地語系化的內容結構。
role: Architect, Developer, Admin, User
exl-id: 861c1fd1-6d6d-426c-a338-a558326fe16e
source-git-commit: 91969e4956bef1a511b8d588d5290a7999bf86ec
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 1%

---


# 電子郵件體驗片段元件 {#email-experience-fragment-component}

電子郵件體驗片段元件可讓內容作者在其內容中放置體驗片段變數，同時支援當地語系化的內容結構。

## 使用情況 {#usage}

電子郵件體驗片段元件可讓內容作者從現有的體驗片段變數中選取，並將其放置在內容中。 體驗片段是一組內容，包括內容和版面，並可跨管道重複使用。

* 可以在[設定對話方塊](#configure-dialog)中定義元件的屬性。
* 將元件新增至內容時的預設值可以在[設計對話方塊](#design-dialog)中定義。

電子郵件體驗片段元件支援本地化的網站結構。

## 版本和相容性 {#version-and-compatibility}

電子郵件體驗片段元件的目前版本是v1，此版本隨2022年10月的電子郵件核心元件發行版本X的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service  |
|---|---|---|---|
| v1 | 相容 | - | - |

如需電子郵件核心元件版本的詳細資訊，請參閱檔案[電子郵件核心元件版本。](/help/email/versions.md)

## 當地語系化網站結構支援 {#localized-site-structure}

電子郵件體驗片段元件可適應本地化的內容結構，並根據內容的本地化呈現適當的體驗片段。 為此，體驗片段必須符合以下條件。

* 電子郵件體驗片段元件已新增至[頁面範本。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/templates.html?lang=zh-Hant)
* 該範本是用來建立新內容頁面，此頁面是`/content/<site>`以下的本地化結構的一部分。
* 在內容頁面上參考的體驗片段屬於`/content/experience-fragments`以下的本地化體驗結構的一部分，遵循與`/content/<site>`以下的網站相同的模式，包括使用相同的元件名稱。

在這種情況下，與目前頁面具有相同本地化（[語言、Blueprint或即時副本](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/reusing-content/msm-and-translation.html?lang=zh-Hant)）的片段將會呈現為範本的一部分。

此行為僅限新增到範本的電子郵件體驗片段元件。 新增到個別內容頁面的體驗片段元件將轉譯在元件中設定的精確體驗片段轉譯。

* 如需體驗片段元件本地化功能運作方式的範例，請參閱[下節](#example)。
* 如需核心元件的本地化功能如何搭配運作的範例，請參閱核心元件頁面的[本地化功能](/help/get-started/localization.md)。

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

請注意，`/content/experience-fragments/wknd`下的結構會反映`/content/wknd`的結構。

在此案例中，如果電子郵件體驗片段元件`/content/experience-fragments/wknd/us/en/footerTextXf`放在範本上，根據該範本建立的當地語系化頁面將自動轉譯與當地語系化內容頁面對應的當地語系化體驗片段。

因此，如果您導覽至`/content/wknd/ch/de`底下使用相同範本的內容頁面，將會轉譯`/content/experience-fragments/wknd/ch/de/footerTextXf`而非`/content/experience-fragments/wknd/us/en/footerTextXf`。

### 遞補 {#fallback}

電子郵件體驗片段元件將嘗試依照以下順序尋找對應的本地化元件。

1. 首先嘗試尋找語言根。
1. 如果未找到，則會嘗試尋找Blueprint。
1. 如果未找到，則會嘗試尋找即時副本。
1. 如果找不到，其預設值為元件中設定的體驗片段。

## 技術細節 {#technical-details}

閱讀有關體驗片段元件[&#128279;](https://www.adobe.com/go/aem_cmp_xf_v1_tw)的最新技術檔案。

如需開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案。](/help/developing/overview.md)

## 設定對話方塊 {#configure-dialog}

此設定對話方塊可讓內容作者選取應在內容中轉譯的體驗片段變數。

![電子郵件體驗片段元件的編輯對話方塊](/help/email/assets/email-experience-fragment-edit.png)

使用&#x200B;**開啟選取範圍對話方塊**&#x200B;按鈕開啟元件選擇器，選擇要新增至內容頁面的體驗片段元件變數。

如果您將電子郵件體驗片段元件新增至範本，只要體驗片段已本地化，該元件就會自動本地化，因此根據您明確選取的元件，頁面上呈現的內容可能會有所不同。 [如需詳細資訊，請參閱以上範例](#example)。

您也可以定義&#x200B;**ID**。 此選項允許控制HTM中元件的唯一識別碼。

* 如果保留為空白，系統會自動為您產生唯一ID，但您可在檢查結果內容時找到該ID。
* 若指定ID，作者應負責確認該ID為唯一ID。
* 變更ID會對CSS造成影響。

### 樣式索引標籤 {#styles-tab-edit}

電子郵件體驗片段元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉式清單，選取要套用至元件的樣式。 在「編輯」對話方塊中所做的選取與從元件工具列中選擇的選取具有相同的效果。

必須在[設計對話方塊](#design-dialog)中為此元件設定樣式，才能使用索引標籤。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義哪些選項可供使用電子郵件體驗片段元件的內容作者使用，以及在放置電子郵件體驗片段元件時的預設設定。

### 樣式索引標籤 {#styles-tab}

電子郵件體驗片段元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)
