---
title: 文本元件(v1)
description: 「文本元件」是一個富格文本編輯和合成元件，可進行就地編輯。
index: n
role: Architect, Developer, Admin, User
exl-id: c9fe3052-a33d-412e-9456-52c9a0cea292
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '1657'
ht-degree: 3%

---

# 文本元件(v1) {#text-component-v}

「文本元件」是一個富格文本編輯和合成元件，可進行就地編輯。

## 使用狀況 {#usage}

「文本元件」提供強大的富格文本編輯器，使用簡化的串聯編輯器和全屏格式可以輕鬆編輯文本。

的 [編輯對話框](#edit-dialog) 功能是使用有限選項進行線上編輯，而全屏編輯對話框中提供了全部功能。 使用 [設計對話框](#design-dialog)，可以為內容作者的模板配置文本格式選項，如標題、特殊字元和段落樣式。

## 版本和相容性 {#version-and-compatibility}

本文檔介紹文本元件的v1，最初是隨帶有6.3的核心元件1.0.0版而引AEM入的。

下表列出了文本元件v1的相容性。

| 版AEM本 | 文本元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本文檔介紹文本元件的v1。
>
>有關文本元件當前版本的詳細資訊，請參閱 [文本元件](/help/components/text.md) 的子菜單。

## 元件輸出示例 {#sample-component-output}

以下是從 [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>從核心元件導出JSON需要1.1.0版核心元件。 請參閱 [核心元件v1的相容性資訊](/help/versions.md) 的子菜單。

## 編輯對話框 {#edit-dialog}

編輯對話框提供了用戶希望合成文本的標準富格文本格式工具。

![](/help/assets/chlimage_1-52.png)

* 粗體

   ![](/help/assets/chlimage_1-53.png)

   用於將粗體格式應用於選定文本或大膽設定游標後輸入的文本格式。

   **Ctrl+B** 可用作鍵盤快捷鍵。

* 斜體

   ![](/help/assets/chlimage_1-54.png)

   用於將斜體格式應用於游標後輸入的選定文本或斜體文本。

   **Ctrl+I** 可用作鍵盤快捷鍵。

* 底線

   ![](/help/assets/chlimage_1-55.png)

   用於將下划線格式應用於游標後輸入的選定文本或下划線文本。

   **Ctrl+U鍵** 可用作鍵盤快捷鍵。

* 下標

   ![](/help/assets/chlimage_1-56.png)

   用於將游標後輸入的選定文本或文本格式化為下標。

* 上標

   ![](/help/assets/chlimage_1-57.png)

   用於將游標後輸入的選定文本或文本格式化為上標。

* 貼上為文本

   ![](/help/assets/chlimage_1-58.png)

   將任何複製的文本貼上為純文字檔案，而不使用任何格式。

   選擇此選項時，將開啟一個窗口，在將文本插入文本之前，可以將文本貼上為純文字檔案，且不將格式設定為預覽。 按一下或按一下複選標籤接受，按一下或按一下x取消。

   ![](/help/assets/chlimage_1-59.png)

* 從 Word 貼上

   ![](/help/assets/chlimage_1-60.png)

   選擇此選項時，將開啟一個窗口，在將文本插入文本之前，可以在其中貼上文本，將其格式保持為預覽。 按一下或按一下複選標籤接受，按一下或按一下x取消。

   ![](/help/assets/chlimage_1-61.png)

* 超連結

   ![](/help/assets/chlimage_1-62.png)

   使用此選項可將所選文本轉換為超連結或修改已定義的連結。 僅當已選擇文本並開啟窗口時，此選項才處於活動狀態，其中包含用於設定連結的其他選項。

   ![](/help/assets/chlimage_1-63.png)

   * 輸入地點

      * 使用「開啟選擇」對話框在中選擇路AEM徑
      * 如果連結不在AEM其中，則輸入絕對URL(非絕對路徑被解釋為相對AEM)
   * 輸入連結的備選說明性文本
   * 選擇連結行為

      * 目標
      * 相同索引標籤
      * 新索引標籤
      * 父框架
      * 上框架

   點擊或按一下複選標籤以應用連結，或按一下x以取消。

* 取消連結

   ![](/help/assets/chlimage_1-64.png)

   使用此選項可刪除已應用於所選文本的連結。 僅當已選擇連結時，此選項才處於活動狀態。

* 尋找

   ![](/help/assets/chlimage_1-65.png)

   使用此選項可搜索文本以查找指定文本字串。 選擇此選項將開啟一個窗口，用於指定搜索選項。

   ![](/help/assets/chlimage_1-66.png)

   輸入要搜索的文本，點擊或按一下 **查找** 開始搜索。 點擊或按一下x取消。

   如果要根據大小寫進行精確匹配，請選擇選項 **匹配大小寫** 開始搜索。

   如果找到匹配項，則會加亮該匹配項，並且搜索對話框會變暗。 點擊或按一下 **查找** 的子菜單。

   ![](/help/assets/chlimage_1-67.png)

   如果找不到其他出現的情況，將顯示一條消息，並從文本的開頭重新開始搜索。

   ![](/help/assets/chlimage_1-68.png)

* 取代

   ![](/help/assets/chlimage_1-69.png)

   使用此選項可搜索文本以查找指定文本字串的具體值，並將匹配項替換為另一個字串。 選擇此選項將開啟一個窗口，用於指定搜索和替換選項。

   ![](/help/assets/chlimage_1-70.png)

   輸入要搜索的文本以及應替換它的文本。

   點擊或按一下 **查找** 開始搜索。 按一下或點擊x取消。

   如果要根據大小寫進行精確匹配，請選擇選項 **匹配大小寫** 開始搜索。

   如果找到匹配項，則會加亮該匹配項，並且搜索對話框會變暗。 按一下 **查找** 按鈕，以搜索下一個出現項或選擇 **替換** 按鈕，將選定控制項在Tab鍵次序中下移一個位置。 請注意 **替換** 只有匹配後，按鈕才處於活動狀態。

   選擇 **全部替換** 來同時替換所有出現的文本。

* 向左對齊文字

   ![](/help/assets/chlimage_1-71.png)

   用於將文本與左邊距對齊。

* 文字置中

   ![](/help/assets/chlimage_1-72.png)

   用於居中文本。

* 向右對齊文字

   ![](/help/assets/chlimage_1-73.png)

   用於將文本與右邊距對齊。

* 項目符號

   ![](/help/assets/chlimage_1-74.png)

   用於將所選文本格式化為項目符號清單或開始在游標後插入項目符號清單。

   要結束項目符號清單，請點擊或按一下 **項目符號** 按鈕或輸入兩個回車符。

* 編號

   ![](/help/assets/chlimage_1-75.png)

   用於將所選文本格式化為編號清單或開始在游標後插入編號清單。

   要結束編號清單，請點擊或按一下 **編號** 按鈕或輸入兩個回車符。

* 凸排

   ![](/help/assets/chlimage_1-76.png)

   用於減少在游標後輸入的選定文本或文本的縮進級別。

   僅當游標的選定文本或位置已縮進時才處於活動狀態。

* 縮排

   ![](/help/assets/chlimage_1-77.png)

   用於增加游標後輸入的選定文本或文本的縮進級別。

* 表格

   ![](/help/assets/chlimage_1-78.png)

   用於將表插入文本。 選擇此選項將開啟一個窗口，用於指定表的詳細資訊。

   ![](/help/assets/chlimage_1-79.png)

   * **列**  — 表的列數（必需）
   * **行**  — 表的行數（必需）
   * **寬度**  — 表的寬度
   * **高度**  — 表的高度
   * **細胞帕丁** g — 單元格內容周圍的空間
   * **單元格間距**  — 單元格之間的空格
   * **邊框**  — 表的邊框線的重量
   * 如果表的標題：

      * 應使用第一行
      * 應使用第一列
      * 應使用第一行和第一列
      * 或者不應使用標題。
   * **標題**  — 表的標題


* 檢查拼寫

   ![](/help/assets/chlimage_1-80.png)

   用於檢查文本內容的拼寫。 可能的拼寫錯誤用破折的紅線加下划線。

* 特殊字元

   ![](/help/assets/chlimage_1-81.png)

   用於在文本中插入特殊字元。 選擇此選項將開啟一個顯示可用字元的窗口。

   ![](/help/assets/chlimage_1-82.png)

   點擊或按一下所需字元，將其插入游標後的文本。 可以插入多個字元。 點擊或按一下x關閉選擇窗口。

* 來源編輯

   ![](/help/assets/chlimage_1-83.png)

   用於查看和修改文本的HTML源。

   點擊或按一下 **源編輯** 表徵圖以更改格式化視圖中文本的內容以查看原始HTML。 在此模式下，所有其它格式選項都被禁用。 點擊或按一下 **源編輯** 表徵圖以返回到格式化視圖。

   >[!CAUTION]
   >
   >與訪問原始HTML的情況一樣，在使用 **源編輯** 選項！
   >
   >
   >HTML輸入方式 **源編輯** 將掃描XSS風險，並刪除插入的任何指令碼，且不會顯示在生成的頁面上。 但是，在中輸入的HTML格式錯誤 **源編輯** 可能會中斷頁面的模板，導致意外的格式設定或導致生成的頁面無法使用。

* 段落格式

   ![](/help/assets/chlimage_1-84.png)

   用於將段落格式應用於選定文本或插入游標後的文本。 選擇此選項將開啟一個下拉清單，從中選擇段落格式。

   ![](/help/assets/chlimage_1-85.png)

文本元件也可以串聯編輯，但由於空間限制，並非所有格式選項都可串聯使用。 要查看所有選項，請切換到全屏模式。

![](/help/assets/chlimage_1-86.png)

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義內容作者可以使用哪些文本格式選項。

### 功能 {#features}

![](/help/assets/chlimage_1-28.png)

可以為元件激活或停用以下特徵。

* 貼上純文字檔案
* 過去自單詞
* 查找和替換
* 拼寫檢查
* 源編輯

### 正在格式化 {#formatting}

![](/help/assets/chlimage_1-29.png)

可以為元件激活或停用以下格式設定選項。

* 表格
* 清單
* 對齊方式
* 粗體、斜體、下划線
* 連結
* 下標/上標

### 段落樣式 {#paragraph-styles}

![](/help/assets/chlimage_1-30.png)

可以為元件激活或停用段落樣式。 激活後，可以定義允許的格式。

* 點擊或按一下 **添加** 按鈕。
* 輸入樣式的代碼和將在編輯對話框中顯示的說明。
* 要刪除樣式點擊，或按一下 **刪除** 按鈕
* 要重新排列格式的順序，請點擊或按一下並拖動控制滑塊。

### 特殊字元 {#special-characters}

![](/help/assets/chlimage_1-31.png)

可以為元件激活或停用插入特殊字元的選項。 激活後，可以定義允許的字元。

* 點擊或按一下 **添加** 按鈕
* 輸入字元的HTML代碼和將在編輯對話框中顯示的說明。
* 要刪除字元點擊，或按一下 **刪除** 按鈕
* 要重新排列字元點擊的順序，或按一下並拖動控制滑塊。

## 技術詳細資訊 {#technical-details}

有關文本元件的最新技術文檔 [可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v1/text)。

整個核心元件項目可從GitHub下載。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。
