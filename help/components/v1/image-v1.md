---
title: 影像元件(v1)
description: 核心元件影像元件是自我調整影像元件，具備就地編輯的功能。
index: n
role: Architect, Developer, Admin, User
exl-id: 625ce8de-5c4a-476d-b749-895493d169b1
source-git-commit: 5f25aee6ebcb7a5c6b8db0df5b8b853f15af97d0
workflow-type: tm+mt
source-wordcount: '1293'
ht-degree: 2%

---

# 影像元件(v1) {#image-component-v}

核心元件影像元件是自我調整影像元件，具備就地編輯的功能。

## 使用情況 {#usage}

影像元件可讓您輕鬆放置影像資產，並就地編輯。 它具有帶有延遲載入的自我調整影像選擇，以及內容作者的裁切。

範本作者可以在[設計對話方塊](#design-dialog)中定義允許的影像寬度以及裁切和其他設定。 內容編輯者可以在[設定對話方塊](#configure-dialog)上傳或選取資產，並在[編輯對話方塊](#edit-dialog)裁切影像。 為了增加便利性，您也可以簡單地就地修改影像。

## 版本和相容性 {#version-and-compatibility}

本檔案說明影像元件v1，其最初隨附於AEM 6.3的核心元件1.0.0版引入。

下表列出影像元件v1的相容性。

| AEM 版本 | 影像元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明影像元件v1。
>
>如需目前版本的影像元件的詳細資訊，請參閱[影像元件](/help/components/image.md)檔案。

## 範例元件輸出 {#sample-component-output}

以下是從[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)中取得的範例。

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
>從核心元件匯出JSON需要版本1.1.0的核心元件。 如需詳細資訊，請參閱核心元件v1](/help/versions.md)的[相容性資訊。

## 設定對話方塊 {#configure-dialog}

除了標準[編輯對話方塊](#edit-dialog)和[設計對話方塊](#design-dialog)之外，影像元件還提供設定對話方塊，其中影像本身與其描述和基本屬性一起定義。

![](/help/assets/chlimage_1-50.png)

* **影像資產**
   * 從[資產瀏覽器](https://helpx.adobe.com/experience-manager/6-3/sites/authoring/using/author-environment-tools.html#main-pars_title)拖放資產，或點選&#x200B;**瀏覽**&#x200B;選項，以從本機檔案系統上傳。
   * 點選或按一下&#x200B;**清除**&#x200B;以取消選取目前選取的影像。
   * 點選或按一下&#x200B;**編輯**&#x200B;以[在資產編輯器中管理資產](https://helpx.adobe.com/experience-manager/6-3/assets/using/managing-assets-touch-ui.html#main-pars_title_19)的轉譯。

* **影像為裝飾性** — 檢查輔助技術是否應忽略影像，因此不需要替代文字。 這僅適用於裝飾性影像。
* **替代文字** — 影像含義或功能的替代文字，適用於視障讀者。
* **連結**
   * 將影像連結至其他資源。
   * 使用選取對話方塊可連結至其他AEM資源。
   * 如果未連結至AEM資源，請輸入絕對URL。 非絕對URL將會解譯為相對於AEM。

* **標題** — 影像的其他相關資訊，預設會顯示於影像下方。
* **以快顯視窗顯示註解** -   檢查完畢後，註解不會顯示在影像下方，但如在某些瀏覽器中將滑鼠懸停在影像上，註解會以快顯模式顯示。

## 編輯對話方塊 {#edit-dialog}

此編輯對話方塊可讓內容作者裁切、修改啟動地圖及縮放影像。

![](/help/assets/chlimage_1-8.png)

* 開始裁切

  ![](/help/assets/chlimage_1-9.png)

  選取此選項會開啟預先定義裁切比例的下拉式清單。

   * 選擇選項&#x200B;**手繪**&#x200B;來定義您自己的裁切。
   * 選擇選項&#x200B;**移除裁切**&#x200B;以顯示原始資產。

  選取裁切選項後，請使用藍色控點來調整影像上的裁切大小。

  ![](/help/assets/chlimage_1-10.png)

* 向右旋轉

  ![](/help/assets/chlimage_1-11.png)

  使用此選項可將影像向右（順時針）旋轉90°。

* 啟動地圖

  ![](/help/assets/chlimage_1-12.png)

  使用此選項將啟動地圖套用至影像。 選取此選項會開啟一個新視窗，讓使用者選取地圖的形狀：

   * **新增矩形地圖**
   * **新增圓形地圖**
   * **新增多邊形地圖**

      * 依預設，會新增三角形地圖。 連按兩下圖案的線條，在新的一側加入新的藍色調整大小控點。

  選取地圖形狀後，它就會疊加在影像上，允許調整大小。 拖放藍色調整大小控點以調整形狀。

  ![](/help/assets/chlimage_1-13.png)

  調整啟動地圖的大小後，按一下它可開啟浮動工具列以定義連結的路徑。

   * **路徑**
      * 使用路徑選擇器選項可在AEM中選取路徑
      * 如果路徑不在AEM中，請使用絕對URL。 非絕對路徑將解譯為相對於AEM。

      * **替代文字**
路徑目的地的替代說明
      * **目標**
         * **相同標籤**
         * **新索引標籤**
         * **父框架**
         * **上框架**

  點選或按一下藍色核取記號即可儲存，點選或按一下黑色x可取消，點選或按一下紅色垃圾桶可刪除地圖。

  ![](/help/assets/chlimage_1-14.png)

* 重設縮放

  ![](/help/assets/chlimage_1-15.png)

  如果影像已經縮放，請使用此選項來重設縮放等級。

* 開啟縮放滑桿

  ![](/help/assets/chlimage_1-16.png)

  使用此選項可顯示控制影像縮放等級的滑桿。

  ![](/help/assets/chlimage_1-17.png)

就地編輯器也可用於修改影像。 由於空間限制，僅基本選項內嵌。 如需完整的編輯選項，請使用全熒幕模式。

![](/help/assets/chlimage_1-18.png)

>[!NOTE]
>
>GIF影像不支援影像編輯操作（裁切、翻轉、旋轉）。 在編輯模式下對GIF所做的任何此類變更都不會持續存在。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者在使用此元件時，定義內容作者的裁切、上傳和輪換上傳。

### 主要 {#main}

在&#x200B;**主要**&#x200B;標籤上，您可以定義允許的寬度（以畫素為單位）清單，讓影像從清單中自動載入最適當的寬度。

![](/help/assets/chlimage_1-51.png)

點選或按一下「新增」按鈕以新增其他大小。

* 使用抓取操作框來重新排列大小。
* 使用刪除圖示可移除寬度。

依預設，影像載入會延遲到影像可見為止。 選取選項&#x200B;**停用延遲載入**&#x200B;以在頁面載入時載入影像。

* **啟用Web最佳化影像** — 勾選後，[Web最佳化影像傳送服務](/help/developing/web-optimized-image-delivery.md)將以WebP格式傳送影像，平均將影像大小減少25%。
   * 此選項僅在AEMaaCS中可用。
   * 取消勾選或Web最佳化的影像傳遞服務無法使用時，會使用[最適化影像Servlet](/help/developing/adaptive-image-servlet.md)。

### 功能 {#features}

在&#x200B;**功能**&#x200B;標籤上，您可以定義在使用元件時內容作者可用的選項，包括上傳選項、方向以及裁切選項。

* **啟用Web最佳化影像** — 選取後，Web最佳化影像傳送服務會傳送WebP格式的影像，平均將影像大小減少25%。
   * 此選項僅在AEMaaCS中可用。
   * 取消勾選或Web最佳化的影像傳遞服務無法使用時，會使用[最適化影像Servlet](/help/developing/adaptive-image-servlet.md)。

* 來源

  ![](/help/assets/chlimage_1-19.png)

  選取選項&#x200B;**允許從檔案系統上傳資產**，以允許內容作者從其本機電腦上傳影像。 若要強制內容作者僅從AEM中選取資產，請取消選取此選項。

* 方向

  ![](/help/assets/chlimage_1-20.png)

   * **旋轉** — 使用此選項可允許內容作者使用&#x200B;**向右旋轉**&#x200B;選項。
   * **翻轉**
使用此選項可允許內容作者使用**水準翻轉**&#x200B;和&#x200B;**垂直翻轉**&#x200B;選項。

  >[!CAUTION]
  >
  >**Flip**&#x200B;選項預設為停用。 啟用此選項會在影像元件的編輯對話方塊中顯示&#x200B;**垂直翻轉**&#x200B;和&#x200B;**水準翻轉**&#x200B;按鈕，但AEM目前不支援此功能，且不會保留使用這些選項所做的任何變更。

* 裁切

  ![](/help/assets/chlimage_1-21.png)

  選取選項&#x200B;**允許裁切**，以允許內容作者在編輯對話方塊中裁切元件中的影像。
   * 按一下「新增&#x200B;****」以新增預先定義的裁切外觀比例。
   * 輸入描述性名稱，此名稱將顯示在&#x200B;**開始裁切**&#x200B;下拉式清單中。
   * 輸入外觀的數字比例。
   * 使用拖曳操作框來重新排列長寬比
   * 使用垃圾桶圖示可刪除外觀比例。

  >[!CAUTION]
  >
  >請注意，在AEM中，裁切外觀比例定義為&#x200B;**高度/寬度**。 這和寬度/高度比的傳統定義不同，並且是由於舊有相容性的原因完成的。只要您提供明確的比率名稱，內容作者就不會察覺任何差異，因為該名稱會顯示在UI中，而非比率本身。

## 技術細節 {#technical-details}

在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v1/image)上可找到有關影像元件[的最新技術檔案。

您可以從GitHub下載整個核心元件專案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。
