---
title: 內容片段清單元件
description: 核心元件內容片段清單元件可顯示內容片段清單。
role: Architect, Developer, Admin, User
exl-id: 0f2295b1-d287-4f72-8ee4-fa98c4850e53
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 5%

---

# 內容片段清單元件{#content-fragment-list-component}

核心元件內容片段清單元件允許顯示[內容片段](https://docs.adobe.com/content/help/zh-Hant/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)的清單。

## 使用狀況 {#usage}

核心元件內容片段清單元件允許在基於內容片段模型的頁面上包含[內容片段](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)的清單。 這對於建立[無頭內容](https://helpx.adobe.com/tw/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js)特別有用，這些內容可以被其他應用程式輕鬆使用。

* 可在[配置對話框](#configure-dialog)中選擇清單及其屬性。
* 樣式可套用至[design對話方塊](#design-dialog)中的元件。

## 版本與相容性 {#version-and-compatibility}

目前的內容片段元件版本為v1，已於2019年5月隨核心元件2.4.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗內容片段清單元件，並查看其設定選項以及HTML和JSON輸出的範例，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_cflist)。

## 技術詳細資訊 {#technical-details}

如需內容片段清單元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_cflist_v1)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

設定對話方塊可讓內容作者定義要包含清單的內容片段以及這些片段的元素。

### 屬性標籤

**屬性**&#x200B;標籤定義清單中包含的內容片段。 這主要是根據選取的內容片段模型，但有其他可用的篩選選項。

![內容片段清單元件的編輯對話框的屬性頁簽](/help/assets/content-fragment-list-properties.png)

* **模型**  — 清單所依據之內容片段模型的路徑。
   * 依預設，定義為&#x200B;**模型路徑**&#x200B;之模型的所有內容片段都會包含在清單中。
* **父路徑**  — 應建立清單的父路徑。
   * 根據所選&#x200B;**模型路徑**&#x200B;的內容片段將篩選為指定&#x200B;**父路徑**&#x200B;上的內容片段。
      * 按一下或點選欄位右側的&#x200B;**開啟選取對話方塊**&#x200B;按鈕，以指定路徑。
* **標籤**  — 清單中只會包含具有指定標籤的內容片段。
   * 按一下或點選欄位右側的&#x200B;**開啟選取對話方塊**&#x200B;按鈕，以指定標籤。
   * 按一下或點選所選標籤旁的X以移除這些標籤。
* **排序依據**  — 內容片段模型的欄位，依此欄位排序清單
   * 只能選取文字欄位（包括數值、日期和時間）。
* **排序順序**  — 依「順序」欄位排序清單 **的方** 式
   * 遞增或遞減
* **項目數上限**  — 要在清單中顯示的項目數上限
   * 沒有值將返回所有項目。
* **ID**  — 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

>[!NOTE]
>核心元件2.7.0版推出了&#x200B;**Order By**、**Sort Order**&#x200B;和&#x200B;**Max Items**&#x200B;選項。

### 元素標籤

依預設，內容片段模型的所有元素都會包含在清單中（除非受&#x200B;**最大項目**&#x200B;欄位限制）。 **Elements**&#x200B;索引標籤可讓您僅指定要包含的特定元素。

![內容片段清單元件的編輯對話方塊的元素索引標籤](/help/assets/content-fragment-list-elements.png)

* **元素**  — 只會顯示指定清單中內容片段的元素。
   * 按一下或點選&#x200B;**Add**&#x200B;按鈕以新增元素。
   * 按一下或點選&#x200B;**Delete**&#x200B;按鈕以移除選取的元素。
   * 拖動&#x200B;**Order**&#x200B;控制代碼以重新排列元素的順序。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義套用至內容片段清單元件的樣式。
