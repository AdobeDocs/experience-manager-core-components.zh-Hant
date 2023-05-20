---
title: 體驗片段元件(v1)
description: 體驗片段元件允許內容作者將體驗片段變體添加到頁面。
role: Architect, Developer, Admin, User
exl-id: 42230a7b-6feb-4535-baf9-b8fc06978d98
source-git-commit: e291d4c1bfd37292d68c236178f9681c4e5ee741
workflow-type: tm+mt
source-wordcount: '780'
ht-degree: 0%

---

# 體驗片段元件(v1) {#experience-fragment-component}

核心元件體驗片段元件允許內容作者在支援本地化站點結構的同時將體驗片段變體放置在頁面上。

## 使用狀況 {#usage}

核心元件體驗片段元件允許內容作者從現有體驗片段變體中進行選擇，並將其放在內容頁面上。 「體驗片段」元件還支援本地化的站點結構。

* 元件的屬性可在 [配置對話框](#configure-dialog)。
* 在將元件添加到頁面時，可以在 [設計對話框](#design-dialog)。

## 版本和相容性 {#version-and-compatibility}

本文檔介紹了2019年9月在核心元件2.6.0版中引入的經驗片段元件v1。

>[!CAUTION]
>
>本文檔介紹「體驗片段」元件的v1。
>
>有關體驗片段元件當前版本的詳細資訊，請參閱 [體驗片段元件](/help/components/experience-fragment.md) 的子菜單。

## 本地化站點結構支援 {#localized-site-structure}

經驗片段元件適用於局部化的站點結構，並基於頁面的本地化來呈現適當的經驗片段。 為此，經驗片段必須滿足以下條件。

* 「體驗片段」元件將添加到模板。
* 該模板用於建立新內容頁面，該頁面是下面本地化結構的一部分 `/content/<site>`。
* 內容頁面上引用的體驗片段是下面本地化體驗片段結構的一部分 `/content/experience-fragments` 遵循與下面的站點相同的模式 `/content/<site>` 包括使用相同的元件名稱。

在這種情況下，與當前頁面具有相同本地化（語言、藍圖或即時副本）的片段將作為模板的一部分呈現。

此行為僅限於添加到模板的「體驗片段元件」。 添加到單個內容頁面的體驗片段元件將呈現元件中配置的確切體驗片段呈現形式。

* 有關體驗片段元件的本地化功能的示例，請參見 [下面一節](#example)。
* 有關核心元件的本地化功能如何協同工作的示例，請參見 [「核心元件」頁的本地化功能](/help/get-started/localization.md)。

### 範例 {#example}

假設您的內容類似以下內容：

```
/content
+-- experience-fragments
   \-- wknd
      +-- language-masters
      +-- us
         +-- en
            +-- footerTextXf
            \-- headerTextXf
         \-- es
            +-- footerTextXf
            \-- headerTextXf
      \-- ch
         +-- de
            +-- footerTextXf
            \-- headerTextXf
         +-- fr
            +-- footerTextXf
            \-- headerTextXf
         \-- it
            +-- footerTextXf
            \-- headerTextXf
+-- wknd
   +-- language-masters
   +-- us
      +-- en
      \-- es
   +-- ch
      +-- de
      +-- fr
      \-- it
+-- wknd-events
\-- wknd-shop
```

請注意以下結構 `/content/experience-fragments/wknd` 反映了 `/content/wknd`。

在本例中，如果「體驗片段」元件 `/content/experience-fragments/wknd/us/en/footerTextXf` 放置在模板上，基於該模板建立的本地化頁面將自動呈現與本地化內容頁面對應的本地化體驗片段。

所以，如果您導航到 `/content/wknd/ch/de` 使用相同模板， `/content/experience-fragments/wknd/ch/de/footerTextXf` 將呈現 `/content/experience-fragments/wknd/us/en/footerTextXf`。

### 回退 {#fallback}

體驗片段元件將嘗試按以下順序查找相應的本地化元件。

1. 首先，它試圖找到語言根。
1. 如果找不到，它會嘗試找到一個藍圖。
1. 如果找不到，它會嘗試查找即時副本。
1. 如果找不到，則預設為元件中配置的體驗片段。

## 元件輸出示例 {#sample-component-output}

要體驗Experience Fragment元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_xf)。

## 技術詳細資訊 {#technical-details}

有關體驗片段元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_xf_v1)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

通過「配置」對話框，內容作者可以選擇應在頁面上呈現的體驗片段變體。

![體驗片段元件的編輯對話框](/help/assets/experience-fragment-edit.png)

使用 **開啟選擇對話框** 按鈕以開啟元件選擇器，以選擇要添加到內容頁面的體驗片段元件變體。

如果將「體驗片段」元件添加到模板，請注意，如果「體驗片段」已本地化，則它將自動本地化，因此在頁面上呈現的內容可能與您明確選擇的元件不同。 [請參閱上面的示例](#example) 的子菜單。

也可以定義 **ID**。 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。

* 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
* 如果指定了ID，則作者有責任確保其唯一。
* 更改ID可能會影響CSS、JS和資料層跟蹤。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義內容作者可用的選項，內容作者使用「體驗片段元件」以及放置「體驗片段元件」時設定的預設值。

### 樣式頁籤 {#styles-tab}

體驗片段元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。
