---
title: 頁面元件
seo-title: 頁面元件
description: 頁面元件是可擴充的頁面元件，可用於範本編輯器，並允許頁面頁首/頁尾以及結構元件與範本編輯器一起組合。
seo-description: 頁面元件是可擴充的頁面元件，可用於範本編輯器，並允許頁面頁首/頁尾以及結構元件與範本編輯器一起組合。
uuid: 7052a5b1-e7 f1-4944-a55 c-faf739 b6 e89 c
contentOwner: 使用者
content-type: 引用
topic-tags: 製作
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: cb1a745a-30c4-4ad6-a04 f-ffb3666 cd95
translation-type: tm+mt
source-git-commit: 1243d6cc1b0b015ee2f37ae89d0e2e42d366cc02

---


# 頁面元件{#page-component}

頁面元件是可擴充的頁面元件，可用於 [範本編輯器](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) ，並允許頁面頁首/頁尾以及結構元件與範本編輯器一起組合。

## 使用狀況 {#usage}

頁面元件是使用核心元件以及可編輯範本所設計之所有頁面的基礎。使用頁面元件、頁首、頁尾及頁面結構，可將頁面定義為使用其他核心元件的範本。

使用 [設計對話方塊](#design-dialog)，可為頁面定義自訂用戶端程式庫。不同於其他元件可直接從元件存取，因為元件是頁面本身，所以頁面元件 [的編輯對話方塊](#edit-dialog) 是頁面屬性視窗。

## 版本與相容性 {#version-and-compatibility}

目前版本的Page Component is v2，它是在2018年月發行的版本2.0.0推出，並在本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|---|---|---|---|
| [v2](page-v1.md) | 相容相容性 | 相容相容性 | 相容相容性 |
| v1 | 相容相容性 | 相容相容性 | 相容相容性 |

如需核心元件版本和版本的詳細資訊，請參閱文件 [核心元件版本](versions.md)。

>[!NOTE]
>
>若要針對頁面元件的Verison啓用重新導向 `cq:Page` ，則需要 [Service Pack或](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp2-release-notes.html) 更新版本。舊版無法使用此重新導向。

## 元件輸出範例 {#sample-component-output}

以下是取自 [「我們零售](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)業」的範例。

### 螢幕擷圖 {#screenshot}

![](assets/chlimage_1.png)

### 技術細節 {#technical-details}

有關頁面元件 [的最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。

## 編輯對話方塊 {#edit-dialog}

由於元件代表整個頁面，所以通常會在 [「頁面屬性](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-page-properties.html) 」視窗中找到通常位於編輯對話方塊中的設定。

## 設計對話方塊 {#design-dialog}

由於元件代表整個頁面，所以編輯頁面範本時，會透過 **「頁面資訊-&gt;頁面原則** 」存取設計對話方塊。

![](assets/screen_shot_2018-04-03at113410.png)

>[!NOTE]
>
>在舊版AEM中 **，頁面原則** 稱為 **頁面設計**。

### 屬性索引標籤 {#properties-tab}

您可以使用「頁面設計」視窗定義要載入的用戶端程式庫，以及頁面的Web資源庫。

* **用戶端程式庫**：此定義要載入的用戶端程式庫類別。JavaScript會新增至內文端，而CSS會新增至頁面標題。
* **用戶端程式庫JavaScript頁面標題**定義要在頁面標題中載入的JavaScript用戶端程式庫類別。
   * 此處定義的類別也會出現 **在「用戶端資料庫** 」欄位中，將JavaScript載入頁面標題而非內文端。
   * 不會載入CSS，除非類別也出現 **在「用戶端資料庫」** 欄位中。

* **Web資源用戶端程式庫：**用來提供網站資源(例如字型)的用戶端程式庫類別。

![](assets/screenshot_2018-10-19at104949.png)

您可以將「 **用戶端程式庫** 」和 **「用戶端程式庫JavaScript頁面標題** 」欄位設定為如下所示：

* 若要新增欄位，或點選欄位下方的 **「新增** 」按鈕。
* 若要移除欄位，或點選欄位旁的垃圾桶圖示，請加以移除。
* 若要重新排列載入順序，請按一下或點選並拖曳欄位旁的控點以進行移動。

如需使用用戶端程式庫的詳細資訊，請參閱 [「使用用戶端程式庫](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html)」。

>[!CAUTION]
>
>為頁面標題個別定義用戶端程式庫的能力，是由核心元件2.2.0推出。

### 樣式標籤 {#styles-tab}

頁面元件支援AEM [樣式系統](authoring.md#component-styling)。