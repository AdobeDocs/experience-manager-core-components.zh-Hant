---
title: 電子郵件標題元件
description: 「電子郵件標題元件」是您的電子郵件的一個標題元件，可進行就地編輯。
role: Architect, Developer, Admin, User
exl-id: f65b6973-bb36-406f-bbea-f85a23f5340b
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 1%

---


# 電子郵件標題元件 {#email-title-component}

「電子郵件標題元件」是您的電子郵件的一個標題元件，可進行就地編輯。

## 使用狀況 {#usage}

「電子郵件標題」元件用作電子郵件部分的標題或標題。

* 可用標題級別可由模板作者在 [設計對話框。](#design-dialog)
* 內容作者可以從中的可用標題級別中選擇 [編輯對話框。](#edit-dialog)

為了方便起見，酒店還提供標題文本的簡單就地編輯。

## 版本和相容性 {#version-and-compatibility}

電子郵件標題元件的當前版本是v1，該版本於2022年10月隨電子郵件核心元件的第x版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | - |

有關核心元件版本和版本的詳細資訊，請參閱文檔 [核心電子郵件元件版本](/help/versions.md)。

### 技術詳細資訊 {#technical-details}

有關標題元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_email_title_v1)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 編輯對話框 {#edit-dialog}

編輯對話框允許內容作者定義標題文本並選擇標題級別。

* **標題**  — 如果為空，則使用頁面標題
   * 按一下「市場活動」表徵圖以開啟 [選擇Adobe Campaign變數](/help/email/campaign-variables.md) 對話框，插入來自Adobe Campaign的動態內容。
* **類型/大小**  — 定義標題的標題級別
* **連結**  — 定義標題將連結到的內容。 這可以是內容頁面、外部URL或頁面錨點的路徑。
   * 按一下「市場活動」表徵圖以開啟 [選擇Adobe Campaign變數](/help/email/campaign-variables.md) 對話框，插入來自Adobe Campaign的動態內容。
* **ID**  — 此選項允許控制HTML中元件的唯一標識符。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS。

![電子郵件標題元件的編輯對話框](/help/email/assets/email-title-edit.png)

就地編輯器還可用於編輯標題元件的文本。

![電子郵件標題元件的就地編輯](/help/email/assets/email-title-edit-inline.png)

### 樣式頁籤 {#styles-tab-edit}

電子郵件標題元件支AEM持 [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉框選擇要應用於元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須在 [設計對話框](#design-dialog) 以便下拉菜單可用。

![標題元件的編輯對話框的「樣式」頁籤](/help/email/assets/email-title-edit-styles.png)

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義由內容作者建立時標題元件將具有的預設標題級別。

### 「大小」頁籤 {#sizes-tab}

![標題元件的設計對話框](/help/email/assets/email-title-design.png)

* **作者允許的類型/大小**  — 啟用或禁用內容作者在使用電子郵件標題元件時可用的標題類型。
* **預設類型/大小**  — 定義內容作者將「電子郵件標題元件」添加到頁面時將自動分配的標題類型。
* **禁用連結**  — 禁用對電子郵件標題元件中連結的支援，以禁止內容作者從標題連結。

### 樣式頁籤 {#styles-tab}

電子郵件標題元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。
