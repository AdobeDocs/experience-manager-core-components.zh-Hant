---
title: 標題元件
description: 核心元件標題元件是具有就地編輯功能的區段標題元件。
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 2%

---


# 標題元件{#title-component}

核心元件標題元件是具有就地編輯功能的區段標題元件。

## 使用狀況 {#usage}

「標題元件」可用作內容區段的標題或標題。 可用標題層級可由範本作者在設計對話方塊中 [定義](#design-dialog)。 內容編輯器可以在編輯對話框中從可用的標題 [級別中選擇](#edit-dialog)。 為方便起見，您也可以在原地編輯標題文字。

## 版本與相容性 {#version-and-compatibility}

目前版本的標題元件為v2，此版本於2018年1月隨核心元件2.0.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM 雲端服務 |
|---|---|---|---|---|
| v2 | - | 相容 | 相容 | 相容 |
| [v1](v1/title-v1.md) | 相容 | 相容 | 相容 | - |

如需核心元件版本與版本的詳細資訊，請參閱檔案核 [心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

若要體驗「標題元件」，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪「元件 [庫」](https://adobe.com/go/aem_cmp_library_title)。

### 技術詳細資訊 {#technical-details}

有關Title Component的最新技術文 [件可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_title_v2)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](/help/developing/overview.md)。

## Edit Dialog {#edit-dialog}

編輯對話方塊可讓內容作者定義標題文字，並選取標題層級。

* **Title** —— 如果空白，將使用頁面標題
* **類型／大小** -定義標題的標題層級
* **連結** -定義標題將連結至的內容。 這可以是內容頁面、外部URL或頁面錨點的路徑。
* **ID** —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

![標題元件的編輯對話方塊](/help/assets/title-edit.png)

>[!NOTE]
>
>核心元件2.2.0版中已引入定義標題連結的功能。

就地編輯器也可用於編輯標題元件的文本。

![就地編輯標題元件](/help/assets/title-edit-inline.png)

## 設計對話框 {#design-dialog}

設計對話方塊可讓範本作者定義標題元件在內容作者建立時所具有的預設標題層級。

### 大小標籤 {#sizes-tab}

![標題元件的設計對話方塊](/help/assets/title-design.png)

* **作者允許的類型／大小** -啟用或停用內容作者使用標題元件時可用的標題類型。
* **預設類型／大小**-定義內容作者將標題元件新增至頁面時會自動指派的標題類型。
* **停用連結**-停用標題元件中連結的支援，以禁止內容作者從標題連結。

>[!NOTE]
>
>核心元件2.2.0版中已引入定義標題連結的功能。

### 樣式標籤 {#styles-tab}

Title Component支援AEM [Style System](/help/get-started/authoring.md#component-styling)。
