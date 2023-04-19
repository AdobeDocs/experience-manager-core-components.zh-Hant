---
title: 電子郵件按鈕元件
description: 「電子郵件按鈕」元件可讓您設定並顯示內容中的按鈕項目。
role: Architect, Developer, Admin, User
exl-id: b144e8d1-1097-475d-b2eb-3353c176afb9
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---


# 電子郵件按鈕元件 {#email-button-component}

「電子郵件按鈕」元件可讓您設定並顯示內容中的按鈕項目。

## 使用狀況 {#usage}

「電子郵件按鈕」元件可讓內容中包含按鈕，可由內容讀取器點選，並連結至其他資源。

* 您可以在 [配置對話框。](#configure-dialog)
* 您可以在 [設計對話方塊。](#design-dialog)

## 版本與相容性 {#version-and-compatibility}

電子郵件按鈕元件的目前版本為v1，此版本於2022年10月隨電子郵件核心元件第x版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | - |

如需核心元件版本和版本的詳細資訊，請參閱本檔案 [電子郵件核心元件版本。](/help/email/versions.md)

## 技術詳細資訊 {#technical-details}

電子郵件按鈕元件的最新技術檔案 [可在GitHub上找到。](https://adobe.com/go/aem_cmp_tech_email_button_v1)

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案。](/help/developing/overview.md)

## 配置對話框 {#configure-dialog}

「設定」對話方塊可讓內容作者定義按鈕及其運作方式，並供內容的讀者使用。

### 屬性標籤 {#properties-tab}

![按鈕元件的編輯對話框的屬性頁簽](/help/email/assets/email-button-edit-properties.png)

* **文字**  — 要在按鈕上顯示的文字
   * 按一下促銷活動圖示以開啟 [選取Adobe Campaign變數](/help/email/campaign-variables.md) 對話方塊，從Adobe Campaign插入動態內容。
* **連結**  — 連結至AEM、外部資源或錨點內的內容頁面
   * 使用 **選擇對話框** 來選擇AEM內的路徑。
   * 按一下促銷活動圖示以開啟 [選取Adobe Campaign變數](/help/email/campaign-variables.md) 對話方塊，從Adobe Campaign插入動態內容。
* **圖示**  — 在按鈕中顯示圖示的識別碼
* **ID**  — 此選項可控制HTML中元件的唯一標識符。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查產生的內容來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會對CSS造成影響。
* **在新索引標籤中開啟連結**  — 若勾選此選項，連結將會在新的瀏覽器索引標籤中開啟。

### 協助工具標籤 {#accessibility-tab}

![按鈕元件的編輯對話方塊的協助工具索引標籤](/help/email/assets/email-button-edit-accessibility.png)

在 **協助工具** 索引標籤中，可為 [ARIA協助工具](https://www.w3.org/WAI/standards-guidelines/aria/) 元件的標籤。

* **標籤**  — 元件的ARIA標籤屬性值

### 樣式標籤 {#styles-tab-edit}

電子郵件按鈕元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling).

使用下拉式清單選取您要套用至元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須針對此元件在 [設計對話](#design-dialog) 讓索引標籤可用。

## 設計對話方塊 {#design-dialog}

### 樣式標籤 {#styles-tab}

電子郵件按鈕元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).
