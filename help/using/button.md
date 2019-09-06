---
title: 按鈕元件
seo-title: 按鈕元件
description: 'null'
seo-description: 核心元件按鈕元件可讓您建立和顯示按鈕。
uuid: ec807de9-f76 c-4850-9ee-c3 e439 a1 d626
contentOwner: 使用者
content-type: 引用
topic-tags: 製作
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: f093f58e-9755-4a4f-803a-ab93 a50 e6870
translation-type: tm+mt
source-git-commit: d37cde072dea612ccb55ad31b4aaf42f17839cb4

---


# 按鈕元件{#button-component}

核心元件按鈕元件可讓您在頁面上設定和顯示按鈕項目。

## 使用狀況 {#usage}

核心元件按鈕元件可讓您加入頁面上的按鈕。

* 您可以在 [設定對話方塊](#configure-dialog)中選取按鈕的屬性。
* 按鈕元件的樣式可在 [設計對話方塊中定義](#design-dialog)。

## 版本與相容性 {#version-and-compatibility}

目前版本的Button元件是v1，是在2019年月發行的版本2.5.0推出的v1，本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|--- |--- |--- |---|
| v1 | 相容相容性 | 相容相容性 | 相容相容性 |

如需核心元件版本和版本的詳細資訊，請參閱文件 [核心元件版本](versions.md)。

## 元件輸出範例 {#sample-component-output}

若要體驗Button元件，以及查看其組態選項以及HTML和JSON輸出的範例，請造訪 [元件庫](http://opensource.adobe.com/aem-core-wcm-components/library/button.html)。

## 技術細節 {#technical-details}

有關按鈕元件 [的最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/button/v1/button)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者定義按鈕，以及該按鈕對頁面的行為和顯示方式。

### 屬性索引標籤 {#properties-tab}

![](assets/screen-shot-2019-08-29-12.19.32.png)

* **文字** -要在按鈕上顯示的文字
* **連結** -連結至AEM內內容頁面、外部資源或錨點
   * 使用 **「選擇對話方塊** 」，在AEM中選擇路徑。
* **圖示** -在按鈕中顯示圖示的識別碼

### 協助工具標籤 {#accessibility-tab}

![](assets/screen-shot-2019-08-29-12.19.43.png)

在 **「協助工具** 」索引標籤上，可為元件設定 [AIA協助工具](https://www.w3.org/WAI/standards-guidelines/aria/) 標籤的值。

* **標籤** -元件的AIA標籤屬性值

## 設計對話方塊 {#design-dialog}

### 樣式標籤 {#styles-tab}

Image Component支援AEM [Style System](authoring.md#component-styling)。
