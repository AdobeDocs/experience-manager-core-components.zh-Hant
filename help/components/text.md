---
title: 文字元件
description: 文本元件是富文本編輯和合成元件，具有就地編輯功能。
role: Architect, Developer, Admin, User
exl-id: bcea202a-9ecb-4dcd-99b6-0848cbb9d500
source-git-commit: d435e82d5950336c66997399829e3baf23f170c0
workflow-type: tm+mt
source-wordcount: '2205'
ht-degree: 2%

---

# 文字元件{#text-component}

核心元件文本元件是RTF編輯和合成元件，具有就地編輯功能。

## 使用狀況 {#usage}

文字元件提供強大的RTF編輯器，以簡化的內嵌編輯器和全螢幕格式輕鬆編輯文字。

[edit dialog](#edit-dialog)使用全螢幕編輯對話框中提供的有限功能選項進行串聯編輯。 使用[設計對話框](#design-dialog)，可為內容作者的模板配置標題、特殊字元和段落樣式等文本格式選項。

## 版本與相容性 {#version-and-compatibility}

目前的文字元件版本為v2，此版本於2018年1月隨核心元件2.0.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|---|
| v2 | 相容 | 相容 | 相容 |
| [v1](v1/text-v1.md) | 相容 | 相容 | - |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗文字元件，並查看其設定選項以及HTML和JSON輸出的範例，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_text)。

### 技術詳細資訊 {#technical-details}

