---
title: 最適化Forms核心元件 — 頁尾
description: 使用或自訂最適化Forms頁尾核心元件。
role: Architect, Developer, Admin, User
exl-id: c8e7d3fe-4b82-4a80-8da2-19f6cff1e3e9
source-git-commit: be630c4d0a10ebaa679b77419b901fac818addb1
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 5%

---

# 頁尾 {#footer-adaptive-forms-core-component}

最適化表單中的頁尾元件是通常出現在表單底部的區域，並包含版權宣告、相關資源連結或聯絡資訊等資訊。 頁尾可提供額外資訊（例如上次更新的日期），對有協助工具需求的使用者有利。

**範例**

![](/help/adaptive-forms/assets/footer.png)

## 使用狀況 {#reasons-to-use-footer}

以表單形式加入頁尾元件有幾個好處，包括：

* **法律要求**：包含免責宣告、版權宣告或其他法律資訊可能需要一些表單。 頁尾是加入這項資訊的便利地方。

* **導覽**：頁尾可提供網站上其他重要頁面的連結，例如隱私權政策、服務條款或聯絡頁面。

* **品牌化**：頁尾可用來包含標誌或其他品牌要素，有助於強化組織或網站的身分。

* **一致性**：頁尾可讓表單的設計和版面保持一致，讓使用者導覽時更直覺且容易。

* **其他內容**：頁尾可為表單提供其他內容，例如說明表單的文字或相關資源的連結，讓表單更具資訊量且方便使用。

## 版本和相容性 {#version-and-compatibility}

最適化Forms摺疊式功能表核心元件於2023年2月發行，屬於AEM 6.5.16.0 Forms或更新版本適用的Cloud Service核心元件2.0.4和核心元件1.1.12的一部分。 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service  | AEM 6.5.16.0 Forms或更新版本 |
|---|---|---|
| v1 | 相容於<br>[版本2.0.4](/help/adaptive-forms/version.md) 及更新版本 | 相容於<br>[第1.1.12發行版本](/help/adaptive-forms/version.md) 和較新版本，但小於2.0.0。 |

如需核心元件版本的詳細資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 檔案。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術細節 {#technical-details}

在的技術檔案中取得最適化Forms頁尾核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/footer/v1/footer). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).


## 設定對話方塊 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的頁尾體驗。 您也可以輕鬆定義頁尾選項，提供順暢的使用者體驗。

![屬性標籤](/help/adaptive-forms/assets/footer_propertiestab.png)

* **編輯對話方塊**
「編輯」對話方塊提供標準的RTF格式工具，讓使用者可以為頁尾建立文字。

* **粗體**  — 此選項會將粗體格式套用至選取的文字，或套用粗體格式在游標後輸入的文字。 `Ctrl+B` 是鍵盤快速鍵。

* **斜體**  — 此選項會將斜體格式套用至選取的文字，或將游標之後輸入的文字套用斜體格式。 `Ctrl+I` 是鍵盤快速鍵。

![專案符號選項](/help/adaptive-forms/assets/footer_bullet.png)


* **項目符號**

   * **專案符號圖示**  — 它會將選取的文字格式化為專案符號清單，或在游標之後開始插入專案符號清單。 若要結束專案符號清單，請再次點選或按一下「專案符號」按鈕，或輸入兩個歸位字元。

   * **編號清單圖示**  — 將選取文字格式化為編號清單，或在游標後開始插入編號清單。 若要結束編號清單，請再次點選或按一下「編號」按鈕或輸入兩個歸位字元。

   * **「減少縮排」圖示**  — 會減少所選文字的縮排層級，或在游標之後輸入的文字。 只有當選取的文字或游標位置已經縮排時，才為作用中。

   * **縮排圖示**  — 它會增加所選文字的縮排層級，或在游標之後輸入的文字。

![超連結選項](/help/adaptive-forms/assets/footer_link.png)

* **超連結**

   * **路徑**  — 輸入路徑
      1. 使用「開啟選取範圍」對話方塊在AEM中選擇路徑。
      1. 如果連結不在AEM內，請輸入絕對URL。
      1. 非絕對路徑會解譯為相對於AEM。

   * **替代文字**  — 輸入連結的替代描述文字。

   * **Target**  — 選取連結行為
      * 目標
      * 相同索引標籤
      * 新索引標籤
      * 父框架
      * 上框架

   * **取消連結圖示**  — 此選項會移除已套用至所選文字的連結。 只有在已選取連結時，此選項才會啟用。

   * **段落格式圖示**  — 此選項可讓您將段落格式套用至選取的文字。 它也可以協助您格式化在游標後插入的文字。 它會定義標題的標題層級。

* **ID**：此選項可讓您控制HTML和資料層中元件的唯一識別碼。

   * 如果保留為空白，系統會自動為您產生唯一ID *，您可在檢查結果頁面時找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->


>[!MORELIKETHIS]
>
>* [折疊式面板](/help/adaptive-forms/components/accordion.md)
>* [按鈕](/help/adaptive-forms/components/button.md)
>* [核取方塊群組](/help/adaptive-forms/components/checkbox-group.md)
>* [日期挑選器](/help/adaptive-forms/components/date-picker.md)
>* [下拉式清單](/help/adaptive-forms/components/drop-down.md)
>* [電子郵件輸入](/help/adaptive-forms/components/email-input.md)
>* [來自容器](/help/adaptive-forms/components/form-container.md)
>* [檔案附件](/help/adaptive-forms/components/file-attachment.md)
>* [頁首](/help/adaptive-forms/components/header.md)
>* [水準索引標籤](/help/adaptive-forms/components/horizontal-tabs.md)
>* [影像](/help/adaptive-forms/components/image.md)
>* [數字輸入](/help/adaptive-forms/components/number-input.md)
>* [面板容器](/help/adaptive-forms/components/panel-container.md)
>* [選項按鈕](/help/adaptive-forms/components/radio-button.md)
>* [重設按鈕](/help/adaptive-forms/components/reset-button.md)
>* [提交按鈕](/help/adaptive-forms/components/submit-button.md)
>* [電話輸入](/help/adaptive-forms/components/telephone-input.md)
>* [文字輸入](/help/adaptive-forms/components/text-input.md)
>* [文字](/help/adaptive-forms/components/text.md)
>* [標題](/help/adaptive-forms/components/title.md)
>* [精靈](/help/adaptive-forms/components/wizard.md)


## 另請參閱 {#see-also}

{{see-also}}