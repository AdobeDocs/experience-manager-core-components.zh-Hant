---
title: 影像元件
seo-title: 影像元件
description: 核心元件影像元件是可調式影像元件功能，可進行就地編輯。
seo-description: 核心元件影像元件是可調式影像元件功能，可進行就地編輯。
uuid: 1a229d42-2428-43aa-895a-9b7c1bf02834
contentOwner: 使用者
content-type: 引用
topic-tags: 製作
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: d4684f33-2fb5-4f32-866f-7136cf1800d
translation-type: tm+mt
source-git-commit: 1243d6cc1b0b015ee2f37ae89d0e2e42d366cc02

---


# 影像元件{#image-component}

核心元件影像元件是一種調適性影像元件，可用來進行就地編輯。

## 使用狀況 {#usage}

Image Component可讓您輕鬆放置影像資產並提供就地編輯。它具備漸進式影像選擇功能，以及內容製作的延遲載入功能。

影像寬度以及裁切和其他設定可由 [設計對話方塊中的範本作者定義](#design-dialog)。內容編輯器可以在 [設定對話方塊](#configure-dialog) 中上傳或選取資產，並在 [編輯對話方塊中裁切影像](#edit-dialog)。為方便您加入，也提供簡單易用的影像就地修改功能。

## 版本與相容性 {#version-and-compatibility}

目前的Image Component版本是v2，是在2018年月發行的版本2.0.0推出，並在本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|--- |--- |--- |--- |
| v2 | 相容相容性 | 相容相容性 | 相容相容性 |
| [v1](image-v1.md) | 相容相容性 | 相容相容性 | 相容相容性 |

如需核心元件版本和版本的詳細資訊，請參閱文件 [核心元件版本](versions.md)。

## SVG支援 {#svg-support}

影像元件支援可縮放向量圖形(SVG)。

* 同時支援從DAM拖放SVG資產，以及從本機檔案系統上傳SVG檔案。
* 最適化影像Servlet串流原始SVG檔案(跳過變形)。
* 對於SVG影像，「智慧型影像」和「智慧大小」會設為影像模型中的空白陣列。

### 安全性 {#security}

基於安全理由，影像編輯器絕不會直接呼叫原始SVG。會被呼叫 `<img src=“path-to-component”>`。因此，瀏覽器會防止內嵌於SVG檔案中的指令碼執行。

>[!CAUTION]
>
>SVG支援需要核心元件的2.1.0版，以及AEM6.4或Service [Pack for](https://helpx.adobe.com/experience-manager/6-4/release-notes/sp-release-notes.html) AEM6.3或 [Service Pack](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html) 的Service Pack2，以支援AEM內 [的新影像編輯器功能](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/image-editor.html) 。

## 元件輸出範例 {#sample-component-output}

以下是取自 [「我們零售](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)業」的範例。

### 螢幕擷圖 {#screenshot}

![](assets/chlimage_1-7.png)

### 元件庫

若要體驗Image Component，以及查看其組態選項以及HTML和JSON輸出的範例，請造訪 [元件庫](http://opensource.adobe.com/aem-core-wcm-components/library/image.html)。

### 技術細節 {#technical-details}

有關Image Component [的最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/image/v2/image)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。

>[!NOTE]
>
>如同核心元件2.1.0版，Image Component支援 [schema.org微型資料](https://schema.org)。

## 設定對話方塊 {#configure-dialog}

除了標準 [編輯對話方塊](#edit-dialog) 和 [設計對話方塊](#design-dialog)外，影像元件還提供設定對話方塊的對話方塊，其中定義影象本身及其說明和基本屬性。

### 資產索引標籤 {#asset-tab}

![](assets/screen_shot_2018-01-08at114245.png)

* **影像資產**
   * 從 [資產瀏覽器拖曳資產，](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html) 或點選 **瀏覽** 選項以從本機檔案系統上傳。
   * 點選或按一下 **清除** ，以取消選取目前選取的影像。
   * 點選或按一下 **「編輯** 」，在資產編輯器中 [插入資產](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html) 的轉譯。

### 中繼資料索引標籤 {#metadata-tab}

![](assets/screen_shot_2018-01-08at114527.png)

* **影像為裝飾性**檢查影像是否應由輔助技術忽略，因此不需要替代文字。這僅適用於裝飾影像。
* **替代文字**替代影像的意義或函數替代文字，適用於視覺效果不穩定的讀者。
   * 從DAM取得替代文字-檢查影像的替代文字時，會在DAM中填入 `dc:description` 中繼資料的值。

* **標題**其他關於影像的資訊，依預設會顯示在影像下方。
   * **從DAM**取得標題時，影像的標題文字會填入DAM `dc:title` 中中繼資料的值。
   * **顯示標題為**快顯視窗時，標題不會顯示在影像下方，但會在某些瀏覽器停留在影像上時顯示為快顯視窗。

* **連結**
   * 將影像連結到另一個資源。
   * 使用選取對話方塊連結至其他AEM資源。
   * 如果未連結到AEM資源，請輸入絕對URL。非解決方案URL將被解讀為相對於AEM。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者裁切、修改啓動地圖並縮放影象。

![](assets/chlimage_1-8.png)

* 開始裁切

   ![](assets/chlimage_1-9.png)

   選取此選項會開啓預先定義裁切比例的下拉式清單。

   * 選擇「Free Hand」( **免費手** )選項，以定義自己的裁切。
   * 選擇 **「移除裁切」** 選項，以顯示原始資產。
   選取裁切選項後，請使用藍色控點來調整影像的裁切大小。

   ![](assets/chlimage_1-10.png)

* 向右旋轉

   ![](assets/chlimage_1-11.png)

   使用此選項可將影像旋轉至右側(順時針)。

* 水平翻轉

   ![](assets/screen_shot_2018-04-16at091404.png)

   使用此選項可水平翻轉影像，或沿著y軸旋轉影像180°。

* 垂直翻轉

   ![](assets/screen_shot_2018-04-16at091410.png)

   使用此選項可垂直翻轉影像，或沿著x軸旋轉影像180°。

* 啓動地圖

   >[!CAUTION]
   >
   >Launch Map功能需要核心元件的2.1.0版，以及AEM6.4或Service [Pack for](https://helpx.adobe.com/experience-manager/6-4/release-notes/sp-release-notes.html) AEM6.3或 [Service Pack](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html) 的Service Pack2，以支援AEM中 [的新影像編輯器功能](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/image-editor.html) 。

   ![](assets/chlimage_1-12.png)

   使用此選項可套用啓動地圖至影像。選取此選項會開啓新視窗，讓使用者選取地圖的形狀：

   * **新增矩形地圖**
   * **新增圓形圖**
   * **新增多邊形地圖**
      * 預設會新增三角形地圖。連按兩下形狀線條，新增新邊的藍色大小控制點。
   選取地圖形狀後，就會疊加在影像上，以便調整大小。拖放藍色大小控點以調整形狀。

   ![](assets/chlimage_1-13.png)

   調整啓動地圖的大小後，按一下它以開啓浮動工具列，以定義連結路徑。

   * **路徑**
      * 使用路徑選擇器選項在AEM中選取路徑
      * 如果路徑不在AEM中，請使用絕對URL。非絕對路徑將與AEM相關。
   * **Alt文字**替代說明路徑目的地
   * **目標**
      * **相同標籤**
      * **新標籤**
      * **父框架**
      * **上框架**
   點選或按一下藍色勾號以儲存、要取消的黑色x，以及紅色垃圾桶可以刪除地圖。

   ![](assets/chlimage_1-14.png)

* 重設縮放

   ![](assets/chlimage_1-15.png)

   如果影像已經縮放，請使用此選項重設縮放等級。

* 開啓縮放滑桿

   ![](assets/chlimage_1-16.png)

   使用此選項可顯示滑桿，以控制影像縮放等級。

   ![](assets/chlimage_1-17.png)

就地編輯器也可以用來修改影像。由於空間限制，僅提供基本選項。若需完整編輯選項，請使用全螢幕模式。

![](assets/chlimage_1-18.png)

>[!NOTE]
>
>GIF影像不支援影像編輯作業(裁切、翻轉、旋轉)。在編輯模式中對GIF進行的任何這類變更都不會持續存在。

## 設計對話方塊 {#design-dialog}

此設計對話方塊可讓範本作者定義當使用此元件時，內容作者所擁有的裁切、上傳和旋轉以及上傳選項。

### 主標籤 {#main-tab}

**在主** 標籤上，您可以定義影像的像素寬度清單，以自動從清單中載入最適當的寬度。

此外，您也可以定義當作者新增元件至頁面時，會自動或停用哪些一般元件選項。

![](assets/screenshot_2018-10-19at102756.png)

* **啓用延遲載入**：在新增影像元件至頁面時，自動啓用延遲載入選項。
* **影像為裝飾性**定義：在新增影像元件至頁面時，會自動啓用裝飾影像選項。
* **從DAM取得替代文字**，如果在新增影像元件至頁面時，自動啓用從DAM擷取替代文字的選項。
* **取得DAM**定義的標題：在新增影像元件至頁面時，自動啓用從DAM擷取標題的選項。
* **顯示標題做為彈出式**定義，如果將影像元件新增至頁面時，自動啓用顯示影像標題的選項。
* **停用UUID追蹤**檢查以停用影像資產的UUID追蹤。

* **寬度**：定義影像的像素寬度清單，自動從清單中載入最適當的寬度。
   * 點選或按一下「 **新增** 」按鈕以新增另一個大小。
      * 使用抓取控點重新排列大小順序。
      * 使用 **「刪除** 」圖示可移除寬度。
   * 依預設載入影像會延遲，直到顯示出來為止。
      * 選取「 **停用延遲載入** 」選項，以載入頁面時載入影像。
* **JPEG品質**：變形(例如縮放或裁切)
JPEG影像的品質因數(以和100為單位)。

>[!CAUTION]
>
>「JPEG品質」選項可從核心元件2.2.0發行。

>[!NOTE]
>
>從核心元件2.2.0版開始，Image Component會新增唯一UUID屬性 `data-asset-id` 至影像資產，以允許追蹤和分析個別資產收到的檢視次數。

### 功能標籤 {#features-tab}

在 **「功能** 」索引標籤上，您可以定義內容作者在使用元件時可用的選項，包括上傳選項、方向和裁切選項。

* 來源

   ![](assets/chlimage_1-19.png)

   選取 **允許從檔案系統** 上傳資產的選項，允許內容作者從本機電腦上傳影像。若要強制內容作者只選取AEM的資產，請取消選取此選項。

* 方向

   ![](assets/chlimage_1-20.png)

* **旋轉**：使用此選項可允許內容作者使用 **「旋轉正確」** 選項。
* **Flip**使用此選項可讓內容作者使用 **「水平翻轉** 」和 **「翻轉垂直** 」選項。

   >[!CAUTION]
   >
   >預設會停用 **「翻轉」** 選項。啓用它會在影像元件的編輯對話方塊中顯示 **「翻轉垂直** 」和 **「翻轉」** 按鈕，但是AEM目前不支援此功能，而使用這些選項所做的任何變更都不會持續存在。

<!-- 
Comment Type: remark
Last Modified By: Chris Bohnert (bohnert)
Last Modified Date: 2017-11-20T05:51:34.378-0500

<p>Added caution based on CQDOC-11457. Hid the flip options in the procedure using the <strong>Draft</strong> option so that when this feature is implemented in CQ-4221539, the <strong>Draft</strong> property can simply be removed along with the caution.</p>
 -->

* 裁切

   ![](assets/chlimage_1-21.png)

   選取 **「允許裁切** 」選項，允許內容作者在編輯對話方塊中裁切元件中的影像。
   * 按一下 **「新增** 」，新增預先定義的裁切外觀比例。
   * 輸入描述性名稱，此名稱將顯示在 **「開始裁切」** 下拉式清單中。
   * 輸入外觀的數值比例。
   * 使用拖曳控點重新排列外觀比例的順序
   * 使用垃圾筒圖示可刪除外觀比例。
   >[!CAUTION]
   >
   >請注意，在AEM中，裁切外觀比例定義為 **高度/寬度**。這與傳統的寬度/高度定義不同，而且會基於舊有相容性原因而執行。只要您在UI中顯示名稱，而非比例本身，內容作者就不會察覺任何差異。

### 樣式標籤 {#styles-tab-1}

Image Component支援AEM [Style System](authoring.md#component-styling)。