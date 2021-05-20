---
title: 影像元件(v1)
description: 核心元件影像元件是就地編輯的自適應影像元件功能。
index: n
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 625ce8de-5c4a-476d-b749-895493d169b1
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '1229'
ht-degree: 1%

---

# 影像元件(v1){#image-component-v}

核心元件影像元件是就地編輯的自適應影像元件功能。

## 使用狀況 {#usage}

影像元件可輕鬆放置影像資產和就地編輯選件。 此功能提供具有延遲載入的最適化影像選取，以及內容作者的裁切功能。

範本作者可在[design對話方塊](#design-dialog)中定義允許的影像寬度以及裁切和其他設定。 內容編輯器可以上傳或選取[設定對話方塊](#configure-dialog)中的資產，並在[編輯對話方塊](#edit-dialog)中裁切影像。 為了更方便，還可以簡單地就地修改影像。

## 版本和相容性{#version-and-compatibility}

本檔案說明影像元件v1，最初是透過AEM 6.3推出核心元件1.0.0版。

下表列出映像元件v1的相容性。

| AEM版本 | 影像元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明影像元件的v1。
>
>有關當前版本的影像元件的詳細資訊，請參閱[影像元件](/help/components/image.md)文檔。

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
>從核心元件匯出JSON需使用1.1.0版的核心元件。 如需詳細資訊，請參閱核心元件v1](/help/versions.md)的[相容性資訊。

## 配置對話框{#configure-dialog}

除了標準[edit dialog](#edit-dialog)和[design dialog](#design-dialog)之外，影像元件還提供配置對話框，在其中定義影像本身及其說明和基本屬性。

![](/help/assets/chlimage_1-50.png)

* **影像資產**
   * 從[資產瀏覽器](https://helpx.adobe.com/experience-manager/6-3/sites/authoring/using/author-environment-tools.html#main-pars_title)拖放資產，或點選&#x200B;**browse**&#x200B;選項，從本機檔案系統上傳。
   * 點選或按一下&#x200B;**清除**&#x200B;以取消選取目前選取的影像。
   * 點選或按一下「**編輯** 」，在資產編輯器中[管理資產](https://helpx.adobe.com/experience-manager/6-3/assets/using/managing-assets-touch-ui.html#main-pars_title_19)的轉譯。

* **影像是裝飾性的**  — 檢查影像是否應由輔助技術忽略，因此不需要替代文字。這僅適用於裝飾影像。
* **替代文字**  — 視覺障礙讀者影像意義或功能的文字替代項目。
* **連結**
   * 將影像連結至其他資源。
   * 使用選取對話方塊連結至其他AEM資源。
   * 如果未連結至AEM資源，請輸入絕對URL。 非溶質URL會解譯為相對於AEM。

* **註解**  — 預設會顯示影像下方的影像其他資訊。
* **將字幕顯示為快顯視窗**  — 若勾選此選項，字幕不會顯示在影像下方，但會顯示為將游標暫留在影像上時，由某些瀏覽器顯示的快顯視窗。

## 編輯對話框{#edit-dialog}

編輯對話方塊可讓內容作者裁切、修改啟動對映，以及縮放影像。

![](/help/assets/chlimage_1-8.png)

* 開始裁切

   ![](/help/assets/chlimage_1-9.png)

   選取此選項會開啟預先定義的裁切比例的下拉式清單。

   * 選擇選項&#x200B;**自由手**&#x200B;以定義您自己的裁切。
   * 選擇選項&#x200B;**移除裁切**&#x200B;以顯示原始資產。

   選取裁切選項後，使用藍色控點來調整影像上裁切的大小。

   ![](/help/assets/chlimage_1-10.png)

* 向右旋轉

   ![](/help/assets/chlimage_1-11.png)

   使用此選項將影像90°向右（順時針）旋轉。

* 啟動圖

   ![](/help/assets/chlimage_1-12.png)

   使用此選項可將啟動對應套用至影像。 選擇此選項將開啟一個新窗口，允許用戶選擇映射的形狀：

   * **新增矩形地圖**
   * **添加循環圖**
   * **添加多邊形映射**

      * 依預設，會新增三角形地圖。 按兩下形狀的一行，在新側添加新的藍色調整大小手柄。

   一旦選擇了映射形狀，該映射形狀被疊加在影像上以允許調整大小。 拖放藍色的調整大小手柄以調整形狀。

   ![](/help/assets/chlimage_1-13.png)

   調整啟動對映大小後，按一下地圖以開啟浮動工具列以定義連結的路徑。

   * **路徑**
      * 使用「路徑選擇器」選項在AEM中選取路徑
      * 如果路徑不在AEM中，請使用絕對URL。 非絕對路徑會相對於AEM來解譯。

      * **替**
代文本路徑目標的替代說明
      * **目標**
         * **相同標籤**
         * **新標籤**
         * **父框架**
         * **上框架**

   點選或按一下藍色勾號以儲存、黑色x以取消，紅色垃圾桶可以刪除地圖。

   ![](/help/assets/chlimage_1-14.png)

* 重設縮放

   ![](/help/assets/chlimage_1-15.png)

   如果影像已縮放，則使用此選項來重設縮放等級。

* 開啟縮放滑桿

   ![](/help/assets/chlimage_1-16.png)

   使用此選項可顯示滑塊以控制影像的縮放級別。

   ![](/help/assets/chlimage_1-17.png)

就地編輯器也可用來修改影像。 由於空間限制，只有基本選項可在內使用。 如需完整編輯選項，請使用全螢幕模式。

![](/help/assets/chlimage_1-18.png)

>[!NOTE]
>
>GIF影像不支援影像編輯操作（裁切、翻轉、旋轉）。 在編輯模式中對GIF所做的任何此類變更都不會持續存在。

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者定義使用此元件時，內容作者所具有的裁切、上傳和旋轉上傳。

### 主要 {#main}

在&#x200B;**Main**&#x200B;頁簽上，您可以定義允許的寬度清單（以像素表示），以便從清單自動載入最合適的寬度。

![](/help/assets/chlimage_1-51.png)

點選或按一下「新增」按鈕以新增其他大小。

* 使用抓握手柄重新排列大小的順序。
* 使用刪除圖示來移除寬度。

依預設，載入影像會延遲，直到變成可見為止。 選取選項&#x200B;**停用延遲載入**&#x200B;以在頁面載入時載入影像。

### 功能 {#features}

在&#x200B;**Features**&#x200B;標籤上，您可以定義使用元件時，內容作者可使用的選項，包括上傳選項、方向和裁切選項。

* 來源

   ![](/help/assets/chlimage_1-19.png)

   選取「允許從檔案系統上傳資產&#x200B;**」選項，允許內容作者從其本機電腦上傳影像。**&#x200B;若要強制內容作者僅從AEM選取資產，請取消選取此選項。

* 方向

   ![](/help/assets/chlimage_1-20.png)

   * **旋轉**  — 使用此選項可讓內容作者使用「旋轉 **右** 鍵」。
   * ****
反向使用此選項可允許內容作者使用 
**「水準** 翻轉」和「垂直 **翻** 轉」選項。
   >[!CAUTION]
   >
   >預設情況下禁用&#x200B;**Flip**&#x200B;選項。 啟用後，將在影像元件的編輯對話方塊中顯示&#x200B;**垂直翻轉**&#x200B;和&#x200B;**水準翻轉**&#x200B;按鈕，但AEM目前不支援此功能，且使用這些選項所做的任何變更都不會持續存在。

* 裁切

   ![](/help/assets/chlimage_1-21.png)

   選取「**允許裁切**」選項，以允許內容作者在編輯對話方塊中裁切元件中的影像。
   * 按一下&#x200B;**Add**&#x200B;以新增預先定義的裁切長寬比。
   * 輸入描述性名稱，該名稱將顯示在&#x200B;**開始裁切**&#x200B;下拉式清單中。
   * 輸入外觀的數值比。
   * 使用拖動控制滑塊重新排列縱橫比的順序
   * 使用垃圾桶圖示來刪除外觀比例。

   >[!CAUTION]
   >
   >請注意，在AEM中，裁切長寬比定義為&#x200B;**height/width**。 這與傳統的寬度/高度定義不同，因為舊版相容性原因而完成。 只要您提供比例的明確名稱，內容作者就不會察覺任何差異，因為該名稱會顯示在UI中，而非比例本身。

## 技術詳細資訊{#technical-details}

您可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v1/image)上找到影像元件[的最新技術檔案。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。
