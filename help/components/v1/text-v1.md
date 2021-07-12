---
title: 文字元件(v1)
description: 文本元件是富文本編輯和合成元件，具有就地編輯功能。
index: n
role: Architect, Developer, Admin, User
exl-id: c9fe3052-a33d-412e-9456-52c9a0cea292
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '1657'
ht-degree: 3%

---

# 文字元件(v1) {#text-component-v}

文本元件是富文本編輯和合成元件，具有就地編輯功能。

## 使用狀況 {#usage}

文字元件提供強大的RTF編輯器，以簡化的內嵌編輯器和全螢幕格式輕鬆編輯文字。

[edit dialog](#edit-dialog)使用全螢幕編輯對話框中提供的有限功能選項進行串聯編輯。 使用[設計對話框](#design-dialog)，可為內容作者的模板配置標題、特殊字元和段落樣式等文本格式選項。

## 版本與相容性 {#version-and-compatibility}

本檔案說明文字元件v1，此元件最初於AEM 6.3的核心元件1.0.0版中推出。

下表列出文本元件v1的相容性。

| AEM版本 | 文字元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明文字元件的v1。
>
>有關文本元件的當前版本的詳細資訊，請參閱[文本元件](/help/components/text.md)文檔。

## 範例元件輸出 {#sample-component-output}

以下範例取自[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>從核心元件匯出JSON需使用1.1.0版的核心元件。 如需詳細資訊，請參閱核心元件v1](/help/versions.md)的[相容性資訊。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊提供使用者預期要撰寫文字的標準RTF格式工具。

![](/help/assets/chlimage_1-52.png)

* 粗體

   ![](/help/assets/chlimage_1-53.png)

   用於將粗體格式應用於選定文本或在游標後輸入的大膽格式文本。

   **Ctrl+** B可用作鍵盤快速鍵。

* 斜體

   ![](/help/assets/chlimage_1-54.png)

   用於將斜體格式應用到選定文本或在游標之後輸入的斜體文本。

   **Ctrl+** 可用作鍵盤快捷鍵。

* 底線

   ![](/help/assets/chlimage_1-55.png)

   用於將下划線格式應用於在游標之後輸入的選定文本或下划線文本。

   **Ctrl+** Ucan用作鍵盤快捷鍵。

* 下標

   ![](/help/assets/chlimage_1-56.png)

   用於將游標之後輸入的選定文本或文本格式化為下標。

* 上標

   ![](/help/assets/chlimage_1-57.png)

   用於將游標之後輸入的選定文本或文本格式化為上標。

* 貼上為文字

   ![](/help/assets/chlimage_1-58.png)

   將任何複製的文本貼上為純文字檔案，不使用任何格式。

   選取此選項時，將開啟一個窗口，其中文本可以貼上為純文字檔案，在插入文本之前，不以格式作為預覽。 點選或按一下核取標籤即可接受，點選或按一下x即可取消。

   ![](/help/assets/chlimage_1-59.png)

* 從 Word 貼上

   ![](/help/assets/chlimage_1-60.png)

   選取此選項時，會開啟一個視窗，可以貼上文字，在將其插入文字之前，將其格式維持為預覽。 點選或按一下核取標籤即可接受，點選或按一下x即可取消。

   ![](/help/assets/chlimage_1-61.png)

* 超連結

   ![](/help/assets/chlimage_1-62.png)

   使用此選項可將選定文本轉換為超連結或修改已定義的連結。 只有在已選取文字時，此選項才會作用中，並會開啟包含其他連結設定選項的視窗。

   ![](/help/assets/chlimage_1-63.png)

   * 輸入位置

      * 使用「開啟選擇」對話框在AEM中選擇路徑
      * 如果連結不在AEM內，請輸入絕對URL(非絕對路徑會解譯為相對AEM)
   * 輸入連結的替代描述性文字
   * 選取連結行為

      * 目標
      * 相同索引標籤
      * 新索引標籤
      * 父框架
      * 上框架

   點選或按一下核取記號以套用連結，或按x以取消。

* 取消連結

   ![](/help/assets/chlimage_1-64.png)

   使用此選項可移除已套用至所選文字的連結。 只有在已選取連結時，此選項才會作用中。

* 尋找

   ![](/help/assets/chlimage_1-65.png)

   使用此選項可搜索文本以查找指定文本字串的出現次數。 選擇此選項將開啟一個窗口，用於指定搜索選項。

   ![](/help/assets/chlimage_1-66.png)

   輸入要搜索的文本，點選或按一下&#x200B;**Find**&#x200B;以開始搜索。 點選或按一下x以取消。

   如果要根據大小寫進行完全匹配，請在開始搜索之前選擇選項&#x200B;**匹配大小寫**。

   如果找到相符項目，則會加亮顯示，而搜尋對話方塊則呈現灰色。 在灰色對話方塊中，再點選或按一下&#x200B;**尋找**&#x200B;按鈕，以搜尋下一個出現次數。

   ![](/help/assets/chlimage_1-67.png)

   如果找不到其他發生次數，則會顯示訊息，並從文字的開頭開始搜尋。

   ![](/help/assets/chlimage_1-68.png)

* 取代

   ![](/help/assets/chlimage_1-69.png)

   使用此選項可搜索文本以查找指定文本字串的出現次數，並將匹配項替換為另一個字串。 選擇此選項將開啟一個窗口，用於指定搜索和替換選項。

   ![](/help/assets/chlimage_1-70.png)

   輸入要搜索的文本以及應替換的文本。

   點選或按一下&#x200B;**尋找**&#x200B;以開始搜尋。 按一下或點選x以取消。

   如果要根據大小寫進行完全匹配，請在開始搜索之前選擇選項&#x200B;**匹配大小寫**。

   如果找到相符項目，則會加亮顯示，而搜尋對話方塊則呈現灰色。 再次在灰色對話框中按一下&#x200B;**查找**&#x200B;按鈕以搜索下一個出現項，或選擇&#x200B;**替換**&#x200B;按鈕以替換突出顯示的匹配文本。 請注意，**Replace**&#x200B;按鈕僅在匹配後才處於活動狀態。

   選擇&#x200B;**全部替換**&#x200B;一次替換所有出現的文本。

* 向左對齊文字

   ![](/help/assets/chlimage_1-71.png)

   用來將文字對齊左側邊界。

* 文字置中

   ![](/help/assets/chlimage_1-72.png)

   用來將文字置中。

* 向右對齊文字

   ![](/help/assets/chlimage_1-73.png)

   用於將文字對齊右側邊界。

* 項目符號

   ![](/help/assets/chlimage_1-74.png)

   用於將所選文本格式化為項目符號清單，或在游標後開始插入項目符號清單。

   若要結束項目符號清單，請點選或再次按一下&#x200B;**項目符號**&#x200B;按鈕，或輸入兩個歸位字元。

* 編號

   ![](/help/assets/chlimage_1-75.png)

   用於將所選文本格式化為編號清單，或開始在游標後插入編號清單。

   若要結束編號清單，請點選或再次按一下「編號」**「編號」按鈕，或輸入兩個歸位字元。**

* 凸排

   ![](/help/assets/chlimage_1-76.png)

   用於減少在游標之後輸入的選定文本或文本的縮進級別。

   僅當游標的選定文本或位置已縮排時才處於活動狀態。

* 縮排

   ![](/help/assets/chlimage_1-77.png)

   用於增加在游標之後輸入的選定文本或文本的縮進級別。

* 表格

   ![](/help/assets/chlimage_1-78.png)

   用於將表插入文本中。 選擇此選項將開啟一個窗口，用於指定表的詳細資訊。

   ![](/help/assets/chlimage_1-79.png)

   * **列**  — 表的列數（必要）
   * **行**  — 表格的行數（必要）
   * **寬度**  — 表格的寬度
   * **高度**  — 表格的高度
   * **儲**&#x200B;存格邊框間距 — 儲存格內容周圍的空間
   * **儲存格間距**  — 儲存格之間的空間
   * **邊框**  — 表格邊框的粗細
   * 若表格的標題：

      * 應使用第一列
      * 應使用第一欄
      * 應使用第一列和第一列
      * 或者不應使用標題。
   * **註解**  — 表格的註解


* 檢查拼寫

   ![](/help/assets/chlimage_1-80.png)

   用於檢查文本內容的拼寫。 可能拼錯的字，加上破折的紅線。

* 特殊字元

   ![](/help/assets/chlimage_1-81.png)

   用於將特殊字元插入文字中。 選擇此選項將開啟一個顯示可用字元的窗口。

   ![](/help/assets/chlimage_1-82.png)

   點選或按一下所需的字元，將其插入游標後的文字中。 可插入多個字元。 點選或按一下x以關閉選取視窗。

* 來源編輯

   ![](/help/assets/chlimage_1-83.png)

   用於查看和修改文本的HTML源。

   點選或按一下&#x200B;**來源編輯**&#x200B;圖示，以從格式化檢視變更文字的內容，以檢視原始HTML。 在此模式中，會禁用所有其他格式選項。 再次點選或按一下「**來源編輯**」圖示，以返回格式化檢視。

   >[!CAUTION]
   >
   >如同存取原始HTML的情況一樣，使用&#x200B;**來源編輯**&#x200B;選項時，請務必小心！
   >
   >
   >透過&#x200B;**Source Edit**&#x200B;輸入的HTML會掃描XSS風險，且會移除任何已插入的指令碼，且不會顯示在產生的頁面上。 但是，在&#x200B;**Source Edit**&#x200B;中輸入的格式錯誤的HTML可能會中斷頁面的模板，導致意外的格式化或導致頁面無法使用。

* 段落格式

   ![](/help/assets/chlimage_1-84.png)

   用於將段落格式應用於選定文本或游標後插入的文本。 選擇此選項將開啟一個下拉清單，從中選擇段落格式。

   ![](/help/assets/chlimage_1-85.png)

文本元件也可以聯機編輯，但由於空間限制，並非所有格式選項都可以聯機編輯。 若要查看所有選項，請切換至全螢幕模式。

![](/help/assets/chlimage_1-86.png)

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義內容作者可使用的文字格式選項。

### 功能 {#features}

![](/help/assets/chlimage_1-28.png)

可為元件啟用或停用下列功能。

* 貼上純文字
* 過去
* 查找和替換
* 拼字檢查程式
* 源編輯

### 正在格式化 {#formatting}

![](/help/assets/chlimage_1-29.png)

可為元件啟用或停用下列格式選項。

* 表格
* 清單
* 對齊方式
* 粗體，斜體，底線
* 連結
* 子/上標

### 段落樣式 {#paragraph-styles}

![](/help/assets/chlimage_1-30.png)

可為元件啟用或停用段落樣式。 激活後，可定義允許的格式。

* 點選或按一下&#x200B;**Add**&#x200B;按鈕以插入新樣式。
* 輸入樣式的代碼以及將在編輯對話框中顯示的說明。
* 若要移除樣式點選，或按一下「**刪除**」按鈕。
* 要重新排列格式的順序，請點選或按一下並拖動控點。

### 特殊字元 {#special-characters}

![](/help/assets/chlimage_1-31.png)

可為元件啟用或停用插入特殊字元的選項。 啟動後，可定義允許的字元。

* 點選或按一下&#x200B;**Add**&#x200B;按鈕以插入新字元。
* 輸入字元的HTML代碼，以及將在編輯對話方塊中顯示的說明。
* 若要移除字元點選，或按一下「**刪除**」按鈕。
* 要重新排列字元點選的順序，或按一下並拖動控點。

## 技術詳細資訊 {#technical-details}

有關文字元件[的最新技術檔案可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v1/text)上找到。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。
