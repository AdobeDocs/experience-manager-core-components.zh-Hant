---
title: 自適應表單核心元件 - 表單容器
description: 將自適應表單新增至網頁。
role: Architect, Developer, Admin, User
exl-id: 03c4cf7c-51d6-4850-a566-1c0514d52dab
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: ht
source-wordcount: '1524'
ht-degree: 100%

---


# 表單容器 {#form-container-adaptive-forms-core-component}

<span class="preview">本文討論&#x200B;**草稿** <!--and **Hamburger Menu Support** --> 功能，這是一項預先發佈功能。此項預先發佈功能可透過我們的[預先發佈管道](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html?lang=zh-Hant#new-features)存取。</span>

表單可提供寶貴資訊，讓網站訪客與網站互動，進而提高參與度和使用者滿意度。Adobe Experience Manager (AEM) Sites 中的自適應表單容器可讓網站擁有者輕鬆將表單新增至其頁面。這有助於促進網站訪客與網站擁有者或組織之間的溝通，透過提供簡化的方式，讓訪客提供意見回饋、提出查詢並完成其他動作

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

自適應表單摺疊面板核心元件於 2023 年 2 月發行，屬於 Cloud Service 核心元件 2.0.4 和 AEM 6.5.16.0 Forms 或更新版本的核心元件 1.1.12 的一部分。下表顯示所有支援版本、AEM 相容性以及對應文件的連結：

| 元件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更新版本 |
|---|---|---|
| v1 | 與<br>[ 2.0.4 版](/help/adaptive-forms/version.md)及更新版本相容 | 與<br>[ 1.1.12 版](/help/adaptive-forms/version.md)及更新版本相容，但低於 2.0.0 版。 |

如需「核心元件」版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)文件。
<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion_tw). -->

## 技術詳細資訊 {#technical-details}

[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/container/v1/container) 的技術文件中可找到自適應表單容器核心元件的最新資訊。如需開發核心元件的更多資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

透過設定對話框，您可以輕鬆自訂訪客的表單容器體驗。同樣能夠輕鬆定義表單容器選項，以提供順暢無礙的使用者體驗。

### 基本索引標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/formcontainer_basictab1.png)

- **標題** - 您可以使用其標題輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。若未新增標題，則會顯示該元件的名稱而非標題文字。

