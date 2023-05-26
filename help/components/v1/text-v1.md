---
title: 文字元件(v1)
description: 文字元件是RTF文字編輯和撰寫元件，具備就地編輯功能。
index: n
role: Architect, Developer, Admin, User
exl-id: c9fe3052-a33d-412e-9456-52c9a0cea292
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '1657'
ht-degree: 3%

---

# 文字元件(v1) {#text-component-v}

文字元件是RTF文字編輯和撰寫元件，具備就地編輯功能。

## 使用狀況 {#usage}

文字元件提供強大的RTF編輯器，允許在簡化的內嵌編輯器中以全熒幕格式輕鬆編輯文字。

此 [編輯對話方塊](#edit-dialog) 具備內嵌編輯功能，提供全熒幕編輯對話方塊中完整功能的有限選項。 使用 [設計對話方塊](#design-dialog)，您可以為內容作者設定範本的文字格式選項，例如標題、特殊字元和段落樣式。

## 版本和相容性 {#version-and-compatibility}

本檔案說明文字元件v1，其最初隨附於AEM 6.3的核心元件1.0.0版引入。

下表列出文字元件v1的相容性。

| AEM版本 | 文字元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明文字元件v1。
>
>如需目前版本的文字元件的詳細資訊，請參閱 [文字元件](/help/components/text.md) 檔案。

## 範例元件輸出 {#sample-component-output}

以下是取自下列專案的範例： [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

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
>從核心元件匯出JSON需要核心元件1.1.0版。 請參閱 [核心元件v1的相容性資訊](/help/versions.md) 以取得詳細資訊。

## 編輯對話方塊 {#edit-dialog}

「編輯」對話方塊提供使用者將用於撰寫文字的標準RTF格式工具。

![](/help/assets/chlimage_1-52.png)

* 粗體

   ![](/help/assets/chlimage_1-53.png)

   用於將粗體格式套用至選取的文字，或粗體格式套用至游標後輸入的文字。

   **Ctrl+B** 可用作鍵盤快速鍵。

* 斜體

   ![](/help/assets/chlimage_1-54.png)

   用於將斜體格式套用至選取的文字，或將游標之後輸入的文字斜體化。

   **Ctrl+I** 可用作鍵盤快速鍵。

* 底線

   ![](/help/assets/chlimage_1-55.png)

   用於將加底線格式套用至選取的文字，或在游標後輸入的文字加底線。

   **Ctrl+U** 可用作鍵盤快速鍵。

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

   當選取此選項時，會開啟一個視窗，其中的文字可以貼上並保留其格式，作為插入文字中之前的預覽。 點選或按一下核取記號即可接受，點選或按一下x可取消。

   ![](/help/assets/chlimage_1-61.png)

* 超連結

   ![](/help/assets/chlimage_1-62.png)

   使用此選項可將選取的文字轉換為超連結或修改已定義的連結。 此選項只有在已選取文字並開啟一個視窗，其中包含設定連結的其他選項時才會啟用。

   ![](/help/assets/chlimage_1-63.png)

   * 輸入位置

      * 使用「開啟選取範圍」對話方塊來選擇AEM中的路徑
      * 如果連結不在AEM內，請輸入絕對URL (非絕對路徑會解譯為相對於AEM)
   * 輸入連結的替代描述文字
   * 選取連結行為

      * 目標
      * 相同索引標籤
      * 新索引標籤
      * 父框架
      * 上框架

   點選或按一下核取記號以套用連結，或點選x以取消。

* 取消連結

   ![](/help/assets/chlimage_1-64.png)

   使用此選項可移除已套用至所選文字的連結。 只有在已選取連結時，此選項才會啟用。

* 尋找

   ![](/help/assets/chlimage_1-65.png)

   使用此選項可搜尋指定文字字串出現位置的文字。 選取此選項會開啟一個視窗來指定搜尋選項。

   ![](/help/assets/chlimage_1-66.png)

   輸入您要搜尋的文字，然後點選或按一下 **尋找** 以開始搜尋。 點選或按一下x以取消。

   如果您想要根據大小寫進行完全比對，請選取選項 **符合大小寫** 開始搜尋之前。

   如果找到相符專案，則會反白該專案，且搜尋對話方塊會變暗。 點選或按一下 **尋找** 在灰色的對話方塊中再次使用按鈕來搜尋下一個出現位置。

   ![](/help/assets/chlimage_1-67.png)

   如果找不到其他匹配項，則會顯示一則訊息，且搜尋會從文字的開頭重新開始。

   ![](/help/assets/chlimage_1-68.png)

* 取代

   ![](/help/assets/chlimage_1-69.png)

   使用此選項來搜尋文字以確定指定文字字串的出現次數，並將符合專案取代為其他字串。 選取此選項會開啟一個視窗，用於指定搜尋和取代選項。

   ![](/help/assets/chlimage_1-70.png)

   輸入您要搜尋的文字以及應取代的文字。

   點選或按一下 **尋找** 以開始搜尋。 按一下或點選「 x 」以取消。

   如果您想要根據大小寫進行完全比對，請選取選項 **符合大小寫** 開始搜尋之前。

   如果找到相符專案，則會反白該專案，且搜尋對話方塊會變暗。 按一下 **尋找** 在灰色的對話方塊中再次按一下按鈕以搜尋下一個出現位置或選取 **Replace** 按鈕來取代醒目提示的相符文字。 請注意 **Replace** 按鈕只有在進行比對後才會啟用。

   選取 **全部取代** 一次取代所有出現的文字。

* 向左對齊文字

   ![](/help/assets/chlimage_1-71.png)

   用於將文字對齊左邊界。

* 文字置中

   ![](/help/assets/chlimage_1-72.png)

   用於置中文字。

* 向右對齊文字

   ![](/help/assets/chlimage_1-73.png)

   用於將文字對齊右邊界。

* 項目符號

   ![](/help/assets/chlimage_1-74.png)

   用於將選取的文字格式化為專案符號清單，或在游標後開始插入專案符號清單。

   若要結束專案符號清單，請點選或按一下 **專案符號** 再次按一下按鈕或輸入兩個歸位字元。

* 編號

   ![](/help/assets/chlimage_1-75.png)

   用於將選取的文字格式化為編號清單，或在游標後開始插入編號清單。

   若要結束編號清單，請點選或按一下 **編號** 再次按一下按鈕或輸入兩個歸位字元。

* 凸排

   ![](/help/assets/chlimage_1-76.png)

   用來減少所選文字的縮排層級，或在游標後輸入的文字。

   只有在選取的文字或游標位置已經縮排時才啟用。

* 縮排

   ![](/help/assets/chlimage_1-77.png)

   用於增加所選文字的縮排層級，或在游標後輸入的文字。

* 表格

   ![](/help/assets/chlimage_1-78.png)

   用於將表格插入文字中。 選取此選項會開啟一個視窗，用於指定表格的詳細資訊。

   ![](/help/assets/chlimage_1-79.png)

   * **欄**  — 表格的欄數（必要）
   * **列**  — 表格的列數（必要）
   * **寬度**  — 表格的寬度
   * **高度**  — 表格的高度
   * **儲存格內邊距** g — 儲存格內容周圍的空間
   * **儲存格間距**  — 儲存格之間的空間
   * **邊框**  — 表格邊框線條的粗細
   * 若為表格的標頭：

      * 應使用第一列
      * 應使用第一欄
      * 應使用第一列和第一欄
      * 或不應使用標題。
   * **註解**  — 表格的標題


* 檢查拼字

   ![](/help/assets/chlimage_1-80.png)

   用於檢查文字內容的拼字。 可能的拼字錯誤會以紅色的破折線加底線。

* 特殊字元

   ![](/help/assets/chlimage_1-81.png)

   用於將特殊字元插入文字中。 選取此選項會開啟一個視窗，其中顯示可用的字元。

   ![](/help/assets/chlimage_1-82.png)

   點選或按一下所需的字元，將其插入游標後面的文字中。 可以插入多個字元。 點選或按一下x以關閉選取範圍視窗。

* 來源編輯

   ![](/help/assets/chlimage_1-83.png)

   用於檢視和修改文字的HTML來源。

   點選或按一下 **來源編輯** 圖示可從格式化檢視變更文字內容，以檢視原始HTML。 在此模式中，會停用所有其他格式選項。 點選或按一下 **來源編輯** 圖示返回格式化檢視。

   >[!CAUTION]
   >
   >與存取原始HTML的情況一樣，使用時必須小心 **來源編輯** 選項！
   >
   >
   >HTML輸入方式 **來源編輯** 會掃描XSS風險，插入的任何指令碼都會被移除，且不會顯示在結果頁面上。 不過，輸入的HTML格式不正確 **來源編輯** 可能會破壞頁面的範本，導致非預期的格式設定或導致產生的頁面無法使用。

* 段落格式

   ![](/help/assets/chlimage_1-84.png)

   用於將段落格式套用至選取的文字，或套用至游標後插入的文字。 選取此選項會開啟一個下拉式清單，您可從其中選取段落格式。

   ![](/help/assets/chlimage_1-85.png)

文字元件也可以內嵌編輯，但由於空間限制，並非所有格式選項都內嵌可用。 若要檢視所有選項，請切換到全熒幕模式。

![](/help/assets/chlimage_1-86.png)

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義哪些文字格式選項可供內容作者使用。

### 功能 {#features}

![](/help/assets/chlimage_1-28.png)

可為元件啟用或停用下列功能。

* 貼上純文字
* 從Word過去
* 尋找和取代
* 拼字檢查程式
* 來源編輯

### 正在格式化 {#formatting}

![](/help/assets/chlimage_1-29.png)

您可以為元件啟用或停用下列格式選項。

* 表格
* 清單
* 對齊方式
* 粗體、斜體、底線
* 連結
* 下標/上標

### 段落樣式 {#paragraph-styles}

![](/help/assets/chlimage_1-30.png)

可以為元件啟用或停用段落樣式。 啟用時，可以定義允許的格式。

* 點選或按一下 **新增** 按鈕以插入新樣式。
* 輸入將在「編輯」對話方塊中顯示的樣式代碼和說明。
* 若要移除樣式，請點選或按一下 **刪除** 按鈕。
* 若要重新排列格式，請點選或按一下並拖曳操作框。

### 特殊字元 {#special-characters}

![](/help/assets/chlimage_1-31.png)

可以為元件啟用或停用插入特殊字元的選項。 啟用時，可以定義允許的字元。

* 點選或按一下 **新增** 按鈕以插入新字元。
* 輸入將在編輯對話方塊中顯示的字元HTML碼和說明。
* 若要移除字元，請點選或按一下 **刪除** 按鈕。
* 若要重新排列字元順序，請點選或按一下並拖曳控點。

## 技術細節 {#technical-details}

有關文字元件的最新技術檔案 [可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v1/text).

您可以從GitHub下載整個核心元件專案。

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).
