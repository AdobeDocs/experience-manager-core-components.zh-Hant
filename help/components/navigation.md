---
title: 導覽元件
description: 導覽元件可讓使用者輕鬆導覽全球化網站結構。
role: Architect, Developer, Admin, User
exl-id: 9154f2a3-3d1e-4865-a413-298748fa66d3
source-git-commit: eea159ad494150c3f132166d48f624605eb92e64
workflow-type: tm+mt
source-wordcount: '1469'
ht-degree: 1%

---

# 導覽元件{#navigation-component}

導覽元件可讓使用者輕鬆導覽全球化網站結構。

## 使用狀況 {#usage}

導覽元件會列出一組頁面樹狀結構，讓網站的使用者可輕鬆導覽網站結構。

導覽元件可自動偵測您網站的全球化網站結構，並且[可自動適應本地化頁面。](#localized-site-structure) 此外，它可以使用陰影重新導向頁面來表示 [除主要內](#shadow-structure) 容結構以外的其他結構，以支援任何任意網站結構。

[edit對話方塊](#edit-dialog)可讓內容作者定義導覽根頁面和導覽深度。 [設計對話方塊](#design-dialog)允許範本作者定義導覽根和深度的預設值。

## 本地化網站結構支援 {#localized-site-structure}

網站通常針對不同地區提供多種語言版本。 通常每個本地化頁面都會包含一個包含在頁面範本中的導覽元素。 導覽元件可讓您將其放置在網站所有頁面的範本上一次，然後會根據您的全球化網站結構，自動適應個別本地化頁面。

* 如需導覽元件本地化功能如何運作的範例，請參閱[下方的](#example-localization)一節。
* 如需核心元件本地化功能如何搭配運作的範例，請參閱核心元件頁面[本地化功能頁面](/help/get-started/localization.md)。

### 範例 {#example-localization}

假設您的內容如下所示：

```
/content
+-- wknd
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

對於網站WKND，您可能會想要將導覽元件置於頁面範本中，作為標題的一部分。 一旦加入範本，您就可以將元件的&#x200B;**導覽根**&#x200B;設為`/content/wknd/language-masters/en`，因為這是該網站的主內容開始的位置。 您可能也想要將&#x200B;**導航結構深度**&#x200B;設定為`2`，因為您可能不希望元件顯示整個內容樹，而是顯示前兩個級別，以作為概覽。

使用&#x200B;**導航根**&#x200B;值，導航元件知道在`/content/wknd/language-masters/en`之後，導航開始，它可以通過向下遞歸站點結構的兩個級別來生成導航選項（由&#x200B;**導航結構深度**&#x200B;值定義）。

無論使用者檢視的本地化頁面為何，導覽元件都能透過知道目前頁面的位置，向後工作至根目錄，然後轉送至對應的頁面，來尋找對應的本地化頁面。

因此，如果訪客正在檢視`/content/ch/de/experience/arctic-surfing-in-lofoten`，元件會知道根據`/content/wknd/language-masters/de`產生導覽結構。 同樣地，如果訪客檢視`/content/us/en/experience/arctic-surfing-in-lofoten`，元件會根據`/content/wknd/language-masters/en`產生導覽結構。

## 陰影站點結構支援 {#shadow-structure}

有時候，您必須為與實際網站結構不同的訪客建立導覽功能表。 或許促銷活動應透過重新排列內容清單來反白標示功能表中的特定內容。 使用卷影頁面（它只是重定向到其他內容頁面），導航元件可以生成任何必要的任意導航結構。

若要這麼做，您必須：

1. 將卷影頁面建立為代表您所需網站結構的空白頁面。 這通常稱為陰影站點結構。
1. 在這些頁面的頁面屬性中設定&#x200B;**重新導向**&#x200B;值，以指向實際的內容頁面。
1. 在卷影頁的頁屬性中設定&#x200B;**在導航中隱藏**&#x200B;選項。
1. 設定導航元件的&#x200B;**導航根**&#x200B;值以指向新卷影站點結構的根。

然後，導航元件將根據陰影站點結構來呈現菜單。 元件呈現的連結指向實際內容頁面，而陰影頁面本身重定向到而非陰影頁面。 此外，元件還會顯示實際頁面的名稱，並正確加亮活動頁面，即使導航是基於陰影頁面。 導覽元件可有效讓訪客完全透明的影子頁面。

>[!NOTE]
>卷影頁面可讓您的導覽選項更加彈性，但請記住，此結構的維護是完全手動進行的。 如果您重新排列實際的網站內容或添加/刪除內容，則需要手動更新卷影結構。

>[!NOTE]
>呈現陰影站點結構時，導航邏輯只遞歸陰影頁。 此邏輯不會遞回重新導向目的地的結構。

## 導覽中的重新導向 {#redirects}

當頁面具有重定向目標時(無論它指向的是外部URL還是指向另一個AEM頁面)，則導航元件將包含指向該指向重定向目標的URL的直接連結。

### 範例 {#redirect-example}

* 建立重新導向至頁面B的頁面A。
* 建立重新導向至`https://aemcomponents.dev`的頁面C
* 在頁面D上，插入或導覽元件，此元件包含頁面A和C
* 接著，產生的個別連結會直接指向頁面B和`https://aemcomponents.dev`


## 版本與相容性 {#version-and-compatibility}

導覽元件的目前版本為v1，此版本於2018年1月隨核心元件2.0.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗導覽元件，並查看其設定選項以及HTML和JSON輸出的範例，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_navigation)。

## 技術詳細資訊 {#technical-details}

如需導覽元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_navigation_v1)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

>[!NOTE]
>
>自核心元件2.1.0版起，導覽元件支援[schema.org microdata](https://schema.org)。

## 編輯對話方塊 {#edit-dialog}

在編輯對話方塊中，內容作者可定義導覽的根頁面和導覽結構的深度。

### 屬性標籤 {#properties-tab}

![導航元件的編輯對話框屬性頁簽](/help/assets/navigation-edit-properties.png)

* **導航根**  — 用於生成導航樹的根頁。
* **排除根層級**  — 導覽中通常不應包含根。此選項可讓您指定要從根目錄上排除多少個層級。 例如：
   * 0 =顯示根級別
   * 1 =排除根層級
   * 2 =排除根，向上增加1個
   * 等。
* **收集所有子頁**  — 收集所有是導航根子代的頁。
* **導覽結構深度**  — 定義元件應相對於導覽根在導覽樹狀結構下顯示的層級數(僅在未選取「收集所 **有子** 頁面」時可用)。
* **停用陰影**  — 如果階層中的頁面是重新導向，則會顯示重新導向頁面的名稱，而非目標名稱。有關詳細資訊，請參閱[卷影站點結構支援](#shadow-structure)。
* **ID**  — 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

### 協助工具標籤 {#accessibility-tab}

![導航元件的編輯對話框輔助工具頁簽](/help/assets/navigation-edit-accessibility.png)

在&#x200B;**協助工具**&#x200B;標籤上，可以為元件的[ARIA協助工具](https://www.w3.org/WAI/standards-guidelines/aria/)標籤設定值。

* **標籤**  — 元件的ARIA標籤屬性值

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者為內容作者呈現的導覽根頁面和導覽深度設定預設值。

### 屬性標籤 {#properties-tab-design}

![導航元件的設計對話框](/help/assets/navigation-design.png)

* **導航根**  — 導航結構的根頁的預設值，該值將用於生成導航樹，並在內容作者將元件添加到頁面時預設。
* **排除根層級**  — 導覽中通常不應包含根。此選項可讓您指定要從根目錄上排除多少個層級的預設值。 例如：
   * 0 =顯示根級別
   * 1 =排除根層級
   * 2 =排除根，向上增加1個
   * 等。
* **收集所有子頁**  — 用於收集所有屬於導航根子體的頁的選項的預設值。
* **導航結構深度**  — 導航結構深度的預設值。
* **停用陰影**  — 新增導覽元件時，如果應停用陰影的預設值

### 樣式標籤 {#styles-tab}

導航元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe用戶端資料層 {#data-layer}

導航元件支援[Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
