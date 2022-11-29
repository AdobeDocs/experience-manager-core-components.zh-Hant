---
title: 電子郵件分段元件
description: 電子郵件分段元件
role: Architect, Developer, Admin, User
exl-id: 6c88b8c5-189a-40c0-ab28-04d37dc5fbac
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 0%

---


# 電子郵件分段元件 {#email-segmentation-component}

「電子郵件分段」元件使用Adobe Campaign中的變數，根據內容的收件者來顯示和隱藏內容。

## 使用狀況 {#usage}

電子郵件分段元件可讓內容作者根據Adobe Campaign所提供收件者相關變數所符合的條件，來隱藏和顯示內容。 如此一來，內容的收件者就能根據其細分查看內容。

* 範本作者可使用 [設計對話](#design-dialog) 以定義可以新增為區段的元件。
* 內容作者可使用 [配置對話框](#configure-dialog) 若要新增元件作為區段，並設定要根據Adobe Campaign變數顯示的區段。

除了使用設定對話方塊外，內容作者一旦將電子郵件分段元件新增至內容頁面，內容作者就可以將其他元件拖放至電子郵件分段元件以建立新區段。

## 版本與相容性 {#version-and-compatibility}

電子郵件分段元件的目前版本為v1，已於2022年10月隨電子郵件核心元件第x版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | 相容 |

## 範例元件輸出 {#sample-component-output}

若要體驗電子郵件分段元件，並查看其設定選項、HTML和JSON輸出的範例，請造訪 [元件庫。](https://adobe.com/go/aem_cmp_library_email_segmentation)

### 技術詳細資訊 {#technical-details}

電子郵件宣傳預告元件的最新技術檔案 [可在GitHub上找到。](https://adobe.com/go/aem_cmp_tech_email_segmentation_v1)

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案。](/help/developing/overview.md)

## 配置對話框 {#configure-dialog}

「設定」對話方塊可讓內容作者建立、重新命名和重新排列區段，以及定義使用中的區段。 在「電子郵件分段」元件中，區段只是另一個根據內容收件者符合的條件而隱藏或顯示的元件。 您可以與 [核心元件索引標籤元件、](/help/components/tabs.md) 但在分段元件中，只會顯示符合條件的索引標籤內容。

### 項目標籤 {#items-tab}

![電子郵件分段元件的設定對話項目索引標籤](/help/email/assets/email-segmentation-configure-items.png)

使用 **新增區段** 按鈕，開啟元件選取器以選擇要新增為區段的元件。 新增後，會將項目新增至清單，其中包含下列元素：

* **圖示**  — 區段的元件類型圖示，以便在清單中輕鬆識別。 將滑鼠移至以顯示完整的元件名稱，作為工具提示。
* **條件**  — 必須符合的條件，才能向內容的收件者顯示此區段。
   * 可用條件定義於 [設計對話方塊。](#design-dialog)
   * **預設**  — 定義預設區段，以在未符合其他條件時顯示
   * **自訂**  — 允許作者定義條件
      * 條件以Adobe Campaign個人化變數為基礎
      * [請參閱這裡以取得Adobe Campaign Standard個人化資源。](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?)
      * [請參閱這裡以取得Adobe Campaign Classic個人化資源。](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html)
* **刪除**  — 點選或按一下，從「電子郵件分段元件」中刪除區段。
* **重新排列**  — 點選或按一下並拖曳以重新排列區段。

>[!TIP]
>
>如果內容的檢視區縮小，使編輯對話方塊變成全螢幕，則 **新增** 按鈕。 您仍可以透過 [從元件瀏覽器拖曳，並拖曳至內容編輯器中的「電子郵件分段」元件。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component)

### 屬性標籤 {#properties-tab}

![電子郵件分段元件的設定對話方塊屬性索引標籤](/help/email/assets/email-segmentation-configure-properties.png)

* **ID**  — 此選項可控制HTML中元件的唯一標識符。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查產生的內容來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會對CSS造成影響。

### 協助工具標籤 {#accessibility-tab}

![「電子郵件分段」元件的「配置」對話框輔助工具頁簽](/help/email/assets/email-segmentation-configure-accessibility.png)

在 **協助工具** 索引標籤中，可為 [ARIA協助工具](https://www.w3.org/WAI/standards-guidelines/aria/) 元件的標籤。

* **標籤**  — 元件的ARIA標籤屬性值

### 樣式標籤 {#styles-tab-edit}

電子郵件分段元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉式清單選取您要套用至元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須針對此元件在 [設計對話](#design-dialog) 讓索引標籤可用。

## 選擇面板 {#select-panel}

內容作者可使用 **選擇面板** 選項，以更改為不同的段進行編輯，並輕鬆重新排列段。

![「選擇」面板表徵圖](/help/email/assets/select-panel-icon.png)

選取 **選擇面板** 選項中，設定的區段會顯示為下拉式清單。

* 清單按分段的分配排列排序，並反映在編號中。
* 區段的元件類型會先顯示，接著以較淺的字型顯示區段說明。

![選取面板彈出視窗](/help/email/assets/select-panel-popover.png)

* 點選或按一下下拉式清單中的項目，將編輯器中的檢視切換至該區段。
* 可使用拖曳控點就地重新排列區段。

>[!NOTE]
>
>區段在頁面編輯器中會以索引標籤的形式呈現，以顯示最終內容有多個選項。 作者無法在頁面編輯器中選取這些標籤。 使用「選取」面板，在顯示的區段之間切換。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義哪些元件可新增為「電子郵件分段元件」的區段，以及定義哪些自訂樣式可供內容作者使用。

### 「允許的元件」頁簽 {#allowed-components-tab}

此 **允許的元件** 索引標籤可用來定義哪些元件可由內容作者新增為「電子郵件分段元件」的區段。

此 **允許的元件** 頁簽函式與相同名稱的頁簽函式 [在模板編輯器中定義佈局容器的策略和屬性。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 樣式標籤 {#styles-tab}

電子郵件分段元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)

### 「定義的條件」頁簽 {#defined-conditions}

使用 **定義的條件** 標籤，範本編輯器可定義內容作者在建立區段時可選取的條件。

![「設計」對話框「定義的條件」頁簽](/help/email/assets/email-segmentation-design-defined-conditions.png)

點選或按一下 **新增** 按鈕以建立新條件。

* **區段條件名稱**  — 條件說明
* **區段條件**  — 根據Adobe Campaign個人化變數，必須符合的實際條件
   * [請參閱這裡以取得Adobe Campaign Standard個人化資源。](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?)
   * [請參閱這裡以取得Adobe Campaign Classic個人化資源。](https://experienceleague.adobe.com/docs/)
* **移除**  — 點選以按一下以移除條件
* **重新排列**  — 點選或按一下並拖曳以重新排列條件的順序
