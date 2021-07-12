---
title: 階層連結元件
description: 核心元件階層連結元件是導覽元件，可根據頁面在內容階層中的位置建立連結的階層連結。
role: Architect, Developer, Admin, User
exl-id: 19d65b9d-a407-4f50-9c55-8de0f12222ed
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 1%

---

# 階層連結元件{#breadcrumb-component}

核心元件階層連結元件是導覽元件，可根據頁面在內容階層中的位置建立連結的階層連結。

## 使用狀況 {#usage}

階層連結元件會顯示網站階層中目前頁面的位置，讓頁面訪客可從其目前位置導覽頁面階層。 這通常會整合至頁首或頁尾。

可用選項（例如預設導航級別和顯示當前頁面或隱藏頁面的功能）可由模板作者在[設計對話框](#design-dialog)中定義。 然後，內容編輯器可以在[edit對話框](#edit-dialog)中選擇是否顯示隱藏頁面以及元件的實際導航級別。

## 版本與相容性 {#version-and-compatibility}

目前的階層連結元件版本為v2，此版本於2018年1月隨核心元件2.0.0版推出，本檔案已詳細說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- | --- |--- |---|
| v2 | 相容 | 相容 | 相容 |
| [v1](v1/breadcrumb-v1.md) | 相容 | 相容 | - |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗階層連結元件並查看其設定選項以及HTML和JSON輸出的範例，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_breadcrumb)。

>[!NOTE]
>
>自核心元件2.1.0版起，階層連結元件支援[schema.org微資料](https://schema.org/BreadcrumbList)。

## 技術詳細資訊 {#technical-details}

如需有關階層連結元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者隱藏階層連結中的隱藏和作用中頁面，以及階層中應顯示的深度。

![階層連結元件編輯對話方塊](/help/assets/breadcrumb-edit.png)

* **導覽開始層級**  — 階層中，階層連結元件應開始向下游到目前頁面的位置。例如：

   * 0開始於`/content`
   * 1開始於`/content/<yourSite>`
   * 2從`/content/<yourSite>/<country>`開始

* **顯示隱藏的導覽項目**  — 顯示在階層連結中標示為隱藏的頁面（依預設不會顯示）
* **隱藏目前頁面**  — 在階層連結中隱藏目前頁面（預設會顯示）
* **停用陰影**  — 如果階層中的頁面是重新導向，則會顯示重新導向頁面的名稱，而非目標名稱。有關詳細資訊，請參閱導航元件的[卷影站點結構支援](navigation.md#shadow-structure)。
* **ID**  — 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義預設值，供選項在階層連結中隱藏隱藏和作用中的頁面，以及應顯示的階層深度。

### 主要標籤 {#main-tab}

![](/help/assets/breadcrumb-design.png)

* **導覽開始層級**  — 定義階層中，當階層連結元件新增至頁面時，階層連結元件應該從哪個位置開始向下游到目前頁面的預設值。
* **顯示隱藏的導覽項目**  — 定義將階層連結元 **件新增** 至頁面時，顯示隱藏的導覽項目選項的預設值。

   * 它不會啟用或停用作者的選項。 它只設定預設值。

* **隱藏目前頁面** — 定義將階層連結元 **件新** 增至頁面時，隱藏目前頁面選項的預設值。

   * 它不會啟用或停用作者的選項。 它只設定預設值。

* **停用陰影**  — 定義將階層連結元 **件新** 增至頁面時，停用陰影選項的預設值。

### 樣式標籤 {#styles-tab}

階層連結元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe用戶端資料層 {#data-layer}

階層連結元件支援[Adobe用戶端資料層。](/help/developing/data-layer/overview.md)
