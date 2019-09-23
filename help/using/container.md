---
title: 容器元件
seo-title: 容器元件
description: 'null'
seo-description: 「核心元件容器」元件可讓您在頁面上建立多個其他元件的容器。
uuid: ec807de9-f76c-4850-9ece-c3e439a1d626
contentOwner: 使用者
content-type: 引用
topic-tags: 編寫
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-新功能
discoiquuid: f093f58e-9755-4a4f-803a-ab93a50e6870
translation-type: tm+mt
source-git-commit: 3e2e7a297c6ee1d6c8d092c619df8febdc900e25

---


# 容器元件{#container-component}

「核心元件容器」元件可讓您在頁面上建立多個其他元件的容器。

## 使用狀況 {#usage}

「核心元件容器」元件可讓您在頁面上建立多個其他元件的容器，並可用來群組其他元件，以及套用共用樣式或版面。

* 可在「設定」對話方塊中選取容器 [的屬性](#configure-dialog)。
* 將容器元件新增至頁面時的預設值，可在設計對話方塊中 [定義](#design-dialog)。

## 版本與相容性 {#version-and-compatibility}

目前的容器元件版本為v1，此版本於2019年6月隨核心元件2.5.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本與版本的詳細資訊，請參閱檔案核 [心元件版本](versions.md)。

## 元件輸出示例 {#sample-component-output}

若要體驗容器元件，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪元 [件庫](http://opensource.adobe.com/aem-core-wcm-components/library/container.html)。

## 技術詳細資訊 {#technical-details}

有關容器元件的最新技術文 [件可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/container/v1/container)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](developing.md)。

## 配置對話框 {#configure-dialog}

「設定」對話方塊可讓內容作者定義容器項目，以及該項目對頁面訪客的行為和顯示方式。

![](assets/screen-shot-2019-06-21-13.59.26.png)

* **配置** -此選項定義容器元件的行為或配置行為。
   * **Simple** —— 將容器定義為簡單的元件集合
   * **自適應格線** -將容器定義為 [AEM自適應格線](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/responsive-layout.html)
* **ID** —— 使用此選項定義要套用至元件的HTML ID屬性。
* **背景顏色** -可定義為自由格式的RGB值，或使用檢色器(視 [配置而定)](#background-tab)
* **背景影像** -定義容器的背景顏色，視 [組態而定](#background-tab)

## 設計對話框 {#design-dialog}

設計對話方塊可讓範本作者定義使用容器元件的內容作者可用的選項。

### 允許的元件頁籤 {#allowed-components-tab}

「允 **許的元件** 」標籤可用來定義哪些元件可由內容作者新增為項目至「容器元件」。

在範本編輯器中定義配置容器的原則和屬性時，「允許的元件」標 [簽的功能與相同名稱的標籤相同。](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### 預設元件頁籤 {#default-components-tab}

當容器上放置特定資產類型時，「預設元件」索引標籤會用來定義要新增至元件的元件，類似於頁面範本上 [定義預設元件的方式](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html#EditingTemplatesTemplateAuthors)。

### 互動式設定標籤 {#responsive-settings-tab}

![](assets/screen-shot-2019-06-21-09.33.03.png)

* **欄** -定義產生容器格線中的欄數。

### 背景標籤 {#background-tab}

![](assets/screen-shot-2019-06-21-09.42.42.png)

* **背景影像**
   * **啟用背景影像** -選取此選項可讓內容作者為容器定義背景影像。
* **背景色彩**
   * **啟用背景顏色** -選取此選項可讓內容作者為容器定義背景顏色。
   * **僅色票** -選擇此選項僅允許內容作者從預先定義的容器背景顏色色票中選擇。
      * 僅在選取「啟 **用背景顏色** 」時可用
* **允許的色票** -定義預先定義的顏色，內容作者可從中選取容器背景顏色
   * 使用「 **新增** 」按鈕新增預先定義的色票。 新增後，會將一個項目新增至清單，其中包含下列欄：
   * **值** -通過RGB值手動定義顏色
      * 點選或按一下檢色器，可調整個別RGB值或定義十六進位值，以更輕鬆地選取顏色。
   * **刪除** -點選或按一下以刪除色票。
   * **重新排列** -點選或按一下並拖曳以重新排列色票順序。

### 樣式標籤 {#styles-tab}

容器元件支援AEM [樣式系統](authoring.md#component-styling)。
