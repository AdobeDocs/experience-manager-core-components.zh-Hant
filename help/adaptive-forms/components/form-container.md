---
title: 自適應表單核心元件 - 表單容器
description: 將自適應表單新增至網頁。
role: Developer, Admin, User
exl-id: 03c4cf7c-51d6-4850-a566-1c0514d52dab
TQID: https://experienceleague.adobe.com/kMG6SKHisAUmKhOh9AFLI8NG6w0vH7tP4XimBKAMo-I
product_v2: id: c45915cf-e157-4af7-a80d-97b905bcb3a5id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: e2c1b6d3-bb7e-4fe8-8c72-f7b403298e91
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 0af65c80f9cc58c4ba48d5b3dc7a026820bd2833
workflow-type: tm+mt
source-wordcount: 2555
ht-degree: 64%

---

# 表單容器 {#form-container-adaptive-forms-core-component}

<span class="preview">本文討論&#x200B;**草稿**&#x200B;和&#x200B;**漢堡功能表支援**&#x200B;功能，這些是發行前功能。 此項預先發佈功能可透過我們的[預先發佈管道](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html#new-features)存取。</span>

表單可提供寶貴資訊，讓網站訪客與網站互動，進而提高參與度和使用者滿意度。 Adobe Experience Manager (AEM) Sites 中的自適應表單容器可讓網站擁有者輕鬆將表單新增至其頁面。 這有助於促進網站訪客與網站擁有者或組織之間的溝通，透過提供簡化的方式，讓訪客提供意見回饋、提出查詢並完成其他動作

{{traditional-aem}}

## 用途 {#reasons-to-use-forms-container}

可能將表單新增至網站的原因有幾個：
- **資料收集**：表單可用來收集網站訪客的資料，以進行各種用途，例如市場調查、使用者行為分析等。

- **商機開發**：表單可用於從潛在客戶收集資訊，例如姓名和電子郵件地址，以開發銷售和行銷工作的商機。

- **電子商務**：表單可用於線上購物，允許客戶透過網站下訂單及付款。

- **聯絡**：聯絡表單可讓網站訪客輕鬆聯絡網站擁有者或組織。

- **問卷和投票**：表單可用於透過問卷和投票，從網站訪客收集回饋和意見。

- **事件註冊**：表單可用於事件註冊，讓網站訪客註冊事件或網路研討會。

- **訂閱**：表單可用於網站訂閱，讓訪客註冊電子報或其他定期通訊。

- **使用者驗證**：表單可用於使用者驗證，允許網站訪客建立帳戶並登入以存取專屬的內容或功能。

- **提高轉換率**：設計良好的表單可讓使用者輕鬆完成想要的動作，例如購買產品或註冊服務，進而提高轉換率。

## 版本和相容性 {#version-and-compatibility}

自適應表單摺疊面板核心元件於 2023 年 2 月發行，屬於 Cloud Service 核心元件 2.0.4 和 AEM 6.5.16.0 Forms 或更新版本的核心元件 1.1.12 的一部分。 下表顯示所有支援版本、AEM 相容性以及對應文件的連結：

| 元件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更新版本 |
|---|---|---|
| v1 | 與<br>[ 2.0.4 版](/help/adaptive-forms/version.md)及更新版本相容 | 與<br>[ 1.1.12 版](/help/adaptive-forms/version.md)及更新版本相容，但低於 2.0.0 版。 |

如需「核心元件」版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)文件。
<!--
## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). 
-->

## 技術詳細資訊 {#technical-details}

[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/container/v1/container) 的技術文件中可找到自適應表單容器核心元件的最新資訊。 如需開發核心元件的更多資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

透過設定對話框，您可以輕鬆自訂訪客的表單容器體驗。 同樣能夠輕鬆定義表單容器選項，以提供順暢無礙的使用者體驗。

### 基本索引標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/formcontainer_basictab1.png)

- **標題** - 您可以使用其標題輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。 若未新增標題，則會顯示該元件的名稱而非標題文字。

