---
title: 電子郵件文字元件
description: 電子郵件文字元件是RTF編輯和撰寫元件，具備就地編輯功能。
role: Architect, Developer, Admin, User
exl-id: 4aa192f6-8314-40e7-8732-c6626d647986
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '2291'
ht-degree: 2%

---


# 電子郵件文字元件 {#email-text-component}

電子郵件文字元件是RTF編輯和撰寫元件，具備就地編輯功能。

## 使用狀況 {#usage}

電子郵件文字元件提供強大的RTF編輯器，允許在簡化的內嵌編輯器中以全熒幕格式輕鬆編輯文字。

* 此 [編輯對話方塊](#edit-dialog) 具備內嵌編輯功能，提供全熒幕編輯對話方塊中完整功能的有限選項。
* 使用 [設計對話方塊，](#design-dialog) 可為內容作者設定範本的文字格式選項，例如標題、特殊字元和段落樣式。

## 版本和相容性 {#version-and-compatibility}

電子郵件文字元件的目前版本是v1，此版本隨2022年10月的電子郵件核心元件發行版本X的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | - |

如需核心元件版本和發行版本的詳細資訊，請參閱檔案 [電子郵件核心元件版本。](/help/email/versions.md)

### 技術細節 {#technical-details}

有關電子郵件文字元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_email_text_v1).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 電子郵件文字元件和RTF編輯器 {#the-text-component-and-the-rich-text-editor}

電子郵件文字元件會利用AEM RTF編輯器(RTE)。 RTE為內容作者提供廣泛的功能來編輯其文字內容。 RTE的設定有彈性，並提供許多選項。 有關如何設定RTE的更多詳細資訊，請參閱文章 [設定RTF編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/rich-text-editor.html) 和 [設定RTF編輯器外掛程式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html).

本檔案的其餘部分示範了具有現成RTE設定的電子郵件文字元件的標準設定。

>[!NOTE]
>
>僅啟用選項，啟用者： [RTE的UI設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html) 可在電子郵件文字元件中使用。

## 編輯對話方塊 {#edit-dialog}

![文字元件的編輯對話方塊](/help/email/assets/email-text-edit.png)

### 格式選項 {#options}

「編輯」對話方塊提供使用者要撰寫文字的標準RTF格式工具。

#### 粗體

![粗體圖示](/help/assets/text-bold.png)

用於將粗體格式套用至選取的文字，或粗體格式套用至游標後輸入的文字。

**Ctrl+B** 可用作鍵盤快速鍵。

#### 斜體

![斜體圖示](/help/assets/text-italic.png)

用於將斜體格式套用至選取的文字，或將游標之後輸入的文字斜體化。

**Ctrl+I** 可用作鍵盤快速鍵。

#### 底線

![「加底線」圖示](/help/assets/text-underline.png)

用於將加底線格式套用至選取的文字，或在游標後輸入的文字加底線。

**Ctrl+U** 可用作鍵盤快速鍵。

#### 下標

![「下標」圖示](/help/assets/text-subscript.png)

用於將選取的文字或在游標之後輸入的文字格式化為下標。

#### 上標

![上標圖示](/help/assets/text-superscript.png)

用於將選取的文字或在游標之後輸入的文字格式化為上標。

#### 貼上成文字

![「貼上成文字」圖示](/help/assets/text-paste-text.png)

將任何複製的文字貼上為純文字，不設定任何格式。

選取此選項時，會開啟一個視窗，其中的文字可以貼上成無格式的純文字，作為插入文字中之前的預覽。 點選或按一下核取記號即可接受，點選或按一下x可取消。

![貼上為文字範例](/help/assets/text-paste-text-example.png)

#### 從 Word 貼上

![從Word貼上圖示](/help/assets/text-paste-word.png)

選取此選項時，會開啟一個視窗，其中的文字可以貼上並保留其格式，作為插入文字中之前的預覽。 點選或按一下核取記號即可接受，點選或按一下x可取消。

![從Word貼上的範例](/help/assets/text-paste-word-example.png)

#### 超連結

![超連結圖示](/help/assets/text-hyperlink.png)

使用此選項可將選取的文字轉換為超連結或修改已定義的連結。 此選項會開啟一個視窗，其中包含設定連結的其他選項。

![超連結範例](/help/assets/text-hyperlink-example.png)

* 輸入路徑
   * 使用 **開啟選取範圍** 用於在AEM中選擇路徑的對話方塊
   * 如果連結不在AEM內，請輸入絕對URL
      * 非絕對路徑會解譯為相對於AEM
* 輸入連結的替代描述文字
* 選取連結行為
   * 目標
   * 相同索引標籤
   * 新索引標籤
   * 父框架
   * 上框架

點選或按一下核取記號以套用連結，或點選x以取消。

#### 取消連結

![取消連結圖示](/help/assets/text-unlink.png)

使用此選項可移除已套用至所選文字的連結。 只有在已選取連結時，此選項才會啟用。

#### 錨點 {#anchor}

![錨點圖示](/help/email/assets/anchor.png)

使用此選項可在文字中插入錨點。

#### 尋找

![尋找圖示](/help/assets/text-find.png)

使用此選項可搜尋指定文字字串出現位置的文字。 選取此選項會開啟一個視窗來指定搜尋選項。

![尋找範例](/help/assets/text-find-example.png)

輸入您要搜尋的文字，然後點選或按一下 **尋找** 以開始搜尋。 點選或按一下x以取消。
如果您想要根據大小寫進行完全比對，請選取選項 **符合大小寫** 開始搜尋之前。
如果找到相符專案，則會反白該專案，且搜尋對話方塊會變暗。 點選或按一下 **尋找** 在灰色的對話方塊中再次使用按鈕來搜尋下一個出現位置。

![找到範例](/help/assets/text-find-example-found.png)

如果找不到其他匹配項，則會顯示一則訊息，且搜尋會從文字的開頭重新開始。

![尋找範例不再發生](/help/assets/text-find-example-found-end.png)

#### 取代

![「取代」圖示](/help/assets/text-replace.png)

使用此選項來搜尋文字以確定指定文字字串的出現次數，並將符合專案取代為其他字串。 選取此選項會開啟一個視窗，用於指定搜尋和取代選項。

![取代範例](/help/assets/text-replace-example.png)

輸入您要搜尋的文字以及應取代的文字。

* 點選或按一下 **尋找** 以開始搜尋。 按一下或點選「 x 」以取消。
* 如果您想要根據大小寫進行完全比對，請選取選項 **符合大小寫** 開始搜尋之前。
* 選取 **全部取代** 一次取代所有出現的文字。

如果找到相符專案，則會反白該專案，且搜尋對話方塊會變暗。 按一下 **尋找** 在灰色的對話方塊中再次按一下按鈕以搜尋下一個出現位置或選取 **Replace** 按鈕來取代醒目提示的相符文字。 此 **Replace** 按鈕只有在進行比對後才會啟用。

在按一下「尋找」時，「尋找和取代」對話方塊會變成透明，而在按一下「取代」時，對話方塊會變成不透明。 這可讓作者檢閱作者將取代的文字。

>[!NOTE]
>
>使用取代功能時，要取代的字串應與要尋找的字串同時輸入。 不過，您仍然可以按一下「尋找」來搜尋字串，然後再取代它。 如果在按一下「尋找」之後輸入取代字串，則搜尋會重設為文字的開頭。

#### 復原

![「還原」圖示](/help/email/assets/undo.png)

用於還原RTF編輯器中的上次編輯。

#### 重做

![「重做」圖示](/help/email/assets/redo.png)

用於還原使用還原圖示還原的編輯。

#### 向左對齊文字

![「靠左對齊」圖示](/help/assets/text-left.png)

用於將文字對齊左邊界。

#### 文字置中

![文字圖示置中對齊](/help/assets/text-center.png)

用於置中文字。

#### 向右對齊文字

![「靠右對齊」圖示](/help/assets/text-right.png)

用於將文字對齊右邊界。

#### 項目符號

![專案符號圖示](/help/assets/text-bullet.png)

用於將選取的文字格式化為專案符號清單，或在游標後開始插入專案符號清單。

若要結束專案符號清單，請點選或按一下 **專案符號** 再次按一下按鈕或輸入兩個歸位字元。

#### 編號

![編號清單圖示](/help/assets/text-numbered.png)

用於將選取的文字格式化為編號清單，或在游標後開始插入編號清單。

若要結束編號清單，請點選或按一下 **編號** 再次按一下按鈕或輸入兩個歸位字元。

#### 凸排

![「減少縮排」圖示](/help/assets/text-outdent.png)

用來減少所選文字的縮排層級，或在游標後輸入的文字。

只有在選取的文字或游標位置已經縮排時才啟用。

#### 縮排

![縮排圖示](/help/assets/text-indent.png)

用於增加所選文字的縮排層級，或在游標後輸入的文字。

#### 表格

![表格圖示](/help/assets/text-table.png)

用於將表格插入文字中。 選取此選項會開啟一個視窗，用於指定表格的詳細資訊。

![表格範例](/help/assets/text-table-example.png)

* **欄**  — 表格的欄數（必要）
* **列**  — 表格的列數（必要）
* **寬度**  — 表格的寬度
* **高度**  — 表格的高度
* **儲存格邊距**  — 儲存格內容周圍的空間
* **儲存格間距**  — 儲存格之間的空間
* **邊框**  — 表格邊框線條的粗細
   * 若為表格的標頭：
      * 應使用第一列
      * 應使用第一欄
      * 應使用第一列和第一欄
      * 或不應使用標題。
* **註解**  — 表格的標題

#### 影像

![影像圖示](/help/email/assets/image-icon.png)

用於對齊插入的影像。

#### 檢查拼字

![檢查拼字圖示](/help/assets/text-spellcheck.png)

用於檢查文字內容的拼字。 可能的拼字錯誤會以紅色的破折線加底線。

有關拼字檢查和自訂拼字檢查字典的詳細資訊，請參閱檔案 [設定RTF編輯器外掛程式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html).

#### 特殊字元 {#special-characters}

![特殊字元圖示](/help/assets/text-special-characters.png)

用於將特殊字元插入文字中。 選取此選項會開啟一個視窗，其中顯示可用的字元。

![特殊字元範例](/help/assets/text-special-characters-example.png)

點選或按一下所需的字元，將其插入游標後面的文字中。 可以插入多個字元。 點選或按一下x以關閉選取範圍視窗。

#### 來源編輯

![來源編輯圖示](/help/assets/text-source.png)

用於檢視和修改文字的HTML來源。

點選或按一下 **來源編輯** 圖示可從格式化檢視變更文字內容，以檢視原始HTML。 在此模式中，會停用所有其他格式選項。 點選或按一下 **來源編輯** 圖示返回格式化檢視。

>[!CAUTION]
>
>與存取原始HTML的情況一樣，使用時必須小心 **來源編輯** 選項！
>
>HTML輸入方式 **來源編輯** 會掃描XSS風險，插入的任何指令碼都會被移除，且不會顯示在結果頁面上。 不過，輸入的HTML格式不正確 **來源編輯** 可能會破壞頁面的範本，導致非預期的格式設定或導致產生的頁面無法使用。

>[!NOTE]
>
>因為HTML是透過以下方式輸入： **來源編輯** 會掃描XSS風險和任何指令碼，並自動移除找到的指令碼，實際持續儲存的內容可能會與輸入內容有所不同 **來源編輯**. 因此，若要儲存變更，請使用 **來源編輯**，您必須先退出 **來源編輯** 在儲存之前，使用一般編輯器檢視文字。

#### 段落格式

![段落格式圖示](/help/assets/text-paragraph.png)

用於將段落格式套用至選取的文字，或套用至游標後插入的文字。 選取此選項會開啟一個下拉式清單，您可從其中選取段落格式。

![段落格式範例](/help/assets/text-paragraph-example.png)

#### 選取 Adobe Campaign 變數

![選取Adobe Campaign變數圖示](/help/email/assets/select-adobe-campaign-variable-icon.png)

開啟 [選取Adobe Campaign變數](/help/email/campaign-variables.md) 對話方塊，插入來自Adobe Campaign的動態內容。

### 內嵌編輯 {#in-line-editing}

文字元件也可以內嵌編輯。 若要內嵌編輯，請在內容頁面上選取電子郵件文字元件。

![選取電子郵件文字元件](/help/email/assets/email-text-select-component.png)

然後點選或按一下 **編輯** 圖示來標籤元件。 工具列會變更為顯示有限的文字格式選項(包括存取 **選取Adobe Campaign變數** 選項)，您可以編輯內嵌文字。

![內嵌編輯範例](/help/email/assets/email-text-edit-inline-example.png)

點選或按一下工具列中的核取記號以儲存您的變更，或點選X以捨棄。

由於空間限制，並非所有格式選項都內嵌於內。 若要檢視所有選項，請切換到全熒幕模式。

### 設定ID {#setting-id}

此選項可讓您控制HTM中元件的唯一識別碼。

* 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
* 若指定ID，作者應負責確認該ID是唯一的。
* 變更ID會對CSS造成影響。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義哪些文字格式選項可供內容作者使用。

### 外掛程式索引標籤 {#plugins-tab}

此 **外掛程式** tab可用來啟用和停用內容作者可用的各種文字格式選項。

### 功能 {#features}

![設計對話方塊功能](/help/assets/text-design-features.png)

可為元件啟用或停用下列功能。

* 貼上純文字
* 從Word過去
* 尋找和取代
* 還原和重做
* 拼字檢查程式
* 插入的影像修改選項
* HTML來源編輯

### 正在格式化 {#formatting}

![設計對話方塊格式](/help/assets/text-design-formatting.png)

您可以為元件啟用或停用下列格式選項。

* 表格
* 清單（專案符號、數字、縮排、減少縮排）
* 對齊方式（靠左、靠右、置中）
* 粗體、斜體、底線
* 連結（和取消連結）
* 下標/上標

### 段落樣式 {#paragraph-styles}

![設計對話方塊段落樣式](/help/assets/text-design-paragraph.png)

可以為元件啟用或停用段落樣式。 啟用時，可以定義允許的格式。

* 點選或按一下 **新增** 按鈕以插入新樣式。
* 輸入將在「編輯」對話方塊中顯示的樣式代碼和說明。
* 若要移除樣式，請點選或按一下 **刪除** 按鈕。
* 若要重新排列格式，請點選或按一下並拖曳控點。

### 特殊字元 {#configuring-special-characters}

![設計對話方塊特殊字元](/help/assets/text-design-special-characters.png)

可以為元件啟用或停用插入特殊字元的選項。 啟用時，可以定義允許的字元。

* 點選或按一下 **新增** 按鈕以插入新字元。
* 輸入將在編輯對話方塊中顯示的字元HTML碼和說明。
* 若要移除字元，請點選或按一下 **刪除** 按鈕。
* 若要重新排列字元順序，請點選或按一下並拖曳控點。

## 樣式索引標籤 {#styles-tab}

電子郵件文字元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).
