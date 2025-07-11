---
title: 最適化Forms核心元件 — 電子郵件輸入
description: 使用或自訂最適化Forms電子郵件輸入核心元件。
role: Architect, Developer, Admin, User
exl-id: f6a2974b-991e-4cea-9ef8-0b03e8975eeb
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: tm+mt
source-wordcount: '2111'
ht-degree: 0%

---


# 電子郵件元件 {#Email-input-adaptive-forms-core-component}

最適化表單電子郵件輸入核心元件是用來收集使用者的電子郵件地址。 電子郵件輸入欄位可讓瀏覽器驗證輸入的資料是否為有效的電子郵件地址格式。 它通常以文字方塊表示，並且具備僅接受有效電子郵件地址的模式驗證。 可使用其他屬性（例如「必要」、「預留位置」和「模式」）來進一步自訂電子郵件輸入欄位，以設定輸入資料的驗證。

{{traditional-aem}}

**範例**

![範例](/help/adaptive-forms/assets/emailid-example.png)

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion_tw). -->

在最適化表單中加入電子郵件輸入元件有幾個好處，包括：

- **使用者便利性**：電子郵件輸入可清楚表示欄位中預期的資料，讓使用者更容易輸入電子郵件地址。

- **個人化通訊**：透過允許個人化通訊的表單從使用者收集電子郵件地址，例如傳送確認電子郵件或電子報。

- **銷售機會開發**：透過表單收集電子郵件地址，企業可以建立其電子郵件清單，並將其用於銷售機會開發。

- **使用者驗證**：電子郵件地址可做為存取受限制內容或服務的驗證方式。

- **意見回饋集合**：意見回饋表單中的電子郵件輸入可讓企業與使用者溝通，以跟進或釐清其意見回饋。

## 版本和相容性 {#version-and-compatibility}

最適化Forms電子郵件核心元件於2023年2月發行，屬於Cloud Service核心元件2.0.4以及AEM 6.5.16.0 Forms或更新版本的核心元件1.1.12的一部分。 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms或更新版本 |
|---|---|---|
| v1 | 與<br>[版本2.0.4](/help/adaptive-forms/version.md)和更新版本相容 | 與<br>[版本1.1.12](/help/adaptive-forms/version.md)及更新版本相容，但小於2.0.0。 |

如需核心元件版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)檔案。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion_tw). -->

## 技術細節 {#technical-details}

在[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/emailinput/v1/emailinput)上的技術檔案中取得最適化Forms電子郵件輸入核心元件的最新資訊。 如需開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 設定對話方塊 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的電子郵件輸入體驗。 您也可以輕鬆定義電子郵件輸入選項，以提供順暢的使用者體驗。

### 基本標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/email_basictab.png)

- **名稱** — 此名稱可唯一識別規則編輯器中的元件。名稱字串中不允許特殊字元和空格。

- **標題** — 您可以使用其Title輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。 如果您未新增標題，則會顯示元件的名稱而非標題文字。
- **允許標題使用RTF格式** — 此功能可讓使用者格式化純文字標題，並整合如粗體、斜體、底線文字、各種字型、字型大小、顏色等功能以及可增強視覺呈現和自訂的其他選項。 它提供更大的彈性和創意控制，讓標題在檔案、網站或應用程式中脫穎而出。\
  選取&#x200B;**允許標題為RTF格式**&#x200B;的核取方塊後，即可看到格式化選項，以設定元件標題的樣式。 若要存取所有可用的格式選項，您可以按一下![全熒幕圖示](/help/adaptive-forms/assets/fullscreen-icon.png)標籤。

  ![RTF支援](/help/adaptive-forms/assets/richtext-support-title.png)

- **隱藏標題** — 選取隱藏元件標題的選項。

