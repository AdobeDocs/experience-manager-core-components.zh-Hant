---
title: 電子郵件標題元件
description: 電子郵件標題元件是您電子郵件的章節標題元件，具有就地編輯功能。
role: Architect, Developer, Admin, User
exl-id: f65b6973-bb36-406f-bbea-f85a23f5340b
source-git-commit: 91969e4956bef1a511b8d588d5290a7999bf86ec
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 1%

---


# 電子郵件標題元件 {#email-title-component}

電子郵件標題元件是您電子郵件的章節標題元件，具有就地編輯功能。

## 使用情況 {#usage}

電子郵件標題元件旨在用作電子郵件區段的標題或標題。

* 可用的標題層級可由範本作者在[設計對話方塊中定義。](#design-dialog)
* 內容作者可以在[編輯對話方塊中，從可用的標題層級中選取。](#edit-dialog)

為了增加便利性，也可以簡單地就地編輯標題文字。

## 版本和相容性 {#version-and-compatibility}

電子郵件標題元件的目前版本是v1，此版本隨2022年10月的電子郵件核心元件發行版本X的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service  |
|---|---|---|---|
| v1 | 相容 | - | - |

如需核心元件版本的詳細資訊，請參閱檔案[核心電子郵件元件版本](/help/versions.md)。

### 技術細節 {#technical-details}

您可以在GitHub](https://adobe.com/go/aem_cmp_tech_email_title_v1)上找到有關標題元件[的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者定義標題文字並選取標題層級。

* **標題** — 如果留空，則使用頁面標題
   * 按一下Campaign圖示以開啟[選取Adobe Campaign變數](/help/email/campaign-variables.md)對話方塊，插入來自Adobe Campaign的動態內容。
* **型別/大小** — 定義標題的標題層級
* **連結** — 定義標題將連結的內容。 這可以是內容頁面的路徑、外部URL或頁面錨點。
   * 按一下Campaign圖示以開啟[選取Adobe Campaign變數](/help/email/campaign-variables.md)對話方塊，插入來自Adobe Campaign的動態內容。
* **ID** — 此選項允許控制HTML中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS造成影響。

![電子郵件標題元件的編輯對話方塊](/help/email/assets/email-title-edit.png)

就地編輯器也可用於編輯標題元件的文字。

![就地編輯電子郵件標題元件](/help/email/assets/email-title-edit-inline.png)

### 樣式索引標籤 {#styles-tab-edit}

電子郵件標題元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉式清單，選取要套用至元件的樣式。 在「編輯」對話方塊中所做的選取與從元件工具列中選擇的選取具有相同的效果。

必須在[設計對話方塊](#design-dialog)中為此元件設定樣式，以便下拉式功能表可用。

標題元件](/help/email/assets/email-title-edit-styles.png)的編輯對話方塊的![樣式索引標籤

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義內容作者建立標題元件時的預設標題層級。

### 大小索引標籤 {#sizes-tab}

![標題元件的設計對話方塊](/help/email/assets/email-title-design.png)

* **允許的作者型別/大小** — 啟用或停用內容作者使用電子郵件標題元件時可用的標題型別。
* **預設型別/大小** — 定義內容作者將電子郵件標題元件新增至頁面時，將自動指派的標題型別。
* **停用連結** — 停用電子郵件標題元件中連結的支援，不允許內容作者從標題進行連結。

### 樣式索引標籤 {#styles-tab}

電子郵件標題元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
