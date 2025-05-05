---
title: 最適化Forms核心元件 — 頁首
description: 使用或自訂最適化Forms頁首核心元件。
role: Architect, Developer, Admin, User
exl-id: aa18def9-0bec-4475-8dde-213860621ef5
source-git-commit: 732efc9ed450aa31078ecaad65c0c306679fe97e
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 1%

---

# 頁首 {#header-adaptive-forms-core-component}

調適型表單中的頁首元件是表單頂端的區段，通常包含表單的標題、標誌或名稱。 標題也可以包含其他資訊，例如表單用途的簡短說明、建立表單的組織名稱，或表單相關說明的聯絡資訊。 標題可用來讓使用者概略瞭解表單，並為他們要填寫的資訊提供上下文。 它可用來協助使用者瞭解表單的用途以及如何正確填寫。

**範例**

![範例](/help/adaptive-forms/assets/header.png)

## 使用情況 {#reasons-to-use-header}

- **品牌**：頁首可用來顯示建立表單之組織的標誌或名稱，有助於建立品牌認知度和可信度。

- **內容**：標題可提供表單用途的簡短說明，以協助使用者瞭解正在使用表單的內容。

- **導覽**：標題可以包含連結或按鈕，讓使用者可以導覽至網站或應用程式的其他部分。

- **資訊**：標題可以包含連絡資訊或協助資源的連結，讓使用者在需要時更容易取得協助。

- **使用者體驗**：標題可讓使用者以清楚且直覺的方式存取及填寫表單欄位，讓表單更人性化。

## 版本和相容性 {#version-and-compatibility}

最適化Forms標題核心元件於2023年2月發行，屬於Cloud Service核心元件2.0.4以及適用於AEM 6.5.16.0 Forms或更新版本的核心元件1.1.12的一部分。 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service  | AEM 6.5.16.0 Forms或更新版本 |
|---|---|---|
| v1 | 與<br>[版本2.0.4](/help/adaptive-forms/version.md)和更新版本相容 | 與<br>[版本1.1.12](/help/adaptive-forms/version.md)及更新版本相容，但小於2.0.0。 |

如需核心元件版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)檔案。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion_tw). -->

## 技術細節 {#technical-details}

在[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/pageheader/v1/pageheader)的技術檔案中取得最適化Forms標題核心元件的最新資訊。 如需開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 設定對話方塊 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的標題體驗。 您也可以輕鬆定義標題選項，以提供順暢的使用者體驗。

### 影像標籤 {#image-tab}

頁首的這個部分包含頁首標題和影像。

![影像標籤](/help/adaptive-forms/assets/header_image.png)

- **影像資產** — 此選項允許以滑鼠拖放方式放置影像等資產。 您也可以使用&#x200B;**瀏覽**&#x200B;按鈕，從本機檔案系統上傳檔案。 新增影像後，影像底部會顯示三個按鈕。 新增影像後，影像底部會顯示三個按鈕：
   - **編輯** — 點選或按一下「**編輯**」，在Assets編輯器中管理資產的轉譯。
   - **清除** — 點選或按一下&#x200B;**清除**&#x200B;以取消選取目前選取的影像。
   - **挑選** — 點選或按一下&#x200B;**挑選**&#x200B;選項，從Assets資料夾中選取其他影像。

- **標題** — 此選項用於將標題新增至標題。 預先定義的文字會包含在對話方塊中，而且使用者可以修改它。
- **連結至** — 您可以使用&#x200B;**瀏覽**&#x200B;圖示將標題連結至資料夾。
- **描述** — 描述是簡短文字說明，提供特定影像用途的其他資訊或說明。
- **大小（畫素）** — 增加或減少畫素，有助於調整影像的長度和寬度。

![accessibilitytab](/help/adaptive-forms/assets/header_accessibility.png)

- **替代文字** — 此選項用於輸入文字，為影像提供簡短且描述性的替代文字，向視障使用者說明影像。

- **影像為裝飾性** — 檢查輔助技術是否應忽略影像，因此不需要替代文字。 這僅適用於裝飾性影像。

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
