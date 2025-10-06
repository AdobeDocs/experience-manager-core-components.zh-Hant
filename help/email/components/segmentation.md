---
title: 電子郵件細分元件
description: 電子郵件細分元件
role: Architect, Developer, Admin, User
exl-id: 6c88b8c5-189a-40c0-ab28-04d37dc5fbac
index: false
source-git-commit: eb77567dc32cccb81a9fc131493d11fb55b7e93b
workflow-type: ht
source-wordcount: '1089'
ht-degree: 100%

---


# 電子郵件細分元件 {#email-segmentation-component}

「電子郵件細分元件」使用 Adobe Campaign 中的變數，根據內容收件者顯示和隱藏內容。

## 用途 {#usage}

使用「電子郵件細分元件」，內容作者可根據 Adobe Campaign 提供的收件者相關變數所符合的條件，以隱藏和顯示內容。如此一來，內容收件者會看到根據其細分所顯示的內容。

* 範本作者可以使用[設計對話框](#design-dialog)，定義可新增為區段的元件。
* 內容作者可以使用[設定對話框](#configure-dialog)將元件新增為區段，並根據 Adobe Campaign 變數設定要顯示的區段。

除了使用設定對話框之外，內容作者將「電子郵件細分元件」新增至內容頁面後，就可以將其他元件拖放至「電子郵件細分元件」，以建立新區段。

## 版本和相容性 {#version-and-compatibility}

「電子郵件細分元件」的目前版本為 v1，此版本於 2022 年 10 月隨著「電子郵件核心元件」x 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 相容 | - | - |

### 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_email_segmentation_v1)有關「電子郵件 Teaser 元件」的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者建立、重新命名和重新排列區段，並可定義作用中的區段。在「電子郵件細分元件」中，區段只是另一個根據內容收件者所符合的條件隱藏或顯示的元件。您可以將其與[核心元件索引標籤元件](/help/components/tabs.md)相比，但在「細分元件」中，僅會顯示符合條件的索引標籤內容。

### 項目索引標籤 {#items-tab}

![電子郵件細分元件的設定對話框項目索引標籤](/help/email/assets/email-segmentation-configure-items.png)

使用&#x200B;**新增區段**&#x200B;按鈕開啟元件選擇器，選擇要新增為區段的元件。新增後，項目就會新增至清單，其中包含以下元素：

* **圖示** - 區段的元件類型圖示，以便在清單中輕鬆識別。將滑鼠移至上方，即可看到包含完整元件名稱的工具提示。
* **條件** - 區段必須符合條件，才會向內容收件者顯示。
   * 可用的條件於[設計對話框](#design-dialog)中定義。
   * **預設** - 定義未符合其他條件時，會顯示的預設區段
   * **自訂** - 允許作者定義條件
      * 條件根據 Adobe Campaign 個人化變數而定
      * [請參閱此處，以了解 Adobe Campaign Standard 個人化資源。](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?)
      * [請參閱此處，以了解 Adobe Campaign Classic 個人化資源。](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html)
* **刪除** - 點選或按一下以從「電子郵件細分元件」中刪除該區段。
* **重新排列** - 點選或按一下並拖曳以重新排列區段。

>[!TIP]
>
>若縮小內容檢視區，使編輯對話框進入全螢幕模式，則會隱藏&#x200B;**新增**&#x200B;按鈕。元件仍可新增至「電子郵件細分元件」，只需[從元件瀏覽器拖曳並放置到內容編輯器中的「電子郵件細分元件」上。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component)

### 屬性索引標籤 {#properties-tab}

![電子郵件細分元件的設定對話框屬性索引標籤](/help/email/assets/email-segmentation-configure-properties.png)

* **ID** - 此選項允許控制 HTML 中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的內容找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS 產生影響。

### 協助工具索引標籤 {#accessibility-tab}

![電子郵件細分元件的設定對話框協助工具索引標籤](/help/email/assets/email-segmentation-configure-accessibility.png)

在&#x200B;**協助工具**&#x200B;索引標籤上，可以設定元件的 [ARIA 協助工具](https://www.w3.org/WAI/standards-guidelines/aria/)標籤值。

* **標籤** - 元件的 ARIA 標籤屬性值

### 樣式索引標籤 {#styles-tab-edit}

「電子郵件細分元件」支援 AEM [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉式清單，選取想要套用至元件的樣式。在編輯對話框中所做的選取，與從元件工具列中選擇具有相同效果。

元件樣式必須在[設計對話框](#design-dialog)中設定，才能使用該索引標籤。

## 選取面板 {#select-panel}

內容作者可以使用元件工具列中的&#x200B;**選取面板**&#x200B;選項，切換至不同區段以進行編輯，亦可輕鬆重新排列區段。

![選取面板圖示](/help/email/assets/select-panel-icon.png)

在元件工具列中選取&#x200B;**選取面板**&#x200B;選項後，已設定的區段會顯示為下拉式清單。

* 清單會根據指派給區段的排列方式排序，並反映在編號中。
* 首先顯示區段元件類型，後面接著以較淺的字體顯示區段說明。

![選取面板彈出視窗](/help/email/assets/select-panel-popover.png)

* 在下拉式清單中點選或按一下項目，將編輯器中的視圖切換至該區段。
* 您可以使用拖曳控點就地重新排列區段。

>[!NOTE]
>
>在頁面編輯器中，區段會以索引標籤形式呈現，以顯示最終內容具備多個選項。作者無法在頁面編輯器中選取這些索引標籤。使用選取面板，以在顯示的區段之間切換。

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可定義哪些元件可作為區段新增至「電子郵件細分元件」，以及可供內容作者使用的自訂樣式。

### 允許的元件索引標籤 {#allowed-components-tab}

**允許的元件**&#x200B;索引標籤用於定義哪些元件可供內容作者作為區段新增至電子郵件細分元件。

[在「範本編輯器」中定義「版面容器」的原則與屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)時，**允許的元件**&#x200B;索引標籤與同名索引標籤的功能相同。

### 樣式索引標籤 {#styles-tab}

「電子郵件細分元件」支援 AEM [樣式系統。](/help/get-started/authoring.md#component-styling)

### 已定義的條件索引標籤 {#defined-conditions}

使用&#x200B;**已定義的條件**&#x200B;索引標籤，範本編輯者可定義內容作者在建立區段時能夠選取的條件。

![設計對話框已定義的條件索引標籤](/help/email/assets/email-segmentation-design-defined-conditions.png)

點選或按一下&#x200B;**新增**&#x200B;按鈕，以建立新條件。

* **區段條件名稱** - 條件的說明
* **區段條件** - 必須符合的實際條件，根據 Adobe Campaign 個人化變數而定
   * [請參閱此處，以了解 Adobe Campaign Standard 個人化資源。](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?)
   * [請參閱此處，以了解 Adobe Campaign Classic 個人化資源。]&#x200B;(https://experienceleague.adobe.com/docs/
* **移除** - 點選或按一下以移除該條件
* **重新排列** - 點選或按一下並拖曳，以重新排列條件的順序
