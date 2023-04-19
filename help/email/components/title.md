---
title: 電子郵件標題元件
description: 電子郵件標題元件是您電子郵件的區段標題元件，可就地編輯。
role: Architect, Developer, Admin, User
exl-id: f65b6973-bb36-406f-bbea-f85a23f5340b
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 1%

---


# 電子郵件標題元件 {#email-title-component}

電子郵件標題元件是您電子郵件的區段標題元件，可就地編輯。

## 使用狀況 {#usage}

「電子郵件標題元件」可作為電子郵件區段的標題或標題。

* 可用的標題層級可由範本作者在 [設計對話方塊。](#design-dialog)
* 內容作者可從 [編輯對話框。](#edit-dialog)

為方便起見，您也可以輕鬆就地編輯標題文字。

## 版本與相容性 {#version-and-compatibility}

電子郵件標題元件的目前版本為v1，已於2022年10月隨電子郵件核心元件第x版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | - |

如需核心元件版本和版本的詳細資訊，請參閱本檔案 [核心電子郵件元件版本](/help/versions.md).

### 技術詳細資訊 {#technical-details}

標題元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_email_title_v1).

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者定義標題文字並選取標題層級。

* **標題**  — 如果空白，則會使用頁面標題
   * 按一下促銷活動圖示以開啟 [選取Adobe Campaign變數](/help/email/campaign-variables.md) 對話方塊，從Adobe Campaign插入動態內容。
* **類型/大小**  — 定義標題的標題層
* **連結**  — 定義標題將連結的內容。 這可以是內容頁面、外部URL或頁面錨點的路徑。
   * 按一下促銷活動圖示以開啟 [選取Adobe Campaign變數](/help/email/campaign-variables.md) 對話方塊，從Adobe Campaign插入動態內容。
* **ID**  — 此選項可控制HTML中元件的唯一標識符。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會對CSS造成影響。

![電子郵件標題元件的編輯對話方塊](/help/email/assets/email-title-edit.png)

就地編輯器也可用來編輯標題元件的文字。

![就地編輯電子郵件標題元件](/help/email/assets/email-title-edit-inline.png)

### 樣式標籤 {#styles-tab-edit}

電子郵件標題元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉式清單選取您要套用至元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須針對此元件在 [設計對話](#design-dialog) 讓下拉式功能表可供使用。

![標題元件的編輯對話框的樣式頁簽](/help/email/assets/email-title-edit-styles.png)

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義內容作者建立時標題元件將具備的預設標題層級。

### 「大小」頁簽 {#sizes-tab}

![標題元件的設計對話框](/help/email/assets/email-title-design.png)

* **作者的允許類型/大小**  — 啟用或停用內容作者使用電子郵件標題元件時可用的標題類型。
* **預設類型/大小**  — 定義內容作者將電子郵件標題元件新增至頁面時，將自動指派的標題類型。
* **停用連結**  — 停用「電子郵件標題」元件中連結的支援，以禁止內容作者從標題連結。

### 樣式標籤 {#styles-tab}

電子郵件標題元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).