- **預填服務** - 此選項可在轉譯自適應表單時，讓使用者選取用於擷取資料的預填服務。深入了解[如何建立和設定預填服務](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/prepopulate-adaptive-form-fields.html?lang=zh-hant#aem-forms-custom-prefill-service)。

- **角色**：角色為 HTML 屬性，用於向輔助技術 (例如螢幕助讀程式) 指定 HTML 元素用途。角色屬性可用來提供元素的其他內容脈絡和語義上的涵義，讓螢幕助讀程式更容易向使用者解譯和播報內容。例如，在 AEM Forms 中，表單欄位的標籤可能會具有「標籤」角色，其輸入欄位則可能會具有「文字方塊」的角色。這可協助螢幕助讀程式瞭解標籤和輸入欄位之間的關係，並向使用者正確播報。

- **用戶端程式庫類別** - 使用者可以根據每個自適應表單設定自訂 JavaScript 資料庫。建議僅保留程式庫內可重複使用的函數，這些函數與 jquery 和 underscore.js 第三方程式庫有相依性。
有時候，如果有**複雜的驗證規則**，則確切的驗證指令碼會駐留在自訂函數中，且使用者會從欄位驗證運算式中呼叫這些自訂函數。若要在執行伺服器端驗證時公開和提供此自訂函數程式庫，表單使用者可以在「自適應表單容器」屬性的&#x200B;**[!UICONTROL 基礎]**&#x200B;索引標籤下方，設定 AEM 用戶端程式庫的名稱。使用者可以根據自適應表單來設定自訂 JavaScript 程式庫。程式庫中只會保留可重複使用的函數，這些函數與 jquery 和 underscore.js 第三方程式庫有相依性。

<!--
- **Enable the hamburger menu for mobile view** - Select the checkbox to integrate a hamburger menu into your form for mobile view. Represented by three horizontal lines stacked vertically, this menu provides a clear and uncluttered display for panels on smaller devices, especially on mobile devices. For more information about the hamburger menu, refer to the [Learn more about the hamburger menu](#learn-more-about-the-hamburger-menu) section. -->


### 資料模型索引標籤 {#data-model-tab}

![提交索引標籤](/help/adaptive-forms/assets/formcontainer_fdmtab.png)

您可以使用「表單資料模型」將表單連接至「資料來源」，以根據使用者動作傳送及接收資料。您也可以將表單連接至 JSON 結構描述，以預先定義的格式接收提交的資料。根據要求，將您的表單連接至 JSON 結構描述或「表單」資料模型：
- 建立 JSON 結構描述並上傳至您的環境
- 建立「表單資料模型」

### 草稿

![提交索引標籤](/help/adaptive-forms/assets/formcontainer_autosavetab.png)

- **自動儲存草稿**：選取&#x200B;**自動儲存草稿**&#x200B;核取方塊，以啟用將表單儲存為草稿。
- **儲存偏好設定**：設定&#x200B;**儲存偏好設定**&#x200B;為&#x200B;**定期儲存草稿**，以在特定時間間隔後自動儲存表單。
  **儲存間隔頻率 (秒)**：指定時間間隔 (以秒為單位)，以設定在定義的間隔觸發自動儲存表單的持續時間。

### 提交索引標籤 {#submission-tab}

使用者可以為自適應表單提交設定不同的動作。

- **重新導向 URL/路徑** - 此選項可讓使用者為每個表單設定頁面，表單使用者在提交自適應表單後會重新導向至該頁面。按一下這裡以取得有關[如何設定重新導向頁面](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-redirect-page.html?lang=zh-Hant)的詳細資訊。

![提交索引標籤](/help/adaptive-forms/assets/formcontainer_submissiontab.png)

- **顯示訊息** - 此選項可讓使用者新增在成功提交自適應表單時顯示的訊息。預先定義的文字會包含在對話框中，使用者可自行修改。「顯示訊息」對話框支援 RTF 格式工具，可讓使用者格式化新增的文字。

![顯示訊息索引標籤](/help/adaptive-forms/assets/formconatiner_showmessage.png)

- **提交動作** - 當使用者按一下「自適應表單」上的「提交按鈕」時，就會觸發「提交動作」。使用者可從下拉式清單中選取現有支援的「提交動作」。了解如何[在「提交」索引標籤中設定「提交動作」](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html?lang=zh-Hant#supporting-custom-functions-in-validation-expressions-br)。

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

- **允許的樣式**：您可以透過提供名稱以及代表該樣式的 CSS 類別，以定義樣式。例如，您可以建立名為「粗體文字」的樣式，並提供 CSS 類別「font-weight: bold」。您可以在自適應表單編輯器中，使用或套用這些樣式至自適應表單。若要套用樣式，請在自適應表單編輯器中選取您要套用樣式的元件，導覽至屬性對話框，然後從&#x200B;**樣式**&#x200B;下拉式清單中選取所需的樣式。如果需要更新或修改樣式，只需返回至設計對話框，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 自訂屬性索引標籤

![自訂屬性對話框](/help/adaptive-forms/assets/formcontainer-custompropertiestab.png)

自訂屬性可讓您使用表單範本，將自訂屬性 (鍵值對) 與自適應表單核心元件建立關聯。自訂屬性會反映在元件的無周邊轉譯屬性區段中。可讓您建立根據自訂屬性值調整的動態表單行為。例如，開發人員可以為行動裝置、桌上型電腦或網頁平台設計各種無周邊表單元件的轉譯，大幅提升各種裝置的使用者體驗。

- **群組名稱**：您可以提供名稱，以識別自訂屬性群組。還可以新增、刪除或重新排列多個自訂屬性群組。新增自訂屬性群組後，您可以看到下列選項：

   - **鍵值對**：按一下每個自訂屬性群組的&#x200B;**新增**&#x200B;按鈕，即可新增多個自訂屬性名稱和自訂屬性值。

   - **刪除**：點選或按一下以刪除自訂屬性名稱和自訂屬性值。

   - **重新排列**：點選或按一下並拖曳，以重新排列自訂屬性名稱和自訂屬性值的順序。

<!--
## Learn more about the hamburger menu

A hamburger menu, often referred to as a mobile menu or navigation drawer, is a popular design element in mobile user interfaces. It features three horizontal lines stacked vertically, resembling a hamburger. The design efficiently conserves screen space by hiding secondary navigation options until they are needed, especially on smaller devices such as mobile. AEM forms can be efficiently organized within the hamburger menu, enabling users to access various panels within a form without overwhelming the main interface.

Consider a scenario, where a financial institution offers an online loan application form that requires users to provide detailed information across several panels, such as personal details, financial information, loan preferences, and supporting documents. The form includes multiple panels and options that can clutter the interface, especially on mobile devices. Users need an organized way to navigate through these panels without feeling overwhelmed. The hamburger menu is implemented to enhance the user experience on mobile devices.

### Components of hamburger menu

![Hamburger Menu](/help/adaptive-forms/assets/hamburger-menu.png){width=50%, align=center}

**A. Hamburger menu**: The hamburger menu features a navigation panel that slides out or drops down when the hamburger icon is clicked or tapped. The menu displays the panel headings, and selecting a panel shifts the focus to that panel. It allows users to easily navigate between different panels.

![Hamburger Menu](/help/adaptive-forms/assets/hamburger-menu-icon.png){width=50%}

**B. Breadcrumb**: Breadcrumbs indicate the user’s current location within the form. They offer a hierarchical trail that shows the user’s navigation path and helps them understand their position in the form.

**C. Active panel**: The active panel refers to the section or part of the form that is currently being displayed. When a user selects an option from the hamburger menu, the corresponding panel becomes the active panel, showing the relevant fields and information for that section.

### Points to consider while working with the hamburger menu

- The hamburger menu displays only the names of the panels. Here are different scenarios illustrating how the panel name appears in the navigation pane of the hamburger menu based on the configuration properties of the panel:  
  
  - If you set the properties of the panel to hidden, the panel's name does not appear in the navigation pane of the hamburger menu. For example, if you configure the properties of the `Financial Information` panel as `hidden`, the panel name does not appear in the navigation pane of the hamburger menu.
    
    ![Hidden panel](/help/adaptive-forms/assets/hidden-panel.png){width=50%}

  - If you set the properties of the panel to `disabled`, its name appears in the navigation pane of the hamburger menu, but you cannot select or edit it. For example, if you configure the properties of the `Financial Information` panel as `disabled`, the panel name appears in the navigation pane, but it cannot be selected or edited. 
     
    ![Disabled panel](/help/adaptive-forms/assets/disabled-panel.png){width=50%}

  - If you hide the  title of the panel, it does not appear in the navigation pane of the hamburger menu. A blank space shows up instead, but you can navigate to the fields of the panel by clicking on that space. For example, if you hide the title of the `Financial Information` panel, the blank space appears in its place in the navigation pane of the hamburger menu. You can navigate to the fields of the panel by clicking on the blank space.
    
    ![Hidden title panel](/help/adaptive-forms/assets/hidden-title-panel.png){width=50%}

- By default, the navigation pane in the breadcrumb component supports up to three levels of navigation. However, with the custom component, you can configure the navigation hierarchy to accommodate as many levels as needed.
- When using the hamburger menu, the user can navigate between panels using arrows. However, once a panel is selected, the menu automatically closes, and focus shifts to the fields within the chosen panel.

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

![Basic tab](/help/adaptive-forms/assets/formcontainer_basictab.png)
-->

## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}