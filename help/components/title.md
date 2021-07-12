---
title: 標題元件
description: 核心元件標題元件是區段標題元件，可就地編輯。
role: Architect, Developer, Admin, User
exl-id: 393af72c-549f-4609-afb0-2712f827b549
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 2%

---

# 標題元件{#title-component}

核心元件標題元件是區段標題元件，可就地編輯。

## 使用狀況 {#usage}

標題元件可用作內容區段的標題或標題。 可用的標題層級可由範本作者在[design對話方塊](#design-dialog)中定義。 內容編輯器可從[edit dialog](#edit-dialog)中的可用標題層級進行選擇。 為方便起見，您也可以輕鬆就地編輯標題文字。

## 版本與相容性 {#version-and-compatibility}

目前的標題元件版本為v2，已於2018年1月隨核心元件2.0.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|---|
| v2 | 相容 | 相容 | 相容 |
| [v1](v1/title-v1.md) | 相容 | 相容 | - |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗標題元件並查看其設定選項以及HTML和JSON輸出的範例，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_title)。

### 技術詳細資訊 {#technical-details}

如需Title元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_title_v2)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者定義標題文字並選取標題層級。

* **標題**  — 如果空白，則會使用頁面標題
* **類型/大小**  — 定義標題的標題層級
* **連結**  — 定義標題要連結的內容。這可以是內容頁面、外部URL或頁面錨點的路徑。
* **ID**  — 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

![標題元件的編輯對話框](/help/assets/title-edit.png)

>[!NOTE]
>
>核心元件2.2.0版已導入定義標題連結的功能。

就地編輯器也可用來編輯標題元件的文字。

![就地編輯標題元件](/help/assets/title-edit-inline.png)

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義內容作者建立時標題元件將具備的預設標題層級。

### 「大小」頁簽 {#sizes-tab}

![標題元件的設計對話框](/help/assets/title-design.png)

* **作者的允許類型/大小**  — 啟用或停用內容作者在使用標題元件時可使用的標題類型。
* **預設類型/大**&#x200B;小 — 定義內容作者將標題元件新增至頁面時，將自動指派的標題類型。
* **停用連結** — 停用標題元件中連結的支援，以禁止內容作者從標題連結。

>[!NOTE]
>
>核心元件2.2.0版已導入定義標題連結的功能。

### 樣式標籤 {#styles-tab}

標題元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe用戶端資料層 {#data-layer}

標題元件支援[Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
