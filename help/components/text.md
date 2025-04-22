---
title: 文字元件
description: 文字元件是RTF編輯和撰寫元件，具備就地編輯功能。
role: Architect, Developer, Admin, User
exl-id: bcea202a-9ecb-4dcd-99b6-0848cbb9d500
source-git-commit: da947be103bd68abad82fcfcbee58d527bc14dbd
workflow-type: tm+mt
source-wordcount: '2185'
ht-degree: 2%

---

# 文字元件{#text-component}

核心元件文字元件是RTF文字編輯和撰寫元件，具備就地編輯功能。

## 使用情況 {#usage}

文字元件提供強大的RTF編輯器，允許在簡化的內嵌編輯器中以全熒幕格式輕鬆編輯文字。

[編輯對話方塊](#edit-dialog)具有內嵌編輯功能，且全熒幕編輯對話方塊中可提供完整功能的有限選項。 使用[設計對話方塊](#design-dialog)，可以為內容作者設定範本的文字格式選項，例如標題、特殊字元和段落樣式。

## 版本和相容性 {#version-and-compatibility}

文字元件的目前版本是v2，此版本隨2018年1月的核心元件發行版本2.0.0的發佈引入，詳情請參閱本檔案。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service  |
|---|---|---|---|---|
| v2 | 與<br>[版本2.17.4](/help/versions.md)和先前版本相容 | 相容 | 相容 | 相容 |
| [v1](v1/text-v1.md) | 相容 | 相容 | - | 相容 |

如需核心元件版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗文字元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫](https://adobe.com/go/aem_cmp_library_text)。

### 技術細節 {#technical-details}

您可以在GitHub](https://adobe.com/go/aem_cmp_tech_text_v2)上找到有關文字元件[的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 文字元件和RTF編輯器 {#the-text-component-and-the-rich-text-editor}

核心元件文字元件採用AEM RTF編輯器(RTE)。 RTE為內容作者提供編輯其文字內容的廣泛功能。 RTE的設定非常靈活，並提供了許多選項。 如需如何設定RTE的詳細資訊，請參閱文章[設定RTF編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/rich-text-editor.html)和[設定RTF編輯器外掛程式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html)。

本文章的其餘部分示範使用現成可用的RTE組態的核心元件文字元件的標準組態。

>[!NOTE]
>
>只有由RTE](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html)的[UI組態啟用的選項在文字元件中才有提供。

## 編輯對話方塊 {#edit-dialog}

「編輯」對話方塊提供使用者將用於撰寫文字的標準RTF格式工具。

![文字元件的編輯對話方塊](/help/assets/text-edit.png)

### 粗體

![粗體圖示](/help/assets/text-bold.png)

用於套用粗體格式至選取的文字，或套用粗體格式至游標後輸入的文字。

**Ctrl+B**&#x200B;可以當做鍵盤快速鍵使用。

### 斜體

![斜體圖示](/help/assets/text-italic.png)

用於將斜體格式設定套用至選取的文字，或將游標後輸入的文字斜體化。

**Ctrl+I**&#x200B;可以當做鍵盤快速鍵使用。

### 底線

![加底線圖示](/help/assets/text-underline.png)

用於將底線格式套用至選取的文字，或在游標之後輸入的文字加上底線。

**Ctrl+U**&#x200B;可以當做鍵盤快速鍵使用。

### 下標

![下標圖示](/help/assets/text-subscript.png)

用於將選取的文字或在游標之後輸入的文字格式化為下標。

### 上標

![上標圖示](/help/assets/text-superscript.png)

用於將選取的文字或在游標之後輸入的文字格式化為上標。

### 貼上成文字

![貼上成文字圖示](/help/assets/text-paste-text.png)

將任何複製的文字貼上為純文字，不設定任何格式。

當選取此選項時，會開啟一個視窗，其中的文字可以貼上成無格式的純文字，作為插入文字中之前的預覽。 透過點選或按一下核取記號來接受，透過點選或按一下x來取消。

![貼上為文字範例](/help/assets/text-paste-text-example.png)

### 從 Word 貼上

![從Word貼上圖示](/help/assets/text-paste-word.png)

當選取此選項時，會開啟一個視窗，其中的文字可貼上並保留其格式，作為插入文字中之前的預覽。 透過點選或按一下核取記號來接受，透過點選或按一下x來取消。

![從Word貼上範例](/help/assets/text-paste-word-example.png)

### 超連結

![超連結圖示](/help/assets/text-hyperlink.png)

使用此選項可將選取的文字轉換為超連結或修改已定義的連結。 此選項只有在已選取文字並開啟視窗（其中包含設定連結的其他選項）時才會啟用。

![超連結範例](/help/assets/text-hyperlink-example.png)

* 輸入路徑
   * 使用「開啟選取範圍」對話方塊可在AEM中選擇路徑
   * 如果連結不在AEM中，請輸入絕對URL
      * 非絕對路徑會解譯為相對於AEM
* 輸入連結的替代描述文字
* 選取連結行為
   * 目標
   * 相同標籤
   * 新標籤
   * 父框架
   * 上框架

  點選或按一下核取記號以套用連結，或點選x以取消。

### 取消連結

![取消連結圖示](/help/assets/text-unlink.png)

使用此選項可移除已套用至所選文字的連結。 此選項僅在已選取連結時有效。

### 尋找

![尋找圖示](/help/assets/text-find.png)

使用此選項來搜尋文字，找出指定文字字串的出現位置。 選取此選項會開啟一個視窗，用以指定搜尋選項。

![尋找範例](/help/assets/text-find-example.png)

輸入您要搜尋的文字，然後點選或按一下[尋找] **開始搜尋。**點選或按一下x以取消。
如果您想要根據大小寫進行完全比對，請先選取選項**符合大小寫**，再開始搜尋。
如果找到相符專案，則會反白該專案，且搜尋對話方塊會變暗。 在灰色的對話方塊中，再次點選或按一下**尋找**&#x200B;按鈕以搜尋下一個專案。

![找到範例](/help/assets/text-find-example-found.png)

如果未找到其他事件，則會顯示訊息，並從文字的開頭重新開始搜尋。

![尋找範例不再發生](/help/assets/text-find-example-found-end.png)

### 取代

![取代圖示](/help/assets/text-replace.png)

使用此選項來搜尋文字以確定指定文字字串的出現位置，並將相符專案取代為其他字串。 選取此選項會開啟一個視窗，用於指定搜尋和取代選項。

![取代範例](/help/assets/text-replace-example.png)

輸入要搜尋的文字以及應取代的文字。

* 點選或按一下&#x200B;**尋找**&#x200B;開始搜尋。 按一下或點選x以取消。
* 如果您想要根據大小寫進行完全比對，請先選取選項&#x200B;**符合大小寫**，再開始搜尋。
* 選取&#x200B;**全部取代**&#x200B;以一次取代所有出現的文字。

如果找到相符專案，則會反白該專案，且搜尋對話方塊會變暗。 在灰色的對話方塊中再次按一下&#x200B;**尋找**&#x200B;按鈕以搜尋下一個專案，或選取&#x200B;**取代**&#x200B;按鈕以取代醒目提示的相符文字。 請注意，**Replace**&#x200B;按鈕只有在進行比對後才會啟用。

按一下「尋找」時，「尋找和取代」對話方塊會變成透明，按一下「取代」時，對話方塊會變成不透明。 這可讓作者檢閱作者將取代的文字。

>[!NOTE]
>
>使用取代功能時，要取代的取代字串應與尋找字串同時輸入。 不過，您仍然可以按一下「尋找」來搜尋字串，然後再取代它。 如果在按一下「尋找」之後輸入取代字串，則搜尋會重設為文字的開頭。


### 向左對齊文字

![靠左對齊圖示](/help/assets/text-left.png)

用於將文字對齊左邊界。

### 文字置中

![居中對齊文字圖示](/help/assets/text-center.png)

用於將文字置中。

### 向右對齊文字

![靠右對齊圖示](/help/assets/text-right.png)

用於將文字對齊右邊界。

### 項目符號

![專案符號圖示](/help/assets/text-bullet.png)

用於將選取的文字格式化為專案符號清單，或在游標後開始插入專案符號清單。

若要結束專案符號清單，請再次點選或按一下&#x200B;**專案符號**&#x200B;按鈕，或輸入兩個歸位字元。

### 編號

![編號清單圖示](/help/assets/text-numbered.png)

用於將選取的文字格式化為編號清單，或在游標後開始插入編號清單。

若要結束編號清單，請再次點選或按一下&#x200B;**編號**&#x200B;按鈕或輸入兩個歸位字元。

### 凸排

![凸排圖示](/help/assets/text-outdent.png)

用來減少所選文字的縮排層級，或在游標之後輸入的文字。

只有當選取的文字或游標位置已經縮排時，才為作用中。

### 縮排

![縮排圖示](/help/assets/text-indent.png)

用於增加所選文字的縮排層級，或在游標之後輸入的文字。

### 表格

![表格圖示](/help/assets/text-table.png)

用於將表格插入文字中。 選取此選項會開啟一個視窗，用於指定表格的詳細資訊。

![資料表範例](/help/assets/text-table-example.png)

* **欄** — 資料表的欄數（必要）
* **列** — 資料表的列數（必填）
* **寬度** — 表格的寬度
* **高度** — 資料表的高度
* **儲存格內距** — 儲存格內容周圍的空間
* **儲存格間距** — 儲存格之間的間距
* **框線** — 資料表的框線粗細
   * 如果針對表格的標頭：
      * 應使用第一列
      * 應使用第一欄
      * 應使用第一列和第一欄
      * 或不應使用任何標頭。
* **標題** — 資料表的標題

### 檢查拼字

![檢查拼字圖示](/help/assets/text-spellcheck.png)

用於檢查文字內容的拼字。 可能的拼字錯誤會以紅色虛線加底線。

如需拼字檢查與自訂拼字檢查字典的詳細資訊，請參閱檔案[設定RTF編輯器外掛程式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html)。

### 特殊字元 {#special-characters}

![特殊字元圖示](/help/assets/text-special-characters.png)

用於將特殊字元插入文字中。 選取此選項會開啟顯示可用字元的視窗。

![特殊字元範例](/help/assets/text-special-characters-example.png)

點選或按一下所需的字元，將其插入游標之後的文字中。 可以插入多個字元。 點選或按一下x以關閉選取範圍視窗。

### 來源編輯

![Source編輯圖示](/help/assets/text-source.png)

用於檢視及修改文字的HTML來源。

點選或按一下&#x200B;**Source Edit**&#x200B;圖示，從格式化檢視變更文字內容以檢視原始HTML。 在此模式中，會停用所有其他格式選項。 再次點選或按一下「**Source編輯**」圖示可返回格式化檢視。

>[!CAUTION]
>
>和存取原始HTML的情況一樣，使用&#x200B;**Source編輯**&#x200B;選項時必須小心！
>
>已掃描透過&#x200B;**Source Edit**&#x200B;輸入的HTML是否有XSS風險，插入的任何指令碼都會被移除，且不會顯示在結果頁面上。 不過，在&#x200B;**Source Edit**&#x200B;中輸入的格式錯誤的HTML可能會破壞頁面的範本，導致未預期的格式設定或導致產生的頁面無法使用。

>[!NOTE]
>
>由於已掃描透過&#x200B;**HTML Edit**&#x200B;輸入的Source是否有XSS風險和任何指令碼，並且會自動移除找到的指令碼，因此保留的實際內容可能會與&#x200B;**Source Edit**&#x200B;中輸入的內容不同。 因此，若要儲存使用&#x200B;**Source Edit**&#x200B;所做的變更，您必須先結束&#x200B;**Source Edit**，以在儲存前於一般編輯器中檢視文字。

### 段落格式

![段落格式圖示](/help/assets/text-paragraph.png)

用於將段落格式套用至選取的文字或游標後插入的文字。 選取此選項會開啟一個下拉式清單，您可從其中選取段落格式。

![段落格式範例](/help/assets/text-paragraph-example.png)

### 內嵌編輯 {#in-line-editing}

文字元件也可以內嵌編輯，但由於空間限制，並非所有格式選項都內嵌可用。 若要檢視所有選項，請切換到全熒幕模式。

![內嵌編輯範例](/help/assets/text-edit-inline-example.png)

### 設定ID {#setting-id}

此選項可讓您控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。

* 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
* 若指定ID，作者應負責確認該ID為唯一ID。
* 變更ID會對CSS、JS和資料層追蹤造成影響。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義哪些文字格式選項可供內容作者使用。

### 外掛程式標籤 {#plugins-tab}

「外掛程式」索引標籤可用來啟用和停用內容作者可用的各種文字格式選項。

### 功能 {#features}

![設計對話方塊功能](/help/assets/text-design-features.png)

可為元件啟用或停用下列功能。

* 貼上純文字
* 從文字貼上
* 尋找並取代
* 拼字檢查程式
* 插入的影像修改選項
* HTML來源編輯

### 正在格式化 {#formatting}

![設計對話方塊格式](/help/assets/text-design-formatting.png)

可為元件啟用或停用下列格式選項。

* 表格
* 清單（專案符號、數字、縮排、減少縮排）
* 對齊方式（左、右、置中）
* 粗體、斜體、底線
* 連結（和取消連結）
* 下標/上標

### 段落樣式 {#paragraph-styles}

![設計對話方塊段落樣式](/help/assets/text-design-paragraph.png)

可為元件啟用或停用段落樣式。 啟用時，可以定義允許的格式。

* 點選或按一下&#x200B;**新增**&#x200B;按鈕以插入新樣式。
* 輸入將在「編輯」對話方塊中顯示的樣式代碼和說明。
* 若要移除樣式，請點選或按一下&#x200B;**刪除**&#x200B;按鈕。
* 若要重新排列格式，請點選或按一下並拖曳控點。

### 特殊字元 {#configuring-special-characters}

![設計對話方塊特殊字元](/help/assets/text-design-special-characters.png)

可以為元件啟用或停用插入特殊字元的選項。 啟用時，可以定義允許的字元。

* 點選或按一下&#x200B;**新增**&#x200B;按鈕以插入新字元。
* 輸入字元的HTML程式碼，以及將顯示在編輯對話方塊中的說明。
* 若要移除字元點選或按一下&#x200B;**刪除**&#x200B;按鈕。
* 若要重新排列字元順序，請點選或按一下並拖曳控點。

## 樣式索引標籤 {#styles-tab}

文字元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe使用者端資料層 {#data-layer}

文字元件支援[Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