- **預填服務** - 此選項可在轉譯自適應表單時，讓使用者選取用於擷取資料的預填服務。 深入了解[如何建立和設定預填服務](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/prepopulate-adaptive-form-fields.html?lang=zh-hant#aem-forms-custom-prefill-service)。

- **角色**：角色為 HTML 屬性，用於向輔助技術 (例如螢幕助讀程式) 指定 HTML 元素用途。 角色屬性可用來提供元素的其他內容脈絡和語義上的涵義，讓螢幕助讀程式更容易向使用者解譯和播報內容。 例如，在 AEM Forms 中，表單欄位的標籤可能會具有「標籤」角色，其輸入欄位則可能會具有「文字方塊」的角色。 這可協助螢幕助讀程式瞭解標籤和輸入欄位之間的關係，並向使用者正確播報。

- **用戶端程式庫類別** - 使用者可以根據每個自適應表單設定自訂 JavaScript 資料庫。 建議僅保留程式庫內可重複使用的函數，這些函數與 jquery 和 underscore.js 第三方程式庫有相依性。有時候，如果有&#x200B;**複雜的驗證規則**，則確切的驗證指令碼會駐留在自訂函數中，且使用者會從欄位驗證運算式中呼叫這些自訂函數。 若要在執行伺服器端驗證時公開和提供此自訂函數程式庫，表單使用者可以在「自適應表單容器」屬性的&#x200B;**[!UICONTROL 基礎]**&#x200B;索引標籤下方，設定 AEM 用戶端程式庫的名稱。使用者可以根據自適應表單來設定自訂 JavaScript 程式庫。 程式庫中只會保留可重複使用的函數，這些函數與 jquery 和 underscore.js 第三方程式庫有相依性。

- **啟用行動檢視的漢堡功能表** — 選取核取方塊，將漢堡功能表整合到您的行動檢視表單中。 此選單以垂直棧疊的三條水平線表示，可為小型裝置（尤其是行動裝置）上的面板提供清晰整潔的顯示。 如需漢堡選單的詳細資訊，請參閱[進一步瞭解漢堡選單](#learn-more-about-the-hamburger-menu)區段。


### 資料模型索引標籤 {#data-model-tab}

![資料模型標籤](/help/adaptive-forms/assets/formcontainer_fdmtab.png)

您可以使用「表單資料模型」將表單連接至「資料來源」，以根據使用者動作傳送及接收資料。 您也可以將表單連接至 JSON 結構描述，以預先定義的格式接收提交的資料。 根據要求，將您的表單連接至 JSON 結構描述或「表單」資料模型：
- **無** — 不要將表單與資料模型建立關聯。
- **結構描述** — 將表單連線至上傳至您環境的JSON結構描述。
- **表單資料模型** — 將表單連線至表單資料模型，以便與外部資料來源整合。
- **Connector** — 將表單連線到以聯結器為基礎的資料來源。
- **表單範本** — 將表單與表單範本建立關聯。

### 草稿標籤 {#drafts-tab}

![草稿標籤](/help/adaptive-forms/assets/formcontainer_autosavetab.png)

- **自動儲存草稿**：選取&#x200B;**自動儲存草稿**&#x200B;核取方塊，以啟用將表單儲存為草稿。
- **儲存偏好設定**：設定&#x200B;**儲存偏好設定**&#x200B;為&#x200B;**定期儲存草稿**，以在特定時間間隔後自動儲存表單。
  **儲存間隔頻率 (秒)**：指定時間間隔 (以秒為單位)，以設定在定義的間隔觸發自動儲存表單的持續時間。

### 提交索引標籤 {#submission-tab}

使用者可以為自適應表單提交設定不同的動作。

- **在送出時** — 選擇&#x200B;**重新導向至URL**，在送出後傳送表單使用者至設定的頁面，或選擇&#x200B;**顯示訊息**，在表單上顯示確認訊息。

- **重新導向 URL/路徑** - 此選項可讓使用者為每個表單設定頁面，表單使用者在提交自適應表單後會重新導向至該頁面。 按一下這裡以取得有關[如何設定重新導向頁面](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-redirect-page.html)的詳細資訊。

![提交索引標籤](/help/adaptive-forms/assets/formcontainer_submissiontab.png)

- **顯示訊息** - 此選項可讓使用者新增在成功提交自適應表單時顯示的訊息。 預先定義的文字會包含在對話框中，使用者可自行修改。 「顯示訊息」對話框支援 RTF 格式工具，可讓使用者格式化新增的文字。

![顯示訊息索引標籤](/help/adaptive-forms/assets/formconatiner_showmessage.png)

- **提交動作** - 當使用者按一下「自適應表單」上的「提交按鈕」時，就會觸發「提交動作」。 使用者可從下拉式清單中選取現有支援的「提交動作」。 了解如何[在「提交」索引標籤中設定「提交動作」](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#supporting-custom-functions-in-validation-expressions-br)。

- **動作設定** — 設定對應以將欄位值傳遞為感謝頁面要求引數。

- **啟用POST要求** — 選取此選項可使用HTTP POST要求提交表單資料。

### 記錄檔案索引標籤 {#document-of-record-tab}

![記錄檔案索引標籤](/help/adaptive-forms/assets/formcontainer_dortab.png)

[記錄檔案(DoR)](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/generate-document-of-record-core-components)是透過表單提交的資料的正式可列印表示法。 使用&#x200B;**記錄檔案**&#x200B;索引標籤來設定使用者提交表單時如何產生DoR：

- **無** — 不要為表單產生記錄檔案。
- **將表單範本關聯為記錄檔案範本** — 使用現有的表單範本做為DoR範本。
- **產生記錄檔案** — 根據提交的表單資料自動產生記錄檔案。
- **從記錄檔案排除檔案附件** — 選取此選項，從產生的DoR中忽略檔案附件。

## 設計對話框 {#design-dialog}

設計對話框可用於定義和管理表單容器元件的 CSS 樣式。

### 允許的元件索引標籤 {#allowed-components-tab}

![設定對話框允許的元件索引標籤](/help/adaptive-forms/assets/formcontainer-allowedcomponents.png)

透過&#x200B;**允許的元件**&#x200B;索引標籤，範本編輯器可設定作為項目新增至自適應表單編輯器中元件內面板的元件。

### 預設元件索引標籤 {#default-components-tab}

![設計對話框預設元件索引標籤](/help/adaptive-forms/assets/formcontainer-defaultcomponents.png)

**預設元件** 索引標籤可讓範本編輯器指定在自適應表單編輯器中，預設顯示為表單容器元件項目的元件。

### 回應式設定索引標籤 {#responsive-tab}

![設計對話框回應式設定索引標籤](/help/adaptive-forms/assets/formcontainer-responsivestyle.png)

**回應式設定** 索引標籤可讓範本編輯器在自適應表單編輯器的表單容器元件中，指定格線中的欄數。

### 樣式索引標籤 {#styles-tab}

自適應表單檔案附件核心元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

![設計對話框](/help/adaptive-forms/assets/formcontainer-styletab.png)

- **預設 CSS 類別**：您可以為自適應表單表單容器核心元件提供預設 CSS 類別。

- **允許的樣式**：您可以透過提供名稱以及代表該樣式的 CSS 類別，以定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供 CSS 類別「font-weight: bold」。 您可以在自適應表單編輯器中，使用或套用這些樣式至自適應表單。 若要套用樣式，請在自適應表單編輯器中選取您要套用樣式的元件，導覽至屬性對話框，然後從&#x200B;**樣式**&#x200B;下拉式清單中選取所需的樣式。 如果需要更新或修改樣式，只需返回至設計對話框，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 自訂屬性索引標籤

![自訂屬性對話框](/help/adaptive-forms/assets/formcontainer-custompropertiestab.png)

自訂屬性可讓您使用表單範本，將自訂屬性 (鍵值對) 與自適應表單核心元件建立關聯。 自訂屬性會反映在元件的無周邊轉譯屬性區段中。 可讓您建立根據自訂屬性值調整的動態表單行為。 例如，開發人員可以為行動裝置、桌上型電腦或網頁平台設計各種無周邊表單元件的轉譯，大幅提升各種裝置的使用者體驗。

- **群組名稱**：您可以提供名稱，以識別自訂屬性群組。 還可以新增、刪除或重新排列多個自訂屬性群組。 新增自訂屬性群組後，您可以看到下列選項：

   - **鍵值對**：按一下每個自訂屬性群組的&#x200B;**新增**&#x200B;按鈕，即可新增多個自訂屬性名稱和自訂屬性值。

   - **刪除**：點選或按一下以刪除自訂屬性名稱和自訂屬性值。

   - **重新排列**：點選或按一下並拖曳，以重新排列自訂屬性名稱和自訂屬性值的順序。

## 進一步瞭解漢堡選單 {#learn-more-about-the-hamburger-menu}

漢堡選單（通常稱為行動選單或導覽抽屜）是行動使用者介面中常見的設計元素。 它有三條垂直棧疊的水平線，看起來像一個漢堡。 此設計可隱藏次要導覽選項，有效節省熒幕空間，直到需要這些選項時為止，尤其是在行動裝置等較小裝置上。 AEM表單可在漢堡選單中有效率地組織，讓使用者能夠存取表單中的各種面板，而不會使主介面不知所措。

考慮一種情況，金融機構提供線上貸款申請表單，要求使用者跨多個面板提供詳細資訊，例如個人詳細資訊、財務資訊、貸款偏好設定和支援檔案。 表單包含多個面板和選項，可能會讓介面變得雜亂，尤其是在行動裝置上。 使用者需要一種有條理的方式來瀏覽這些面板，而不會感到不知所措。 實作漢堡功能表可提升行動裝置上的使用者體驗。

### 漢堡選單元件

![漢堡選單](/help/adaptive-forms/assets/hamburger-menu.png){width=50%, align=center}

**A。漢堡選單**：漢堡選單具有導覽面板，當按一下或點選漢堡圖示時，導覽面板會滑出或下降。 功能表會顯示面板標題，選取面板會將焦點移至該面板。 它讓使用者在不同的面板之間輕鬆導覽。

![漢堡選單](/help/adaptive-forms/assets/hamburger-menu-icon.png){width=50%}

**B。階層連結**：階層連結指出使用者在表單中的目前位置。 它們提供階層式追蹤功能，可顯示使用者的導覽路徑，並協助使用者瞭解其在表單中的位置。

**C。使用中面板**：使用中面板參考到目前顯示的部分或部份表單。 當使用者從漢堡選單中選取選項時，對應的面板會變成使用中面板，顯示該區段的相關欄位和資訊。

### 使用漢堡選單時要考量的點

- 漢堡選單只會顯示面板的名稱。 以下不同案例說明面板名稱如何根據面板的組態屬性出現在漢堡選單的導覽窗格中：

   - 如果您將面板的屬性設定為隱藏，則面板的名稱不會出現在漢堡選單的導覽窗格中。 例如，如果您將`Financial Information`面板的內容設定為`hidden`，面板名稱就不會出現在漢堡選單的導覽窗格中。

     ![隱藏面板](/help/adaptive-forms/assets/hidden-panel.png){width=50%}

   - 如果您將面板的屬性設定為`disabled`，其名稱會出現在漢堡選單的導覽窗格中，但您無法選取或編輯它。 例如，如果您將`Financial Information`面板的內容設定為`disabled`，面板名稱會出現在導覽窗格中，但無法選取或編輯它。

     ![已停用的面板](/help/adaptive-forms/assets/disabled-panel.png){width=50%}

   - 如果您隱藏面板的標題，它就不會出現在漢堡選單的導覽窗格中。 畫面改為顯示空白字元，但您可按一下該空白字元以導覽至面板的欄位。 例如，如果您隱藏`Financial Information`面板的標題，空白區會出現在漢堡功能表導覽窗格中的位置。 您可以按一下空白來導覽至面板的欄位。

     ![隱藏的標題面板](/help/adaptive-forms/assets/hidden-title-panel.png){width=50%}

- 依預設，階層連結元件中的導覽窗格支援最多三個層級的導覽。 不過，使用自訂元件時，您可以設定導覽階層以容納所需的層級。
- 使用漢堡選單時，使用者可以使用箭頭在面板之間導覽。 不過，一旦選取面板，選單就會自動關閉，且焦點會移至所選面板內的欄位。

<!--
### Advantages to use hamburger menu

- **Space efficiency**: By hiding form navigation options until needed, the hamburger menu maximizes screen space, which is especially beneficial on smaller devices.

- **Clutter reduction**: It minimizes visual clutter by consolidating various form navigation links into a single, collapsible menu.

- **Improved focus**: With fewer visible navigation elements, users can concentrate on the main content of the form without being distracted by secondary options.

- **Simplified design**: It creates a more streamlined user interface, resulting in a cleaner and more organized form layout.

- **Enhanced mobile experience**: On mobile devices, where screen space is limited, the hamburger menu offers an efficient way to access all form navigation options without overwhelming the user.

### How to enable hamburger menu for your form?

To enable hamburger menu for form, perform the following steps:

1. Open form in an edit mode.
1. Open the Content browser, and select the **[!UICONTROL Guide Container]** component of your Adaptive Form. 
1. Click the Guide Container properties ![Guide properties](/help/adaptive-forms/assets/configure_icon.png) icon. The Adaptive Form Container dialog box opens. 
1. Click the  **[!UICONTROL Basic]** tab. 
1. Select the **[!UICONTROL Add hamburger menu support]** checkbox.
1. Click **[!UICONTROL Done]**.

![Basic tab](/help/adaptive-forms/assets/formcontainer_basictab1.png)
-->

## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}