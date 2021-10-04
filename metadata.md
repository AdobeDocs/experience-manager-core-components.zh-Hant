---
product: adobe experience manager
solution: Experience Manager, Experience Manager Sites
type: Documentation
description: Adobe Experience Manager核心元件檔案
git-repo: https://git.corp.adobe.com/AdobeDocs/experience-manager-core-components.zh-Hant
index: y
source-git-commit: 2fbf593dee19f22b87a0f7e98d8a1f0c9252e7e7
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 內部使用的中繼資料

GitHub製作系統中的中繼資料是階層式的，其定義為下列不斷提升的先例層級。

1. metadata.md
1. ToC
1. 文章

中繼資料.md檔案中定義的中繼資料會套用至整個存放庫，但可以在ToC和文章層級覆寫。 任何中繼資料的覆寫都應盡可能在最低層級完成。

experience-manager-core-components.en repo中的中繼資料是最低需求。

metadata.md

* `product`
* `git-repo`
* `index: y`
* `solution-title`
* `solution-hub-url`
* `getting-started-title`
* `getting-started-url`
* `tutorials-title`
* `tutorials-url`

ToCs

* `sub-product`
* `user-guide-title`

文章

* `title`
* `description`
* `index: n` （僅限舊版元件）

有關元資料的其他資訊，請參見[內部創作指南。](https://experienceleague.adobe.com/docs/authoring-guide-exl/using/authoring/features/metadata.html#solution)
