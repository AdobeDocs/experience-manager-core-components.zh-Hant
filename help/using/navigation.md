---
title: 導覽元件
seo-title: 導覽元件
description: 'null'
seo-description: 導覽元件可讓使用者輕鬆導覽全球化的網站結構。
uuid: 616c03fb-39b3-402a-b990-f56 c87 bc6 df
content-type: 引用
topic-tags: 製作
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: da8d67d7-b65 e-4041-bc0 e-e998 f24 a68 f9
disttype: dist5
gnavtheme: 淺色
groupsectionnavitems: 否
hidemerchandisingbar: 繼承
hidepromocomponent: 繼承
modalsize: 426x240
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 48d23edbcdf4c4ed70d590cf6c6e4ac1db14f852

---


# 導覽元件{#navigation-component}

導覽元件可讓使用者輕鬆導覽全球化的網站結構。

## 使用狀況 {#usage}

導覽元件清單列出頁面的樹狀結構，讓網站的使用者輕鬆導覽網站結構。

導覽元件可自動偵測您網站的全球化網站結構， [並自動調整為本地化頁面。](#localized-site-strucutre) 此外，它還可支援 [任何任意的網站結構，以代表其他](#shadow-structure) 結構，而非主要內容結構的其他結構。

[編輯對話方塊](#edit-dialog) 可讓內容作者定義導覽根頁面以及導覽深度。[設計對話方塊](#design-dialog) 可讓範本作者定義導覽根目錄和深度的預設值。

## 本地化的網站結構支援 {#localized-site-structure}

網站通常以多種語言提供給不同地區。通常每個本地化頁面都會包含一個包含在頁面範本中的巢狀元素。「Navigation Component」(導覽元件)可讓您將它放置在網站所有頁面的範本上一次，然後根據您的全球化網站結構自動針對個別本地化頁面進行調整。

### 例如 {#example-localization}

假設您的內容看起來像這樣：

```
/content
+-- we-retail
   +-- language-masters
      +-- de
         \-- experience
            \-- arctic-surfing-in-lofoten
      +-- en
         \-- experience
            \-- arctic-surfing-in-lofoten
      +-- es
      +-- fr
      \-- it
   +-- us
      +-- en
         \-- experience
            \-- arctic-surfing-in-lofoten
      \-- es
   \-- ch
      +-- de
         \-- experience
            \-- arctic-surfing-in-lofoten
      +-- fr
      \-- it
+-- wknd-events
\-- wknd-shop
```

對於我們的零售網站，您可能想要將導覽元件置於頁首，做為標題的一部分。在範本的一部分中，您可以將元件 **的導覽根目錄** 設定為 `/content/we-retail/language-masters/en` 該元件的導覽根目錄，因為該網站的主內容已開始。您可能也希望設定 **「導覽結構深度」** ， `2` 因為您可能不希望元件顯示整個內容樹狀結構，而是前兩個層級，以便做為概述。

透過 **導覽根目錄** 值，Navigation `/content/we-retail/language-masters/en` Component會知道導覽開始後，它會循環播放網站的結構兩級(由 **「導覽結構深度** 」值定義)，以產生導覽選項。

不論使用者檢視何種本地化頁面，導覽元件都可透過知道目前頁面的位置，以回溯至根目錄，然後轉送至對應的頁面，以找到對應的本地化頁面。

因此，如果訪客正在檢視 `/content/ch/de/experience/arctic-surfing-in-lofoten`，則元件會知道以產生導覽結構 `/content/we-retail/language-masters/de`。同樣地，如果訪客正在檢視 `/content/us/en/experience/arctic-surfing-in-lofoten`，則元件會知道以產生導覽結構 `/content/we-retail/language-masters/en`。

## 陰影網站結構支援 {#shadow-structure}

有時需要為訪客建立不同於實際網站結構的導覽功能表。促銷活動可能會透過重新排列內容清單，強調功能表中的特定內容。使用可直接重新導向至其他內容頁面的陰影頁面，導覽元件可產生任何必要的導覽結構。

若要這麼做，您必須：

1. 將陰影頁面建立為代表您所需網站結構的平滑頁面。這通常稱為陰影網站結構。
1. 在這些頁面的頁面屬性中設定 **重新導向** 值，指向實際內容頁面。
1. 在陰影頁面的頁面屬性中設定 **「在導覽** 中隱藏」選項。
1. 設定導覽元件 **的導覽根** 值，指向新陰影網站結構的根目錄。

然後，導覽元件就會根據陰影網站結構來演算功能表。由元件轉換的連結是指實際內容頁面，這些頁面會重新導向至陰影頁面，而非陰影頁面本身。此外，元件會顯示實際頁面的名稱，並正確顯示作用中頁面，即使導覽是以陰影頁面為基礎。導覽元件有效地讓訪客對陰影頁面完全透明。

>[!NOTE]
>陰影頁面讓您的導覽選項更有彈性，但請記住，此結構的基礎是完全手動。如果您重新排列實際的網站內容或新增/移除內容，您必須視需要手動更新陰影結構。

>[!NOTE]
>轉換陰影網站結構時，導覽邏輯只會循環使用陰影頁面。邏輯不會重復重新導向目的地的結構。

## 版本與相容性 {#version-and-compatibility}

目前版本的Navigation Component is v1，它是從2018年月發行的版本2.0.0推出，並在本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|--- |--- |--- |--- |
| v1 | 相容相容性 | 相容相容性 | 相容相容性 |

如需核心元件版本和版本的詳細資訊，請參閱文件 [核心元件版本](versions.md)。

## 元件輸出範例 {#sample-component-output}

若要體驗導覽元件，以及檢視其組態選項以及HTML和JSON輸出的範例，請造訪 [元件庫](http://opensource.adobe.com/aem-core-wcm-components/library/navigation.html)。

## 技術細節 {#technical-details}

有關導覽元件 [的最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/navigation/v1/navigation)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。

>[!NOTE]
>
>從核心元件2.1.0版開始，Navigation Component支援 [schema.org微型資料](https://schema.org)。

## Edit Dialog {#edit-dialog}

在編輯對話方塊中，內容作者可定義導覽的根頁面和導覽結構深度。

### 屬性索引標籤 {#properties-tab}

![](assets/screen-shot-2019-08-29-12.23.45.png)

* **導覽根目錄**：將用來產生導覽樹狀結構的根頁面。
* **排除導覽根目錄**&#x200B;排除產生的樹狀結構中的導覽根目錄，僅包含其子系。
* **收集所有子頁面**&#x200B;收集所有屬於導覽根目錄子項的頁面。
* **導覽結構深度**&#x200B;定義元件相對於導覽根目錄應該顯示的導覽樹狀結構層級層級(僅當 **未選取所有子系頁面** 時可用)。

### 協助工具標籤 {#accessibility-tab}

![](assets/screen-shot-2019-08-29-12.23.53.png)

在 **「協助工具** 」索引標籤上，可為元件設定 [AIA協助工具](https://www.w3.org/WAI/standards-guidelines/aria/) 標籤的值。

* **標籤** -元件的AIA標籤屬性值

## 設計對話方塊 {#design-dialog}

此設計對話方塊可讓範本作者為內容作者設定導覽根頁面和導覽深度的預設值。

### 屬性索引標籤 {#properties-tab-design}

![](assets/screen_shot_2018-04-03at112357.png)

* **導覽根目錄：**&#x200B;導覽結構的根頁面預設值，此值將用於產生導覽樹狀結構，並在內容作者新增元件至頁面時預設。
* **排除導覽根目錄**：選項的預設值，可排除產生之樹狀結構中的導覽根目錄。
* **收集所有子頁面**&#x200B;的選項預設值可收集導覽根目錄中所有屬於子項的頁面。
* **導覽結構深度**&#x200B;導覽結構深度的預設值。

### 樣式標籤 {#styles-tab}

導覽元件支援AEM [樣式系統](authoring.md#component-styling)。
