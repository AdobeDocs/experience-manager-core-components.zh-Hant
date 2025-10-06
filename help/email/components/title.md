---
title: 電子郵件標題元件
description: 電子郵件標題元件是您電子郵件的區段標題元件，具有就地編輯功能。
role: Architect, Developer, Admin, User
exl-id: f65b6973-bb36-406f-bbea-f85a23f5340b
index: false
source-git-commit: eb77567dc32cccb81a9fc131493d11fb55b7e93b
workflow-type: ht
source-wordcount: '596'
ht-degree: 100%

---


# 電子郵件標題元件 {#email-title-component}

電子郵件標題元件是您電子郵件的區段標題元件，具有就地編輯功能。

## 用途 {#usage}

電子郵件標題元件用作電子郵件內容的主標題或區段的標題。

* 可用的標題層級可由範本作者在[設計對話框](#design-dialog)中定義。
* 內容作者可在[編輯對話框](#edit-dialog)中選取可用的標題層級。

為了增加便利性，也可以簡單地就地編輯標題文字。

## 版本和相容性 {#version-and-compatibility}

電子郵件標題元件的目前版本為 v1，此版本於 2022 年 10 月隨著電子郵件核心元件 x 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 相容 | - | - |

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[核心電子郵件元件版本](/help/versions.md)文件。

### 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_email_title_v1)有關標題元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 編輯對話框 {#edit-dialog}

編輯對話框可讓內容作者定義標題文字並選取標題層級。

* **標題** - 如果空白，則使用頁面標題
   * 按一下行銷活動圖示以開啟[選取 Adobe Campaign 變數](/help/email/campaign-variables.md)對話框，插入來自 Adobe Campaign 的動態內容。
* **類型/大小** - 定義標題的標題層級
* **連結** - 定義標題將連結的內容。這可以是內容頁面的路徑、外部 URL 或頁面錨點。
   * 按一下行銷活動圖示以開啟[選取 Adobe Campaign 變數](/help/email/campaign-variables.md)對話框，插入來自 Adobe Campaign 的動態內容。
* **ID** - 此選項允許控制 HTML 中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS 產生影響。

![電子郵件標題元件的編輯對話框](/help/email/assets/email-title-edit.png)

也可以使用就地編輯器來編輯標題元件的文字。

![電子郵件標題元件的就地編輯](/help/email/assets/email-title-edit-inline.png)

### 樣式索引標籤 {#styles-tab-edit}

電子郵件標題元件支援 AEM [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉式清單，選取想要套用至元件的樣式。在編輯對話框中所做的選取，與從元件工具列中選擇具有相同效果。

元件樣式必須在[設計對話框](#design-dialog)中設定，才能使用該下拉式選單。

![標題元件編輯對話框的樣式索引標籤](/help/email/assets/email-title-edit-styles.png)

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可定義內容作者建立標題元件時應具備的預設標題層級。

### 尺寸索引標籤 {#sizes-tab}

![標題元件的設計對話框](/help/email/assets/email-title-design.png)

* **允許作者使用的類型/大小** - 啟用或停用內容作者在使用電子郵件標題元件時可用的標題類型。
* **預設類型/大小** - 定義內容作者將電子郵件標題元件新增至頁面時，將自動指派的標題類型。
* **停用連結** - 停用電子郵件標題元件中連結的支援，不允許內容作者從標題連結。

### 樣式索引標籤 {#styles-tab}

電子郵件標題元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
