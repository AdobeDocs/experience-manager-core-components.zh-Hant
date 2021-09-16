---
product: adobe experience manager
solution: Experience Manager, Experience Manager Sites
type: Documentation
description: Adobe Experience Manager核心元件檔案
git-repo: https://git.corp.adobe.com/AdobeDocs/experience-manager-core-components.zh-Hant
index: y
source-git-commit: 3897e37ed1e24c4a045b7f6cc716b5cabdd7cf9f
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 5%

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

有關元資料的其他資訊，請參見[內部創作指南。](https://docs.adobe.com/help/en/collaborative-doc-instructions/collaboration-guide/markdown/metadata.html#solution-metadata)
