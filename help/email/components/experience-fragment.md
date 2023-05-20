---
title: 電子郵件體驗片段元件
description: 電子郵件體驗片段元件允許內容作者在其內容中放置體驗片段變體，同時支援本地化的內容結構。
role: Architect, Developer, Admin, User
exl-id: 861c1fd1-6d6d-426c-a338-a558326fe16e
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 1%

---


# 電子郵件體驗片段元件 {#email-experience-fragment-component}

電子郵件體驗片段元件允許內容作者在其內容中放置體驗片段變體，同時支援本地化的內容結構。

## 使用狀況 {#usage}

電子郵件體驗片段元件允許內容作者從現有體驗片段變體中進行選擇，並將其放在內容中。 「體驗片段」是一組內容，包括內容和佈局，可跨渠道重複使用。

* 元件的屬性可在 [配置對話框](#configure-dialog)。
* 在將元件添加到內容時，可以在 [設計對話框](#design-dialog)。

電子郵件體驗片段元件支援本地化的站點結構。

## 版本和相容性 {#version-and-compatibility}

電子郵件體驗片段元件的當前版本為v1，該版本於2022年10月隨電子郵件核心元件X版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | - |

有關電子郵件核心元件版本和版本的詳細資訊，請參閱文檔 [電子郵件核心元件版本。](/help/email/versions.md)

## 本地化站點結構支援 {#localized-site-structure}

電子郵件體驗片段元件適應於本地化的內容結構，並基於內容的本地化來呈現適當的體驗片段。 為此，「體驗」部分必須滿足以下條件。

* 電子郵件體驗片段元件已添加到 [的子菜單。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/templates.html)
* 該模板用於建立新內容頁面，該頁面是下面本地化結構的一部分 `/content/<site>`。
* 內容頁上引用的經驗片段是下面本地化的經驗片段結構的一部分 `/content/experience-fragments` 遵循與下面的站點相同的模式 `/content/<site>` 包括使用相同的元件名稱。

在本例中，具有相同本地化的片段([語言、藍圖或即時拷貝](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/reusing-content/msm-and-translation.html))，作為模板的一部分呈現當前頁面。

此行為僅限於添加到模板的電子郵件體驗片段元件。 添加到單個內容頁面的體驗片段元件將呈現元件中配置的確切體驗片段格式副本。

* 有關體驗片段元件的本地化功能如何工作的示例，請參見 [下面一節](#example)。
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

在本例中，如果「電子郵件體驗」片段元件 `/content/experience-fragments/wknd/us/en/footerTextXf` 位於模板上，基於該模板建立的本地化頁面將自動呈現與本地化內容頁面對應的本地化體驗片段。

所以，如果您導航到 `/content/wknd/ch/de` 使用相同模板， `/content/experience-fragments/wknd/ch/de/footerTextXf` 將呈現 `/content/experience-fragments/wknd/us/en/footerTextXf`。

### 回退 {#fallback}

電子郵件體驗片段元件將嘗試按以下順序查找相應的本地化元件。

1. 首先，它試圖找到語言根。
1. 如果找不到，它會嘗試找到一個藍圖。
1. 如果找不到，它會嘗試查找即時副本。
1. 如果找不到，則預設為元件中配置的「體驗片段」。

## 技術詳細資訊 {#technical-details}

有關體驗片段元件的最新技術文檔 [中。](https://adobe.com/go/aem_cmp_email_tech_xf_v1)

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔。](/help/developing/overview.md)

## 配置對話框 {#configure-dialog}

配置對話框允許內容作者選擇應在內容中呈現的體驗片段變體。

![電子郵件體驗片段元件的編輯對話框](/help/email/assets/email-experience-fragment-edit.png)

使用 **開啟選擇對話框** 按鈕以開啟元件選擇器來選擇要添加到內容頁面的體驗片段元件變體。

如果將「電子郵件體驗片段」元件添加到模板中，則如果「體驗片段」已本地化，則它將自動本地化，因此頁面上呈現的內容可能與您明確選擇的元件不同。 [請參閱上面的示例](#example) 的子菜單。

也可以定義 **ID**。 此選項允許控制HTM中元件的唯一標識符。

* 如果留空，則系統會為您自動生成唯一ID，並且可以通過檢查生成的內容來找到它。
* 如果指定了ID，則作者有責任確保其唯一。
* 更改ID可能會影響CSS。

### 樣式頁籤 {#styles-tab-edit}

電子郵件體驗片段元件支AEM持 [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉框選擇要應用於元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須在 [設計對話框](#design-dialog) 以便該頁籤可用。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義內容作者可以使用的選項，內容作者使用電子郵件體驗片段元件以及放置電子郵件體驗片段元件時設定的預設值。

### 樣式頁籤 {#styles-tab}

電子郵件體驗片段元件支AEM持 [樣式系統。](/help/get-started/authoring.md#component-styling)
