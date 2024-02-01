---
title: 核心元件的回應式設計
description: 瞭解核心元件的回應式設計，以及它如何可能影響您的專案。
role: Architect, Developer, Admin, User
source-git-commit: d39fe0084522f67664203a026340b23d325c1883
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 0%

---


# 核心元件的回應式設計 {#responsive-design}

所有核心元件的設計都可充分回應，確保裝置間的順暢體驗。 請務必注意，有些進階元件，例如 [輪播，](/help/components/carousel.md) [標籤，](/help/components/tabs.md) 和 [摺疊式功能表元件、](/help/components/accordion.md) 實施專案的內容中可能需要特別考量，以在所有情況下維持回應速度。

由於這些元件可展現回應式行為的各種方式，以及Adobe承諾將核心元件保持現成可用的輕量版，因此實施詳細回應式層面的責任會刻意留給專案。

例如，在窄熒幕上，索引標籤元件可以透過將寬索引標籤破壞為新行、允許垂直捲動、將索引標籤轉換為下拉清單或採用摺疊式功能表樣式來調整。 由於實作所有這些行為可能會對效能造成潛在影響， [clientlibs](/help/developing/including-clientlibs.md#provided) 旨在作為實作人員的起點，而非完整解決方案。
