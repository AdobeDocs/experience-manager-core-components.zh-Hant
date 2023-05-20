---
title: 電子郵件分段元件
description: 電子郵件分段元件
role: Architect, Developer, Admin, User
exl-id: 6c88b8c5-189a-40c0-ab28-04d37dc5fbac
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '1133'
ht-degree: 0%

---


# 電子郵件分段元件 {#email-segmentation-component}

電子郵件分段元件使用Adobe Campaign的變數根據內容的收件人顯示和隱藏內容。

## 使用狀況 {#usage}

電子郵件分段元件允許內容作者根據Adobe Campaign提供的有關收件人的變數滿足的條件隱藏和顯示內容。 通過這種方式，內容的接收者基於其分段來查看內容。

* 模板作者可以使用 [設計對話框](#design-dialog) 定義可將哪些元件添加為段。
* 內容作者可以使用 [配置對話框](#configure-dialog) 將元件添加為段，並配置根據Adobe Campaign變數顯示哪些段。

作為使用配置對話框的替代方法，一旦內容作者將電子郵件分段元件添加到內容頁面，內容作者就可以將其他元件拖放到電子郵件分段元件上以建立新段。

## 版本和相容性 {#version-and-compatibility}

電子郵件分段元件的當前版本是v1，該版本於2022年10月隨電子郵件核心元件的第x版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | - |

### 技術詳細資訊 {#technical-details}

有關電子郵件預告元件的最新技術文檔 [中。](https://adobe.com/go/aem_cmp_tech_email_segmentation_v1)

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔。](/help/developing/overview.md)

## 配置對話框 {#configure-dialog}

配置對話框允許內容作者建立、更名和重新排列段以及定義活動段。 在電子郵件分段元件中，段只是另一個元件，它根據內容收件人滿足的條件隱藏或顯示。 你可以比較 [核心元件頁籤元件，](/help/components/tabs.md) 但是在分段元件中，只顯示滿足條件的頁籤的內容。

### 項目頁籤 {#items-tab}

![電子郵件分段元件的「配置」對話框項頁籤](/help/email/assets/email-segmentation-configure-items.png)

使用 **添加段** 按鈕以開啟元件選擇器以選擇要作為段添加的元件。 添加後，將向清單中添加一個條目，該清單包含以下元素：

* **表徵圖**  — 用於在清單中輕鬆識別段的元件類型表徵圖。 將滑鼠移到工具提示中，以查看完整的元件名稱。
* **條件**  — 必須滿足的條件，才能將此段顯示給內容的收件人。
   * 可用條件在 [設計對話框。](#design-dialog)
   * **預設**  — 定義預設段以顯示是否未滿足其他條件
   * **自定義**  — 允許作者定義條件
      * 條件基於Adobe Campaign個性化變數
      * [請參閱此處獲取Adobe Campaign Standard個性化資源。](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?)
      * [請參閱此處獲取Adobe Campaign Classic個性化資源。](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html)
* **刪除**  — 按一下或按一下以從「電子郵件分段元件」中刪除段。
* **重新排列**  — 按一下或按一下並拖動以重新排列段。

>[!TIP]
>
>如果內容的視區被縮小，使編輯對話框變為全屏，則 **添加** 按鈕。 元件仍可以通過以下方式添加到電子郵件分段元件 [從元件瀏覽器中拖動，然後放在內容編輯器中的「電子郵件分段元件」上。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component)

### 屬性頁籤 {#properties-tab}

![電子郵件分段元件的「配置」對話框屬性頁籤](/help/email/assets/email-segmentation-configure-properties.png)

* **ID**  — 此選項允許控制HTML中元件的唯一標識符。
   * 如果留空，則系統會為您自動生成唯一ID，並且可以通過檢查生成的內容來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS。

### 輔助功能頁籤 {#accessibility-tab}

![「電子郵件分段元件」的「配置」對話框輔助功能頁籤](/help/email/assets/email-segmentation-configure-accessibility.png)

在 **輔助功能** 頁籤，可為 [ARIA輔助功能](https://www.w3.org/WAI/standards-guidelines/aria/) 元件的標籤。

* **標籤**  — 元件的ARIA標籤屬性的值

### 樣式頁籤 {#styles-tab-edit}

電子郵件分段元件支AEM持 [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉框選擇要應用於元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須在 [設計對話框](#design-dialog) 以便該頁籤可用。

## 選擇面板 {#select-panel}

內容作者可以使用 **選擇面板** 的子菜單。

![「選擇面板」表徵圖](/help/email/assets/select-panel-icon.png)

選擇 **選擇面板** 選項，配置的段將顯示為下拉框。

* 清單按段的指定排列排序，並反映在編號中。
* 該段的元件類型首先顯示，然後以較淺字型顯示該段的說明。

![選擇面板跨距](/help/email/assets/select-panel-popover.png)

* 點擊或按一下下拉清單中的條目，將編輯器中的視圖切換到該段。
* 通過使用拖動手柄，可以就地重新排列這些段。

>[!NOTE]
>
>段在頁面編輯器中呈現為頁籤，以顯示最終內容有多個選項。 作者在頁面編輯器中不能選擇這些頁籤。 使用選擇面板在顯示的段之間切換。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義哪些元件可以作為段添加到「電子郵件分段元件」中，並定義哪些自定義樣式可供內容作者使用。

### 允許的元件頁籤 {#allowed-components-tab}

的 **允許的元件** 頁籤用於定義哪些元件可以作為段由內容作者添加到「電子郵件分段元件」中。

的 **允許的元件** 頁籤函式，與同名的頁籤相同 [在模板編輯器中定義佈局容器的策略和屬性。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 樣式頁籤 {#styles-tab}

電子郵件分段元件支AEM持 [樣式系統。](/help/get-started/authoring.md#component-styling)

### 「定義的條件」頁籤 {#defined-conditions}

使用 **定義的條件** 頁籤，模板編輯器可定義內容作者在建立段時可以選擇的條件。

![「設計」對話框「定義的條件」頁籤](/help/email/assets/email-segmentation-design-defined-conditions.png)

點擊或按一下 **添加** 按鈕

* **段條件名稱**  — 條件說明
* **段條件**  — 根據Adobe Campaign個性化變數必須滿足的實際條件
   * [請參閱此處獲取Adobe Campaign Standard個性化資源。](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?)
   * [請參閱此處獲取Adobe Campaign Classic個性化資源。]https://experienceleague.adobe.com/docs/
* **刪除**  — 點擊以刪除條件
* **重新排列**  — 按一下或按一下並拖動以重新排列條件的順序
