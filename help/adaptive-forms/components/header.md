---
title: 適用性Forms核心元件 — 標題
description: 使用或自訂適用性Forms標題核心元件。
role: Architect, Developer, Admin, User
exl-id: aa18def9-0bec-4475-8dde-213860621ef5
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 1%

---

# 頁首 {#header-adaptive-forms-core-component}

適用性表單中的標題元件是表單頂端的區段，通常包含表單的標題、標誌或名稱。 標題也可包含其他資訊，例如表單用途的簡短說明、建立表單的組織名稱，或表單相關說明的聯絡資訊。 標題可讓使用者概略了解表單，並提供要填寫的資訊的內容。 它可協助使用者了解表單的用途以及如何正確填寫。

**範例**

![](/help/adaptive-forms/assets/header.png)

## 使用狀況 {#reasons-to-use-header}

* **品牌推廣**:標題可用來顯示建立表單之組織的標誌或名稱，有助於建立品牌認可度和信譽。

* **內容**:標題可提供表單用途的簡短說明，協助使用者了解使用表單的內容。

* **導覽**:標題可以包括允許用戶導航到網站或應用程式的其他部分的連結或按鈕。

* **資訊**:標題可包含連絡資訊或協助資源的連結，讓使用者在有需要時更容易取得協助。

* **使用者體驗**:標題可讓使用者以清楚且直覺的方式存取和填寫表單欄位，讓表單更方便使用。

## 版本與相容性 {#version-and-compatibility}

適用性Forms折疊式功能表核心元件已於2023年2月發行，作為Cloud Service核心元件2.0.4的一部分，以及AEM 6.5.16.0 Forms或更新版本核心元件1.1.12的一部分。 下表顯示所有支援的版本、AEM相容性，以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service  | AEM 6.5.16.0 Forms或更新版本 |
|---|---|---|
| v1 | 相容於<br>[版本2.0.4](/help/adaptive-forms/version.md) 和 | 相容於<br>[版本1.1.12](/help/adaptive-forms/version.md) 和2.0.0以下的。 |

如需核心元件版本和版本的相關資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 檔案。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## 技術詳細資訊 {#technical-details}

取得下列主題的技術檔案中適用性Forms標題核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/pageheader/v1/pageheader). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 配置對話框 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的頁首體驗。 您也可以輕鬆定義標題選項，以提供順暢的使用者體驗。

### 影像標籤 {#image-tab}

標題的這一部分包含標題和影像。

![Imagetab](/help/adaptive-forms/assets/header_image.png)

* **影像資產**  — 此選項可讓您拖放滑鼠，拖放影像等資產。 您也可以使用 **瀏覽** 按鈕。 新增影像後，三個按鈕會顯示在影像底部。 新增影像後，影像底部會顯示三個按鈕：
   * **編輯**  — 點選或按一下 **編輯** 在「資產編輯器」中管理資產的轉譯。
   * **清除**  — 點選或按一下 **清除** 以取消選取目前選取的影像。
   * **挑選**  — 點選或按一下 **挑選**  選項，從「資產」資料夾選取其他影像。

* **標題**  — 此選項可用來將標題新增至標題。 預定義文本包含在對話框中，用戶可以修改它。
* **連結至**  — 您可以使用 **瀏覽** 表徵圖。
* **說明**  — 說明是簡短的文本說明，提供有關特定影像用途的其他資訊或說明。
* **大小(px)**  — 通過增加或減少像素，它有助於調整影像的長度和寬度。

![accessibilitytab](/help/adaptive-forms/assets/header_accessibility.png)

* **替代文字**  — 此選項用於輸入文本，該文本為影像提供簡短的描述性文本替代項，該替代項向視障用戶描述影像。

* **影像是裝飾**  — 檢查輔助技術是否應忽略影像，因此不需要替代文字。 這僅適用於裝飾影像。

### 文字索引標籤 {#text-tab}

此部分允許輸入要包含在標題中的文本。

