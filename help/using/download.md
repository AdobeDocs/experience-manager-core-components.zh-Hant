---
title: 下載元件
seo-title: 下載元件
description: 'null'
seo-description: 核心元件下載元件可讓您在頁面上建立下載選項。
uuid: ec807de9-f76c-4850-9ece-c3e439a1d626
contentOwner: 使用者
content-type: 引用
topic-tags: 編寫
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-新功能
discoiquuid: f093f58e-9755-4a4f-803a-ab93a50e6870
translation-type: tm+mt
source-git-commit: 88bc68b60e5de247fe800ac041ffefdf9238cce1

---


# 下載元件{#download-component}

核心元件下載元件可讓您在頁面上建立下載選項。

## 使用狀況 {#usage}

核心元件下載元件可讓下載選項及其相關資產包含在頁面上。

* 可在「設定」對話方塊中選取下載選項 [的屬性](#configure-dialog)。
* 可在設計對話方塊中定義下載元件的 [預設值](#design-dialog)。

## 版本與相容性 {#version-and-compatibility}

目前的下載元件版本為v1，此版本於2019年6月隨核心元件2.5.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本與版本的詳細資訊，請參閱檔案核 [心元件版本](versions.md)。

## 元件輸出示例 {#sample-component-output}

若要體驗「下載元件」，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪「元件 [庫」](http://opensource.adobe.com/aem-core-wcm-components/library/download.html)。

## 技術詳細資訊 {#technical-details}

有關下載元件的最新技術文 [件可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/download/v1/download)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](developing.md)。

## 配置對話框 {#configure-dialog}

「設定」對話方塊可讓內容作者定義下載項目，以及該項目的行為和顯示方式，讓頁面的訪客檢視。

![](assets/screen-shot-2019-06-17-09.49.14.png)

### 資產標籤 {#asset-tab}

選擇下載資產與「影像元件」的功能非常類似 [](image.md) ，而且也運用了AEM的DAM。

* **下載資產**
   * 從資產瀏覽器中 [拖放資產](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html) ，或點選 **** 瀏覽選項，從本機檔案系統上傳。
   * 點選或按一 **下「清除** 」以取消選取目前選取的影像。
   * 點選或按一 **下「編輯** 」, [](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html) 在資產編輯器中管理資產的轉譯。

### 屬性標籤 {#properties-tab}

![](assets/screen-shot-2019-06-17-09.49.51.png)

* **Title** —— 顯示為下載項目的標題
   * **從DAM資產取得標題** -選取此選項時，標題會自動填入DAM資產的標題。
* **說明** -顯示為下載項目的描述性子標題
   * **從DAM資產取得說明** -選取此選項時，描述會自動填入DAM資產的說明。
* **動作文字** -顯示為下載項目的動作文字
   * 從檔案系統上傳資產時，此欄位為必填欄位。
   * **顯示內嵌** -選取時，提供的 **動作文字將會內嵌顯示** 。

## 設計對話框 {#design-dialog}

設計對話方塊可讓範本作者定義使用下載元件的內容作者可用的選項。

### 屬性標籤 {#properties-tab-design}

![](assets/screen-shot-2019-06-17-10.04.31.png)

* **預設動作文字** -定義作者將「下載元件」新 **** 增至頁面時提供的預設動作文字。
* **允許從檔案系統上傳** -允許內容作者從其本機檔案系統上傳資產作為下載資產。
   * 未選取預設值。
* **Title Type** —— 用於下載元件標題的HTML元素。
   * 如果未選取任何值，則預設值為H3。
* **顯示檔案大小** -選取後，資產的檔案大小會顯示在下載元件中。
   * 選取預設值。
* **顯示檔案格式** -選中後，資產的檔案格式將顯示在下載元件中。
   * 選取預設值。
* **顯示檔案名** -選中後，資產的檔案名將顯示在下載元件中。
   * 選取預設值。

### 樣式標籤 {#styles-tab}

影像元件支援AEM [Style系統](authoring.md#component-styling)。
