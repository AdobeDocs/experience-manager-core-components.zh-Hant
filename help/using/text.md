---
title: 文字元件
seo-title: 文字元件
description: 文字元件是豐富的文字編輯和構圖元件，可進行就地編輯。
seo-description: 文字元件是豐富的文字編輯和構圖元件，可進行就地編輯。
uuid: 5f8eee8f-7317-4712-a77 f-e34 e8 a024187
contentOwner: 使用者
content-type: 引用
topic-tags: 核心元件
discoiquuid: 9a290584-565e-43292-999c-999ee4a93da1
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# 文字元件{#text-component}

Core Component Text Component是一種豐富的文字編輯與構圖元件，可進行就地編輯。

## 使用狀況 {#usage}

文字元件提供強穩的豐富文字編輯器，可讓您以簡化的線上編輯器以及全螢幕格式輕鬆編輯文字。

[編輯對話方塊](#edit-dialog) 使用有限選項進行線上編輯，全螢幕編輯對話方塊提供完整功能。Using the [design dialog](#design-dialog), text formatting options such as headings, special characters, and paragraph styles can be configured for the template for the content author.

## Version and Compatibility {#version-and-compatibility}

目前版本的文字元件是v2，是在2018年月發行的版本2.0.0推出，並在本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|---|---|---|---|
| v2 | 相容相容性 | 相容相容性 | 相容相容性 |
| [v1](text-v1.md) | 相容相容性 | 相容相容性 | 相容相容性 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Text Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/text.html).

### Technical Details {#technical-details}

The latest technical documentation about the Text Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## The Text Component and the Rich Text Editor {#the-text-component-and-the-rich-text-editor}

核心元件文字元件運用AEM Rich Text Editor(RTE)。RTE為內容作者提供多種功能來編輯其文字內容。RTE在其配置中非常有彈性，並提供許多選項。Further details about how the RTE can be configured can be found in the articles [Configure the Rich Text Editor](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/rich-text-editor.html) and [Configure the Rich Text Editor plug-ins](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/configure-rich-text-editor-plug-ins.html).

本文的其餘部分說明核心元件文字元件的標準配置，以及立即可用的RTE組態。