- **預留位置文字** — 表單元件中的預留位置文字是指在輸入欄位中顯示的簡短標籤或提示，作為使用者在該欄位中預期輸入何種資訊型別的提示。 當使用者開始在欄位中輸入時，預留位置文字消失，如果欄位留空，則會重新出現。 它向使用者提供視覺提示，但不會作為欄位的永久標籤或值。
- **繫結參考** — 繫結參考是儲存在外部資料來源中並在表單中使用的資料元素的參考。 繫結參考可讓您將資料動態繫結至表單欄位，讓表單可顯示資料來源的最新資料。 例如，繫結參考可用於根據在表單中輸入的客戶ID在表單中顯示客戶名稱和地址。 繫結參考也可用來使用輸入到表單中的資料更新資料來源。 透過這種方式，AEM Forms可讓您建立與外部資料來源互動的表單，提供順暢的使用者體驗來收集和管理資料。
- **標籤為未繫結的表單元素**：選取選項以設定未連結至任何結構描述的表單欄位。 此選項可讓您儲存資料而不更新資料來源。 它也可讓您以自訂方式處理資料，與標準資料庫整合不同。
- **隱藏元件** — 選取選項，以隱藏表單中的元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這將很有用。
- **停用元件** — 選取選項以停用元件。 一般使用者無法啟動或編輯已停用的元件。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。
- **唯讀** — 選取選項，讓元件無法編輯。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

- **預設值** — 此選項可讓您在表單欄位中新增預設值。 如果選取&#x200B;**已停用的元件**&#x200B;或&#x200B;**唯讀元件**，熒幕上會顯示預設值。 如果使用者在表單欄位中未輸入值，此值會在表單提交時提交
- **Autofill屬性**：選項可讓使用者輸入值，該值會根據儲存的資訊自動填入表單欄位中。

### 驗證標籤 {#validation-tab}

![驗證標籤](/help/adaptive-forms/assets/email_validationtab.png)

- **必要** — 如果您想要在最適化表單中顯示元件，請選取此選項。 選取選項後，您必須先輸入值，才能繼續提交表單。選取此選項時，您無法在&#x200B;**基本**&#x200B;索引標籤中選取&#x200B;**隱藏元件**&#x200B;或&#x200B;**停用元件**。

- **錯誤訊息** — 此選項可讓您輸入在勾選「**必要**」核取方塊並將表單欄位保留空白時顯示的訊息。

- **指令碼驗證訊息** — 此選項可讓您輸入指令碼驗證失敗時顯示的訊息。

- **最大字元數** — 此選項可讓您指定欄位中允許的最大字元數。 如果您輸入的字元數大於&#x200B;**最大字元數**&#x200B;中指定的值，畫面會顯示錯誤訊息。 **最大字元錯誤訊息**&#x200B;對話方塊可讓您新增自訂錯誤訊息。

- **字元數上限錯誤訊息** — 如果您輸入的字元數超過&#x200B;**字元數上限**&#x200B;選項中指定的值，則&#x200B;**字元數上限錯誤訊息**&#x200B;對話方塊可讓您新增自訂錯誤訊息。

- **最小字元數** — 此選項可讓您指定欄位中允許的最小字元數。 如果您輸入的字元數小於&#x200B;**字元數下限**&#x200B;中指定的值，畫面會顯示錯誤訊息。 **最少字元錯誤訊息**&#x200B;對話方塊可讓您新增自訂錯誤訊息。

- **最小字元錯誤訊息** — 如果您輸入的字元數少於&#x200B;**最小字元數**&#x200B;選項中指定的值，則&#x200B;**最小字元錯誤訊息**&#x200B;對話方塊可讓您新增自訂錯誤訊息。
<br>

**驗證模式**&#x200B;選項可讓您輸入模式來驗證輸入的電子郵件識別碼。 如果電子郵件ID無法以在&#x200B;**模式**&#x200B;選項中輸入的值驗證，熒幕上會顯示錯誤訊息。

- **模式** — 此選項可讓您為電子郵件輸入允許的驗證模式。 也允許規則運算式。
- **錯誤訊息** — 此選項可讓您在電子郵件ID無法以在&#x200B;**模式**&#x200B;選項中輸入的值驗證時，輸入顯示在熒幕上的訊息

### 說明內容標籤 {#help-content-tab}

![說明內容標籤](/help/adaptive-forms/assets/email_helptab.png)

- **簡短說明** — 簡短說明是簡短文字說明，提供特定表單欄位用途的其他資訊或說明。 它可協助使用者瞭解應在欄位中輸入哪種資料型別，並可提供指引或範例，以協助確保輸入的資訊有效並符合所需條件。 依預設，簡短說明會維持隱藏狀態。 啟用&#x200B;**永遠顯示簡短描述**&#x200B;選項，以在元件下方顯示它。

