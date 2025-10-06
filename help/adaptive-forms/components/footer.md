---
title: 自適應表單核心元件 - 頁尾
description: 使用或自訂自適應表單頁尾核心元件。
role: Architect, Developer, Admin, User
exl-id: c8e7d3fe-4b82-4a80-8da2-19f6cff1e3e9
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: ht
source-wordcount: '767'
ht-degree: 100%

---


# 頁尾 {#footer-adaptive-forms-core-component}

自適應表單中的頁尾元件是通常出現在表單底部的區域，並包含版權聲明、相關資源連結或聯絡資訊等資訊。頁尾可提供額外資訊 (例如上次更新日期)，對有協助工具需求的使用者很有幫助。

{{traditional-aem}}

**範例**

![範例](/help/adaptive-forms/assets/footer.png)

## 用途 {#reasons-to-use-footer}

在表單中加入頁尾元件有多項好處，包括：

- **法律要求**：某些表格可能需要包含免責聲明、版權聲明或其他法律資訊。頁尾是放置此類資訊的便利位置。

- **導覽**：頁尾可在網站上提供其他重要頁面的連結，例如隱私權政策、服務條款或聯絡頁面。

- **品牌化**：頁尾可用來放置標誌或其他品牌元素，有助於強化組織或網站的身分。

- **一致性**：頁尾可為表單的設計和版面提供一致性，讓使用者可以更輕鬆直覺地瀏覽。

- **其他內容**：頁尾可為表單提供其他內容，例如說明表單的文字或相關資源的連結，讓表單更具資訊性和使用便利性。

## 版本和相容性 {#version-and-compatibility}

自適應表單頁尾核心元件於 2023 年 2 月發行，屬於 Cloud Service 核心元件 2.0.4 和 AEM 6.5.16.0 Forms 或更新版本的核心元件 1.1.12 的一部分。下表顯示所有支援版本、AEM 相容性以及對應文件的連結：

| 元件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更新版本 |
|---|---|---|
| v1 | 與<br>[ 2.0.4 版](/help/adaptive-forms/version.md)及更新版本相容 | 與<br>[ 1.1.12 版](/help/adaptive-forms/version.md)及更新版本相容，但低於 2.0.0 版。 |

如需「核心元件」版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)文件。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術詳細資訊 {#technical-details}

[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/footer/v1/footer) 的技術文件中可找到自適應表單頁尾核心元件的最新資訊。如需開發核心元件的更多資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。


## 設定對話框 {#configure-dialog}

透過設定對話框，您可以輕鬆自訂訪客的頁尾體驗。同樣能夠輕鬆定義頁尾選項，以提供順暢無礙的使用者體驗。

![屬性索引標籤](/help/adaptive-forms/assets/footer_propertiestab.png)

- **編輯對話框**
編輯對話框提供標準 RTF 文字格式化工具，可讓使用者建立頁尾文字。

- **粗體** - 此選項會將粗體格式套用至選取的文字，或將游標後方輸入的文字設定為粗體格式。`Ctrl+B` 是鍵盤快速鍵。

- **斜體** - 此選項會將斜體格式套用至選取的文字，或將游標後方輸入的文字設定為斜體。`Ctrl+I` 是鍵盤快速鍵。

![項目符號選項](/help/adaptive-forms/assets/footer_bullet.png)


- **項目符號**

   - **項目符號圖示** - 它會將選取的文字格式化為項目符號清單，或在游標之後開始插入項目符號清單。若要結束項目符號清單，請再次點選或按一下「項目符號」按鈕，或輸入兩個歸位字元。

   - **編號清單圖示** - 會將選取的文字格式化為編號清單，或在游標後開始插入編號清單。若要結束編號符號清單，請再次點選或按一下「編號符號」按鈕，或輸入兩個歸位字元。

   - **凸排圖示** - 會減少所選文字或在游標之後輸入的文字的縮排等級。只有當選取的文字或游標位置已經縮排時才會啟用。

   - **縮排圖示** - 它會增加所選文字或在游標之後輸入的文字的縮排等級。

![超連結選項](/help/adaptive-forms/assets/footer_link.png)

- **超連結**

   - **路徑** - 輸入路徑
      1. 使用開啟選取對話框，在 AEM 中選擇路徑。
      1. 如果連結不在 AEM 中，請輸入絕對 URL。
      1. 非絕對路徑會解譯為相對於 AEM。

   - **替代文字** - 輸入連結的替代說明文字。

   - **目標** - 選取連結行為
      - 目標
      - 相同索引標籤
      - 新索引標籤
      - 上層框架
      - 上框架

   - **取消連結圖示** - 此選項會移除已套用至所選取文字的連結。只有在已選取連結時，此選項才會啟用。

   - **段落格式圖示** - 此選項可讓您將段落格式套用至選取的文字。它也可以協助您格式化在游標後插入的文字。它會定義標題的標題層級。

- **ID** - 此選項可讓您控制 HTML 和「資料層」中元件的唯一識別碼。

   - 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   - 若已指定 ID，則作者應確保其為唯一識別碼。
   - 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->

## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}
