---
title: 電子郵件容器元件
description: 電子郵件容器元件可讓您為電子郵件內容中的多個其他元件建立容器。
role: Architect, Developer, Admin, User
exl-id: 3b271e95-0093-4cb1-bb83-8446ba12a821
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 1%

---


# 電子郵件容器元件 {#email-container-component}

電子郵件容器元件可讓您為電子郵件內容中的多個其他元件建立容器。

## 使用狀況 {#usage}

「電子郵件容器」元件可為電子郵件內容中的多個其他元件建立容器，並可用於將其他元件分組和應用通用樣式或佈局。

* 可在 [配置對話框。](#configure-dialog)
* 將電子郵件容器元件新增至頁面時，其預設值可在 [設計對話方塊。](#design-dialog)

將「電子郵件容器」元件新增至頁面後，內容作者就可以拖放其他元件至頁面中。

## 版本與相容性 {#version-and-compatibility}

電子郵件容器元件的目前版本為v1，此版本於2022年10月隨電子郵件核心元件X版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | 相容 |

如需電子郵件核心元件版本和版本的詳細資訊，請參閱本檔案 [電子郵件核心元件版本。](/help/email/versions.md)

## 範例元件輸出 {#sample-component-output}

若要體驗電子郵件容器元件，並查看其設定選項、HTML和JSON輸出的範例，請造訪 [元件庫。](https://adobe.com/go/aem_cmp_library_email_container)

## 技術詳細資訊 {#technical-details}

容器元件的最新技術檔案 [可在GitHub上找到。](https://adobe.com/go/aem_cmp_tech_email_container_v1)

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案。](/help/developing/overview.md)

## 配置對話框 {#configure-dialog}

「設定」對話方塊可讓內容作者定義容器項目及其行為和顯示在內容中的方式。

![電子郵件容器元件的編輯對話方塊](/help/email/assets/email-container-configure.png)

* **版面**  — 此選項定義電子郵件容器元件的行為或配置行為。
   * **全寬**
   * **半|半**
   * **三分之一|三分之二**
   * **三分之二|三分之一**
   * **第三|第三|第三**
* **背景顏色**  — 可定義為自由格式RGB值，或使用檢色器 [視設定而定](#container-settings-tab)
* **背景影像**  — 定義容器的背景影像， [視設定而定](#container-settings-tab)
* **ID**  — 此選項可控制HTML中元件的唯一標識符。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查產生的內容來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會對CSS造成影響。

### 樣式標籤 {#styles-tab-edit}

電子郵件容器元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉式清單選取您要套用至元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須針對此元件在 [設計對話](#design-dialog) 讓索引標籤可用。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義使用電子郵件容器元件的內容作者可用的選項。

### 「允許的元件」頁簽 {#allowed-components-tab}

此 **允許的元件** 索引標籤可用來定義哪些元件可由內容作者新增為電子郵件容器元件的項目。

此 **允許的元件** 頁簽函式與相同名稱的頁簽函式 [在模板編輯器中定義佈局容器的策略和屬性。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 預設元件頁簽 {#default-components-tab}

此 **預設元件** 索引標籤用來定義將特定資產類型拖放到容器上時，要將哪個元件新增至元件，類似於 [如何在頁面範本中定義預設元件。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 容器設定標籤 {#container-settings-tab}

此 **容器設定** 索引標籤會定義作者是否可定義背景影像或顏色。

![電子郵件容器元件設計對話方塊的「容器設定」標籤](/help/email/assets/email-container-design-container-settings.png)

* **背景影像**
   * **啟用背景影像**  — 選取此選項，讓內容作者可定義容器的背景影像。
* **背景色彩**
   * **啟用背景顏色**  — 選取此選項，讓內容作者可定義容器的背景顏色。
   * **僅色票**  — 選取此選項，僅允許內容作者從預先定義的容器背景顏色色票中選取。
      * 僅適用於 **啟用背景顏色** 已選取
* **允許的色票**  — 定義內容作者可從中選取容器背景顏色的預先定義顏色
   * 使用 **新增** 按鈕添加預定義的色板。 新增後，會將項目新增至清單，其中包含下列欄：
   * **值**  — 透過RGB值手動定義顏色
      * 點選或按一下檢色器，借由調整個別RGB值或定義十六進位值，更輕鬆地選取顏色。
   * **刪除**  — 點選或按一下以刪除色票。
   * **重新排列**  — 點選或按一下並拖曳以重新排序色票。

### 樣式標籤 {#styles-tab}

電子郵件容器元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)
