---
title: 最適化Forms核心元件 — 頁首
description: 使用或自訂最適化Forms頁首核心元件。
role: Architect, Developer, Admin, User
exl-id: aa18def9-0bec-4475-8dde-213860621ef5
source-git-commit: 7888cfa0f1358ce8018fc1e3cc3b19eb66a82b9d
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 1%

---

# 頁首 {#header-adaptive-forms-core-component}

調適型表單中的頁首元件是表單頂端的區段，通常包含表單的標題、標誌或名稱。 頁首也可包含其他資訊，例如表單用途的簡短說明、建立表單的組織名稱，或表單相關說明的聯絡資訊。 標題是用來為使用者提供表單的概觀，並提供他們要填寫的資訊的前後關聯。 它可用來協助使用者瞭解表單的用途以及如何正確填寫。

**範例**

![](/help/adaptive-forms/assets/header.png)

## 使用狀況 {#reasons-to-use-header}

* **品牌化**：標題可用來顯示建立表單的組織的標誌或名稱，有助於建立品牌認知度和可信度。

* **內容**：標題可提供表單用途的簡短說明，協助使用者瞭解使用表單的上下文。

* **導覽**：標題可包含連結或按鈕，讓使用者導覽至網站或應用程式的其他部分。

* **資訊**：標題可包含聯絡資訊或說明資源的連結，讓使用者更容易在需要時獲得協助。

* **使用者體驗**：標題可讓使用者透過清晰且直覺的方式存取及填寫表單欄位，進而讓表單更人性化。

## 版本和相容性 {#version-and-compatibility}

Adaptive Forms摺疊式功能表核心元件於2023年2月發行，屬於AEM 6.5.16.0 Forms或更新版本適用的Cloud Service核心元件2.0.4和核心元件1.1.12的一部分。 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service  | AEM 6.5.16.0 Forms或更新版本 |
|---|---|---|
| v1 | 相容於<br>[版本2.0.4](/help/adaptive-forms/version.md) 和更新版本 | 相容於<br>[第1.1.12發行版本](/help/adaptive-forms/version.md) 和更新版本，但低於2.0.0。 |

如需核心元件版本和發行版本的詳細資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 檔案。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## 技術細節 {#technical-details}

在以下位置的技術檔案中取得最適化Forms標題核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/pageheader/v1/pageheader). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

您可以使用「設定」對話方塊輕鬆自訂訪客的標題體驗。 您也可以輕鬆定義標題選項，以提供順暢的使用者體驗。

### 影像標籤 {#image-tab}

標頭的這個部分包含標頭標題和影像。

![影像標籤](/help/adaptive-forms/assets/header_image.png)

* **影像資產**  — 此選項可讓您使用滑鼠拖放功能拖放影像等資產。 您也可以使用 **瀏覽** 按鈕。 新增影像後，三個按鈕會出現在影像底部。 新增影像後，影像底部會顯示三個按鈕：
   * **編輯**  — 點選或按一下 **編輯** 在「資產編輯器」中管理資產的轉譯。
   * **清除**  — 點選或按一下 **清除** 以取消選取目前選取的影像。
   * **選取**  — 點選或按一下 **選取**  從「資產」資料夾中選取其他影像的選項。

* **標題**  — 此選項用於將標題新增到標題。 預先定義的文字會包含在對話方塊中，且使用者可加以修改。
* **連結至**  — 您可以使用將標題連結至資料夾 **瀏覽** 圖示。
* **說明**  — 說明是簡短文字說明，提供有關特定影像用途的其他資訊或說明。
* **大小（畫素）**  — 增加或減少畫素，有助於調整影像的長度和寬度。

![accessibilitytab](/help/adaptive-forms/assets/header_accessibility.png)

* **替代文字**  — 此選項用於輸入提供影像的簡短描述性替代文字的文字，向視障使用者說明影像。

* **裝飾性影像**  — 檢查輔助技術是否應忽略影像，因此不需要替代文字。 這僅適用於裝飾性影像。

### 文字索引標籤 {#text-tab}

此區段允許輸入要包含在標頭中的文字。

## 相關文章 {#related-article}

* [在AEM Sites頁面或體驗片段中建立最適化表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html)

* [建立獨立的最適化表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)
