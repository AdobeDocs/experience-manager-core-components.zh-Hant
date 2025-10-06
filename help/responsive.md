---
title: 核心元件的回應式設計
description: 進一步了解核心元件的回應式設計，以及其將如何影響您的專案。
role: Architect, Developer, Admin, User
exl-id: c0eff174-6803-4b44-aeb1-eae3bc8a36ea
source-git-commit: 5f49fb45869d1721e16a787a2c6ff927b6ad49fe
workflow-type: ht
source-wordcount: '174'
ht-degree: 100%

---

# 核心元件的回應式設計 {#responsive-design}

所有「核心元件」都設計為可充分回應，以確保裝置間的順暢體驗。請務必注意，某些進階元件 (例如[輪播、](/help/components/carousel.md)[索引標籤](/help/components/tabs.md)和[摺疊面板](/help/components/accordion.md)) 在實施專案的內容中可能需要特別考量，以保持在所有條件下的回應能力。

由於各元件可透過多種方式展現回應式行為，而 Adobe 致力於讓核心元件保持立即可用的輕量特性，刻意將具體的回應式層面實施責任交由專案團隊處理。

例如，在較窄的畫面上，索引標籤元件可能會進行自動調整，將寬索引標籤換行、允許垂直捲動、將索引標籤轉換為下拉式清單或採用摺疊面板樣式。由於實施所有這些行為可能會對效能造成潛在影響，因此 [clientlib](/help/developing/including-clientlibs.md#provided) 旨在作為實施者的起點，而不是詳盡的解決方案。
