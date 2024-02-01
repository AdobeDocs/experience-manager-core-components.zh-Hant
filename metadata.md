---
product: adobe experience manager
solution: Experience Manager, Experience Manager Sites
type: Documentation
description: Adobe Experience Manager核心元件的檔案
git-repo: https://github.com/AdobeDocs/experience-manager-core-components.zh-Hant
index: y
recommendations: noDisplay
source-git-commit: 55e5ef9271b07d8fffc7b396c890af1637309ff3
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 91%

---


# 內部使用的中繼資料

GitHub 編寫系統中的中繼資料具有階層式架構，而且會定義以下相對於前一項的遞增層級。

1. metadata.md
1. ToC
1. 文章

metadata.md 檔案中所定義的中繼資料會套用到整個存放庫，但可以在 ToC 和文章層級被覆寫。 中繼資料的任何覆寫都應該盡量在最低層級進行。

experience-manager-core-components.en 存放庫中的中繼資料是最低要求。

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
* `index: n` (僅適用於舊版元件)

[內部編寫指南](https://experienceleague.adobe.com/docs/authoring-guide-exl/using/authoring/features/metadata.html?lang=zh-Hant#solution)中可以找到有關中繼資料的其他資訊。
