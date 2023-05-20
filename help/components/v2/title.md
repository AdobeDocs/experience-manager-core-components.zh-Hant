---
title: 標題元件(v2)
description: 核心元件標題元件是具有就地編輯功能的節標題元件。
role: Architect, Developer, Admin, User
exl-id: f853ec46-19fd-4569-a9d3-5c376d2a2101
source-git-commit: e291d4c1bfd37292d68c236178f9681c4e5ee741
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 0%

---

# 標題元件(v2) {#title-component}

核心元件標題元件是具有就地編輯功能的節標題元件。

## 使用狀況 {#usage}

標題元件將用作內容部分的標題或標題。 可用標題級別可由模板作者在 [設計對話框](#design-dialog)。 內容編輯器可從 [編輯對話框](#edit-dialog)。 為了方便起見，酒店還提供標題文本的簡單就地編輯。

## 版本和相容性 {#version-and-compatibility}

本文檔介紹了2018年1月核心元件2.0.0版中引入的標題元件v2。

>[!CAUTION]
>
>本文檔介紹「標題元件」的v2。
>
>有關「標題元件」的當前版本的詳細資訊，請參閱 [標題元件](/help/components/title.md) 的子菜單。

## 元件輸出示例 {#sample-component-output}

要體驗「標題元件」，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_title)。

### 技術詳細資訊 {#technical-details}

有關標題元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_title_v2)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 編輯對話框 {#edit-dialog}

編輯對話框允許內容作者定義標題文本並選擇標題級別。

* **標題**  — 如果為空，則使用頁面標題
* **類型/大小**  — 定義標題的標題級別
* **連結**  — 定義標題將連結到的內容。 這可以是內容頁面、外部URL或頁面錨點的路徑。
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

![標題元件的編輯對話框](/help/assets/title-edit.png)

>[!NOTE]
>
>在核心元件2.2.0版中引入了定義標題連結的功能。

就地編輯器還可用於編輯標題元件的文本。

![就地編輯標題元件](/help/assets/title-edit-inline.png)

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義由內容作者建立時標題元件將具有的預設標題級別。

### 「大小」頁籤 {#sizes-tab}

![標題元件的設計對話框](/help/assets/title-design.png)

* **作者允許的類型/大小**  — 啟用或禁用內容作者在使用標題元件時可用的標題類型。
* **預設類型/大小** — 定義內容作者將標題元件添加到頁面時將自動分配的標題類型。
* **禁用連結** — 禁用對標題元件中連結的支援，以禁止內容作者從標題連結。

>[!NOTE]
>
>在核心元件2.2.0版中引入了定義標題連結的功能。

### 樣式頁籤 {#styles-tab}

標題元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe客戶端資料層 {#data-layer}

標題元件支援 [Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