- **永遠顯示簡短描述** — 啟用選項以在元件下方顯示簡短描述。

- **說明文字** — 說明文字是指提供給使用者的其他資訊或指引，以協助使用者正確填寫表單欄位。 當使用者按一下放置於元件旁的說明圖示(i)時，就會出現此選項。 說明文字提供的資訊比表單欄位的標籤或預留位置文字更詳細，其設計旨在協助使用者瞭解欄位的需求或限制。 它也可以提供建議或範例，讓填寫表單更容易、更準確。

### 協助工具標籤 {#accessibility-tab}

![協助工具標籤](/help/adaptive-forms/assets/email_accessibilitytab.png)

- **熒幕助讀程式文字** — 熒幕助讀程式文字是指視力不佳人士使用的輔助技術（例如熒幕助讀程式）專門用於閱讀的其他文字。 此文字提供表單欄位用途的音訊說明，並可包含欄位標題、說明、名稱和任何相關訊息（自訂文字）的相關資訊。 熒幕助讀程式文字可協助確保表單可供所有使用者存取，包括視覺障礙的使用者，並提供他們對表單欄位及其要求的完整瞭解。

   - **自訂文字**：選取此選項即可使用ARIA協助工具標籤的自訂文字。 選取此選項會顯示「自訂文字」對話方塊。 您可以在「自訂文字」對話方塊中新增相關資訊。
   - **說明**：選取此選項即可使用ARIA協助工具標籤的說明。
   - **標題**：選取此選項即可使用ARIA協助工具標籤的標題。
   - **名稱**：選取此選項即可使用ARIA協助工具標籤的名稱。
   - **無**：如果您不想新增ARIA協助工具標籤，請選取此選項。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可用來定義和管理電子郵件輸入元件的CSS樣式。

### 樣式索引標籤 {#styles-tab}

索引標籤可用來定義和管理元件的CSS樣式。 最適化Forms電子郵件輸入核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

![樣式標籤](/help/adaptive-forms/assets/datepicker_styletab.png)

- **預設CSS類別**：您可以為最適化Forms電子郵件輸入核心元件提供預設CSS類別。

- **允許的樣式**：您可以提供名稱以及代表樣式的CSS類別來定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight： bold」。 您可以在最適化Forms編輯器中將這些樣式使用或套用至最適化表單。 若要套用樣式，請在最適化Forms編輯器中，選取您要套用樣式的元件，導覽至屬性對話方塊，然後從&#x200B;**樣式**&#x200B;下拉式清單中選取所需的樣式。 如果您需要更新或修改樣式，只要返回「設計」對話方塊，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 自訂屬性

![自訂屬性對話方塊](/help/adaptive-forms/assets/datepicker_customproperties.png)

自訂屬性可讓您使用表單範本，將自訂屬性（索引鍵/值組）與最適化表單核心元件建立關聯。 自訂屬性會反映在元件Headless轉譯的properties區段中。 它可讓您建立根據自訂屬性值調整的動態表單行為。 例如，開發人員可以為行動、桌上型電腦或Web平台設計各種無頭Forms元件的轉譯，大幅提升各種裝置的使用者體驗。

- **群組名稱**：您可以提供一個名稱來識別自訂屬性群組。 您可以新增、刪除或重新排列多個自訂屬性群組。 新增自訂屬性群組後，您可以看到下列選項：

   - **索引鍵 — 值配對**：您可以按一下每個自訂屬性群組的&#x200B;**新增**&#x200B;按鈕，以新增多個自訂屬性名稱和自訂屬性值。

   - **刪除**：點選或按一下以刪除自訂屬性名稱和自訂屬性值。

   - **重新排列**：點選或按一下並拖曳以重新排列自訂屬性名稱和自訂屬性值。

### 格式標籤 {#formats-tab}

格式索引標籤可讓您指定預設和自訂日期格式。

![Formattab](/help/adaptive-forms/assets/emailinput_formattab.png)

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=zh-Hant)

-->

## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}
