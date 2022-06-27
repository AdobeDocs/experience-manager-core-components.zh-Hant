---
title: 影像元件(v1)
description: 核心元件影像元件是自適應影像元件特徵就地編輯。
index: n
role: Architect, Developer, Admin, User
exl-id: 625ce8de-5c4a-476d-b749-895493d169b1
source-git-commit: 5f25aee6ebcb7a5c6b8db0df5b8b853f15af97d0
workflow-type: tm+mt
source-wordcount: '1323'
ht-degree: 1%

---

# 影像元件(v1) {#image-component-v}

核心元件影像元件是自適應影像元件特徵就地編輯。

## 使用狀況 {#usage}

「影像元件」允許輕鬆放置影像資產，並提供就地編輯。 該方法具有自適應影像選擇和緩慢載入以及裁剪內容作者的特點。

允許的影像寬度以及裁剪和附加設定可由模板作者在 [設計對話框](#design-dialog)。 內容編輯器可以在 [配置對話框](#configure-dialog) 並在 [編輯對話框](#edit-dialog)。 為了更方便，還提供了影像的簡單就地修改。

## 版本和相容性 {#version-and-compatibility}

本文檔介紹了最初隨帶有6.3的核心元件1.0.0版而引AEM入的映像元件v1。

下表列出了映像元件v1的相容性。

| 版AEM本 | 影像元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本文檔介紹「影像元件」的v1。
>
>有關當前版本的映像元件的詳細資訊，請參閱 [影像元件](/help/components/image.md) 的子菜單。

## 元件輸出示例 {#sample-component-output}

以下是從 [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>從核心元件導出JSON需要1.1.0版核心元件。 請參閱 [核心元件v1的相容性資訊](/help/versions.md) 的子菜單。

## 配置對話框 {#configure-dialog}

除了 [編輯對話框](#edit-dialog) 和 [設計對話框](#design-dialog)，影像元件提供一個配置對話框，其中定義了影像本身及其說明和基本屬性。

![](/help/assets/chlimage_1-50.png)

* **影像資產**
   * 從 [資產瀏覽器](https://helpx.adobe.com/experience-manager/6-3/sites/authoring/using/author-environment-tools.html#main-pars_title) 或點擊 **瀏覽** 從本地檔案系統上載。
   * 點擊或按一下 **清除** 來取消選擇當前選定的映像。
   * 點擊或按一下 **編輯** 至 [管理資產的格式副本](https://helpx.adobe.com/experience-manager/6-3/assets/using/managing-assets-touch-ui.html#main-pars_title_19) 的子菜單。

* **影像是裝飾性的**  — 檢查影像是否應被輔助技術忽略，因此不需要替代文本。 這僅適用於裝飾性影像。
* **備選文本**  — 視障讀者對影像含義或功能的文字選擇。
* **連結**
   * 將映像連結到其他資源。
   * 使用選擇對話框連結到另AEM一資源。
   * 如果未連結到AEM資源，請輸入絕對URL。 非溶質URL將被解釋為相對於AEM。

* **標題**  — 預設顯示在影像下方的有關影像的其他資訊。
* **將標題顯示為彈出窗口**  — 選中後，標題不會顯示在影像下方，而是當懸停在影像上方時，由某些瀏覽器顯示的彈出窗口。

## 編輯對話框 {#edit-dialog}

編輯對話框允許內容作者裁剪、修改啟動映射和縮放影像。

![](/help/assets/chlimage_1-8.png)

* 開始裁剪

   ![](/help/assets/chlimage_1-9.png)

   選擇此選項將開啟預定義裁剪比例的下拉框。

   * 選擇選項 **自由手** 來定義自己的作物。
   * 選擇選項 **刪除裁剪** 顯示原始資產。

   選擇裁剪選項後，使用藍色手柄來調整影像上的裁剪大小。

   ![](/help/assets/chlimage_1-10.png)

* 向右旋轉

   ![](/help/assets/chlimage_1-11.png)

   使用此選項將影像向右（順時針）旋轉90°。

* 啟動映射

   ![](/help/assets/chlimage_1-12.png)

   使用此選項可將啟動映射應用於影像。 選擇此選項將開啟一個新窗口，允許用戶選擇映射的形狀：

   * **添加矩形映射**
   * **添加循環映射**
   * **添加多邊形映射**

      * 預設情況下，添加三角形映射。 按兩下形狀的一行，在新側添加新的藍色調整手柄。

   一旦選擇了映射形狀，它就被疊加在影像上，允許調整大小。 拖放藍色大小調整手柄以調整形狀。

   ![](/help/assets/chlimage_1-13.png)

   調整啟動映射的大小後，按一下它以開啟浮動工具欄以定義連結的路徑。

   * **路徑**
      * 使用「路徑選取器」選項選擇AEM中
      * 如果路徑未在AEM中，請使用絕對URL。 非絕對路徑將相對於進行解AEM釋。

      * **替代文字**
路徑目標的替代說明
      * **目標**
         * **相同頁籤**
         * **新建頁籤**
         * **父框架**
         * **上框架**

   點擊或按一下要保存的藍色複選標籤、要取消的黑色x以及可刪除地圖的紅色垃圾。

   ![](/help/assets/chlimage_1-14.png)

* 重設縮放

   ![](/help/assets/chlimage_1-15.png)

   如果影像已縮放，則使用此選項重置縮放級別。

* 開啟縮放滑塊

   ![](/help/assets/chlimage_1-16.png)

   使用此選項可顯示滑塊以控制影像的縮放級別。

   ![](/help/assets/chlimage_1-17.png)

就地編輯器也可用於修改影像。 由於空間限制，只有基本選項可線上使用。 對於完全編輯選項，請使用全屏模式。

![](/help/assets/chlimage_1-18.png)

>[!NOTE]
>
>GIF影像不支援影像編輯操作（裁剪、翻轉、旋轉）。 在編輯模式下對GIF所做的任何此類更改都不會保留。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義內容作者在使用此元件時具有的裁剪、上載和旋轉上載。

### 主要 {#main}

在 **主** 頁籤，您可以定義允許的寬度清單（以像素為單位），以便影像自動從清單中載入最合適的寬度。

![](/help/assets/chlimage_1-51.png)

點擊或按一下「添加」按鈕添加其他大小。

* 使用抓握手柄重新排列大小的順序。
* 使用刪除表徵圖可刪除寬度。

預設情況下，將延遲載入影像，直到其可見。 選擇選項 **禁用延遲載入** 在載入頁面時載入影像。

* **啟用Web優化映像**  — 選中時， [Web優化的影像傳遞服務](/help/developing/web-optimized-image-delivery.md) 將以WebP格式提供影像，平均將影像大小減少25%。
   * 此選項僅在AEMaCS中可用。
   * 如果未選中或Web優化映像提供服務不可用， [自適應影像Servlet](/help/developing/adaptive-image-servlet.md) 的子菜單。

### 功能 {#features}

在 **功能** 頁籤，您可以定義在使用元件（包括上載選項、方向和裁剪選項）時內容作者可以使用的選項。

* **啟用Web優化映像**  — 選中後， Web優化的映像交付服務將以WebP格式提供映像，平均將映像大小減少25%。
   * 此選項僅在AEMaCS中可用。
   * 如果未選中或Web優化映像提供服務不可用， [自適應影像Servlet](/help/developing/adaptive-image-servlet.md) 的子菜單。

* 來源

   ![](/help/assets/chlimage_1-19.png)

   選擇選項 **允許從檔案系統上載資產** 允許內容作者從本地電腦上傳影像。 要強制內容作者僅從中選擇資AEM產，請取消選擇此選項。

* 方向

   ![](/help/assets/chlimage_1-20.png)

   * **旋轉**  — 使用此選項允許內容作者使用 **向右旋轉** 的雙曲餘切值。
   * **翻轉**
使用此選項允許內容作者使用 
**水準翻轉** 和 **垂直翻轉** 頁籤
   >[!CAUTION]
   >
   >的 **翻轉** 選項。 啟用它將顯示 **垂直翻轉** 和 **水準翻轉** 影像元件的「編輯」對話框中的按鈕，但當前不支援該功能AEM，並且不會保留使用這些選項所做的任何更改。

* 裁切

   ![](/help/assets/chlimage_1-21.png)

   選擇選項 **允許裁剪** 允許內容作者在「編輯」對話框的元件中裁剪影像。
   * 按一下 **添加** 添加預定義的裁剪縱橫比。
   * 輸入描述性名稱，該名稱將在 **開始裁剪** 下拉清單。
   * 輸入縱橫比。
   * 使用拖動手柄重新排列長寬比的順序
   * 使用垃圾桶表徵圖刪除縱橫比。

   >[!CAUTION]
   >
   >請注意，AEM在中，裁剪縱橫比定義為 **高度/寬度**。 這不同於傳統的寬度/高度定義，是出於傳統相容性原因。 只要您提供比率的明確名稱，內容作者就不會察覺到任何差異，因為該名稱顯示在UI中，而不是比率本身。

## 技術詳細資訊 {#technical-details}

有關映像元件的最新技術文檔 [可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v1/image)。

整個核心元件項目可從GitHub下載。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。
