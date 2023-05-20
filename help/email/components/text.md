---
title: 電子郵件文本元件
description: 電子郵件文本元件是一個富格文本編輯和合成元件，具有就地編輯功能。
role: Architect, Developer, Admin, User
exl-id: 4aa192f6-8314-40e7-8732-c6626d647986
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '2291'
ht-degree: 2%

---


# 電子郵件文本元件 {#email-text-component}

電子郵件文本元件是一個富格文本編輯和合成元件，具有就地編輯功能。

## 使用狀況 {#usage}

電子郵件文本元件提供強大的富格文本編輯器，它允許以簡化的串聯編輯器以及全屏格式輕鬆編輯文本。

* 的 [編輯對話框](#edit-dialog) 功能是使用有限選項進行線上編輯，而全屏編輯對話框中提供了全部功能。
* 使用 [設計對話框，](#design-dialog) 可以為內容作者的模板配置文本格式選項，如標題、特殊字元和段落樣式。

## 版本和相容性 {#version-and-compatibility}

電子郵件文本元件的當前版本是v1，該版本於2022年10月隨電子郵件核心元件的X版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | - |

有關核心元件版本和版本的詳細資訊，請參閱文檔 [電子郵件核心元件版本。](/help/email/versions.md)

### 技術詳細資訊 {#technical-details}

有關電子郵件文本元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_email_text_v1)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 電子郵件文本元件和富格文本編輯器 {#the-text-component-and-the-rich-text-editor}

電子郵件文本元件利AEM用富格文本編輯器(RTE)。 RTE為內容作者提供了多種編輯其文本內容的功能。 RTE的配置靈活，提供了多種選項。 有關如何配置RTE的進一步詳細資訊，請參閱文章 [配置RTF編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/rich-text-editor.html) 和 [配置RTF編輯器插件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html)。

本文檔的其餘部分演示了電子郵件文本元件的標準配置以及現成的RTE配置。

>[!NOTE]
>
>僅選項啟用者 [RTE的UI配置](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html) 在「電子郵件文本」元件中。

## 編輯對話框 {#edit-dialog}

![文本元件的編輯對話框](/help/email/assets/email-text-edit.png)

### 格式設定選項 {#options}

編輯對話框提供了用戶希望合成文本的標準富格文本格式工具。

#### 粗體

![粗體表徵圖](/help/assets/text-bold.png)

用於將粗體格式應用於選定文本或大膽設定游標後輸入的文本格式。

**Ctrl+B** 可用作鍵盤快捷鍵。

#### 斜體

![斜體表徵圖](/help/assets/text-italic.png)

用於將斜體格式應用於游標後輸入的選定文本或斜體文本。

**Ctrl+I** 可用作鍵盤快捷鍵。

#### 底線

![下划線表徵圖](/help/assets/text-underline.png)

用於將下划線格式應用於游標後輸入的選定文本或下划線文本。

**Ctrl+U鍵** 可用作鍵盤快捷鍵。

#### 下標

![下標表徵圖](/help/assets/text-subscript.png)

用於將游標後輸入的選定文本或文本格式化為下標。

#### 上標

![上標表徵圖](/help/assets/text-superscript.png)

用於將游標後輸入的選定文本或文本格式化為上標。

#### 貼上為文本

![貼上為文本表徵圖](/help/assets/text-paste-text.png)

將任何複製的文本貼上為純文字檔案，而不使用任何格式。

選擇此選項時，將開啟一個窗口，在將文本插入文本之前，可以將文本貼上為純文字檔案，且沒有格式作為預覽。 按一下或按一下複選標籤接受，按一下或按一下x取消。

![貼上為文本示例](/help/assets/text-paste-text-example.png)

#### 從 Word 貼上

![「從Word貼上」表徵圖](/help/assets/text-paste-word.png)

選擇此選項時，將開啟一個窗口，在將文本插入文本之前，可以在其中貼上文本，將其格式保持為預覽。 按一下或按一下複選標籤接受，按一下或按一下x取消。

![從Word貼上示例](/help/assets/text-paste-word-example.png)

#### 超連結

![超連結表徵圖](/help/assets/text-hyperlink.png)

使用此選項可將所選文本轉換為超連結或修改已定義的連結。 此選項開啟一個窗口，其中包含用於設定連結的其他選項。

![超連結示例](/help/assets/text-hyperlink-example.png)

* 輸入路徑
   * 使用 **開啟選擇** 對話框，在中選擇路AEM徑
   * 如果連結不在AEM其中，請輸入絕對URL
      * 非絕對路徑被解釋為相對於AEM
* 輸入連結的備選說明性文本
* 選擇連結行為
   * 目標
   * 相同索引標籤
   * 新索引標籤
   * 父框架
   * 上框架

點擊或按一下複選標籤以應用連結，或按一下x以取消。

#### 取消連結

![取消連結表徵圖](/help/assets/text-unlink.png)

使用此選項可刪除已應用於所選文本的連結。 僅當已選擇連結時，此選項才處於活動狀態。

#### 錨點 {#anchor}

![錨點表徵圖](/help/email/assets/anchor.png)

使用此選項將錨點插入文本。

#### 尋找

![查找表徵圖](/help/assets/text-find.png)

使用此選項可搜索文本以查找指定文本字串的出現情況。 選擇此選項將開啟一個窗口，用於指定搜索選項。

![查找示例](/help/assets/text-find-example.png)

輸入要搜索的文本，點擊或按一下 **查找** 開始搜索。 點擊或按一下x取消。
如果要根據大小寫進行精確匹配，請選擇選項 **匹配大小寫** 開始搜索。
如果找到匹配項，則會加亮該匹配項，並且搜索對話框會變暗。 點擊或按一下 **查找** 的子菜單。

![找到示例](/help/assets/text-find-example-found.png)

如果找不到其他出現的情況，將顯示一條消息，並從文本的開頭重新開始搜索。

![查找示例，不再出現](/help/assets/text-find-example-found-end.png)

#### 取代

![「替換」表徵圖](/help/assets/text-replace.png)

使用此選項可搜索文本以查找指定文本字串的具體值，並將匹配項替換為另一個字串。 選擇此選項將開啟一個窗口，用於指定搜索和替換選項。

![替換示例](/help/assets/text-replace-example.png)

輸入要搜索的文本以及應替換它的文本。

* 點擊或按一下 **查找** 開始搜索。 按一下或點擊x取消。
* 如果要根據大小寫進行精確匹配，請選擇選項 **匹配大小寫** 開始搜索。
* 選擇 **全部替換** 來同時替換所有出現的文本。

如果找到匹配項，則會加亮該匹配項，並且搜索對話框會變暗。 按一下 **查找** 按鈕，以搜索下一個出現項或選擇 **替換** 按鈕，將選定控制項在Tab鍵次序中下移一個位置。 的 **替換** 只有匹配後，按鈕才處於活動狀態。

按一下「查找」(find)和「替換」(replace)對話框時，該對話框將變為透明，按一下「替換」(replace)時，該對話框將變為不透明。 這允許作者審閱作者將替換的文本。

>[!NOTE]
>
>使用替換功能時，應在輸入要替換的字串的同時輸入要查找的字串。 但是，您仍可以按一下「查找」在替換字串之前搜索該字串。 如果在按一下「查找」後輸入替換字串，則搜索將重置為文本的開頭。

#### 復原

![撤消表徵圖](/help/email/assets/undo.png)

用於撤消富格文本編輯器中的上次編輯。

#### 重做

![重做表徵圖](/help/email/assets/redo.png)

用於使用撤消表徵圖撤消編輯。

#### 向左對齊文字

![左對齊表徵圖](/help/assets/text-left.png)

用於將文本與左邊距對齊。

#### 文字置中

![居中文本表徵圖](/help/assets/text-center.png)

用於居中文本。

#### 向右對齊文字

![右對齊表徵圖](/help/assets/text-right.png)

用於將文本與右邊距對齊。

#### 項目符號

![項目符號表徵圖](/help/assets/text-bullet.png)

用於將所選文本格式化為項目符號清單或開始在游標後插入項目符號清單。

要結束項目符號清單，請點擊或按一下 **項目符號** 按鈕或輸入兩個回車符。

#### 編號

![編號清單表徵圖](/help/assets/text-numbered.png)

用於將所選文本格式化為編號清單或開始在游標後插入編號清單。

要結束編號清單，請點擊或按一下 **編號** 按鈕或輸入兩個回車符。

#### 凸排

![輸出表徵圖](/help/assets/text-outdent.png)

用於減少在游標後輸入的選定文本或文本的縮進級別。

僅當游標的選定文本或位置已縮進時才處於活動狀態。

#### 縮排

![縮進表徵圖](/help/assets/text-indent.png)

用於增加游標後輸入的選定文本或文本的縮進級別。

#### 表格

![「表格」表徵圖](/help/assets/text-table.png)

用於將表插入文本。 選擇此選項將開啟一個窗口，用於指定表的詳細資訊。

![表示例](/help/assets/text-table-example.png)

* **列**  — 表的列數（必需）
* **行**  — 表的行數（必需）
* **寬度**  — 表的寬度
* **高度**  — 表的高度
* **單元格填充**  — 單元格內容周圍的空間
* **單元格間距**  — 單元格之間的空格
* **邊框**  — 表的邊框線的重量
   * 如果表的標題：
      * 應使用第一行
      * 應使用第一列
      * 應使用第一行和第一列
      * 或者不應使用標題。
* **標題**  — 表的標題

#### 影像

![影像表徵圖](/help/email/assets/image-icon.png)

用於對齊插入的影像。

#### 檢查拼寫

![檢查拼寫表徵圖](/help/assets/text-spellcheck.png)

用於檢查文本內容的拼寫。 可能的拼寫錯誤用破折的紅線加下划線。

有關拼寫檢查和自定義拼寫檢查詞典的詳細資訊，請參閱文檔 [配置RTF編輯器插件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html)。

#### 特殊字元 {#special-characters}

![特殊字元表徵圖](/help/assets/text-special-characters.png)

用於在文本中插入特殊字元。 選擇此選項將開啟一個顯示可用字元的窗口。

![特殊字元示例](/help/assets/text-special-characters-example.png)

點擊或按一下所需字元，將其插入游標後的文本。 可以插入多個字元。 點擊或按一下x關閉選擇窗口。

#### 來源編輯

![源編輯表徵圖](/help/assets/text-source.png)

用於查看和修改文本的HTML源。

點擊或按一下 **源編輯** 表徵圖以更改格式化視圖中文本的內容以查看原始HTML。 在此模式下，所有其它格式選項都被禁用。 點擊或按一下 **源編輯** 表徵圖以返回到格式化視圖。

>[!CAUTION]
>
>與訪問原始HTML的情況一樣，在使用 **源編輯** 選項！
>
>HTML輸入方式 **源編輯** 將掃描XSS風險，並刪除插入的任何指令碼，且不會顯示在生成的頁面上。 但是，在中輸入的HTML格式錯誤 **源編輯** 可能會中斷頁面的模板，導致意外的格式設定或導致生成的頁面無法使用。

>[!NOTE]
>
>因為HTML通過 **源編輯** 掃描XSS風險和任何指令碼並自動刪除那些發現的指令碼，保留的實際內容可能與在中輸入的內容不同 **源編輯**。 因此，為了保存使用 **源編輯**，必須先退出 **源編輯** 在普通編輯器中查看文本，然後再保存。

#### 段落格式

![段落格式表徵圖](/help/assets/text-paragraph.png)

用於將段落格式應用於選定文本或插入游標後的文本。 選擇此選項將開啟一個下拉清單，從中選擇段落格式。

![段落格式示例](/help/assets/text-paragraph-example.png)

#### 選取 Adobe Campaign 變數

![選擇Adobe Campaign變數表徵圖](/help/email/assets/select-adobe-campaign-variable-icon.png)

開啟 [選擇Adobe Campaign變數](/help/email/campaign-variables.md) 對話框，插入來自Adobe Campaign的動態內容。

### 聯機編輯 {#in-line-editing}

文本元件也可以進行串聯編輯。 要串聯編輯，請在內容頁面上選擇「電子郵件文本元件」。

![選擇電子郵件文本元件](/help/email/assets/email-text-select-component.png)

然後點擊或按一下 **編輯** 表徵圖。 工具欄將更改為顯示受限文本格式選項(包括對 **選擇Adobe Campaign變數** 的子菜單。

![行內編輯示例](/help/email/assets/email-text-edit-inline-example.png)

點擊或按一下工具欄中的複選標籤以保存更改，或按一下X放棄。

由於空間限制，並非所有格式選項都是串聯的。 要查看所有選項，請切換到全屏模式。

### 設定ID {#setting-id}

此選項允許控制HTM中元件的唯一標識符。

* 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
* 如果指定了ID，則作者有責任確保其唯一。
* 更改ID可能會影響CSS。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義內容作者可以使用哪些文本格式選項。

### 插件標籤 {#plugins-tab}

的 **插件** 頁籤用於啟用和禁用內容作者可用的各種文本格式選項。

### 功能 {#features}

![設計對話框功能](/help/assets/text-design-features.png)

可以為元件激活或停用以下特徵。

* 貼上純文字檔案
* 過去自單詞
* 查找和替換
* 撤消和重做
* 拼寫檢查
* 插入的影像修改選項
* HTML源編輯

### 正在格式化 {#formatting}

![設計對話框格式](/help/assets/text-design-formatting.png)

可以為元件激活或停用以下格式設定選項。

* 表格
* 清單（項目符號、數字、縮進、縮進）
* 對齊（左、右、居中）
* 粗體、斜體、下划線
* 連結（和取消連結）
* 下標/上標

### 段落樣式 {#paragraph-styles}

![設計對話框段落樣式](/help/assets/text-design-paragraph.png)

可以為元件激活或停用段落樣式。 激活後，可以定義允許的格式。

* 點擊或按一下 **添加** 按鈕。
* 輸入樣式的代碼和將在編輯對話框中顯示的說明。
* 要刪除樣式，請點擊或按一下 **刪除** 按鈕
* 要重新排列格式的順序，請點擊或按一下並拖動控制滑塊。

### 特殊字元 {#configuring-special-characters}

![設計對話框特殊字元](/help/assets/text-design-special-characters.png)

可以為元件激活或停用插入特殊字元的選項。 激活後，可以定義允許的字元。

* 點擊或按一下 **添加** 按鈕
* 輸入字元的HTML代碼和將在編輯對話框中顯示的說明。
* 要刪除字元，請點擊或按一下 **刪除** 按鈕
* 要重新排列字元點擊的順序，或按一下並拖動控制滑塊。

## 樣式頁籤 {#styles-tab}

電子郵件文本元件支AEM持 [風格系統](/help/get-started/authoring.md#component-styling)。
