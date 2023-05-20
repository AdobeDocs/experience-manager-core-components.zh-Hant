---
title: 自適應Forms核心元件 — 標題
description: 使用或自定義自適應Forms頭核心元件。
role: Architect, Developer, Admin, User
exl-id: aa18def9-0bec-4475-8dde-213860621ef5
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 1%

---

# 頁首 {#header-adaptive-forms-core-component}

自適應表單中的標題元件是表單頂部的一個部分，通常包含表單的標題、徽標或名稱。 題頭還可以包括其他資訊，如表單用途的簡要說明、建立表單的組織名稱，或幫助表單的聯繫資訊。 標題用於向用戶提供表單的概述，並提供要填寫的資訊的上下文。 它用於幫助用戶理解表單的目的以及如何正確填寫表單。

**範例**

![](/help/adaptive-forms/assets/header.png)

## 使用狀況 {#reasons-to-use-header}

* **品牌**:標題可用於顯示建立表單的組織的徽標或名稱，有助於建立品牌認可和信譽。

* **上下文**:標題可以提供表單用途的簡要說明，幫助用戶瞭解使用表單的上下文。

* **導航**:標題可以包括允許用戶導航到網站或應用程式的其他部分的連結或按鈕。

* **資訊**:標題可以包括聯繫資訊或幫助資源的連結，使用戶在需要時更容易獲得幫助。

* **用戶體驗**:通過為用戶提供訪問和填寫表單欄位的清晰直觀的方式，可以使用標題來使表單更加用戶友好。

## 版本和相容性 {#version-and-compatibility}

自適應Forms手風琴核心元件於2023年2月發佈，作為用於Cloud Service的核心元件2.0.4的一部分，以及用於Forms或更晚版本的核心元件1.1.12的核心元件6.5.16.0的一部分。 下面是一個表，其中顯示了所有支援的版本AEM、相容性以及指向相應文檔的連結：

| 元件版本 | AEM as a Cloud Service  | AEM6.5.16.0Forms |
|---|---|---|
| v1 | 相容<br>[發行版2.0.4](/help/adaptive-forms/version.md) 之後 | 相容<br>[發行版1.1.12](/help/adaptive-forms/version.md) 晚但小於2.0.0。 |

有關核心元件版本和版本的資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 的子菜單。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## 技術詳細資訊 {#technical-details}

獲取有關自適應Forms標頭核心元件的最新資訊，請參閱 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/pageheader/v1/pageheader)。 有關開發核心元件的詳細資訊，請查看 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

通過「配置」對話框，您可以輕鬆自定義訪問者的頁眉體驗。 您還可以輕鬆定義標題選項，以獲得無縫的用戶體驗。

### 影像頁籤 {#image-tab}

標題的這一部分包含標題標題和影像。

![影像頁籤](/help/adaptive-forms/assets/header_image.png)

* **影像資產**  — 此選項允許使用滑鼠拖放來放置資產，如影像。 您還可以使用 **瀏覽** 按鈕 添加影像後，影像底部會出現三個按鈕。 添加影像後，影像底部會出現三個按鈕：
   * **編輯**  — 點擊或按一下 **編輯** 以在「資產編輯器」中管理資產的格式副本。
   * **清除**  — 點擊或按一下 **清除** 來取消選擇當前選定的映像。
   * **選擇**  — 點擊或按一下 **選擇**  選項從「資產」資料夾中選擇另一個影像。

* **標題**  — 此選項用於將標題添加到標題。 預定義文本包含在對話框中，用戶可以修改它。
* **連結至**  — 您可以使用 **瀏覽** 表徵圖
* **說明**  — 說明是簡短的文本說明，提供有關特定影像用途的其他資訊或說明。
* **大小(px)**  — 它通過增加或減少像素來幫助調整影像的長度和寬度。

![訪問性頁籤](/help/adaptive-forms/assets/header_accessibility.png)

* **備選文本**  — 此選項用於輸入文本，該文本為影像提供了簡短和描述性的文本選項，用於向視障用戶描述影像。

* **影像是裝飾性的**  — 檢查影像是否應被輔助技術忽略，因此不需要替代文本。 這僅適用於裝飾性影像。

### 文本頁籤 {#text-tab}

此部分允許輸入要包含在標題中的文本。

