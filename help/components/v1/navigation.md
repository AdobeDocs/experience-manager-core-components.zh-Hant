---
title: 導航元件(v1)
description: 導航元件允許用戶輕鬆導航全球化的站點結構。
role: Architect, Developer, Admin, User
source-git-commit: e5251010ca41025eb2bb56b66164ecf4cc0145c8
workflow-type: tm+mt
source-wordcount: '1430'
ht-degree: 0%

---


# 導航元件(v1) {#navigation-component}

導航元件允許用戶輕鬆導航全球化的站點結構。

## 使用狀況 {#usage}

導航元件列出一個頁面樹，以便站點的用戶能夠輕鬆地導航站點結構。

導航元件可自動檢測站點的全球化站點結構， [自動適應本地化頁面。](#localized-site-structure) 另外，通過使用 [卷影重定向頁](#shadow-structure) 表示除主內容結構之外的其他結構。

的 [編輯對話框](#edit-dialog) 允許內容作者定義導航根頁面以及導航深度。 的 [設計對話框](#design-dialog) 允許模板作者為導航根和深度定義預設值。

## 版本和相容性 {#version-and-compatibility}

本文檔介紹導航元件的v1，該版本於2018年1月隨核心元件2.0.0版而推出。

>[!CAUTION]
>
>本文檔介紹導航元件的v1。
>
>有關導航元件當前版本的詳細資訊，請參閱 [導航元件](/help/components/navigation.md) 的子菜單。

## 本地化站點結構支援 {#localized-site-structure}

網站通常以多種語言提供，適用於不同的區域。 通常，每個本地化頁面都包含作為頁面模板一部分包含的導航元素。 導航元件允許您將其放置在站點所有頁面的模板上一次，然後它將根據您的全球化網站結構自動適應各個本地化頁面。

* 有關導航元件的本地化功能如何工作的示例，請參見 [下面一節](#example-localization)。
* 有關核心元件的本地化功能如何協同工作的示例，請參見 [「核心元件」頁的本地化功能](/help/get-started/localization.md)。

### 範例 {#example-localization}

假設您的內容類似以下內容：

```
/content
+-- wknd
   +-- language-masters
      +-- de
         \-- experience
            \-- arctic-surfing-in-lofoten
      +-- en
         \-- experience
            \-- arctic-surfing-in-lofoten
      +-- es
      +-- fr
      \-- it
   +-- us
      +-- en
         \-- experience
            \-- arctic-surfing-in-lofoten
      \-- es
   \-- ch
      +-- de
         \-- experience
            \-- arctic-surfing-in-lofoten
      +-- fr
      \-- it
+-- wknd-events
\-- wknd-shop
```

對於站點WKND，您可能希望將導航元件作為頁眉的一部分放置在頁面模板上。 一旦成為模板的一部分，您就可以 **導航根** 到 `/content/wknd/language-masters/en` 因為您的網站主內容就是從那裡開始的。 你可能也想 **導航結構深度** 要 `2` 因為您可能不希望整個內容樹由元件顯示，而是由前兩個級別顯示，因此它可作為概述。

使用 **導航根** 值，導航元件知道 `/content/wknd/language-masters/en` 導航開始，它可以通過向下遞歸站點結構兩個級別(由 **導航結構深度** 值)。

無論用戶正在查看哪個本地化頁面，導航元件都可以通過瞭解當前頁面的位置找到相應的本地化頁面，然後向後向根頁面工作，然後轉發到相應頁面。

所以如果有訪客 `/content/ch/de/experience/arctic-surfing-in-lofoten`，構件知道基於 `/content/wknd/language-masters/de`。 同樣，如果訪問者正在查看 `/content/us/en/experience/arctic-surfing-in-lofoten`，構件知道基於 `/content/wknd/language-masters/en`。

## 卷影站點結構支援 {#shadow-structure}

有時，需要為訪問者建立與實際站點結構不同的導航菜單。 或許，通過重新安排內容清單，促銷應突出菜單中的某些內容。 使用僅重定向到其他內容頁的陰影頁，導航元件可以生成任何必要的任意導航結構。

為此，您需要：

1. 將卷影頁建立為表示所需站點結構的空頁。 這通常稱為陰影站點結構。
1. 設定 **重定向** 這些頁面上的頁面屬性中的值，以指向實際的內容頁面。
1. 設定 **在導航中隱藏** 選項。
1. 設定 **導航根** 指向新陰影站點結構的根的導航元件的值。

然後，導航元件將基於陰影站點結構呈現菜單。 元件呈現的連結指向陰影頁重定向到的實際內容頁，而不是陰影頁本身。 此外，元件還顯示實際頁的名稱，並正確加亮活動頁，即使導航基於陰影頁也是如此。 導航元件有效地使陰影頁面對訪問者完全透明。

>[!NOTE]
>陰影頁使您的導航選項更加靈活，但請記住，此結構的維護將完全手動進行。 如果您重新排列實際的站點內容或添加/刪除內容，則需要根據需要手動更新卷影結構。

>[!NOTE]
>在渲染陰影站點結構時，導航邏輯僅遞歸陰影頁。 該邏輯不遞歸重定向目標的結構。

## 導航重定向 {#redirects}

當頁面具有重定向目標(無論它指向外部URL還是指向另一頁AEM)時，導航元件將包含指向該指向重定向目標的URL的連結。

### 範例 {#redirect-example}

* 建立重定向到B頁的A頁。
* 建立重定向到 `https://aemcomponents.dev`
* 在頁D上，插入包含頁A和C的或導航元件
* 然後生成的各個連結直接指向B頁和 `https://aemcomponents.dev`

## 元件輸出示例 {#sample-component-output}

要體驗導航元件，並查看其配置選項示例以及HTML和JSON輸出，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_navigation)。

## 技術詳細資訊 {#technical-details}

有關導航元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_navigation_v1)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

>[!NOTE]
>
>自2.1.0版核心元件起，導航元件支援 [schema.org微資料](https://schema.org)。

## 編輯對話框 {#edit-dialog}

在「編輯」對話框中，內容作者可以定義導航的根頁面和導航結構的深度。

### 屬性頁籤 {#properties-tab}

![導航元件的編輯對話框屬性頁籤](/help/assets/navigation-edit-properties.png)

* **導航根**  — 根頁，用於生成導航樹。
* **排除根級別**  — 通常，導航中不應包含根。 此選項允許您指定要從根目錄中排除的級別數。 例如：
   * 0 =顯示根級別
   * 1 =排除根級別
   * 2 =排除根並向上1層
   * 等。
* **收集所有子頁**  — 收集所有作為導航根子體的頁面。
* **導航結構深度**  — 定義元件相對於導航根應在導航樹下顯示多少個級別(僅在 **收集所有子頁** )。
* **禁用跟蹤**  — 如果層次結構中的頁面是重定向，則將顯示重定向頁面的名稱，而不是目標頁面。 查看 [卷影站點結構支援](#shadow-structure) 的子菜單。
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

### 輔助功能頁籤 {#accessibility-tab}

![導航元件的編輯對話框輔助功能頁籤](/help/assets/navigation-edit-accessibility.png)

在 **輔助功能** 頁籤，可為 [ARIA輔助功能](https://www.w3.org/WAI/standards-guidelines/aria/) 元件的標籤。

* **標籤**  — 元件的ARIA標籤屬性的值

## 設計對話框 {#design-dialog}

設計對話框允許模板作者設定向內容作者顯示的導航根頁面和導航深度的預設值。

### 屬性頁籤 {#properties-tab-design}

![導航元件的設計對話框](/help/assets/navigation-design.png)

* **導航根**  — 導航結構的根頁的預設值，該值將用於生成導航樹，並在內容作者將元件添加到頁面時預設。
* **排除根級別**  — 通常，導航中不應包含根。 此選項允許您指定要從根目錄中排除的級別數的預設值。 例如：
   * 0 =顯示根級別
   * 1 =排除根級別
   * 2 =排除根並向上1層
   * 等。
* **收集所有子頁**  — 用於收集所有作為導航根子體的頁面的選項的預設值。
* **導航結構深度**  — 導航結構深度的預設值。
* **禁用跟蹤**  — 在添加導航元件時，如果應禁用陰影，則預設值為

### 樣式頁籤 {#styles-tab}

導航元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe客戶端資料層 {#data-layer}

導航元件支援 [Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
