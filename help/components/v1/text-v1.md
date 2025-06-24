---
title: 文字元件(v1)
description: 文字元件是RTF編輯和撰寫元件，具備就地編輯功能。
index: n
role: Architect, Developer, Admin, User
exl-id: c9fe3052-a33d-412e-9456-52c9a0cea292
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: tm+mt
source-wordcount: '1639'
ht-degree: 3%

---


# 文字元件(v1) {#text-component-v}

文字元件是RTF編輯和撰寫元件，具備就地編輯功能。

## 使用情況 {#usage}

文字元件提供強大的RTF編輯器，允許在簡化的內嵌編輯器中以全熒幕格式輕鬆編輯文字。

[編輯對話方塊](#edit-dialog)具有內嵌編輯功能，且全熒幕編輯對話方塊中可提供完整功能的有限選項。 使用[設計對話方塊](#design-dialog)，可以為內容作者設定範本的文字格式選項，例如標題、特殊字元和段落樣式。

## 版本和相容性 {#version-and-compatibility}

本檔案說明文字元件v1，其最初隨附於AEM 6.3的核心元件1.0.0版引入。

下表列出文字元件v1的相容性。

| AEM 版本 | 文字元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明文字元件v1。
>
>如需目前版本的文字元件的詳細資訊，請參閱[文字元件](/help/components/text.md)檔案。

## 範例元件輸出 {#sample-component-output}

以下是從[We.Retail](https://helpx.adobe.com/tw/experience-manager/6-4/sites/developing/using/we-retail.html)中取得的範例。

### 螢幕擷圖 {#screenshot}

![](/help/assets/chlimage_1-27.png)

### HTML {#html}

```
<div class="cmp cmp-text aem-GridColumn aem-GridColumn--default--12">
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer porttitor ante a tortor volutpat maximus. Donec eu porta eros. Aenean sit amet eleifend arcu, eu vestibulum magna. Fusce eget nisi tincidunt, tristique felis quis, tincidunt est. Aliquam consequat aliquam quam non eleifend. Phasellus ut magna luctus, aliquam risus eget, fermentum augue. Aliquam lobortis accumsan magna, quis efficitur enim dictum eu. Pellentesque iaculis felis eget felis commodo, non euismod dolor euismod. Quisque nec arcu rutrum, mollis tortor non, sollicitudin odio. Sed dictum nulla mauris, eu pretium dui vulputate a. Maecenas lacus massa, egestas vitae tincidunt eu, interdum et magna. Lorem ipsum dolor sit amet, consectetur adipiscing elit. In eleifend ex lacus, in consectetur nunc interdum et. Donec interdum mi vitae dolor pretium mattis. In quis arcu sapien. Phasellus at metus vitae nisi tincidunt varius.<br />
</p>
</div>
```

### JSON {#json}

```
"text": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "text": "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer porttitor ante a tortor volutpat maximus. Donec eu porta eros. Aenean sit amet eleifend arcu, eu vestibulum magna. Fusce eget nisi tincidunt, tristique felis quis, tincidunt est. Aliquam consequat aliquam quam non eleifend. Phasellus ut magna luctus, aliquam risus eget, fermentum augue. Aliquam lobortis accumsan magna, quis efficitur enim dictum eu. Pellentesque iaculis felis eget felis commodo, non euismod dolor euismod. Quisque nec arcu rutrum, mollis tortor non, sollicitudin odio. Sed dictum nulla mauris, eu pretium dui vulputate a. Maecenas lacus massa, egestas vitae tincidunt eu, interdum et magna. Lorem ipsum dolor sit amet, consectetur adipiscing elit. In eleifend ex lacus, in consectetur nunc interdum et. Donec interdum mi vitae dolor pretium mattis. In quis arcu sapien. Phasellus at metus vitae nisi tincidunt varius.</p>\n",
              "richText": true,
              ":type": "weretail/components/content/text"
            }
```

>[!NOTE]
>
>從核心元件匯出JSON需要版本1.1.0的核心元件。 如需詳細資訊，請參閱核心元件v1[&#128279;](/help/versions.md)的相容性資訊。

## 編輯對話方塊 {#edit-dialog}

「編輯」對話方塊提供使用者將用於撰寫文字的標準RTF格式工具。

![](/help/assets/chlimage_1-52.png)

* 粗體

  ![](/help/assets/chlimage_1-53.png)

  用於套用粗體格式至選取的文字，或套用粗體格式至游標後輸入的文字。

  **Ctrl+B**&#x200B;可以當做鍵盤快速鍵使用。

* 斜體

  ![](/help/assets/chlimage_1-54.png)

  用於將斜體格式設定套用至選取的文字，或將游標後輸入的文字斜體化。

  **Ctrl+I**&#x200B;可以當做鍵盤快速鍵使用。

* 底線

  ![](/help/assets/chlimage_1-55.png)

  用於將底線格式套用至選取的文字，或在游標之後輸入的文字加上底線。

  **Ctrl+U**&#x200B;可以當做鍵盤快速鍵使用。

* 下標

  ![](/help/assets/chlimage_1-56.png)

  用於將選取的文字或在游標之後輸入的文字格式化為下標。

* 上標

  ![](/help/assets/chlimage_1-57.png)

  用於將選取的文字或在游標之後輸入的文字格式化為上標。

* 貼上成文字

  ![](/help/assets/chlimage_1-58.png)

  將任何複製的文字貼上為純文字，不設定任何格式。

  當選取此選項時，會開啟一個視窗，其中的文字可以貼上成無格式的純文字，作為插入文字中之前的預覽。 點選或按一下核取記號即可接受，點選或按一下x可取消。

  ![](/help/assets/chlimage_1-59.png)

* 從 Word 貼上

  ![](/help/assets/chlimage_1-60.png)

  當選取此選項時，會開啟一個視窗，其中的文字可貼上並保留其格式，作為插入文字中之前的預覽。 點選或按一下核取記號即可接受，點選或按一下x可取消。

  ![](/help/assets/chlimage_1-61.png)

* 超連結

  ![](/help/assets/chlimage_1-62.png)

  使用此選項可將選取的文字轉換為超連結或修改已定義的連結。 此選項只有在已選取文字並開啟視窗（其中包含設定連結的其他選項）時才會啟用。

  ![](/help/assets/chlimage_1-63.png)

   * 輸入位置

      * 使用「開啟選取範圍」對話方塊可在AEM中選擇路徑
      * 如果連結不在AEM中，請輸入絕對URL (非絕對路徑會解譯為相對於AEM)

   * 輸入連結的替代描述文字
   * 選取連結行為

      * 目標
      * 相同標籤
      * 新標籤
      * 父框架
      * 上框架

  點選或按一下核取記號以套用連結，或點選x以取消。

* 取消連結

  ![](/help/assets/chlimage_1-64.png)

  使用此選項可移除已套用至所選文字的連結。 此選項僅在已選取連結時有效。

* 尋找

  ![](/help/assets/chlimage_1-65.png)

  使用此選項來搜尋文字，找出指定文字字串的出現位置。 選取此選項會開啟一個視窗，用以指定搜尋選項。

  ![](/help/assets/chlimage_1-66.png)

  輸入您要搜尋的文字，然後點選或按一下[尋找] **開始搜尋。**&#x200B;點選或按一下x以取消。

  如果您想要根據大小寫進行完全比對，請先選取選項&#x200B;**符合大小寫**，再開始搜尋。

  如果找到相符專案，則會反白該專案，且搜尋對話方塊會變暗。 在灰色的對話方塊中，再次點選或按一下&#x200B;**尋找**&#x200B;按鈕以搜尋下一個專案。

  ![](/help/assets/chlimage_1-67.png)

  如果未找到其他事件，則會顯示訊息，並從文字的開頭重新開始搜尋。

  ![](/help/assets/chlimage_1-68.png)

* 取代

  ![](/help/assets/chlimage_1-69.png)

  使用此選項來搜尋文字以確定指定文字字串的出現位置，並將相符專案取代為其他字串。 選取此選項會開啟一個視窗，用於指定搜尋和取代選項。

  ![](/help/assets/chlimage_1-70.png)

  輸入要搜尋的文字以及應取代的文字。

  點選或按一下&#x200B;**尋找**&#x200B;開始搜尋。 按一下或點選x以取消。

  如果您想要根據大小寫進行完全比對，請先選取選項&#x200B;**符合大小寫**，再開始搜尋。

  如果找到相符專案，則會反白該專案，且搜尋對話方塊會變暗。 在灰色的對話方塊中再次按一下&#x200B;**尋找**&#x200B;按鈕以搜尋下一個專案，或選取&#x200B;**取代**&#x200B;按鈕以取代醒目提示的相符文字。 請注意，**Replace**&#x200B;按鈕只有在進行比對後才會啟用。

  選取&#x200B;**全部取代**&#x200B;以一次取代所有出現的文字。

* 向左對齊文字

  ![](/help/assets/chlimage_1-71.png)

  用於將文字對齊左邊界。

* 文字置中

  ![](/help/assets/chlimage_1-72.png)

  用於將文字置中。

* 向右對齊文字

  ![](/help/assets/chlimage_1-73.png)

  用於將文字對齊右邊界。

* 項目符號

  ![](/help/assets/chlimage_1-74.png)

  用於將選取的文字格式化為專案符號清單，或在游標後開始插入專案符號清單。

  若要結束專案符號清單，請再次點選或按一下&#x200B;**專案符號**&#x200B;按鈕，或輸入兩個歸位字元。

* 編號

  ![](/help/assets/chlimage_1-75.png)

  用於將選取的文字格式化為編號清單，或在游標後開始插入編號清單。

  若要結束編號清單，請再次點選或按一下&#x200B;**編號**&#x200B;按鈕或輸入兩個歸位字元。

* 凸排

  ![](/help/assets/chlimage_1-76.png)

  用來減少所選文字的縮排層級，或在游標之後輸入的文字。

  只有當選取的文字或游標位置已經縮排時，才為作用中。

* 縮排

  ![](/help/assets/chlimage_1-77.png)

  用於增加所選文字的縮排層級，或在游標之後輸入的文字。

* 表格

  ![](/help/assets/chlimage_1-78.png)

  用於將表格插入文字中。 選取此選項會開啟一個視窗，用於指定表格的詳細資訊。

  ![](/help/assets/chlimage_1-79.png)

   * **欄** — 資料表的欄數（必要）
   * **列** — 資料表的列數（必填）
   * **寬度** — 表格的寬度
   * **高度** — 資料表的高度
   * **儲存格內邊距** g — 儲存格內容周圍的空間
   * **儲存格間距** — 儲存格之間的間距
   * **框線** — 資料表的框線粗細
   * 如果針對表格的標頭：

      * 應使用第一列
      * 應使用第一欄
      * 應使用第一列和第一欄
      * 或不應使用任何標頭。

   * **標題** — 資料表的標題

* 檢查拼字

  ![](/help/assets/chlimage_1-80.png)

  用於檢查文字內容的拼字。 可能的拼字錯誤會以紅色虛線加底線。

* 特殊字元

  ![](/help/assets/chlimage_1-81.png)

  用於將特殊字元插入文字中。 選取此選項會開啟顯示可用字元的視窗。

  ![](/help/assets/chlimage_1-82.png)

  點選或按一下所需的字元，將其插入游標之後的文字中。 可以插入多個字元。 點選或按一下x以關閉選取範圍視窗。

* 來源編輯

  ![](/help/assets/chlimage_1-83.png)

  用於檢視及修改文字的HTML來源。

  點選或按一下&#x200B;**Source Edit**&#x200B;圖示，從格式化檢視變更文字內容以檢視原始HTML。 在此模式中，會停用所有其他格式選項。 再次點選或按一下「**Source編輯**」圖示可返回格式化檢視。

  >[!CAUTION]
  >
  >和存取原始HTML的情況一樣，使用&#x200B;**Source編輯**&#x200B;選項時必須小心！
  >
  >
  >已掃描透過&#x200B;**Source Edit**&#x200B;輸入的HTML是否有XSS風險，插入的任何指令碼都會被移除，且不會顯示在結果頁面上。 不過，在&#x200B;**Source Edit**&#x200B;中輸入的格式錯誤的HTML可能會破壞頁面的範本，導致未預期的格式設定或導致產生的頁面無法使用。

* 段落格式

  ![](/help/assets/chlimage_1-84.png)

  用於將段落格式套用至選取的文字或游標後插入的文字。 選取此選項會開啟一個下拉式清單，您可從其中選取段落格式。

  ![](/help/assets/chlimage_1-85.png)

文字元件也可以內嵌編輯，但由於空間限制，並非所有格式選項都內嵌可用。 若要檢視所有選項，請切換到全熒幕模式。

![](/help/assets/chlimage_1-86.png)

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義哪些文字格式選項可供內容作者使用。

### 功能 {#features}

![](/help/assets/chlimage_1-28.png)

可為元件啟用或停用下列功能。

* 貼上純文字
* 從文字貼上
* 尋找並取代
* 拼字檢查程式
* Source編輯

### 正在格式化 {#formatting}

![](/help/assets/chlimage_1-29.png)

可為元件啟用或停用下列格式選項。

* 表格
* 清單
* 對齊方式
* 粗體、斜體、底線
* 連結
* 下標/上標

### 段落樣式 {#paragraph-styles}

![](/help/assets/chlimage_1-30.png)

可為元件啟用或停用段落樣式。 啟用時，可以定義允許的格式。

* 點選或按一下&#x200B;**新增**&#x200B;按鈕以插入新樣式。
* 輸入將在「編輯」對話方塊中顯示的樣式代碼和說明。
* 若要移除樣式，請點選或按一下&#x200B;**刪除**&#x200B;按鈕。
* 若要重新排列格式，請點選或按一下並拖曳控點。

### 特殊字元 {#special-characters}

![](/help/assets/chlimage_1-31.png)

可以為元件啟用或停用插入特殊字元的選項。 啟用時，可以定義允許的字元。

* 點選或按一下&#x200B;**新增**&#x200B;按鈕以插入新字元。
* 輸入字元的HTML程式碼，以及將顯示在編輯對話方塊中的說明。
* 若要移除字元點選或按一下&#x200B;**刪除**&#x200B;按鈕。
* 若要重新排列字元順序，請點選或按一下並拖曳控點。

## 技術細節 {#technical-details}

您可以在GitHub[&#128279;](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v1/text)上找到有關文字元件的最新技術檔案。

您可以從GitHub下載整個核心元件專案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。
