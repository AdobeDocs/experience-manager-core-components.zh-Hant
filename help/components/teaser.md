---
title: Teaser元件
description: 預告元件可顯示影像、標題、RTF，以及可選地連結至其他內容。
role: Architect, Developer, Admin, User
exl-id: ec75e168-6f3b-4dff-8df6-06ca7dc18688
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 2%

---

# Teaser元件 {#teaser-component}

核心元件預告元件可顯示影像、標題、RTF，以及視需要連結至其他內容。

## 使用狀況 {#usage}

預告元件可讓內容作者使用影像、標題或RTF來輕鬆建立預告以進一步內容，並連結至更多內容或其他動作。

範本作者可使用[design對話方塊](#design-dialog)來定義建立動作呼叫和新增連結的選項是否可用，以及停用各種顯示選項。 內容作者可以使用[設定對話方塊](#configure-dialog)來設定影像、定義CTA、設定標題和說明，以及設定個別預告的連結。 可以訪問[影像元件](image.md)的[編輯對話框](image.md#edit-dialog)以修改預告影像。

## 版本與相容性 {#version-and-compatibility}

目前的預告元件版本為v1，此版本於2018年7月隨核心元件2.1.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|---|
| v1 | 相容 | 相容 | 相容 |

## 範例元件輸出 {#sample-component-output}

若要體驗預告元件，並查看其設定選項以及HTML和JSON輸出的範例，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_teaser)。

### 技術詳細資訊 {#technical-details}

您可在GitHub](https://adobe.com/go/aem_cmp_tech_teaser_v1)上找到有關Teaser元件[的最新技術檔案。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

內容作者可使用設定對話方塊來定義個別預告的屬性。 還有一個[edit對話框](#edit-dialog)，用於修改預告影像（如果已選）。

### 影像 {#image}

![Teaser元件的編輯對話方塊影像索引標籤](/help/assets/teaser-edit-image.png)

* **影像資產**
   * 從[資產瀏覽器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html)拖放資產，或點選&#x200B;**browse**&#x200B;選項，從本機檔案系統上傳。
   * 點選或按一下&#x200B;**清除**&#x200B;以取消選取目前選取的影像。
   * 點選或按一下「**編輯** 」，在資產編輯器中[管理資產](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html)的轉譯。

>[!NOTE]
>
>[Dynamic Media](image.md#dynamic-media) 功能目前無法在Teaser元件中使用。

### 文字 {#text}

![Teaser元件的編輯對話框文本頁簽](/help/assets/teaser-edit-text.png)

* **Pretitle**  — 預先標題會顯示在預告標題之前。
* **Title**  — 定義標題以顯示為預告的標題。
   * **從連結頁面取得標題**  — 勾選此選項後，標題會填入連結頁面的標題。
* **說明**  — 定義要顯示為預告子標題的說明。
   * **從連結頁面取得說明**  — 勾選此選項後，說明會填入連結頁面的說明。
* **ID**  — 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

### 連結與動作 {#links-actions}

![Teaser元件的編輯對話方塊連結索引標籤](/help/assets/teaser-edit-link.png)

* **連結**  — 套用至預告的連結。使用路徑瀏覽器來選取連結目標。
* **啟用呼叫至動作**  — 若勾選此選項，會啟用呼叫至動作的定義。清單中的第一個動作呼叫連結會作為其他宣傳預告元素的連結。

## 編輯對話方塊 {#edit-dialog}

預告元件將影像呈現委派給[影像元件](image.md)。 因此，內容作者可以使用影像元件的[編輯對話方塊](image.md#edit-dialog)來操控預告影像。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義內容作者使用此元件時具有的宣傳預告選項。

### Teaser標籤 {#teaser-tab}

![預告元件的設計對話框](/help/assets/teaser-design.png)

* **呼叫動作**
   * **停用呼叫至動作**  — 隱藏內 **容作者的呼叫** 至動作選項
* **元素**
   * **隱藏首頁**  — 隱藏內容作 **** 者的「首頁」選項
   * **隱藏標題**  — 隱藏內容作 **** 者的「標題」選項
      * 選擇&#x200B;**標題類型**&#x200B;後隱藏
   * **隱藏說明**  — 隱藏內容作 **** 者的「說明」選項
* **Title Type**  — 定義預告標題所要使用的H標籤。
* **連結**
   * **不連結影像**  — 選取時，預告影像不會連結
   * **不連結標題**  — 選取時，預告標題不會連結
* **影像委派**  — 資訊性顯示，指出Teaser委派影像處理的元件。

### 樣式標籤 {#styles-tab}

Teaser元件支援AEM [Style System](/help/get-started/authoring.md#component-styling)。

## Adobe用戶端資料層 {#data-layer}

Teaser元件支援[Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
