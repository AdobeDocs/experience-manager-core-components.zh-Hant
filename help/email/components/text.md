---
title: 電子郵件文字元件
description: 電子郵件文字元件是RTF編輯和合成元件，可就地編輯。
role: Architect, Developer, Admin, User
exl-id: 4aa192f6-8314-40e7-8732-c6626d647986
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '2328'
ht-degree: 2%

---


# 電子郵件文字元件 {#email-text-component}

電子郵件文字元件是RTF編輯和合成元件，可就地編輯。

## 使用狀況 {#usage}

電子郵件文字元件提供強大的RTF編輯器，以簡化的內嵌編輯器和全螢幕格式輕鬆編輯文字。

* 此 [編輯對話框](#edit-dialog) 全螢幕編輯對話方塊中提供有限選項和完整功能的串列編輯功能。
* 使用 [設計對話方塊，](#design-dialog) 可為內容作者的範本設定標題、特殊字元和段落樣式等文字格式選項。

## 版本與相容性 {#version-and-compatibility}

電子郵件文字元件的目前版本為v1，已於2022年10月隨電子郵件核心元件X版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | 相容 |

如需核心元件版本和版本的詳細資訊，請參閱本檔案 [電子郵件核心元件版本。](/help/email/versions.md)

## 範例元件輸出 {#sample-component-output}

若要體驗文字元件，並查看其設定選項、HTML和JSON輸出的範例，請造訪 [元件庫](https://adobe.com/go/aem_cmp_library_email_text).

### 技術詳細資訊 {#technical-details}

電子郵件文字元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_email_text_v1).

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 電子郵件文字元件和RTF編輯器 {#the-text-component-and-the-rich-text-editor}

電子郵件文字元件採用AEM RTF編輯器(RTE)。 RTE為內容作者提供多種功能，可編輯其文字內容。 RTE在設定上是彈性的，並提供許多選項。 如需RTE設定方式的詳細資訊，請參閱文章 [設定RTF編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/rich-text-editor.html) 和 [設定RTF編輯器外掛程式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html).

本檔案的其餘部分示範使用現成可用RTE設定的電子郵件文字元件的標準設定。

>[!NOTE]
>
>僅由啟用的選項 [RTE的UI設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html) 可在「電子郵件文字」元件中使用。

## 編輯對話方塊 {#edit-dialog}

![文本元件的編輯對話框](/help/email/assets/email-text-edit.png)

### 格式選項 {#options}

編輯對話方塊提供標準RTF格式工具，使用者可預期這些工具來撰寫文字。

#### 粗體

![粗體圖示](/help/assets/text-bold.png)

用於將粗體格式應用於選定文本或在游標後輸入的大膽格式文本。

**Ctrl+B** 可用作鍵盤快速鍵。

#### 斜體

![斜體圖示](/help/assets/text-italic.png)

用於將斜體格式應用到選定文本或在游標之後輸入的斜體文本。

**Ctrl+I** 可用作鍵盤快速鍵。

#### 底線

![下划線表徵圖](/help/assets/text-underline.png)

用於將下划線格式應用於在游標之後輸入的選定文本或下划線文本。

**Ctrl+U** 可用作鍵盤快速鍵。

#### 下標

![下標表徵圖](/help/assets/text-subscript.png)

用於將游標之後輸入的選定文本或文本格式化為下標。

#### 上標

![上標表徵圖](/help/assets/text-superscript.png)

用於將游標之後輸入的選定文本或文本格式化為上標。

#### 貼上為文字

![貼上為文字圖示](/help/assets/text-paste-text.png)

將任何複製的文本貼上為純文字檔案，不使用任何格式。

選取此選項時，將開啟一個窗口，在該窗口中，文本可以貼上為純文字檔案，在插入文本之前不以格式作為預覽。 點選或按一下複選標籤以接受，點選或按一下x以取消。

![貼上為文字範例](/help/assets/text-paste-text-example.png)

#### 從 Word 貼上

![「從Word貼上」圖示](/help/assets/text-paste-word.png)

選取此選項時，會開啟一個視窗，可貼上文字，並在將其插入文字之前，維持其格式作為預覽。 點選或按一下複選標籤以接受，點選或按一下x以取消。

![從Word貼上範例](/help/assets/text-paste-word-example.png)

#### 超連結

![超連結表徵圖](/help/assets/text-hyperlink.png)

使用此選項可將選定文本轉換為超連結或修改已定義的連結。 此選項會開啟一個視窗，其中包含設定連結的其他選項。

![超連結範例](/help/assets/text-hyperlink-example.png)

* 輸入路徑
   * 使用 **開啟選取項目** 對話方塊，在AEM中選擇路徑
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

#### 取消連結

![取消連結表徵圖](/help/assets/text-unlink.png)

使用此選項可移除已套用至所選文字的連結。 只有在已選取連結時，此選項才會作用中。

#### 錨點 {#anchor}

![錨點圖示](/help/email/assets/anchor.png)

使用此選項將錨點插入文本中。

#### 尋找

![查找表徵圖](/help/assets/text-find.png)

使用此選項可搜索文本以查找指定文本字串的出現。 選擇此選項將開啟一個窗口，用於指定搜索選項。

![尋找範例](/help/assets/text-find-example.png)

輸入要搜索的文本，點選或按一下 **查找** 開始搜索。 點選或按一下x以取消。
如果您想根據大小寫執行完全相符的動作，請選取選項 **符合案例** 開始搜尋之前。
如果找到相符項目，則會加亮顯示，而搜尋對話方塊則呈現灰色。 點選或按一下 **查找** 按鈕，以搜尋下一個出現次數。

![查找找到的示例](/help/assets/text-find-example-found.png)

如果找不到其他發生次數，則會顯示訊息，並從文字的開頭開始搜尋。

![查找示例，不再出現](/help/assets/text-find-example-found-end.png)

#### 取代

![取代圖示](/help/assets/text-replace.png)

使用此選項可搜索文本以查找指定文本字串的出現次數，並將匹配項替換為另一個字串。 選擇此選項將開啟一個窗口，用於指定搜索和替換選項。

![取代範例](/help/assets/text-replace-example.png)

輸入要搜索的文本以及應替換的文本。

* 點選或按一下 **查找** 開始搜索。 按一下或點選x以取消。
* 如果您想根據大小寫執行完全相符的動作，請選取選項 **符合案例** 開始搜尋之前。
* 選擇 **全部替換** 一次替換所有出現的文本。

如果找到相符項目，則會加亮顯示，而搜尋對話方塊則呈現灰色。 按一下 **查找** 按鈕，以搜索下一個出現次數或選擇 **取代** 按鈕，替換突出顯示的匹配文本。 此 **取代** 按鈕只有在進行匹配後才處於活動狀態。

點擊查找時，查找和替換對話框變為透明，點擊替換時變為不透明。 這可讓作者檢閱作者將取代的文字。

>[!NOTE]
>
>使用取代功能時，應在輸入要取代的字串的同時找到該字串。 不過，在替換字串之前，您仍可以按一下「尋找」來搜尋字串。 如果在按一下「查找」後輸入替換字串，則搜索將重置為文本的開頭。

#### 復原

![還原圖示](/help/email/assets/undo.png)

用來還原RTF編輯器中上次的編輯。

#### 重做

![重做圖示](/help/email/assets/redo.png)

用於使用還原圖示來還原已還原的編輯。

#### 向左對齊文字

![靠左對齊圖示](/help/assets/text-left.png)

用來將文字對齊左側邊界。

#### 文字置中

![中間文字圖示](/help/assets/text-center.png)

用來將文字置中。

#### 向右對齊文字

![靠右對齊圖示](/help/assets/text-right.png)

用於將文字對齊右側邊界。

#### 項目符號

![項目符號圖示](/help/assets/text-bullet.png)

用於將所選文本格式化為項目符號清單，或在游標後開始插入項目符號清單。

若要結束項目符號清單，請點選或按一下 **項目符號** 按鈕或輸入兩個歸位。

#### 編號

![編號清單圖示](/help/assets/text-numbered.png)

用於將所選文本格式化為編號清單，或開始在游標後插入編號清單。

若要結束編號清單，請點選或按一下 **編號** 按鈕或輸入兩個歸位。

#### 凸排

![輸出表徵圖](/help/assets/text-outdent.png)

用於減少在游標之後輸入的選定文本或文本的縮進級別。

僅當游標的選定文本或位置已縮排時才處於活動狀態。

#### 縮排

![縮進表徵圖](/help/assets/text-indent.png)

用於增加在游標之後輸入的選定文本或文本的縮進級別。

#### 表格

![表格圖示](/help/assets/text-table.png)

用於將表插入文本中。 選擇此選項將開啟一個窗口，用於指定表的詳細資訊。

![表格範例](/help/assets/text-table-example.png)

* **欄**  — 表格的欄數（必要）
* **列**  — 表格的列數（必要）
* **寬度**  — 表格寬度
* **高度**  — 表格高度
* **單元格填充**  — 儲存格內容周圍的空間
* **儲存格間距**  — 儲存格之間的空間
* **邊框**  — 表格的邊框粗細
   * 若表格的標題：
      * 應使用第一列
      * 應使用第一欄
      * 應使用第一列和第一列
      * 或者不應使用標題。
* **註解**  — 表格標題

#### 影像

![影像圖示](/help/email/assets/image-icon.png)

用於對齊插入的影像。

#### 檢查拼寫

![檢查拼寫表徵圖](/help/assets/text-spellcheck.png)

用於檢查文本內容的拼寫。 可能拼錯的字，加上破折的紅線。

有關拼寫檢查和自定義拼寫檢查字典的詳細資訊，請參見文檔 [設定RTF編輯器外掛程式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html).

#### 特殊字元 {#special-characters}

![特殊字元表徵圖](/help/assets/text-special-characters.png)

用於將特殊字元插入文字中。 選擇此選項將開啟一個顯示可用字元的窗口。

![特殊字元範例](/help/assets/text-special-characters-example.png)

點選或按一下所需的字元，將其插入游標後的文字中。 可插入多個字元。 點選或按一下x以關閉選取視窗。

#### 來源編輯

![源編輯表徵圖](/help/assets/text-source.png)

用於查看和修改文本的HTML源。

點選或按一下 **源編輯** 表徵圖來更改格式化視圖中的文本內容以查看原始HTML。 在此模式中，會禁用所有其他格式選項。 點選或按一下 **源編輯** 圖示返回格式化視圖。

>[!CAUTION]
>
>如同存取原始HTML的情況，使用 **源編輯** 選項！
>
>HTML輸入方式 **源編輯** 會掃描XSS風險，且會移除所插入的任何指令碼，且這些指令碼不會顯示在產生的頁面上。 但在中輸入的HTML格式錯誤 **源編輯** 可能會中斷頁面的範本，導致非預期的格式設定，或導致頁面無法使用。

>[!NOTE]
>
>因為HTML是透過 **源編輯** 會針對XSS風險和任何指令碼進行掃描並自動移除發現的這些風險，則保存的實際內容可能會與中輸入的內容有所不同 **源編輯**. 因此，為了儲存使用 **源編輯**，您必須先退出 **源編輯** 在保存之前在普通編輯器中查看文本。

#### 段落格式

![段落格式表徵圖](/help/assets/text-paragraph.png)

用於將段落格式應用於選定文本或游標後插入的文本。 選擇此選項將開啟一個下拉清單，從中選擇段落格式。

![段落格式示例](/help/assets/text-paragraph-example.png)

#### 選取 Adobe Campaign 變數

![選取Adobe Campaign變數圖示](/help/email/assets/select-adobe-campaign-variable-icon.png)

開啟 [選取Adobe Campaign變數](/help/email/campaign-variables.md) 對話方塊，從Adobe Campaign插入動態內容。

### 線上編輯 {#in-line-editing}

也可以內嵌編輯文字元件。 若要內嵌編輯，請在內容頁面上選取「電子郵件文字元件」 。

![選取電子郵件文字元件](/help/email/assets/email-text-select-component.png)

然後點選或按一下 **編輯** 圖示（位於工具列上），此圖示會彈出至元件上。 工具列會變更為顯示有限的文字格式選項(包括 **選取Adobe Campaign變數** 選項)，並可以編輯文本行。

![行內編輯範例](/help/email/assets/email-text-edit-inline-example.png)

點選或按一下工具列中的核取標籤，以儲存您的變更或捨棄X。

由於空間限制，並非所有格式選項都可串聯使用。 若要查看所有選項，請切換至全螢幕模式。

### 設定ID {#setting-id}

此選項允許控制HTM中元件的唯一標識符。

* 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
* 若已指定ID，則作者應負責確認其唯一。
* 變更ID可能會對CSS造成影響。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義內容作者可使用的文字格式選項。

### 外掛程式標籤 {#plugins-tab}

此 **外掛程式** 索引標籤可用來啟用和停用內容作者可用的各種文字格式選項。

### 功能 {#features}

![設計對話方塊功能](/help/assets/text-design-features.png)

可為元件啟用或停用下列功能。

* 貼上純文字
* 過去
* 查找和替換
* 還原和重做
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

* 點選或按一下 **新增** 按鈕以插入新樣式。
* 輸入樣式的代碼以及將在編輯對話框中顯示的說明。
* 若要移除樣式，請點選或按一下 **刪除** 按鈕。
* 要重新排列格式的順序，請點選或按一下並拖動控點。

### 特殊字元 {#configuring-special-characters}

![設計對話框特殊字元](/help/assets/text-design-special-characters.png)

可為元件啟用或停用插入特殊字元的選項。 啟動後，可定義允許的字元。

* 點選或按一下 **新增** 按鈕插入新字元。
* 輸入字元的HTML代碼，以及將在編輯對話方塊中顯示的說明。
* 若要移除字元，請點選或按一下 **刪除** 按鈕。
* 要重新排列字元點選的順序，或按一下並拖動控點。

## 樣式標籤 {#styles-tab}

電子郵件文字元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).
