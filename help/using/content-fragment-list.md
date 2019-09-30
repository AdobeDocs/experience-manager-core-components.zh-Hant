---
title: 內容片段清單元件
seo-title: 內容片段清單元件
description: 'null'
seo-description: 核心元件內容片段清單元件可顯示內容片段的清單。
contentOwner: 博納特
content-type: 引用
topic-tags: 編寫
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-新功能
translation-type: tm+mt
source-git-commit: 6882a0d8247328c403dc11a25ed9d079aefede69

---


# 內容片段清單元件{#content-fragment-list-component}

核心元件內容片段清單元件可顯示內容片段 [清單](https://helpx.adobe.com/experience-manager/6-5/assets/using/content-fragments.html)。

## 使用狀況 {#usage}

核心元件內容片段清單元件允許根據內容片段模型 [在頁面上包含](https://helpx.adobe.com/experience-manager/6-5/assets/using/content-fragments.html) 內容片段的清單。 這對於建立其他應用程式可 [輕鬆使用的無頭內容](https://helpx.adobe.com/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js) ，特別有用。

* 可以在配置對話框中選擇清單及其 [屬性](#configure-dialog)。
* 樣式可套用至設計對話方 [塊中的元件](#design-dialog)。

## 版本與相容性 {#version-and-compatibility}

目前的內容片段元件版本為v1，此版本於2019年5月隨核心元件2.4.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | 相容 | Compatible | 相容 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Content Fragment List Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment-list.html).

## Technical Details {#technical-details}

The latest technical documentation about the Content Fragment List Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/contentfragmentlist/v1/contentfragmentlist).

Further details about developing Core Components can be found in the Core Components developer documentation.[](developing.md)

## Configure Dialog {#configure-dialog}

The configure dialog allows the content author to define the which content fragments comprise the list and the elements of those fragments to be included.

### Properties Tab

The Properties tab defines which Content Fragments are included in the list. **** This is primarily based on a selected Content Fragment Model, but there are other filter options available.

![](assets/screen-shot-2019-09-25-10.32.10.png)

* **模型** -清單所依據之內容片段模型的路徑。
   * By default, all content fragments of the model defined as Model Path are included in the list.****
* **Parent Path - Parent path from which the list should be built.**
   * 根據所選模型路徑的內 **容片段** ，將篩選為指定父路徑 **上的內容片段**。
      * 按一下或點選 **欄位右側的** 「開啟選取範圍對話方塊」按鈕，以指定路徑。
* **標籤** -清單中只會包含具有指定標籤的內容片段。
   * 按一下或點選 **欄位右側的「開啟選取對話方塊** 」按鈕，以指定標籤。
   * 按一下或點選選取標籤旁的X以移除標籤。
* **排序依據** -內容片段模型的欄位，清單將依該欄位排序
   * 只有文字欄位（包括數值、日期和時間）可供選取。
* **排序順序** -如何按「排序方式」字 **段排序** 。
   * 遞增或遞減
* **最大項目** -清單中顯示的項目數上限
   * 沒有值會傳回所有項目。

>[!NOTE]
>核心 **元件2.7.0版中**，已引入「排序方式」、「排序順序 ******** 」和「最大項目」選項。

### Elements Tab

依預設，「內容片段模型」的所有元素都會包含在清單中(除非受「最大項目」欄 **位限制** )。 「元 **素** 」(Elements)頁籤允許您僅指定要包括的特定元素。

![](assets/screen-shot-2019-05-08-10.47.34.png)

* **Elements** —— 只會顯示指定清單中內容片段的元素。
   * 按一下或點選「 **新增** 」按鈕以新增元素。
   * 按一下或點選「刪 **除** 」按鈕以移除選取的元素。
   * 拖動 **Order** （順序）控點以重新排列元素的順序。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義應用於內容片段清單元件的樣式。
