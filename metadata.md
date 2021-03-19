---
product: adobe experience manager
solution: Experience Manager Sites
type: 文件
description: Adobe Experience Manager核心元件文檔
git-repo: https://git.corp.adobe.com/AdobeDocs/experience-manager-core-components.zh-Hant
index: y
translation-type: tm+mt
source-git-commit: 290423c39b925ea8cf4077f31a76ecf01167f344
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 6%

---


# 內部使用的中繼資料

GitHub製作系統中的中繼資料是階層式的，並定義了下列不斷提升的先例等級。

1. metadata.md
1. ToC
1. 文章

中繼資料。md檔案中定義的中繼資料會套用至整個回購區，但可在ToC和文章層級覆寫。 任何對中繼資料的覆寫都應盡可能在最低層級進行。

experience-manager-core-components.en repo中的中繼資料是最低要求。

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
* `index: n` （僅適用於舊版元件）

有關中繼資料的其他資訊，請參閱[內部製作指南。](https://docs.adobe.com/help/en/collaborative-doc-instructions/collaboration-guide/markdown/metadata.html#solution-metadata)
