---
title: 電子郵件體驗片段元件
description: 電子郵件體驗片段元件可讓內容作者在內容中放置體驗片段變異，同時支援本地化的內容結構。
role: Architect, Developer, Admin, User
exl-id: 861c1fd1-6d6d-426c-a338-a558326fe16e
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 0%

---


# 電子郵件體驗片段元件 {#email-experience-fragment-component}

電子郵件體驗片段元件可讓內容作者在內容中放置體驗片段變異，同時支援本地化的內容結構。

## 使用狀況 {#usage}

電子郵件體驗片段元件可讓內容作者從現有的體驗片段變數中選取，並將一個變數放入內容中。 體驗片段是一組內容，其中包含內容和版面，且可跨管道重複使用。

* 元件的屬性可在 [配置對話框](#configure-dialog).
* 將元件新增至內容時，元件的預設值可在 [設計對話](#design-dialog).

電子郵件體驗片段元件支援本地化的網站結構。

## 版本與相容性 {#version-and-compatibility}

電子郵件體驗片段元件的目前版本為v1，已於2022年10月隨電子郵件核心元件X版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | 相容 |

如需電子郵件核心元件版本和版本的詳細資訊，請參閱本檔案 [電子郵件核心元件版本。](/help/email/versions.md)

## 本地化網站結構支援 {#localized-site-structure}

電子郵件體驗片段元件可適用於本地化內容結構，並根據內容本地化轉譯正確的體驗片段。 若要這麼做，體驗片段必須符合下列條件。

* 電子郵件體驗片段元件已新增至 [頁面範本。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/templates.html)
* 該範本可用來建立新內容頁面，此頁面是下列本地化結構的一部分 `/content/<site>`.
* 內容頁面上參考的體驗片段是下方本地化體驗片段結構的一部分 `/content/experience-fragments` 會遵循與下列網站相同的模式 `/content/<site>` 包括使用相同的元件名稱。

在此案例中，具有相同本地化的片段([語言、Blueprint或即時副本](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/reusing-content/msm-and-translation.html))，因為目前頁面將呈現為範本的一部分。

此行為僅限於範本中新增的電子郵件體驗片段元件。 新增至個別內容頁面的體驗片段元件會呈現元件中已設定的確切體驗片段轉譯。

* 如需體驗片段元件的本地化功能如何運作的範例，請參閱 [下節](#example).
* 如需核心元件本地化功能如何搭配運作的範例，請參閱 [「核心元件」頁面的本地化功能](/help/get-started/localization.md).

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

請注意下方的結構 `/content/experience-fragments/wknd` 鏡像的結構 `/content/wknd`.

在此案例中，如果電子郵件體驗片段元件 `/content/experience-fragments/wknd/us/en/footerTextXf` 放在範本上，則根據該範本建立的本地化頁面會自動呈現與本地化內容頁面相對應的本地化體驗片段。

因此，如果您導覽至 `/content/wknd/ch/de` 使用相同範本， `/content/experience-fragments/wknd/ch/de/footerTextXf` 將呈現，而非 `/content/experience-fragments/wknd/us/en/footerTextXf`.

### 備援 {#fallback}

電子郵件體驗片段元件會嘗試依下列順序尋找對應的本地化元件。

1. 首先，它會嘗試尋找語言根。
1. 如果找不到，它會嘗試尋找藍圖。
1. 如果找不到，則會嘗試尋找即時副本。
1. 如果找不到，預設為元件中設定的體驗片段。

## 範例元件輸出 {#sample-component-output}

若要體驗電子郵件體驗片段元件，並查看其設定選項、HTML和JSON輸出的範例，請造訪 [元件庫。](https://adobe.com/go/aem_cmp_library_email_xf)

## 技術詳細資訊 {#technical-details}

體驗片段元件的最新技術檔案 [可在GitHub上找到。](https://adobe.com/go/aem_cmp_email_tech_xf_v1)

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案。](/help/developing/overview.md)

## 配置對話框 {#configure-dialog}

設定對話方塊可讓內容作者選取應在內容中轉譯的體驗片段變化。

![電子郵件體驗片段元件的編輯對話方塊](/help/email/assets/email-experience-fragment-edit.png)

使用 **開啟選取對話方塊** 按鈕，開啟元件選取器以選擇要新增至內容頁面的體驗片段元件變異。

如果您將電子郵件體驗片段元件新增至範本，只要體驗片段已本地化，就會自動本地化，因此頁面上呈現的內容可能會與您明確選取的元件有所不同。 [請參閱上述範例](#example) 以取得更多資訊。

您也可以定義 **ID**. 此選項允許控制HTM中元件的唯一標識符。

* 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查產生的內容來找到。
* 若已指定ID，則作者應負責確認其唯一。
* 變更ID可能會對CSS造成影響。

### 樣式標籤 {#styles-tab-edit}

電子郵件體驗片段元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉式清單選取您要套用至元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須針對此元件在 [設計對話](#design-dialog) 讓索引標籤可用。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義內容作者可用的選項，這些內容作者使用電子郵件體驗片段元件，以及放置電子郵件體驗片段元件時設定的預設值。

### 樣式標籤 {#styles-tab}

電子郵件體驗片段元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)
