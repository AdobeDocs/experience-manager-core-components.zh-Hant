---
title: 文字元件 (v1)
description: 文字元件是 RTF 文字編輯和撰寫元件，具備就地編輯功能。
index: n
role: Architect, Developer, Admin, User
exl-id: c9fe3052-a33d-412e-9456-52c9a0cea292
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '1639'
ht-degree: 100%

---


# 文字元件 (v1) {#text-component-v}

文字元件是 RTF 文字編輯和撰寫元件，具備就地編輯功能。

## 用途 {#usage}

文字元件提供強大的 RTF 文字編輯器，允許在簡化的內嵌編輯器與全螢幕格式中輕鬆編輯文字。

[編輯對話框](#edit-dialog)提供內嵌編輯功能，但選項有限；完整功能則可在全螢幕編輯對話框中使用。使用[設計對話框](#design-dialog)，內容作者可設定範本的文字格式選項，例如標題、特殊字元和段落樣式。

## 版本和相容性 {#version-and-compatibility}

本文件說明文字元件 v1，最初由 AEM 6.3 搭配的核心元件 1.0.0 版導入。

下表列出文字元件 v1 的相容性。

| AEM 版本 | 文字元件 v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本文件說明文字元件 v1。
>
>如需文字元件目前版本的詳細資訊，請參閱[文字元件](/help/components/text.md)文件。

## 範例元件輸出 {#sample-component-output}

以下是從 [We.Retail](https://helpx.adobe.com/tw/experience-manager/6-4/sites/developing/using/we-retail.html) 中取得的範例。

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
>從核心元件匯出 JSON 需要核心元件 1.1.0 版。如需詳細資訊，請參閱[核心元件 v1 的相容性資訊](/help/versions.md)。

## 編輯對話框 {#edit-dialog}

編輯對話框提供使用者將用於撰寫文字的標準 RTF 文字格式工具。

![](/help/assets/chlimage_1-52.png)

* 粗體

  ![](/help/assets/chlimage_1-53.png)

  用於將粗體格式套用至選取的文字，或將游標後方輸入的文字設定為粗體格式。

  **Ctrl+B** 可以當做鍵盤快速鍵使用。

* 斜體

  ![](/help/assets/chlimage_1-54.png)

  用於將斜體格式套用至選取的文字，或將游標後方輸入的文字設定為斜體格式。

  **Ctrl+I** 可以當做鍵盤快速鍵使用。

* 底線

  ![](/help/assets/chlimage_1-55.png)

  用於將底線格式套用至選取的文字，或將游標後方輸入的文字加上底線。

  **Ctrl+U** 可以當做鍵盤快速鍵使用。

* 下標

  ![](/help/assets/chlimage_1-56.png)

  用於將選取的文字或在游標後方輸入的文字格式化為下標。

* 上標

  ![](/help/assets/chlimage_1-57.png)

  用於將選取的文字或在游標後方輸入的文字格式化為上標。

* 以文字格式貼上

  ![](/help/assets/chlimage_1-58.png)

  將任何複製的文字以純文字形式貼上，不包含任何格式。

  當選取此選項時，會開啟一個視窗，可將文字以不含任何格式的純文字形式貼上，作為預覽內容，之後再插入至正文。點選或按一下核取記號即可接受，點選或按一下 x 可取消。

  ![](/help/assets/chlimage_1-59.png)

* 從 Word 貼上

  ![](/help/assets/chlimage_1-60.png)

  當選取此選項時，會開啟一個視窗，可將文字保留原有格式貼上，作為預覽內容，之後再插入至正文。點選或按一下核取記號即可接受，點選或按一下 x 可取消。

  ![](/help/assets/chlimage_1-61.png)

* 超連結

  ![](/help/assets/chlimage_1-62.png)

  使用此選項可將選取的文字轉換為超連結或修改已定義的連結。此選項只有在已選取文字時才會啟用，並開啟一個具有額外連結設定選項的視窗 。

  ![](/help/assets/chlimage_1-63.png)

   * 輸入位置

      * 使用開啟選取對話框，在 AEM 中選擇路徑
      * 如果連結不在 AEM 中，請輸入絕對 URL (非絕對路徑會解譯為相對於 AEM)

   * 輸入連結的替代說明文字
   * 選取連結行為

      * 目標
      * 相同索引標籤
      * 新索引標籤
      * 上層框架
      * 上框架

  點選或按一下核取記號以套用連結，或點選 x 以取消。

* 取消連結

  ![](/help/assets/chlimage_1-64.png)

  使用此選項可移除已套用至所選文字的連結。此選項僅在已選取連結時才會啟用。

* 尋找

  ![](/help/assets/chlimage_1-65.png)

  使用此選項來搜尋文字，找出指定文字字串的出現位置。選取此選項會開啟一個視窗，用以指定搜尋選項。

  ![](/help/assets/chlimage_1-66.png)

  輸入您要搜尋的文字，然後點選或按一下&#x200B;**尋找**&#x200B;開始搜尋。點選或按一下 x 以取消。

  如果您想要根據大小寫進行完全比對，請先選取選項&#x200B;**符合大小寫**，再開始搜尋。

  如果找到相符項目，則會醒目提示該項目，且搜尋對話框會變暗。在變暗的對話框中，再次點選或按一下&#x200B;**尋找**&#x200B;按鈕以搜尋下一個出現位置。

  ![](/help/assets/chlimage_1-67.png)

  如果未找到其他出現位置，則會顯示訊息，並從文字的開頭重新開始搜尋。

  ![](/help/assets/chlimage_1-68.png)

* 取代

  ![](/help/assets/chlimage_1-69.png)

  使用此選項來搜尋文字，找出指定文字字串的出現位置，並將相符項目取代為其他字串。選取此選項會開啟一個視窗，用於指定搜尋和取代選項。

  ![](/help/assets/chlimage_1-70.png)

  輸入要搜尋的文字以及應取代的文字。

  點選或按一下&#x200B;**尋找**&#x200B;開始搜尋。按一下或點選 x 以取消。

  如果您想要根據大小寫進行完全比對，請先選取選項&#x200B;**符合大小寫**，再開始搜尋。

  如果找到相符項目，則會醒目提示該項目，且搜尋對話框會變暗。在變暗的對話框中再次按一下&#x200B;**尋找**&#x200B;按鈕以搜尋下一個出現位置，或選取&#x200B;**取代**&#x200B;按鈕以取代醒目提示的相符文字。請注意，**取代**&#x200B;按鈕只有在進行比對後才會啟用。

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

  用於將選取的文字格式化為項目符號清單，或在游標後開始插入項目符號清單。

  若要結束項目符號清單，請再次點選或按一下&#x200B;**「項目符號」**&#x200B;按鈕，或輸入兩個歸位字元。

* 編號

  ![](/help/assets/chlimage_1-75.png)

  用於將選取的文字格式化為編號符號清單，或在游標後開始插入編號符號清單。

  若要結束編號符號清單，請再次點選或按一下&#x200B;**「編號符號」**&#x200B;按鈕，或輸入兩個歸位字元。

* 凸排

  ![](/help/assets/chlimage_1-76.png)

  用來減少所選文字或在游標之後輸入的文字的縮排等級。

  只有當選取的文字或游標位置已經縮排時才會啟用。

* 縮排

  ![](/help/assets/chlimage_1-77.png)

  用來增加所選文字或在游標之後輸入的文字的縮排等級。

* 表格

  ![](/help/assets/chlimage_1-78.png)

  用於將表格插入文字中。選取此選項會開啟一個視窗，用於指定表格的詳細資訊。

  ![](/help/assets/chlimage_1-79.png)

   * **欄** - 表格的欄數 (必要)
   * **列** - 表格的列數 (必要)
   * **寬度** - 表格的寬度
   * **高度** - 表格的高度
   * **儲存格內邊距** - 儲存格內容周圍的空間
   * **儲存格間距** - 儲存格之間的間距
   * **框線** - 表格的框線粗細
   * 如果針對表格的標頭：

      * 應使用第一列
      * 應使用第一欄
      * 應使用第一列和第一欄
      * 或不應使用任何標頭。

   * **標題** - 表格的標題

* 檢查拼字

  ![](/help/assets/chlimage_1-80.png)

  用於檢查文字內容的拼字。可能的拼字錯誤會以紅色虛線加底線標示。

* 特殊字元

  ![](/help/assets/chlimage_1-81.png)

  用於將特殊字元插入文字中。選取此選項會開啟顯示可用字元的視窗。

  ![](/help/assets/chlimage_1-82.png)

  點選或按一下所需的字元，將其插入游標之後的文字中。可以插入多個字元。點選或按一下 x 以關閉選取視窗。

* 原始碼編輯

  ![](/help/assets/chlimage_1-83.png)

  用於檢視及修改文字的 HTML 原始碼。

  點選或按一下&#x200B;**原始碼編輯**&#x200B;圖示，從格式化檢視變更文字內容以檢視原始 HTML。在此模式中，會停用所有其他格式選項。再次點選或按一下&#x200B;**原始碼編輯** 圖示可返回格式化檢視。

  >[!CAUTION]
  >
  >和存取原始 HTML 的情況一樣，使用&#x200B;**原始碼編輯**&#x200B;選項時必須小心！
  >
  >
  >透過&#x200B;**原始碼編輯** 輸入的 HTML 會進行掃描以確認是否有 XSS 風險，若插入任何指令碼都會被移除，且不會顯示在結果頁面上。不過，在&#x200B;**原始碼編輯**&#x200B;中輸入格式錯誤的 HTML 可能會破壞頁面的範本，導致非預期的格式設定或導致產生的頁面無法使用。

* 段落格式

  ![](/help/assets/chlimage_1-84.png)

  用於將段落格式套用至所選文字或在游標之後輸入的文字。選取此選項會開啟一個下拉式清單，您可從其中選取段落格式。

  ![](/help/assets/chlimage_1-85.png)

文字元件也可以內嵌編輯，但由於空間限制，並非所有格式選項都內嵌可用。若要檢視所有選項，請切換至全螢幕模式。

![](/help/assets/chlimage_1-86.png)

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可定義可供內容作者使用的文字格式選項。

### 功能 {#features}

![](/help/assets/chlimage_1-28.png)

可為元件啟用或停用下列功能。

* 貼上純文字
* 從 Word 貼上
* 尋找並取代
* 拼字檢查工具
* 原始碼編輯

### 格式化 {#formatting}

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

可為元件啟用或停用段落樣式。啟用時，可以定義允許的格式。

* 點選或按一下&#x200B;**新增**&#x200B;按鈕以插入新樣式。
* 輸入將在編輯對話框中顯示的樣式程式碼和說明。
* 若要移除樣式，請點選或按一下&#x200B;**刪除**&#x200B;按鈕。
* 若要重新排列格式的順序，請點選或按一下並拖曳控點。

### 特殊字元 {#special-characters}

![](/help/assets/chlimage_1-31.png)

可以為元件啟用或停用插入特殊字元的選項。啟用時，可以定義允許的字元。

* 點選或按一下&#x200B;**新增**&#x200B;按鈕以插入新字元。
* 輸入將在編輯對話框中顯示的字元 HTML 程式碼和說明。
* 若要移除字元，請點選或按一下&#x200B;**刪除**&#x200B;按鈕。
* 若要重新排列字元的順序，請點選或按一下並拖曳控點。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v1/text)有關文字元件的最新技術文件。

您可以從 GitHub 下載完整的核心元件專案。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。
