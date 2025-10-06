---
title: 電子郵件文字元件
description: 電子郵件文字元件是 RTF 編輯和撰寫元件，具備就地編輯功能。
role: Architect, Developer, Admin, User
exl-id: 4aa192f6-8314-40e7-8732-c6626d647986
index: false
source-git-commit: eb77567dc32cccb81a9fc131493d11fb55b7e93b
workflow-type: ht
source-wordcount: '2264'
ht-degree: 100%

---


# 電子郵件文字元件 {#email-text-component}

電子郵件文字元件是 RTF 編輯和撰寫元件，具備就地編輯功能。

## 用途 {#usage}

電子郵件文字元件提供強大的 RTF 編輯器，允許在簡化的內嵌編輯器與全螢幕格式中輕鬆編輯文字。

* [編輯對話框](#edit-dialog)提供內嵌編輯功能，但選項有限；完整功能則可在全螢幕編輯對話框中使用。
* 使用[設計對話框](#design-dialog)，內容作者可設定範本的文字格式選項，例如標題、特殊字元和段落樣式。

## 版本和相容性 {#version-and-compatibility}

電子郵件文字元件的目前版本為 v1，此版本於 2022 年 10 月隨著電子郵件核心元件 X 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 相容 | - | - |

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[電子郵件核心元件版本](/help/email/versions.md)文件。

### 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_email_text_v1)有關電子郵件文字元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 電子郵件文字元件和 RTF 文字編輯器 {#the-text-component-and-the-rich-text-editor}

電子郵件文字元件採用 AEM RTF 文字編輯器 (RTE)。RTE 為內容作者提供編輯其文字內容的廣泛功能。RTE 的設定有彈性，並提供多個選項。如需有關如何設定 RTE 的詳細資訊，請參閱[設定 RTF 文字編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/rich-text-editor.html?lang=zh-Hant)和[設定 RTF 文字編輯器外掛程式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html?lang=zh-Hant)文章。

本文件的其餘部分示範使用現成 RTE 設定的電子郵件文字元件的標準設定。

>[!NOTE]
>
>只有 [RTE 的 UI 設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html?lang=zh-Hant)所啟用的選項在電子郵件文字元件中可用。

## 編輯對話框 {#edit-dialog}

![文字元件的編輯對話框](/help/email/assets/email-text-edit.png)

### 格式選項 {#options}

編輯對話框提供使用者將用於撰寫文字的標準 RTF 格式工具。

#### 粗體

![粗體圖示](/help/assets/text-bold.png)

用於將粗體格式套用至選取的文字，或將游標後方輸入的文字設定為粗體格式。

**Ctrl+B** 可以當做鍵盤快速鍵使用。

#### 斜體

![斜體圖示](/help/assets/text-italic.png)

用於將斜體格式套用至選取的文字，或將游標後方輸入的文字設定為斜體格式。

**Ctrl+I** 可以當做鍵盤快速鍵使用。

#### 底線

![底線圖示](/help/assets/text-underline.png)

用於將底線格式套用至選取的文字，或將游標後方輸入的文字加上底線。

**Ctrl+U** 可以當做鍵盤快速鍵使用。

#### 下標

![下標圖示](/help/assets/text-subscript.png)

用於將選取的文字或在游標後方輸入的文字格式化為下標。

#### 上標

![上標圖示](/help/assets/text-superscript.png)

用於將選取的文字或在游標後方輸入的文字格式化為上標。

#### 以文字格式貼上

![以文字格式貼上圖示](/help/assets/text-paste-text.png)

將任何複製的文字以純文字形式貼上，不包含任何格式。

當選取此選項時，會開啟一個視窗，可將文字以不含任何格式的純文字形式貼上，作為預覽內容，之後再插入至正文。點選或按一下核取記號即可接受，點選或按一下 x 可取消。

![以文字格式貼上範例](/help/assets/text-paste-text-example.png)

#### 從 Word 貼上

![從 Word 貼上圖示](/help/assets/text-paste-word.png)

當選取此選項時，會開啟一個視窗，可將文字保留原有格式貼上，作為預覽內容，之後再插入至正文。點選或按一下核取記號即可接受，點選或按一下 x 可取消。

![從 Word 貼上範例](/help/assets/text-paste-word-example.png)

#### 超連結

![超連結圖示](/help/assets/text-hyperlink.png)

使用此選項可將選取的文字轉換為超連結或修改已定義的連結。此選項會開啟一個視窗，其中包含設定連結的其他選項。

![超連結範例](/help/assets/text-hyperlink-example.png)

* 輸入路徑
   * 使用&#x200B;**開啟選取**&#x200B;對話框，在 AEM 中選擇路徑
   * 如果連結不在 AEM 中，請輸入絕對 URL
      * 非絕對路徑會解譯為相對於 AEM
* 輸入連結的替代說明文字
* 選取連結行為
   * 目標
   * 相同索引標籤
   * 新索引標籤
   * 上層框架
   * 上框架

點選或按一下核取記號以套用連結，或點選 x 以取消。

#### 取消連結

![取消連結圖示](/help/assets/text-unlink.png)

使用此選項可移除已套用至所選文字的連結。此選項僅在已選取連結時才會啟用。

#### 錨點 {#anchor}

![錨點圖示](/help/email/assets/anchor.png)

使用此選項可在文字中插入錨點。

#### 尋找

![尋找圖示](/help/assets/text-find.png)

使用此選項來搜尋文字，找出指定文字字串的出現位置。選取此選項會開啟一個視窗，用以指定搜尋選項。

![尋找範例](/help/assets/text-find-example.png)

輸入您要搜尋的文字，然後點選或按一下&#x200B;**尋找**開始搜尋。點選或按一下 x 以取消。
如果您想要根據大小寫進行完全比對，請先選取**符合大小寫**選項，再開始搜尋。
如果找到相符項目，則會醒目提示該項目，且搜尋對話框會變暗。在變暗的對話框中，再次點選或按一下**尋找**&#x200B;按鈕以搜尋下一個出現位置。

![已找到的尋找範例](/help/assets/text-find-example-found.png)

如果未找到其他出現位置，則會顯示訊息，並從文字的開頭重新開始搜尋。

![找不到其他出現位置的尋找範例](/help/assets/text-find-example-found-end.png)

#### 取代

![取代圖示](/help/assets/text-replace.png)

使用此選項來搜尋文字，找出指定文字字串的出現位置，並將相符項目取代為其他字串。選取此選項會開啟一個視窗，用於指定搜尋和取代選項。

![取代範例](/help/assets/text-replace-example.png)

輸入要搜尋的文字以及應取代的文字。

* 點選或按一下&#x200B;**尋找**&#x200B;開始搜尋。按一下或點選 x 以取消。
* 如果您想要根據大小寫進行完全比對，請先選取&#x200B;**符合大小寫**&#x200B;選項，再開始搜尋。
* 選取&#x200B;**全部取代**&#x200B;以一次取代所有出現的文字。

如果找到相符項目，則會醒目提示該項目，且搜尋對話框會變暗。在變暗的對話框中再次按一下&#x200B;**尋找**&#x200B;按鈕以搜尋下一個出現位置，或選取&#x200B;**取代**&#x200B;按鈕以取代醒目提示的相符文字。**取代**&#x200B;按鈕只有在進行比對後才會啟用。

按一下「尋找」時，「尋找和取代」對話框會變成透明，按一下「取代」時，對話框會變成不透明。這可讓作者檢閱作者將取代的文字。

>[!NOTE]
>
>使用取代功能時，要取代的字串應與要尋找的字串同時輸入。不過，您仍然可以按一下「尋找」來搜尋字串，然後再取代它。如果在按一下「尋找」之後輸入取代字串，則搜尋會重設回文字的開頭。

#### 還原

![還原圖示](/help/email/assets/undo.png)

用於還原 RTF 編輯器中的上次編輯。

#### 重做

![重做圖示](/help/email/assets/redo.png)

用於還原透過還原圖示還原的編輯。

#### 向左對齊文字

![向左對齊圖示](/help/assets/text-left.png)

用於將文字對齊左邊界。

#### 文字置中

![文字置中圖示](/help/assets/text-center.png)

用於將文字置中。

#### 向右對齊文字

![向右對齊圖示](/help/assets/text-right.png)

用於將文字對齊右邊界。

#### 項目符號

![項目符號圖示](/help/assets/text-bullet.png)

用於將選取的文字格式化為項目符號清單，或在游標後開始插入項目符號清單。

若要結束項目符號清單，請再次點選或按一下&#x200B;**「項目符號」**&#x200B;按鈕，或輸入兩個歸位字元。

#### 編號

![編號清單圖示](/help/assets/text-numbered.png)

用於將選取的文字格式化為編號符號清單，或在游標後開始插入編號符號清單。

若要結束編號符號清單，請再次點選或按一下&#x200B;**「編號符號」**&#x200B;按鈕，或輸入兩個歸位字元。

#### 凸排

![凸排圖示](/help/assets/text-outdent.png)

用來減少所選文字或在游標之後輸入的文字的縮排等級。

只有當選取的文字或游標位置已經縮排時才會啟用。

#### 縮排

![縮排圖示](/help/assets/text-indent.png)

用來增加所選文字或在游標之後輸入的文字的縮排等級。

#### 表格

![表格圖示](/help/assets/text-table.png)

用於將表格插入文字中。選取此選項會開啟一個視窗，用於指定表格的詳細資訊。

![表格範例](/help/assets/text-table-example.png)

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

#### 影像

![影像圖示](/help/email/assets/image-icon.png)

用於對齊插入的影像。

#### 檢查拼字

![檢查拼字圖示](/help/assets/text-spellcheck.png)

用於檢查文字內容的拼字。可能的拼字錯誤會以紅色虛線加底線標示。

如需拼字檢查與自訂拼字檢查字典的詳細資訊，請參閱[設定 RTF 文字編輯器外掛程式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html?lang=zh-Hant)文件。

#### 特殊字元 {#special-characters}

![特殊字元圖示](/help/assets/text-special-characters.png)

用於將特殊字元插入文字中。選取此選項會開啟顯示可用字元的視窗。

![特殊字元範例](/help/assets/text-special-characters-example.png)

點選或按一下所需的字元，將其插入游標之後的文字中。可以插入多個字元。點選或按一下 x 以關閉選取視窗。

#### 原始碼編輯

![原始碼編輯圖示](/help/assets/text-source.png)

用於檢視及修改文字的 HTML 原始碼。

點選或按一下&#x200B;**原始碼編輯**&#x200B;圖示，從格式化檢視變更文字內容以檢視原始 HTML。在此模式中，會停用所有其他格式選項。再次點選或按一下&#x200B;**原始碼編輯** 圖示可返回格式化檢視。

>[!CAUTION]
>
>和存取原始 HTML 的情況一樣，使用&#x200B;**原始碼編輯**&#x200B;選項時必須小心！
>
>透過&#x200B;**原始碼編輯** 輸入的 HTML 會進行掃描以確認是否有 XSS 風險，若插入任何指令碼都會被移除，且不會顯示在結果頁面上。不過，在&#x200B;**原始碼編輯**&#x200B;中輸入格式錯誤的 HTML 可能會破壞頁面的範本，導致非預期的格式設定或導致產生的頁面無法使用。

>[!NOTE]
>
>由於透過&#x200B;**原始碼編輯**&#x200B;輸入的 HTML 已掃描確認是否具有 XSS 風險和任何指令碼，並且會自動移除找到的指令碼，因此保留的實際內容可能會與&#x200B;**原始碼編輯**&#x200B;中輸入的內容不同。因此，若要儲存使用&#x200B;**原始碼編輯**&#x200B;所做的變更，您必須先退出&#x200B;**原始碼編輯** ，以在儲存前於一般編輯器中檢視文字。

#### 段落格式

![段落格式圖示](/help/assets/text-paragraph.png)

用於將段落格式套用至所選文字或在游標之後輸入的文字。選取此選項會開啟一個下拉式清單，您可從其中選取段落格式。

![段落格式範例](/help/assets/text-paragraph-example.png)

#### 選取 Adobe Campaign 變數

![選取 Adobe Campaign 變數圖示](/help/email/assets/select-adobe-campaign-variable-icon.png)

開啟[選取 Adobe Campaign 變數](/help/email/campaign-variables.md)對話框，插入來自 Adobe Campaign 的動態內容。

### 內嵌編輯 {#in-line-editing}

文字元件也可以內嵌編輯。若要內嵌編輯，請在內容頁面上選取電子郵件文字元件。

![選取電子郵件文字元件](/help/email/assets/email-text-select-component.png)

然後點選或按一下元件上方彈出的工具列上的&#x200B;**編輯**&#x200B;圖示。工具列會變更為顯示有限的文字格式選項 (包括存取&#x200B;**選取 Adobe Campaign 變數**&#x200B;選項)，您可以編輯內嵌文字。

![內嵌編輯範例](/help/email/assets/email-text-edit-inline-example.png)

點選或按一下工具列中的核取記號以儲存您的變更，或點選 X 以捨棄。

由於空間限制，並非所有格式選項都可以內嵌使用。若要檢視所有選項，請切換至全螢幕模式。

### 設定 ID {#setting-id}

此選項允許控制 HTML 中元件的唯一識別碼。

* 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
* 若已指定 ID，則作者應確保其為唯一識別碼。
* 變更該 ID 會對 CSS 產生影響。

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可定義可供內容作者使用的文字格式選項。

### 外掛程式索引標籤 {#plugins-tab}

**外掛程式**&#x200B;索引標籤可用來啟用和停用內容作者可用的各種文字格式選項。

### 功能 {#features}

![設計對話框功能](/help/assets/text-design-features.png)

可為元件啟用或停用下列功能。

* 貼上純文字
* 從 Word 貼上
* 尋找並取代
* 還原和重做
* 拼字檢查工具
* 插入的影像修改選項
* HTML 原始碼編輯

### 格式化 {#formatting}

![格式化設計對話框](/help/assets/text-design-formatting.png)

可為元件啟用或停用下列格式選項。

* 表格
* 清單 (項目符號、數字、縮排、凸排)
* 對齊方式 (左、右、置中)
* 粗體、斜體、底線
* 連結 (和取消連結)
* 下標/上標

### 段落樣式 {#paragraph-styles}

![設計對話框段落樣式](/help/assets/text-design-paragraph.png)

可為元件啟用或停用段落樣式。啟用時，可以定義允許的格式。

* 點選或按一下&#x200B;**新增**&#x200B;按鈕以插入新樣式。
* 輸入將在編輯對話框中顯示的樣式程式碼和說明。
* 若要移除樣式，請點選或按一下&#x200B;**刪除**&#x200B;按鈕。
* 若要重新排列格式的順序，請點選或按一下並拖曳控點。

### 特殊字元 {#configuring-special-characters}

![設計對話框特殊字元](/help/assets/text-design-special-characters.png)

可以為元件啟用或停用插入特殊字元的選項。啟用時，可以定義允許的字元。

* 點選或按一下&#x200B;**新增**&#x200B;按鈕以插入新字元。
* 輸入將在編輯對話框中顯示的字元 HTML 程式碼和說明。
* 若要移除字元，請點選或按一下&#x200B;**刪除**&#x200B;按鈕。
* 若要重新排列字元的順序，請點選或按一下並拖曳控點。

## 樣式索引標籤 {#styles-tab}

電子郵件文字元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
