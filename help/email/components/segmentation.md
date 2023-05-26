---
title: 電子郵件區段元件
description: 電子郵件區段元件
role: Architect, Developer, Admin, User
exl-id: 6c88b8c5-189a-40c0-ab28-04d37dc5fbac
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '1133'
ht-degree: 0%

---


# 電子郵件區段元件 {#email-segmentation-component}

電子郵件區段元件會使用Adobe Campaign中的變數，根據內容的收件者來顯示和隱藏內容。

## 使用狀況 {#usage}

電子郵件區段元件可讓內容作者根據Adobe Campaign提供的收件者相關變數符合的條件來隱藏和顯示內容。 透過這種方式，內容的收件者可以看到根據其細分的內容。

* 範本作者可以使用 [設計對話方塊](#design-dialog) 以定義哪些元件可新增為區段。
* 內容作者可以使用 [設定對話方塊](#configure-dialog) 將元件新增為區段，並根據Adobe Campaign變數設定要顯示哪些區段。

除了使用設定對話方塊之外，一旦內容作者將電子郵件分段元件新增到內容頁面，內容作者就可以將其他元件拖放到「電子郵件分段元件」上來建立新區段。

## 版本和相容性 {#version-and-compatibility}

電子郵件區段元件的目前版本是v1，此版本隨2022年10月的電子郵件核心元件發行版本X的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | - |

### 技術細節 {#technical-details}

有關電子郵件Teaser元件的最新技術檔案 [在GitHub上可找到。](https://adobe.com/go/aem_cmp_tech_email_segmentation_v1)

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案。](/help/developing/overview.md)

## 設定對話方塊 {#configure-dialog}

「設定」對話方塊可讓內容作者建立、重新命名和重新排列區段，以及定義作用中區段。 在電子郵件區段元件中，區段只是根據內容收件者符合的條件隱藏或顯示的另一個元件。 您可將其與 [核心元件索引標籤元件](/help/components/tabs.md) 但是在分段元件中，只會顯示符合條件的索引標籤內容。

### 專案標籤 {#items-tab}

![電子郵件分段元件的設定對話方塊專案索引標籤](/help/email/assets/email-segmentation-configure-items.png)

使用 **新增區段** 按鈕來開啟元件選擇器，選擇要新增為區段的元件。 新增後，一個專案會新增到清單中，包含以下元素：

* **圖示**  — 區段的元件型別圖示，用於方便在清單中識別。 將滑鼠移到上方以檢視完整的元件名稱作為工具提示。
* **條件**  — 此區段必須符合的條件，才能顯示給內容的收件者。
   * 可用的條件定義於 [設計對話方塊。](#design-dialog)
   * **預設**  — 定義預設區段以顯示是否不滿足其他條件
   * **自訂**  — 允許作者定義條件
      * 條件以Adobe Campaign個人化變數為基礎
      * [如需Adobe Campaign Standard個人化資源，請參閱此處。](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?)
      * [如需Adobe Campaign Classic個人化資源，請參閱此處。](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html)
* **刪除**  — 點選或按一下以從電子郵件區段元件中刪除區段。
* **重新排列**  — 點選或按一下並拖曳以重新排列區段。

>[!TIP]
>
>如果減少內容的檢視區，讓編輯對話方塊變成全熒幕， **新增** 按鈕將會隱藏。 元件仍可透過以下方式新增至電子郵件細分元件 [從元件瀏覽器拖曳並放置在內容編輯器中的電子郵件區段元件上。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component)

### 屬性標籤 {#properties-tab}

![電子郵件分段元件的設定對話方塊屬性索引標籤](/help/email/assets/email-segmentation-configure-properties.png)

* **ID**  — 此選項可讓您控制HTML中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果內容找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS造成影響。

### 協助工具標籤 {#accessibility-tab}

![電子郵件分段元件的設定對話方塊協助工具標籤](/help/email/assets/email-segmentation-configure-accessibility.png)

於 **協助工具** 標籤，可設定的值 [ARIA協助工具](https://www.w3.org/WAI/standards-guidelines/aria/) 元件的標籤。

* **標籤**  — 元件的ARIA標籤屬性值

### 樣式索引標籤 {#styles-tab-edit}

電子郵件區段元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉式清單，選取要套用至元件的樣式。 在「編輯」對話方塊中所做的選取與從元件工具列中選擇的效果相同。

必須在以下位置為此元件設定樣式： [設計對話方塊](#design-dialog) 讓索引標籤可用。

## 選取面板 {#select-panel}

內容作者可以使用 **選取面板** 元件工具列上的選項，以變更為不同的區段進行編輯以及輕鬆重新排列區段。

![選取面板圖示](/help/email/assets/select-panel-icon.png)

選取 **選取面板** 選項時，已設定的區段會顯示為下拉式清單。

* 清單會依指定的區段排列順序排列，並會反映在編號中。
* 首先顯示區段的元件型別，然後是較細字型的區段說明。

![「選取面板」彈出視窗](/help/email/assets/select-panel-popover.png)

* 在下拉式清單中點選或按一下專案，會在編輯器中將檢視切換到該區段。
* 您可以使用拖曳操作框就地重新排列區段。

>[!NOTE]
>
>區段會呈現為頁面編輯器中的標籤，以顯示最終內容有多個選項。 作者在頁面編輯器中無法選取這些索引標籤。 使用選取面板在顯示的區段之間切換。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義哪些元件可新增為電子郵件區段元件中的區段，並定義哪些自訂樣式可供內容作者使用。

### 允許的元件索引標籤 {#allowed-components-tab}

此 **允許的元件** tab可用來定義哪些元件可由內容作者新增為電子郵件區段元件。

此 **允許的元件** tab的功能與相同名稱的標籤相同，當 [在範本編輯器中定義配置容器的原則和屬性。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 樣式索引標籤 {#styles-tab}

電子郵件區段元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)

### 定義條件標籤 {#defined-conditions}

使用 **已定義的條件** 索引標籤上，範本編輯器可以定義哪些條件可供內容作者在建立區段時選取。

![「設計」對話方塊的「定義條件」索引標籤](/help/email/assets/email-segmentation-design-defined-conditions.png)

點選或按一下 **新增** 按鈕來建立新條件。

* **區段條件名稱**  — 條件說明
* **區段條件**  — 必須符合的實際條件，根據Adobe Campaign個人化變數
   * [如需Adobe Campaign Standard個人化資源，請參閱此處。](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?)
   * [如需Adobe Campaign Classic個人化資源，請參閱此處。](https://experienceleague.adobe.com/docs/
* **移除**  — 點選以按一下以移除條件
* **重新排列**  — 點選或按一下並拖曳以重新排列條件
