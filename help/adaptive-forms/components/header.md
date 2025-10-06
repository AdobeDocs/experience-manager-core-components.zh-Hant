---
title: 自適應表單核心元件 - 頁首
description: 使用或自訂自適應表單頁首核心元件。
role: Architect, Developer, Admin, User
exl-id: aa18def9-0bec-4475-8dde-213860621ef5
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: ht
source-wordcount: '672'
ht-degree: 100%

---


# 頁首 {#header-adaptive-forms-core-component}

自適應表單中的頁首元件是表單頂端的區段，通常包含表單的標題、標誌或名稱。頁首也可以包含其他資訊，例如表單用途的簡短說明、建立表單的組織名稱，或表單相關說明的聯絡資訊。頁首可用來讓使用者概略了解表單，並為其要填寫的資訊提供內容背景。它可用來協助使用者了解表單的用途以及如何正確填寫。

{{traditional-aem}}

**範例**

![範例](/help/adaptive-forms/assets/header.png)

## 用途 {#reasons-to-use-header}

- **品牌化**：頁首可用來顯示建立表單之組織的標誌或名稱，有助於建立品牌認知度和可信度。

- **內容**：頁首可提供表單用途的簡短說明，以協助使用者了解正在使用表單的內容。

- **導覽**：頁首可以包含連結或按鈕，讓使用者可以導覽至網站或應用程式的其他部分。

- **資訊**：頁首可以包含聯絡資訊或說明資源的連結，讓使用者在需要時更容易取得協助。

- **使用者體驗**：透過頁首，可讓使用者以清晰直觀的方式存取及填寫表單欄位，使表單更加易於使用。

## 版本和相容性 {#version-and-compatibility}

自適應表單頁首核心元件於 2023 年 2 月發行，屬於 Cloud Service 核心元件 2.0.4 和 AEM 6.5.16.0 Forms 或更新版本的核心元件 1.1.12 的一部分。下表顯示所有支援版本、AEM 相容性以及對應文件的連結：

| 元件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更新版本 |
|---|---|---|
| v1 | 與<br>[ 2.0.4 版](/help/adaptive-forms/version.md)及更新版本相容 | 與<br>[ 1.1.12 版](/help/adaptive-forms/version.md)及更新版本相容，但低於 2.0.0 版。 |

如需「核心元件」版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)文件。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion_tw). -->

## 技術詳細資訊 {#technical-details}

[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/pageheader/v1/pageheader) 的技術文件中可找到自適應表單頁首核心元件的最新資訊。如需開發核心元件的更多資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

透過設定對話框，您可以輕鬆自訂訪客的頁首體驗。同樣能夠輕鬆定義頁首選項，以提供順暢無礙的使用者體驗。

### 影像索引標籤 {#image-tab}

頁首的這個部分包含頁首標題和影像。

![影像索引標籤](/help/adaptive-forms/assets/header_image.png)

- **影像資產** - 此選項允許以滑鼠拖放方式放置影像等資產。您也可以使用&#x200B;**瀏覽**&#x200B;按鈕，從本機檔案系統上傳檔案。新增影像後，影像底部會顯示三個按鈕。新增影像後，影像底部會顯示三個按鈕：
   - **編輯** - 點選或按一下&#x200B;**「編輯」**，以在「資產編輯器」中管理資產的轉譯。
   - **清除** - 點選或按一下&#x200B;**「清除」**，取消選取目前選取的影像。
   - **挑選** - 點選或按一下&#x200B;**挑選**&#x200B;選項，從資產資料夾中選取其他影像。

- **標題** - 此選項用於將標題新增至頁首。預先定義的文字會包含在對話框中，使用者可自行修改。
- **連結至** - 您可以使用 **瀏覽** 圖示將標題連結至資料夾。
- **說明** - 說明是簡短文字說明，提供特定影像用途的其他資訊或說明。
- **大小 (像素)** - 透過增加或減少像素，有助於調整影像的長度和寬度。

![協助工具索引標籤](/help/adaptive-forms/assets/header_accessibility.png)

- **替代文字** - 此選項用於輸入為影像提供簡短且具描述性的替代文字，以向視障使用者說明影像內容。

- **影像為裝飾性** - 若輔助技術可忽略影像，因此不需要替代文字時，請勾選此選項。這僅適用於裝飾性影像。

### 文字索引標籤 {#text-tab}

此區段允許輸入要包含在頁首中的文字。

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=zh-Hant)

-->

## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}