有關文字元件[的最新技術檔案可在GitHub](https://adobe.com/go/aem_cmp_tech_text_v2)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 文字元件和RTF編輯器 {#the-text-component-and-the-rich-text-editor}

核心元件文字元件採用AEM RTF編輯器(RTE)。 RTE為內容作者提供多種功能，可編輯其文字內容。 RTE的設定非常有彈性，並提供許多選項。 有關如何設定RTE的進一步詳細資訊，請參閱[設定RTF編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/rich-text-editor.html)和[設定RTF編輯器外掛程式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html)文章。

本文的其餘部分示範核心元件文字元件的標準設定及現成可用的RTE設定。

>[!NOTE]
>
>只有由RTE](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html)的[ UI配置啟用的選項可由「文本元件」使用。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊提供使用者預期要撰寫文字的標準RTF格式工具。

![文本元件的編輯對話框](/help/assets/text-edit.png)

### 粗體

![粗體圖示](/help/assets/text-bold.png)

用於將粗體格式應用於選定文本或在游標後輸入的大膽格式文本。

**Ctrl+** B可用作鍵盤快速鍵。

### 斜體

![斜體圖示](/help/assets/text-italic.png)

用於將斜體格式應用到選定文本或在游標之後輸入的斜體文本。

**Ctrl+** 可用作鍵盤快捷鍵。

### 底線

![下划線表徵圖](/help/assets/text-underline.png)

用於將下划線格式應用於在游標之後輸入的選定文本或下划線文本。

**Ctrl+** Ucan用作鍵盤快捷鍵。

### 下標

![下標表徵圖](/help/assets/text-subscript.png)

用於將游標之後輸入的選定文本或文本格式化為下標。

### 上標

![上標表徵圖](/help/assets/text-superscript.png)

用於將游標之後輸入的選定文本或文本格式化為上標。

### 貼上為文字

![貼上為文字圖示](/help/assets/text-paste-text.png)

將任何複製的文本貼上為純文字檔案，不使用任何格式。

選取此選項時，將開啟一個窗口，其中文本可以貼上為純文字檔案，在插入文本之前，不以格式作為預覽。 點選或按一下複選標籤以接受，點選或按一下x以取消。

![貼上為文字範例](/help/assets/text-paste-text-example.png)

### 從 Word 貼上

![「從Word貼上」圖示](/help/assets/text-paste-word.png)

選取此選項時，會開啟一個視窗，可以貼上文字，在將其插入文字之前，將其格式維持為預覽。 點選或按一下複選標籤以接受，點選或按一下x以取消。

![從Word貼上範例](/help/assets/text-paste-word-example.png)

### 超連結

![超連結表徵圖](/help/assets/text-hyperlink.png)

使用此選項可將選定文本轉換為超連結或修改已定義的連結。 只有在已選取文字時，此選項才會作用中，並會開啟包含其他連結設定選項的視窗。

![超連結範例](/help/assets/text-hyperlink-example.png)

* 輸入路徑
   * 使用「開啟選擇」對話框在AEM中選擇路徑
   * 如果連結不在AEM內，請輸入絕對URL
      * 非絕對路徑會解譯為相對於AEM
* 輸入連結的替代描述性文字
* 選取連結行為
   * 目標
   * 相同索引標籤
   * 新索引標籤
   * 父框架
   * 上框架

   點選或按一下核取記號以套用連結，或按x以取消。

### 取消連結

![取消連結表徵圖](/help/assets/text-unlink.png)

使用此選項可移除已套用至所選文字的連結。 只有在已選取連結時，此選項才會作用中。

### 尋找

![查找表徵圖](/help/assets/text-find.png)

使用此選項可搜索文本以查找指定文本字串的出現。 選擇此選項將開啟一個窗口，用於指定搜索選項。

![尋找範例](/help/assets/text-find-example.png)

輸入要搜索的文本，點選或按一下&#x200B;**Find**以開始搜索。 點選或按一下x以取消。
如果要根據大小寫進行完全匹配，請在開始搜索之前選擇選項**匹配大小寫**。
如果找到相符項目，則會加亮顯示，而搜尋對話方塊則呈現灰色。 在灰色對話方塊中，再點選或按一下**尋找**&#x200B;按鈕，以搜尋下一個出現次數。

![查找找到的示例](/help/assets/text-find-example-found.png)

如果找不到其他發生次數，則會顯示訊息，並從文字的開頭開始搜尋。

![查找示例，不再出現](/help/assets/text-find-example-found-end.png)

### 取代

![取代圖示](/help/assets/text-replace.png)

使用此選項可搜索文本以查找指定文本字串的出現次數，並將匹配項替換為另一個字串。 選擇此選項將開啟一個窗口，用於指定搜索和替換選項。

![取代範例](/help/assets/text-replace-example.png)

輸入要搜索的文本以及應替換的文本。

* 點選或按一下&#x200B;**尋找**&#x200B;以開始搜尋。 按一下或點選x以取消。
* 如果要根據大小寫進行完全匹配，請在開始搜索之前選擇選項&#x200B;**匹配大小寫**。
* 選擇&#x200B;**全部替換**&#x200B;一次替換所有出現的文本。

如果找到相符項目，則會加亮顯示，而搜尋對話方塊則呈現灰色。 再次在灰色對話框中按一下&#x200B;**查找**&#x200B;按鈕以搜索下一個出現項，或選擇&#x200B;**替換**&#x200B;按鈕以替換突出顯示的匹配文本。 請注意，**Replace**&#x200B;按鈕僅在匹配後才處於活動狀態。

點擊查找時，查找和替換對話框變為透明，點擊替換時變為不透明。 這可讓作者檢閱作者將取代的文字。

>[!NOTE]
>
>使用取代功能時，應在輸入要取代的取代字串時與尋找字串同時輸入。 不過，在替換字串之前，您仍可以按一下「尋找」來搜尋字串。 如果在按一下「查找」後輸入替換字串，則搜索將重置為文本的開頭。


### 向左對齊文字

![靠左對齊圖示](/help/assets/text-left.png)

用來將文字對齊左側邊界。

### 文字置中

![中間文字圖示](/help/assets/text-center.png)

用來將文字置中。

### 向右對齊文字

![靠右對齊圖示](/help/assets/text-right.png)

用於將文字對齊右側邊界。

### 項目符號

![項目符號圖示](/help/assets/text-bullet.png)

用於將所選文本格式化為項目符號清單，或在游標後開始插入項目符號清單。

若要結束項目符號清單，請點選或再次按一下&#x200B;**項目符號**&#x200B;按鈕，或輸入兩個歸位字元。

### 編號

![編號清單圖示](/help/assets/text-numbered.png)

用於將所選文本格式化為編號清單，或開始在游標後插入編號清單。

若要結束編號清單，請點選或再次按一下「編號」**「編號」按鈕，或輸入兩個歸位字元。**

### 凸排

![輸出表徵圖](/help/assets/text-outdent.png)

用於減少在游標之後輸入的選定文本或文本的縮進級別。

僅當游標的選定文本或位置已縮排時才處於活動狀態。

### 縮排

![縮進表徵圖](/help/assets/text-outdent.png)

用於增加在游標之後輸入的選定文本或文本的縮進級別。

### 表格

![表格圖示](/help/assets/text-table.png)

用於將表插入文本中。 選擇此選項將開啟一個窗口，用於指定表的詳細資訊。

![表格範例](/help/assets/text-table-example.png)

* **列**  — 表的列數（必要）
* **行**  — 表格的行數（必要）
* **寬度**  — 表格的寬度
* **高度**  — 表格的高度
* **儲存格邊框間距**  — 儲存格內容周圍的空格
* **儲存格間距**  — 儲存格之間的空間
* **邊框**  — 表格邊框的粗細
   * 若表格的標題：
      * 應使用第一列
      * 應使用第一欄
      * 應使用第一列和第一列
      * 或者不應使用標題。
* **註解**  — 表格的註解

### 檢查拼寫

![檢查拼寫表徵圖](/help/assets/text-spellcheck.png)

用於檢查文本內容的拼寫。 可能拼錯的字，加上破折的紅線。

有關拼字檢查和自定義拼字檢查字典的詳細資訊，請參見文檔[配置RTF編輯器插件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html)。

### 特殊字元 {#special-characters}

![特殊字元表徵圖](/help/assets/text-special-characters.png)

用於將特殊字元插入文字中。 選擇此選項將開啟一個顯示可用字元的窗口。

![特殊字元範例](/help/assets/text-special-characters-example.png)

點選或按一下所需的字元，將其插入游標後的文字中。 可插入多個字元。 點選或按一下x以關閉選取視窗。

### 來源編輯

![源編輯表徵圖](/help/assets/text-source.png)

用於查看和修改文本的HTML源。

點選或按一下&#x200B;**來源編輯**&#x200B;圖示，以從格式化檢視變更文字的內容，以檢視原始HTML。 在此模式中，會禁用所有其他格式選項。 再次點選或按一下「**來源編輯**」圖示，以返回格式化檢視。

>[!CAUTION]
>
>如同存取原始HTML的情況一樣，使用&#x200B;**來源編輯**&#x200B;選項時，請務必小心！
>
>透過&#x200B;**Source Edit**&#x200B;輸入的HTML會掃描XSS風險，且會移除任何已插入的指令碼，且不會顯示在產生的頁面上。 但是，在&#x200B;**Source Edit**&#x200B;中輸入的格式錯誤的HTML可能會中斷頁面的模板，導致意外的格式化或導致頁面無法使用。

>[!NOTE]
>
>由於透過&#x200B;**Source Edit**&#x200B;輸入的HTML會掃描XSS風險和任何指令碼，並自動刪除發現的指令碼，因此保存的實際內容可能與在&#x200B;**Source Edit**&#x200B;中輸入的內容不同。 因此，要保存使用&#x200B;**源編輯**&#x200B;所做的更改，必須先退出&#x200B;**源編輯**&#x200B;以在正常編輯器中查看文本，然後才保存。

### 段落格式

![段落格式表徵圖](/help/assets/text-paragraph.png)

用於將段落格式應用於選定文本或游標後插入的文本。 選擇此選項將開啟一個下拉清單，從中選擇段落格式。

![段落格式示例](/help/assets/text-paragraph-example.png)

### 線上編輯 {#in-line-editing}

文本元件也可以聯機編輯，但由於空間限制，並非所有格式選項都可以聯機編輯。 若要查看所有選項，請切換至全螢幕模式。

![行內編輯範例](/help/assets/text-edit-inline-example.png)

### 設定和ID {#setting-id}

此選項可控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一標識符。

* 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
* 若已指定ID，則作者應負責確認其唯一。
* 變更ID可能會影響CSS、JS和資料層追蹤。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義內容作者可使用的文字格式選項。

### 外掛程式標籤 {#plugins-tab}

外掛程式索引標籤可用來啟用和停用內容作者可用的各種文字格式選項。

### 功能 {#features}

![設計對話方塊功能](/help/assets/text-design-features.png)

可為元件啟用或停用下列功能。

* 貼上純文字
* 過去
* 查找和替換
* 拼字檢查程式
* 插入的影像修改選項
* HTML來源編輯

### 正在格式化 {#formatting}

![設計對話方塊格式](/help/assets/text-design-formatting.png)

可為元件啟用或停用下列格式選項。

* 表格
* 清單（項目符號、數字、縮進、縮進）
* 對齊方式（左、右、居中）
* 粗體，斜體，底線
* 連結（和取消連結）
* 子/上標

### 段落樣式 {#paragraph-styles}

![設計對話框段落樣式](/help/assets/text-design-paragraph.png)

可為元件啟用或停用段落樣式。 激活後，可定義允許的格式。

* 點選或按一下&#x200B;**Add**&#x200B;按鈕以插入新樣式。
* 輸入樣式的代碼以及將在編輯對話框中顯示的說明。
* 若要移除樣式點選，或按一下「**刪除**」按鈕。
* 要重新排列格式的順序，請點選或按一下並拖動控點。

### 特殊字元 {#configuring-special-characters}

![設計對話框特殊字元](/help/assets/text-design-special-characters.png)

可為元件啟用或停用插入特殊字元的選項。 啟動後，可定義允許的字元。

* 點選或按一下&#x200B;**Add**&#x200B;按鈕以插入新字元。
* 輸入字元的HTML代碼，以及將在編輯對話方塊中顯示的說明。
* 若要移除字元點選，或按一下「**刪除**」按鈕。
* 要重新排列字元點選的順序，或按一下並拖動控點。

## 樣式標籤 {#styles-tab}

文本元件支援AEM [style system](/help/get-started/authoring.md#component-styling)。

## Adobe用戶端資料層 {#data-layer}

文本元件支援[Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
