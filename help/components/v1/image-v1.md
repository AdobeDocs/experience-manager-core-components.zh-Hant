---
title: 影像元件 (v1)
description: 核心元件影像元件是具備就地編輯功能的最適化影像元件。
index: n
role: Architect, Developer, Admin, User
exl-id: 625ce8de-5c4a-476d-b749-895493d169b1
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '1293'
ht-degree: 100%

---


# 影像元件 (v1) {#image-component-v}

核心元件影像元件是具備就地編輯功能的最適化影像元件。

## 用途 {#usage}

影像元件可讓您輕鬆放置影像資產，並提供就地編輯。它具備搭載延遲載入的最適化影像選擇，以及內容作者可用的裁切功能。

範本作者可以使用[設計對話框](#design-dialog)定義允許的影像寬度、裁切和其他設定。內容編輯者可在[設定對話框](#configure-dialog)中上傳或選取資產，並在[編輯對話框](#edit-dialog)中裁切影像。為了增加便利性，也提供簡易的影像就地修改功能。

## 版本和相容性 {#version-and-compatibility}

本文件說明影像元件 v1，最初由 AEM 6.3 搭配的核心元件 1.0.0 版導入。

下表列出影像元件 v1 的相容性。

| AEM 版本 | 影像元件 v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本文件說明影像元件 v1。
>
>如需影像元件目前版本的詳細資訊，請參閱[影像元件](/help/components/image.md)文件。

## 範例元件輸出 {#sample-component-output}

以下是從 [We.Retail](https://helpx.adobe.com/tw/experience-manager/6-4/sites/developing/using/we-retail.html) 中取得的範例。

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
>從核心元件匯出 JSON 需要核心元件 1.1.0 版。如需詳細資訊，請參閱[核心元件 v1 的相容性資訊](/help/versions.md)。

## 設定對話框 {#configure-dialog}

除了標準[編輯對話框](#edit-dialog)和[設計對話框](#design-dialog)之外，「影像元件」還提供設定對話框，其中定義影像本身及其說明和基本屬性。

![](/help/assets/chlimage_1-50.png)

* **影像資產**
   * 從[資產瀏覽器](https://helpx.adobe.com/tw/experience-manager/6-3/sites/authoring/using/author-environment-tools.html#main-pars_title)拖曳資產，或點選&#x200B;**瀏覽**&#x200B;選項，以從本機檔案系統上傳。
   * 點選或按一下&#x200B;**「清除」**，取消選取目前選取的影像。
   * 點選或按一下&#x200B;**編輯**，以在 Asset Editor 中[管理資產的轉譯](https://helpx.adobe.com/tw/experience-manager/6-3/assets/using/managing-assets-touch-ui.html#main-pars_title_19)。

* **影像為裝飾性** - 若輔助技術可忽略該影像，因此不需要替代文字時，請勾選此選項。這僅適用於裝飾性影像。
* **替代文字** - 影像功能或含意的替代文字，以供有視覺障礙的讀者閱讀。
* **連結**
   * 將影像連結至其他資源。
   * 使用選取對話框可連結至其他 AEM 資源。
   * 如果未連結至 AEM 資源，請輸入絕對 URL。非絕對 URL 將解釋為相對於 AEM。

* **註解** - 影像的其他相關資訊，預設會顯示於影像下方。
* **以快顯視窗顯示註解** - 勾選後，註解不會顯示在影像下方，但如在某些瀏覽器中將游標停留在影像上，註解會以快顯視窗顯示。

## 編輯對話框 {#edit-dialog}

此編輯對話框可讓內容作者裁切、修改啟動地圖及縮放影像。

![](/help/assets/chlimage_1-8.png)

* 開始裁切

  ![](/help/assets/chlimage_1-9.png)

  選取此選項會開啟預先定義裁切比例的下拉式清單。

   * 選擇&#x200B;**手繪**&#x200B;選項來定義您自己的裁切。
   * 選擇&#x200B;**移除裁切**&#x200B;選項以顯示原始資產。

  選取裁切選項後，請使用藍色控點來調整影像上的裁切大小。

  ![](/help/assets/chlimage_1-10.png)

* 向右旋轉

  ![](/help/assets/chlimage_1-11.png)

  使用此選項可將影像向右 (順時針) 旋轉 90°。

* 啟動地圖

  ![](/help/assets/chlimage_1-12.png)

  使用此選項將啟動地圖套用至影像。選取此選項會開啟一個新視窗，讓使用者選取地圖的形狀：

   * **新增矩形地圖**
   * **新增圓形地圖**
   * **新增多邊形地圖**

      * 預設情況下，會新增三角形地圖。連按兩下圖案的邊線，即可在新的邊上加入新的藍色調整大小控點。

  選取地圖形狀後，它就會疊加在影像上，允許調整大小。拖放藍色調整大小控點以調整形狀。

  ![](/help/assets/chlimage_1-13.png)

  調整啟動地圖的大小後，按一下它可開啟浮動工具列以定義連結的路徑。

   * **路徑**
      * 使用路徑挑選器選項可在 AEM 中選取路徑
      * 如果路徑不在 AEM 中，請使用絕對 URL。非絕對路徑將解釋為相對於 AEM。

      * **替代文字**
路徑目的地的替代說明
      * **Target**
         * **相同索引標籤**
         * **新索引標籤**
         * **上層框架**
         * **上框架**

  點選或按一下藍色核取記號即可儲存，點選或按一下黑色 x 可取消，點選或按一下紅色垃圾桶可刪除地圖。

  ![](/help/assets/chlimage_1-14.png)

* 重設縮放

  ![](/help/assets/chlimage_1-15.png)

  如果影像已經縮放，請使用此選項來重設縮放等級。

* 開啟縮放滑桿

  ![](/help/assets/chlimage_1-16.png)

  使用此選項可顯示控制影像縮放等級的滑桿。

  ![](/help/assets/chlimage_1-17.png)

就地編輯器也可用於修改影像。由於空間限制，僅基本選項內嵌。如需完整的編輯選項，請使用全螢幕模式。

![](/help/assets/chlimage_1-18.png)

>[!NOTE]
>
>不支援 GIF 影像的影像編輯操作 (裁切、翻轉、旋轉)。在編輯模式下對 GIF 所做的任何此類變更將不會保留。

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可定義內容作者使用此元件時所具備的裁切、上傳和旋轉上傳功能。

### 主要 {#main}

在&#x200B;**主要**&#x200B;索引標籤上，您可以定義影像的寬度 (以像素為單位) 清單，以根據清單自動載入最適當的寬度。

![](/help/assets/chlimage_1-51.png)

點選或按一下「新增」按鈕以新增其他大小。

* 使用抓取控點，以重新排列大小的順序。
* 使用刪除圖示來移除寬度。

根據預設，影像載入會延遲到影像可見為止。選取&#x200B;**停用延遲載入**&#x200B;選項，以便在頁面載入時載入影像。

* **啟用網頁最佳化影像** - 勾選後，[網頁最佳化影像傳遞服務](/help/developing/web-optimized-image-delivery.md)會以 WebP 格式傳送影像，平均將影像大小減少 25%。
   * 此選項僅在 AEMaaCS 中可用。
   * 取消勾選或無法使用網頁最佳化影像傳遞服務時，會使用[最適化影像 Servlet](/help/developing/adaptive-image-servlet.md)。

### 功能 {#features}

在&#x200B;**功能**&#x200B;索引標籤上，您可以定義內容作者在使用元件時可用的選項，包括上傳選項、方向以及裁切選項。

* **啟用網頁最佳化影像** - 勾選後，網頁最佳化影像傳遞服務會以 WebP 格式傳送影像，平均將影像大小減少 25%。
   * 此選項僅在 AEMaaCS 中可用。
   * 取消勾選或無法使用網頁最佳化影像傳遞服務時，會使用[最適化影像 Servlet](/help/developing/adaptive-image-servlet.md)。

* 來源

  ![](/help/assets/chlimage_1-19.png)

  選取&#x200B;**允許從檔案系統上傳資產**&#x200B;選項，以允許內容作者從其本機電腦上傳影像。若要強制內容作者僅從 AEM 中選取資產，請取消選取此選項。

* 方向

  ![](/help/assets/chlimage_1-20.png)

   * **旋轉** - 使用此選項可允許內容作者使用&#x200B;**向右旋轉**&#x200B;選項。
   * **翻轉**
使用此選項可允許內容作者使用**水平翻轉**&#x200B;和&#x200B;**垂直翻轉**&#x200B;選項。

  >[!CAUTION]
  >
  >**翻轉**&#x200B;選項預設為停用。啟用此選項會在影像元件的編輯對話框中顯示&#x200B;**垂直翻轉**&#x200B;和&#x200B;**水平翻轉**&#x200B;按鈕，但 AEM 目前不支援此功能，因此不會保留使用這些選項所做的任何變更。

* 裁切

  ![](/help/assets/chlimage_1-21.png)

  選取&#x200B;**允許裁切**&#x200B;選項以允許內容作者在編輯對話框中裁切元件中的影像。
   * 按一下&#x200B;**新增**&#x200B;以新增預先定義的裁切外觀比例。
   * 輸入描述性名稱，此名稱將顯示在&#x200B;**開始裁切**&#x200B;下拉式清單中。
   * 輸入外觀的數字比例。
   * 使用拖曳控點來重新排列外觀比例
   * 使用垃圾桶圖示可刪除外觀比例。

  >[!CAUTION]
  >
  >請注意，在 AEM 中，裁切外觀比例定義為&#x200B;**高度/寬度**。這和寬度/高度比的傳統定義不同，主要是為了維持與舊版系統的相容性。只要您提供明確的比例名稱，內容作者就不會察覺任何差異，因為該名稱會顯示在 UI 中，而非比例本身。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v1/image)有關影像元件的最新技術文件。

您可以從 GitHub 下載完整的核心元件專案。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。
