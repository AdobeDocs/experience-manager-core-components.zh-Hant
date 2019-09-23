---
title: 摘要元件
seo-title: 摘要元件
description: 摘要元件可顯示影像、標題、豐富文字，並可選擇地連結至其他內容。
seo-description: 摘要元件可顯示影像、標題、豐富文字，並可選擇地連結至其他內容。
uuid: 46989314-df37-448b-8562-c707043f2160
contentOwner: 博納特
content-type: 引用
topic-tags: 核心元件
discoiquuid: e597c18e-3643-41be-9878-4a7872f1ab90
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# 摘要元件{#teaser-component}

核心元件摘要元件可顯示影像、標題、豐富式文字，並可選擇連結至其他內容。

## 使用狀況 {#usage}

The Teaser Component allows the content author to easily create a teaser to further content using an image, title, or rich text and linking to further content or other actions.

範本作者可使用設 [計對話方塊](#design-dialog) ，定義建立動作呼叫和新增連結的選項是否可用，以及停用各種顯示選項。 內容作者可以使用 [設定對話方塊](#configure-dialog) ，來設定影像、定義CTA、設定標題和說明，以及設定個別摘要的連結。 您可 [以存取影像](image.md#edit-dialog) 元件的編輯對話方塊 [](image.md) ，以修改摘要影像。

## 版本與相容性 {#version-and-compatibility}

摘要元件的目前版本為v1，此版本於2018年7月隨核心元件2.1.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|---|---|---|---|
| v1 | 相容 | 相容 | 相容 |

## 元件輸出示例 {#sample-component-output}

若要體驗Teaser元件，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪元 [件庫](http://opensource.adobe.com/aem-core-wcm-components/library/teaser.html)。

### 技術詳細資訊 {#technical-details}

有關摘要元件的最新技術文 [件可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/teaser/v1/teaser)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](developing.md)。

## 配置對話框 {#configure-dialog}

內容作者可以使用設定對話方塊來定義個別摘要的屬性。 There is also an edit dialog to modify the teaser image if one is selected.[](#edit-dialog)

### 影像 {#image}

![](assets/screen_shot_2018-07-03at104125.png)

* **影像資產**
   * 從資產瀏覽器中 [拖放資產](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html) ，或點選 **** 瀏覽選項，從本機檔案系統上傳。
   * 點選或按一 **下「清除** 」以取消選取目前選取的影像。
   * Tap or click Edit to mange the renditions of the asset in the asset editor.****[](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html)

### 文字 {#text}

![](assets/screen_shot_2018-07-03at104138.png)

* **Title**（標題）定義標題，以顯示為摘要標題。
* **Get title from linked page
When checked, the title will be populated with the linked page's title.**
* **Description
Defines a description to display as the subheading of the teaser.**
* **Get description from linked page
When checked, the description will be populated with the linked page's description.**

### Links &amp; Actions {#links-actions}

![](assets/screen_shot_2018-07-03at104146.png)

* **Link
Link applied to the teaser.** Use the path browser to select the link target.
* **Enable Call-To-Actions
When checked, enables definition of Call-To-Actions.** The first Call-To-Action link in the list is used as the link for other teaser elements.

## Edit Dialog {#edit-dialog}

The Teaser Component delegates image rendering to the Image Component. [](image.md)Therefore the edit dialog(image.md#edit-dialog of the Image Component is available to the content author to manipulate the teaser image.[]

## Design Dialog {#design-dialog}

設計對話方塊可讓範本作者定義內容作者使用此元件時擁有的摘要選項。

### 摘要標籤 {#teaser-tab}

![](assets/screen_shot_2018-07-03at105958.png)

* **呼叫動作**
   * **停用內容作者的**「呼 **叫動作」選項**
* **元素**
   * **隱藏標題**
      * Hides the Title option for content authors ****
      * 選取「標題類 **型」(Title Type** )後，
   * **隱藏說明**&#x200B;隱藏內容作 **者的「說明** 」選項
* **標題類**&#x200B;型定義摘要標題要使用的H標籤。
* **連結**
   * **不要連結影像選取**&#x200B;時，未連結摘要影像
   * **不要連結標題選取**&#x200B;時，未連結摘要標題

### 樣式標籤 {#styles-tab}

Teaser元件支援AEM [Style系統](authoring.md#component-styling)。
