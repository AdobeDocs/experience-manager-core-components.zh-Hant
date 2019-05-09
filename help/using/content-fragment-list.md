---
title: 內容片段清單元件
seo-title: 內容片段清單元件
description: 'null'
seo-description: 核心元件內容片段清單元件可讓您顯示內容片段清單。
contentOwner: bohnert
content-type: 引用
topic-tags: 製作
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# 內容片段清單元件{#content-fragment-list-component}

核心元件內容片段清單元件可讓您顯示 [內容片段](https://helpx.adobe.com/experience-manager/6-5/assets/using/content-fragments.html)清單。

## 使用狀況 {#usage}

核心元件內容片段清單元件可讓您根據內容片段模型，在頁面上加入 [內容片段](https://helpx.adobe.com/experience-manager/6-5/assets/using/content-fragments.html) 清單。這對於建立 [無頭內容](https://helpx.adobe.com/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js) 特別有用，因為它可輕鬆地由其他應用程式使用。

* 您可以在 [設定對話方塊中選取清單及其屬性](#configure-dialog)。
* 樣式可套用至 [設計對話方塊](#design-dialog)中的元件。

## 版本與相容性 {#version-and-compatibility}

目前版本的內容片段元件是v1，是在2019年月發行的版本2.4.0推出的，本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|--- |--- |--- |---|
| v1 | 相容相容性 | 相容相容性 | 相容相容性 |

如需核心元件版本和版本的詳細資訊，請參閱文件 [核心元件版本](versions.md)。

## 元件輸出範例 {#sample-component-output}

若要體驗內容片段清單元件，以及查看其組態選項以及HTML和JSON輸出的範例，請造訪 [元件庫](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment-list.html)。

## 技術細節 {#technical-details}

有關內容片段清單元件的 [最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/contentfragmentlist/v1/contentfragmentlist)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者定義哪些內容片段包含要納入其中之片段的清單和元素。

### 屬性索引標籤

**「屬性** 」索引標籤定義了清單中包含的「內容片段」。這主要是根據選取的內容片段模型，但有其他篩選選項可用。

![](assets/screen-shot-2019-05-08-10.47.19.png)

* **模型** -清單所依據之內容片段模型的路徑。
   * 依預設，定義為 **「模型路徑** 」的模型的所有內容片段都會納入清單中。
* **父路徑** -應建立清單的父路徑。
   * 根據選取 **的模型路徑** 來篩選內容片段，將篩選為指定 **的父路徑**上的內容片段。
   * 按一下或點選欄位右側的「 **Open Selection Dialog** 」(開啓選取範圍對話框)按鈕，指定路徑。
* **標記** -只有具有指定標記的內容片段才會包含在清單中。
   * 按一下或點選欄位右側的「 **Open Selection Dialog** 」(開啓選取範圍對話框)按鈕以指定標記。
   * 按一下或點選選取標記旁的X以移除它們。


### 元素標籤

依預設，「內容片段模型」的所有元素都會納入清單中。**「元素** 」可讓您僅指定要包含的特定元素。

![](assets/screen-shot-2019-05-08-10.47.34.png)

* **元素** -只會顯示指定清單中內容片段的元素。
   * 按一下或點選「 **新增** 」按鈕，新增元素
   * 按一下或點選「 **刪除** 」按鈕以移除選取的元素
   * 拖曳 **訂單** 控制代碼以重新排列元素順序。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義套用至內容片段清單元件的樣式。