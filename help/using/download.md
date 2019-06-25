---
title: 下載元件
seo-title: 下載元件
description: 'null'
seo-description: 核心元件下載元件可讓您建立頁面上的下載選項。
uuid: ec807de9-f76 c-4850-9ee-c3 e439 a1 d626
contentOwner: 使用者
content-type: 引用
topic-tags: 製作
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: f093f58e-9755-4a4f-803a-ab93 a50 e6870
translation-type: tm+mt
source-git-commit: 88bc68b60e5de247fe800ac041ffefdf9238cce1

---


# Download Component{#download-component}

核心元件下載元件可讓您建立頁面上的下載選項。

## 使用狀況 {#usage}

核心元件下載元件允許在頁面上加入下載選項及其相關資產。

* The download option&#39;s properties can be selected in the [configure dialog](#configure-dialog).
* Defaults for the download component can be defined in the [design dialog](#design-dialog).

## Version and Compatibility {#version-and-compatibility}

目前版本的下載元件是v1，是在2019年月發行的版本2.5.0推出的v1，本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|--- |--- |--- |---|
| v1 | 相容相容性 | 相容相容性 | 相容相容性 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Download Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/download.html).

## Technical Details {#technical-details}

The latest technical documentation about the Download Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/download/v1/download).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Configure Dialog {#configure-dialog}

設定對話方塊可讓內容作者定義下載項目，以及它對頁面訪客的行為和顯示方式。

![](assets/screen-shot-2019-06-17-09.49.14.png)

### Asset Tab {#asset-tab}

The selection of a download asset is very similar to the functionality of the [Image Component](image.md) and likewise leverages AEM&#39;s DAM.

* **下載資產**
   * Drop an asset from the [asset browser](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html) or tap the **browse** option to upload from a local file system.
   * Tap or click **Clear** to de-select the currently selected image.
   * Tap or click **Edit** to [mange the renditions of the asset](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html) in the asset editor.

### Properties Tab {#properties-tab}

![](assets/screen-shot-2019-06-17-09.49.51.png)

* **標題** -顯示為下載項目的標題
   * **從DAM資產** 取得標題-選取時，標題會自動填入DAM資產的標題。
* **說明** -顯示為下載項目的描述性子標題
   * **從DAM資產取得描述** -選取時，描述會自動填入DAM資產的說明。
* **動作文字** -顯示為下載項目的動作文字
   * 從檔案系統上傳資產時，需要此欄位。
   * **顯示內嵌** -選取所提供 **的動作文字** 將內嵌顯示。

## Design Dialog {#design-dialog}

此設計對話方塊可讓範本作者定義使用下載元件的內容作者可用的選項。

### Properties Tab {#properties-tab-design}

![](assets/screen-shot-2019-06-17-10.04.31.png)

* **預設動作文字** -定義當作者新增下載元件至頁面時所提供的預設 **動作文字** 。
* **允許從檔案系統** 上傳-允許內容作者從本機檔案系統上傳資產做為下載資產。
   * 預設值未選取。
* **標題類型** -用於下載元件標題的HTML元素。
   * 如果未選取任何值，預設值為H3。
* **顯示檔案大小** ：選取資產的檔案大小時，將會在下載元件中顯示檔案大小。
   * 預設值已選取。
* **顯示檔案格式** -選取資產的檔案格式時，會顯示在下載元件中。
   * 預設值已選取。
* **顯示檔案名稱** ：選取資產的檔案名稱時，會顯示在下載元件中。
   * 預設值已選取。

### Styles Tab {#styles-tab}

The Image Component supports the AEM [Style System](authoring.md#component-styling).
