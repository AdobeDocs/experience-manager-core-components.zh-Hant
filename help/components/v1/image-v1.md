---
title: 影像元件(v1)
description: 核心元件影像元件是最適化影像元件，具備就地編輯的功能。
index: n
role: Architect, Developer, Admin, User
exl-id: 625ce8de-5c4a-476d-b749-895493d169b1
source-git-commit: 5f25aee6ebcb7a5c6b8db0df5b8b853f15af97d0
workflow-type: tm+mt
source-wordcount: '1323'
ht-degree: 1%

---

# 影像元件(v1) {#image-component-v}

核心元件影像元件是最適化影像元件，具備就地編輯的功能。

## 使用狀況 {#usage}

影像元件可讓您輕鬆放置影像資產，並就地編輯。 此版本提供具延遲載入功能的自我調整影像選擇，以及為內容作者裁切。

範本作者可以在中定義允許的影像寬度以及裁切和其他設定。 [設計對話方塊](#design-dialog). 內容編輯者可以上傳或選取 [設定對話方塊](#configure-dialog) 並裁切影像 [編輯對話方塊](#edit-dialog). 為了增加便利性，您也可以使用簡單的影像就地修改。

## 版本和相容性 {#version-and-compatibility}

本檔案說明影像元件v1，其最初隨附於AEM 6.3的核心元件1.0.0版引入。

下表列出影像元件v1的相容性。

| AEM版本 | 影像元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明影像元件v1。
>
>如需目前版本的影像元件的詳細資訊，請參閱 [影像元件](/help/components/image.md) 檔案。

## 範例元件輸出 {#sample-component-output}

以下是取自下列專案的範例： [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

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
>從核心元件匯出JSON需要核心元件1.1.0版。 請參閱 [核心元件v1的相容性資訊](/help/versions.md) 以取得詳細資訊。

## 設定對話方塊 {#configure-dialog}

除了標準 [編輯對話方塊](#edit-dialog) 和 [設計對話方塊](#design-dialog)，影像元件會提供「設定」對話方塊，其中會定義影像本身及其說明和基本屬性。

![](/help/assets/chlimage_1-50.png)

* **影像資產**
   * 從拖放資產 [資產瀏覽器](https://helpx.adobe.com/experience-manager/6-3/sites/authoring/using/author-environment-tools.html#main-pars_title) 或點選 **瀏覽** 從本機檔案系統上傳的選項。
   * 點選或按一下 **清除** 以取消選取目前選取的影像。
   * 點選或按一下 **編輯** 至 [管理資產的轉譯](https://helpx.adobe.com/experience-manager/6-3/assets/using/managing-assets-touch-ui.html#main-pars_title_19) 在資產編輯器中。

* **裝飾性影像**  — 檢查輔助技術是否應忽略影像，因此不需要替代文字。 這僅適用於裝飾性影像。
* **替代文字**  — 影像含義或功能的替代文字，適用於視障讀者。
* **連結**
   * 將影像連結至其他資源。
   * 使用選取對話方塊來連結至其他AEM資源。
   * 如果未連結至AEM資源，請輸入絕對URL。 非解決方案URL將解譯為相對於AEM。

* **註解**  — 影像的其他相關資訊，預設顯示在影像下方。
* **以快顯視窗顯示註解**  — 檢查完畢後，註解不會顯示在影像下方，但如在某些瀏覽器中將滑鼠懸停在影像上，註解會以快顯模式顯示。

## 編輯對話方塊 {#edit-dialog}

內容作者可以使用「編輯」對話方塊裁切、修改啟動地圖及縮放影像。

![](/help/assets/chlimage_1-8.png)

* 開始裁切

   ![](/help/assets/chlimage_1-9.png)

   選取此選項會開啟預先定義裁切比例的下拉式清單。

   * 選擇選項 **手繪** 以定義您自己的裁切。
   * 選擇選項 **移除裁切** 以顯示原始資產。

   選取裁切選項後，請使用藍色控點來調整影像上的裁切大小。

   ![](/help/assets/chlimage_1-10.png)

* 向右旋轉

   ![](/help/assets/chlimage_1-11.png)

   使用此選項可將影像向右（順時針）旋轉90°。

* 啟動地圖

   ![](/help/assets/chlimage_1-12.png)

   使用此選項可將啟動地圖套用至影像。 選取此選項會開啟一個新視窗，讓使用者選取地圖的形狀：

   * **新增矩形地圖**
   * **新增圓形地圖**
   * **新增多邊形地圖**

      * 依預設，會新增三角形地圖。 連按兩下形狀的一條線可在新的一側新增新的藍色調整大小操作框。

   選取地圖形狀後，它就會疊加在影像上，允許調整大小。 拖放藍色調整大小控點以調整形狀。

   ![](/help/assets/chlimage_1-13.png)

   調整啟動地圖的大小後，按一下它可開啟浮動工具列以定義連結的路徑。

   * **路徑**
      * 使用路徑選擇器選項可在AEM中選取路徑
      * 如果路徑不在AEM中，請使用絕對URL。 非絕對路徑將解釋為相對於AEM。

      * **替代文字**
路徑目的地的替代說明
      * **目標**
         * **相同標籤**
         * **新索引標籤**
         * **父框架**
         * **上框架**

   點選或按一下藍色勾號可儲存，點選或按一下黑色x可取消，點選或按一下紅色垃圾桶可刪除地圖。

   ![](/help/assets/chlimage_1-14.png)

* 重設縮放

   ![](/help/assets/chlimage_1-15.png)

   如果影像已經縮放，請使用此選項來重設縮放等級。

* 開啟縮放滑桿

   ![](/help/assets/chlimage_1-16.png)

   使用此選項可顯示控制影像縮放等級的滑桿。

   ![](/help/assets/chlimage_1-17.png)

就地編輯器也可用來修改影像。 由於空間限制，僅基本選項內嵌提供。 如需完整編輯選項，請使用全熒幕模式。

![](/help/assets/chlimage_1-18.png)

>[!NOTE]
>
>GIF影像不支援影像編輯操作（裁切、翻轉、旋轉）。 在編輯模式下對GIF所做的任何此類變更都不會持續存在。

## 設計對話方塊 {#design-dialog}

使用「設計」對話方塊，範本作者可在使用此元件時定義內容作者的裁切、上傳和輪換上傳。

### 主要 {#main}

於 **主要** 索引標籤您可以定義允許的寬度清單（以畫素為單位），以便影像從清單中自動載入最適合的寬度。

![](/help/assets/chlimage_1-51.png)

點選或按一下「新增」按鈕以新增其他大小。

* 使用抓取控點來重新排列大小。
* 使用刪除圖示可移除寬度。

依預設，影像載入會延遲到它們變成可見為止。 選取選項 **停用延遲載入** 以在頁面載入時載入影像。

* **啟用Web最佳化的影像**  — 若勾選， [網頁最佳化的影像傳遞服務](/help/developing/web-optimized-image-delivery.md) 將以WebP格式傳送影像，平均將影像大小減少25%。
   * 此選項僅適用於AEMaaCS。
   * 取消勾選或Web最佳化的影像傳送服務無法使用時， [最適化影像Servlet](/help/developing/adaptive-image-servlet.md) 已使用。

### 功能 {#features}

於 **功能** 索引標籤您可以定義在使用元件時內容作者可用的選項，包括上傳選項、方向和裁切選項。

* **啟用Web最佳化的影像**  — 檢查完畢後，網頁最佳化的影像傳送服務會傳送WebP格式的影像，平均將影像大小減少25%。
   * 此選項僅適用於AEMaaCS。
   * 取消勾選或Web最佳化的影像傳送服務無法使用時， [最適化影像Servlet](/help/developing/adaptive-image-servlet.md) 已使用。

* 來源

   ![](/help/assets/chlimage_1-19.png)

   選取選項 **允許從檔案系統上傳資產** 允許內容作者從其本機電腦上傳影像。 若要強制內容作者僅從AEM中選取資產，請取消選取此選項。

* 方向

   ![](/help/assets/chlimage_1-20.png)

   * **旋轉**  — 使用此選項可允許內容作者使用 **向右旋轉** 選項。
   * **翻轉**
使用此選項可允許內容作者使用 
**水準翻轉** 和 **垂直翻轉** 選項。
   >[!CAUTION]
   >
   >此 **翻轉** 選項預設為停用。 啟用時將會顯示 **垂直翻轉** 和 **水準翻轉** 按鈕，但AEM目前不支援此功能，且不會保留使用這些選項所做的任何變更。

* 裁切

   ![](/help/assets/chlimage_1-21.png)

   選取選項 **允許裁切** 讓內容作者在「編輯」對話方塊中裁切元件中的影像。
   * 按一下 **新增** 以新增預先定義的裁切外觀比例。
   * 輸入描述性名稱，該名稱將顯示在 **開始裁切** 下拉式清單。
   * 輸入外觀的數字比例。
   * 使用拖曳操作框來重新排列長寬比
   * 使用垃圾桶圖示可刪除長寬比。

   >[!CAUTION]
   >
   >請注意，在AEM中，裁切比例定義為 **高度/寬度**. 這與傳統的寬度/高度定義不同，這樣做是出於舊版相容性的原因。 只要您提供明確的比率名稱，內容作者就不會察覺到任何差異，因為該名稱顯示在UI中，而不是比率本身。

## 技術細節 {#technical-details}

有關影像元件的最新技術檔案 [可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v1/image).

您可以從GitHub下載整個核心元件專案。

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).
