---
title: 內容片段清單元件(v1)
description: 核心元件內容片段清單元件可讓您顯示內容片段的清單。
role: Architect, Developer, Admin, User
exl-id: 37d6632d-360d-4081-8279-8efbb369a82e
source-git-commit: e291d4c1bfd37292d68c236178f9681c4e5ee741
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 0%

---

# 內容片段清單元件(v1) {#content-fragment-list-component}

核心元件內容片段清單元件允許顯示[內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)的清單。

## 使用情況 {#usage}

核心元件內容片段清單元件允許在根據內容片段模型的頁面上包含[內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)的清單。 這對於建立可由其他應用程式輕鬆使用的[Headless內容](https://helpx.adobe.com/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js)特別有用。

* 清單及其屬性可以在[設定對話方塊](#configure-dialog)中選取。
* 樣式可套用至[設計對話方塊](#design-dialog)中的元件。

## 版本和相容性 {#version-and-compatibility}

本檔案說明內容片段元件v1，此版本隨2019年5月的核心元件發行版本2.4.0的發佈引入。

>[!CAUTION]
>
>本檔案說明內容片段清單元件v1。
>
>如需目前版本的內容片段清單元件的詳細資訊，請參閱[內容片段清單元件](/help/components/content-fragment-list.md)檔案。

## 範例元件輸出 {#sample-component-output}

若要體驗內容片段清單元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫](https://adobe.com/go/aem_cmp_library_cflist)。

## 技術細節 {#technical-details}

在GitHub](https://adobe.com/go/aem_cmp_tech_cflist_v1)上可找到有關內容片段清單元件[的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 設定對話方塊 {#configure-dialog}

此設定對話方塊可讓內容作者定義哪些內容片段包含清單以及要包含的這些片段的元素。

### 屬性標籤

**屬性**&#x200B;索引標籤定義清單中包含的內容片段。 這主要是根據所選的內容片段模式，但還有其他可用的篩選選項。

內容片段清單元件](/help/assets/content-fragment-list-properties.png)的編輯對話方塊的![屬性標籤

* **Model** — 清單所根據的內容片段模式的路徑。
   * 依預設，定義為&#x200B;**模型路徑**&#x200B;的所有模型內容片段都會包含在清單中。
* **父路徑** — 應從中建置清單的父路徑。
   * 根據所選&#x200B;**模型路徑**&#x200B;的內容片段將篩選為指定&#x200B;**父路徑**&#x200B;上的內容片段。
      * 按一下或點選欄位右側的&#x200B;**開啟選取範圍對話方塊**&#x200B;按鈕，以指定路徑。
* **標籤** — 清單中只會包含具有指定標籤的內容片段。
   * 按一下或點選欄位右側的&#x200B;**開啟選取範圍對話方塊**&#x200B;按鈕，以指定標籤。
   * 按一下或點選所選標籤旁的X可將其移除。
* **排序依據** — 清單排序依據的內容片段模型的欄位
   * 只能選取文字欄位（包括數值、日期和時間）。
* **排序順序** — 清單如何依&#x200B;**排序依據**&#x200B;欄位排序
   * 遞增或遞減
* **最大專案數** — 清單中顯示的最大專案數
   * 沒有值會傳回所有專案。
* **ID** — 此選項可控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

>[!NOTE]
>核心元件2.7.0版已匯入&#x200B;**排序依據**、**排序順序**&#x200B;以及&#x200B;**最大專案**&#x200B;選項。

### 元素標籤

依預設，內容片段模式的所有元素將會包含在清單中（除非受&#x200B;**最大專案**&#x200B;欄位限制）。 **Elements**&#x200B;索引標籤允許您僅指定要包含的特定元素。

內容片段清單元件](/help/assets/content-fragment-list-elements.png)的編輯對話方塊的![元素標籤

* **元素** — 只會顯示指定清單中內容片段的元素。
   * 按一下或點選「**新增**」按鈕以新增元素。
   * 按一下或點選「**刪除**」按鈕以移除選取的元素。
   * 拖曳&#x200B;**Order**&#x200B;控制代碼以重新排列元素。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義套用至內容片段清單元件的樣式。
