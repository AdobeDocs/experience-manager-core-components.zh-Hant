---
title: 標題元件
seo-title: 標題元件
description: 'null'
seo-description: 核心元件標題元件是一個區段標題元件，具備就地編輯功能。
uuid: cf190861-e5 cd-42b8-9193-842b8 df8 c5 c6
contentOwner: 使用者
content-type: 引用
topic-tags: 製作
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: 243efc75-fcf9-427d-9303-9642b0602991
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b179888d19a95257602656d456d5c6bfe82877af

---


# 標題元件{#title-component}

核心元件標題元件是一個區段標題元件，具備就地編輯功能。

## 使用狀況 {#usage}

「標題元件」旨在做為內容區段的標題或標題。可用的標題層級可由 [設計對話方塊中的範本作者定義](#design-dialog)。內容編輯器可從 [編輯對話方塊](#edit-dialog)中選擇可用標題層級。為方便您加入，也提供簡單的標題文字就地編輯功能。

## 版本與相容性 {#version-and-compatibility}

目前版本的Title Component is v2，它是在2018年月發行的版本2.0.0推出，並在本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|---|---|---|---|
| v2 | 相容相容性 | 相容相容性 | 相容相容性 |
| [v1](title-v1.md) | 相容相容性 | 相容相容性 | 相容相容性 |

如需核心元件版本和版本的詳細資訊，請參閱文件 [核心元件版本](versions.md)。

## 元件輸出範例 {#sample-component-output}

以下是取自 [「我們零售](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)業」的範例。

### 螢幕擷圖 {#screenshot}

![](assets/chlimage_1-36.png)

### 元件庫

若要體驗「標題元件」，以及查看其組態選項以及HTML和JSON輸出的範例，請造訪 [元件庫](http://opensource.adobe.com/aem-core-wcm-components/library/title.html)。

### 技術細節 {#technical-details}

有關Title Component [的最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/title/v2/title)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者定義標題文字，並選取標題層級。

* **標題** -如果將頁面標題空白，則會使用
* **類型/大小** -定義標題的標題層級
* **連結** -定義標題將會連結的內容。這可以是內容頁面、外部URL或頁面錨點的路徑。

![](assets/screenshot_2018-10-19at110055.png)

>[!CAUTION]
>
>The ability to define a link for the title is delated with the release2.2.0of the Core Components.

原地編輯器也可以用來編輯標題元件的文字。

![](assets/chlimage_1-37.png)

## 設計對話方塊 {#design-dialog}

此設計對話方塊可讓範本作者定義內容作者建立時，標題元件將擁有的預設標題層級。

### 大小標籤 {#sizes-tab}

![](assets/screenshot_2018-10-19at110120.png)

* **適用於作者的允許類型/大小** -啓用或停用內容作者使用標題元件時將可使用的標題類型。
* **預設類型/大小**-定義當內容作者新增「標題元件」至頁面時，自動指派的標題類型。
* **停用連結**-停用標題元件中的連結支援，以避免內容作者從標題連結。

>[!CAUTION]
>
>The ability to define a link for the title is delated with the release2.2.0of the Core Components.

### 樣式標籤 {#styles-tab}

「標題元件」支援AEM [樣式系統](authoring.md#component-styling)。