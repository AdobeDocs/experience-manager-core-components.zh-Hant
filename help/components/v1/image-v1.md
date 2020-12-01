---
title: 影像元件(v1)
description: 核心元件影像元件是就地編輯的自適應影像元件功能。
index: n
translation-type: tm+mt
source-git-commit: 78202dc777b90f795f66873921c55e21ef8a239c
workflow-type: tm+mt
source-wordcount: '1229'
ht-degree: 1%

---


# 影像元件(v1){#image-component-v}

核心元件影像元件是就地編輯的自適應影像元件功能。

## 使用狀況 {#usage}

影像元件可輕鬆放置影像資產，並提供就地編輯功能。 它具備可自適應選擇影像的功能，包括延遲載入以及為內容作者裁切。

範本作者可在[設計對話方塊](#design-dialog)中定義允許的影像寬度以及裁切和其他設定。 內容編輯器可以在[configure dialog](#configure-dialog)中上傳或選擇資產，並在[編輯對話框](#edit-dialog)中裁切影像。 為方便起見，酒店還提供簡單的就地修改影像。

## 版本和相容性{#version-and-compatibility}

本檔案說明影像元件的v1，最初是隨AEM 6.3核心元件的1.0.0版一起推出。

下表列出了映像元件v1的相容性。

| AEM版本 | 影像元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明影像元件的v1。
>
>如需影像元件目前版本的詳細資訊，請參閱[影像元件](/help/components/image.md)檔案。

## 元件輸出示例{#sample-component-output}

以下範例取自[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

### 螢幕擷圖 {#screenshot}

![](/help/assets/chlimage_1-7.png)

### HTML {#html}

```
<div class="cmp cmp-image aem-GridColumn aem-GridColumn--default--12">
 
        <noscript data-cmp-image="{&#34;smartImages&#34;:[],&#34;smartSizes&#34;:[],&#34;lazyEnabled&#34;:true}">
            <img src="/content/we-retail/us/en/equipment/_jcr_content/root/responsivegrid/image.img.jpg" alt="Surfboard"/>
        </noscript>

</div>
```

### JSON {#json}

```
"image": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "smartSizes": [],
              "smartImages": [],
              "lazyEnabled": true,
              "src": "/content/we-retail/us/en/equipment/equipment/jcr%3acontent/root/responsivegrid/image.img.jpeg",
              ":type": "weretail/components/content/image"
            }
```

>[!NOTE]
>
>從核心元件匯出JSON需要1.1.0版的核心元件。 如需詳細資訊，請參閱核心元件v1](/help/versions.md)的[相容性資訊。

## 配置對話框{#configure-dialog}

除了標準的[編輯對話框](#edit-dialog)和[設計對話框](#design-dialog)外，影像元件還提供了配置對話框，其中定義了影像本身及其說明和基本屬性。

![](/help/assets/chlimage_1-50.png)

* **影像資產**
   * 從[資產瀏覽器](https://helpx.adobe.com/experience-manager/6-3/sites/authoring/using/author-environment-tools.html#main-pars_title)拖放資產，或點選&#x200B;**browse**&#x200B;選項，從本機檔案系統上傳。
   * 點選或按一下&#x200B;**Clear**&#x200B;以取消選取目前選取的影像。
   * 點選或按一下「編輯&#x200B;****」，在資產編輯器中管理資產](https://helpx.adobe.com/experience-manager/6-3/assets/using/managing-assets-touch-ui.html#main-pars_title_19)的轉譯。[

* **影像是裝飾性** -檢查協助技術是否應忽略影像，因此不需要替代文字。這僅適用於裝飾性影像。
* **替代文字** -視障讀者，影像意義或功能的文字替代文字。
* **連結**
   * 將影像連結至其他資源。
   * 使用選取對話方塊連結至其他AEM資源。
   * 如果未連結至AEM資源，請輸入絕對URL。 非溶質URL將會解譯為相對於AEM。

* **標題** -影像下方顯示的其他相關資訊為預設值。
* **以快顯方式顯示標題** -勾選後，標題不會顯示在影像下方，但是當將滑鼠暫留在影像上時，某些瀏覽器會顯示為快顯。

## 編輯對話框{#edit-dialog}

編輯對話方塊可讓內容作者裁切、修改啟動地圖，以及縮放影像。

![](/help/assets/chlimage_1-8.png)

* 開始裁切

   ![](/help/assets/chlimage_1-9.png)

   選取此選項會開啟預先定義的裁切比例的下拉式清單。

   * 選擇「Free Hand」（自由手）選項&#x200B;**以定義您自己的裁切。**
   * 選擇「移除裁切」選項&#x200B;**以顯示原始資產。**

   選取裁切選項後，使用藍色控點來調整影像上的裁切大小。

   ![](/help/assets/chlimage_1-10.png)

* 向右旋轉

   ![](/help/assets/chlimage_1-11.png)

   使用此選項可將影像向右（順時針）旋轉90度。

* 啟動地圖

   ![](/help/assets/chlimage_1-12.png)

   使用此選項可將啟動映射套用至影像。 選取此選項會開啟新視窗，讓使用者可選取地圖的形狀：

   * **新增矩形地圖**
   * **新增圓形圖**
   * **新增多邊形地圖**

      * 依預設會新增三角形地圖。 連按兩下形狀的一行，在新側面加入新的藍色調整大小控制點。

   一旦選擇了地圖形狀，該形狀被疊加在影像上以允許調整大小。 拖放藍色的調整大小控制點，以調整形狀。

   ![](/help/assets/chlimage_1-13.png)

   調整啟動地圖大小後，按一下它以開啟浮動工具列，以定義連結的路徑。

   * **路徑**
      * 使用「路徑選擇器」選項，在AEM中選取路徑
      * 如果路徑不在AEM中，請使用絕對URL。 非絕對路徑會相對於AEM進行解譯。

      * **替代**
文本路徑目標的替代說明
      * **目標**
         * **相同標籤**
         * **新標籤**
         * **父框架**
         * **上框架**

   點選或按一下要儲存的藍色核取標籤、要取消的黑色x，以及紅色垃圾桶來刪除地圖。

   ![](/help/assets/chlimage_1-14.png)

* 重設縮放

   ![](/help/assets/chlimage_1-15.png)

   如果影像已經縮放，請使用此選項來重設縮放等級。

* 開啟縮放滑桿

   ![](/help/assets/chlimage_1-16.png)

   使用此選項可顯示滑塊以控制影像的縮放級別。

   ![](/help/assets/chlimage_1-17.png)

就地編輯器也可用於修改影像。 由於空間限制，只有基本選項串聯可用。 如需完整編輯選項，請使用全螢幕模式。

![](/help/assets/chlimage_1-18.png)

>[!NOTE]
>
>GIF影像不支援影像編輯作業（裁切、翻轉、旋轉）。 在編輯模式下對GIF所做的任何此類更改都不會持續存在。

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者定義內容作者使用此元件時的裁切、上傳和旋轉上傳。

### 主要 {#main}

在&#x200B;**Main**&#x200B;標籤上，您可以定義允許寬度的清單（以像素為單位），以便自動從清單中載入最合適的寬度。

![](/help/assets/chlimage_1-51.png)

點選或按一下「新增」按鈕以新增其他大小。

* 使用抓握手柄重新排列尺寸順序。
* 使用刪除表徵圖可移除寬度。

依預設，影像載入會延遲至可見為止。 選取「停用延遲載入&#x200B;**」選項，以在頁面載入時載入影像。**

### 功能 {#features}

在&#x200B;**功能**&#x200B;標籤上，您可以定義當使用元件時，內容作者可使用哪些選項，包括上傳選項、方向和裁切選項。

* 來源

   ![](/help/assets/chlimage_1-19.png)

   選取「允許資產從檔案系統上傳」選項&#x200B;**，允許內容作者從本機電腦上傳影像。**&#x200B;若要強制內容作者僅從AEM選取資產，請取消選取此選項。

* 方向

   ![](/help/assets/chlimage_1-20.png)

   * **旋轉** -使用此選項可讓內容作者使用「旋轉 **右** 鍵」。
   * **反向(**
Flip)使用此選項可讓內容作者使用 
**「水準** 翻轉」和「垂直 **翻** 轉」選項。
   >[!CAUTION]
   >
   >預設情況下，**Flip**&#x200B;選項被禁用。 啟用此功能後，會在影像元件的編輯對話方塊中顯示&#x200B;**垂直翻轉**&#x200B;和&#x200B;**水準翻轉**&#x200B;按鈕，但AEM目前不支援此功能，而且使用這些選項所做的任何變更都不會持續存在。

* 裁切

   ![](/help/assets/chlimage_1-21.png)

   選擇「允許裁切」選項&#x200B;**，允許內容作者在編輯對話框的元件中裁切影像。**
   * 按一下&#x200B;**添加**&#x200B;添加預定義的裁切外觀比例。
   * 輸入描述性名稱，該名稱將顯示在&#x200B;**開始裁切**&#x200B;下拉式清單中。
   * 輸入長寬的數值比。
   * 使用拖動控制滑塊重新排列長寬比順序
   * 使用垃圾桶圖示來刪除外觀比例。

   >[!CAUTION]
   >
   >請注意，在AEM中，裁切長寬比的定義為&#x200B;**height/width**。 這與傳統的寬度／高度定義不同，而且是基於舊有相容性的原因。 只要您提供清楚的比率名稱，內容作者就不會察覺到任何差異，因為該名稱會顯示在UI中，而非比率本身。

## 技術詳細資訊{#technical-details}

有關映像元件[的最新技術文檔可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v1/image)上找到。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。