>[!NOTE]
>
>Only options enabled by [UI configurations of the RTE](https://chl-author-preview.corp.adobe.com/content/help/en/experience-manager/6-5/sites/administering/using/rich-text-editor.html) are available by in the Text Component.

## Edit Dialog {#edit-dialog}

編輯對話方塊提供使用者預期要編寫文字的標準豐富文字格式工具。

![](assets/screen_shot_2018-01-11at143025.png)

### 粗體

![](assets/screen_shot_2018-01-11at125602.png)

用於將粗體格式套用至選取文字或游標在游標後面輸入的粗體格式文字。

**Ctrl+ B** 可當做鍵盤快速鍵使用。

### 斜體

![](assets/screen_shot_2018-01-11at125609.png)

用於將斜體格式套用至選取的文字，或在游標後面輸入斜體文字。

**Ctrl+ I** 可當做鍵盤快速鍵使用。

### 底線

![](assets/screen_shot_2018-01-11at125615.png)

用於將強調的格式套用至在游標後面輸入的選取文字或底線文字。

**Ctrl+ U** 可當做鍵盤快速鍵使用。

### 下標

![](assets/screen_shot_2018-01-11at125703.png)

用來格式化在游標後輸入的選取文字或文字。

### 上標

![](assets/screen_shot_2018-01-11at125708.png)

用來格式化在游標後面輸入的選取文字或文字作為上標。

### 貼上為文字

![](assets/screen_shot_2018-01-11at125713.png)

將任何複製的文字貼為純文字，而不需要任何格式設定。

選取此選項時，會開啓視窗，其中文字可以貼上為不含格式的純文字，並插入文字中。點選或按一下勾號即可接受，只要點選或按一下x即可取消。

![](assets/screen_shot_2018-01-11at143234.png)

### 從 Word 貼上

![](assets/screen_shot_2018-01-11at125717.png)

選取此選項時，會開啓視窗，在其中貼上文字，將其格式設為預覽，然後再插入文字中。點選或按一下勾號即可接受，只要點選或按一下x即可取消。

![](assets/screen_shot_2018-01-11at143250.png)

### 超連結

![](assets/screen_shot_2018-01-11at125839.png)

使用此選項可將選取的文字轉換為超連結，或修改已定義的連結。只有在已選取文字時才會啓用此選項，並開啓含有其他選項來設定連結的視窗。

![](assets/screen_shot_2018-01-11at130003.png)

* 輸入位置
   * 使用Open Selection對話方塊在AEM中選擇路徑
   * 如果連結不在AEM內，請輸入絕對URL(非絕對路徑被解譯為相對於AEM)
* 輸入連結的替代說明文字
* 選取連結行為
   * 目標
   * 相同索引標籤
   * 新索引標籤
   * 父框架
   * 上框架
   點選或按一下勾號以套用連結或x取消。

### 取消連結

![](assets/screen_shot_2018-01-11at125901.png)

使用此選項可移除已套用至選取文字的連結。只有在已選取連結時，才會啓用此選項。

### 尋找

![](assets/screen_shot_2018-01-11at125906.png)

使用此選項可搜尋指定文字字串的文字。選取此選項會開啓指定搜尋選項的視窗。

![](assets/screen_shot_2018-01-11at130107.png)

Enter the text for which you want to search and tap or click **Find** to begin the search. 點選或按一下x以取消。
If you wish to do an exact match according to the case, select the option **Match Case** before starting the search.
如果找到相符項目，則會反白顯示，搜尋對話方塊會暗灰色。Tap or click the **Find** button again in the dimmed dialog to search for the next occurrence.

![](assets/screen_shot_2018-01-11at130145.png)

如果找不到其他發生次數，則會顯示訊息，搜尋將從文字開始開始。

![](assets/screen_shot_2018-01-11at130241.png)

### 取代

![](assets/screen_shot_2018-01-11at125910.png)

使用此選項可搜尋指定文字字串發生的文字，並以其他字串取代相符項目。選取此選項會開啓視窗，以指定搜尋和取代選項。

![](assets/screen_shot_2018-01-11at130441.png)

輸入您要搜尋的文字，以及應取代的文字。

Tap or click **Find** to begin the search. 按一下或點選x以取消。

If you wish to do an exact match according to the case, select the option **Match Case** before starting the search.

如果找到相符項目，則會反白顯示，搜尋對話方塊會暗灰色。Click the **Find** button again in the dimmed dialog to search for the next occurrence or select the **Replace** button to replace the highlighted, matched text. Note that the **Replace** button is only active once a match is made.

Select **Replace all** to replace all occurrences of the text at once.

### 向左對齊文字

![](assets/screen_shot_2018-01-11at142012.png)

用來將文字對齊左側邊界。

### 文字置中

![](assets/screen_shot_2018-01-11at142017.png)

用來中心文字。

### 向右對齊文字

![](assets/screen_shot_2018-01-11at142021.png)

用來將文字對齊正確邊界。

### 項目符號

![](assets/screen_shot_2018-01-11at142025.png)

用於將選取的文字格式化為項目清單，或開始插入游標後的項目清單。

To end a bulleted list, tap or click the **Bullet** button again or enter two carriage returns.

### 編號編號

![](assets/screen_shot_2018-01-11at142030.png)

用以將選取的文字格式化為編號清單，或開始插入游標後的編號清單。

To end a numbered list, tap or click the **Numbered** button again or enter two carriage returns.

### 凸排

![](assets/screen_shot_2018-01-11at141917.png)

用來降低在游標後面輸入所選文字或文字的縮排層級。

只有當游標的選取文字或位置已縮排時，才會作用中。

### 縮排

![](assets/screen_shot_2018-01-11at141922.png)

用來增加所選文字的縮排層級，或游標在游標後面輸入的文字。

### 表格

![](assets/screen_shot_2018-01-11at141928.png)

用來插入表格至文字中。選取此選項會開啓指定表格詳細資訊的視窗。

![](assets/screen_shot_2018-01-11at142405.png)

* **欄**：表格的欄數(必要)
* **列** 表格的列數(必要)
* **寬度**：表格寬度
* **高度**：表格高度
* **儲存格填補** 儲存格內容周圍的空間
* **儲存格間隔** 儲存格之間的間距
* **邊框** 邊框線的粗細
* 如果表格標題：
   * 應使用第一列
   * 應使用第一欄
   * 應使用第一列和第一欄
   * 也不應使用標題。
* **標題**：表格的標題

### 檢查拼字

![](assets/screen_shot_2018-01-11at141935.png)

用來檢查文字內容的拼字。有破損的紅線會強調顯示可能拼字錯誤。

Further details about spell checking and customizing spell check dictionaries can be found in the document [Configure the Rich Text Editor Plug-Ins](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/configure-rich-text-editor-plug-ins.html).

### 特殊字元 {#special-characters}

![](assets/screen_shot_2018-01-11at142600.png)

用來插入特殊字元至文字中。選取此選項會開啓顯示可用字元的視窗。

![](assets/screen_shot_2018-01-11at142635.png)

點選或按一下所要的字元，將其插入游標後面的文字中。可插入多個字元。點選或按一下x以關閉選取視窗。

### 來源編輯

![](assets/screen_shot_2018-01-11at142746.png)

用於檢視和修改文字的HTML來源。

Tap or click the **Source Edit** icon to change the content of the text from the formatted view to view the raw HTML. 在此模式中，所有其他格式選項都會停用。Tap or click the **Source Edit** icon again to return to the formatted view.

>[!CAUTION]
>
>As always the case with access to raw HTML, care must be exercised when using the **Source Edit** option!
>
>HTML entered via **Source Edit** is scanned for XSS risks and any scripts that are inserted are removed and will not appear on the resulting page. However malformed HTML entered in **Source Edit** can break the template for the page resulting in unexpected formatting or rendering the resulting page unusable.

>[!NOTE]
>
>Because HTML entered via **Source Edit** is scanned for XSS risks and any scripts and automatically removes those found, the actual content persisted may vary from what was entered in **Source Edit**. For this reason, in order to save changes made using **Source Edit**, you must first exit **Source Edit** to view the text in the normal editor before saving.

### 段落格式

![](assets/screen_shot_2018-01-11at142752.png)

用於將段落格式套用至所選文字或游標之後插入的文字。選取此選項會開啓一個下拉式清單，從中選取段落格式。

![](assets/screen_shot_2018-01-11at142828.png)

文字元件也可以同時進行編輯，但是由於空間restraints，並非所有格式選項都能內嵌使用。若要查看所有選項，請切換至全螢幕模式。

![](assets/screen_shot_2018-01-11at142921.png)

## Design Dialog {#design-dialog}

設計對話方塊可讓範本作者定義內容作者可用的文字格式化選項。

### Plugins Tab {#plugins-tab}

「外掛程式」索引標籤可用來啓用和停用內容作者可用的各種文字格式化選項。

### 功能 {#features}

![](assets/chlimage_1-28.png)

可為元件啓用或停用下列功能。

* 貼上純文字
* 舊字
* 尋找和取代
* Spell檢查程式
* 來源編輯

### 正在格式化 {#formatting}

![](assets/chlimage_1-29.png)

您可以為元件啓用或停用下列格式設定選項。

* 表格
* 清單
* 對齊方式
* 粗體、斜體、底線
* 連結
* 子/上標

### 段落樣式 {#paragraph-styles}

![](assets/chlimage_1-30.png)

可為元件啓用或停用段落樣式。啓動後，可定義允許的格式。

* Tap or click the **Add** button to insert a new style.
* 輸入樣式的程式碼和將顯示在編輯對話方塊中的說明。
* To remove a style tap or click the **Delete** button.
* 若要重新排列格式的順序，請點選或點選並拖曳控制點。

### Configuring Special Characters {#configuring-special-characters}

![](assets/chlimage_1-31.png)

可為元件啓用或停用插入特殊字元的選項。啓動後，可定義允許的字元。

* Tap or click the **Add** button to insert a new character.
* 輸入字元的HTML程式碼和將顯示在編輯對話方塊中的說明。
* To remove a character tap or click the **Delete** button.
* 若要重新排列字元順序，請點選或點選並拖曳控制點。

## Styles Tab {#styles-tab}

The Text Component supports the AEM [style system](authoring.md#component-styling).