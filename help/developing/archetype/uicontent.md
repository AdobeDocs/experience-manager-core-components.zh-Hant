---
title: 專案原型的ui.contentAEM模組
description: 專案原型的ui.contentAEM模組
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---


# 專案原型的AEMui.content模組{#uicontent-module}

ui.content maven模組(`<src-directory>/<project>/ui.content`)包含`/content`和`/conf`下方的基準內容和配置。 ui.content會編譯為類似ui.AEMapps的套件。 主要區別在於，儲存在ui.content中的節點可直接在例項AEM上修改。 這包括頁面、DAM資產和可編輯的範本。 ui.content模組可用來儲存簡潔例項的範例內容，和／或建立一些要在來源控制項中管理的基準組態。

## filter.xml {#filter}

ui.content模組的`filter.xml`檔案位於`<src>/<project>/ui.content/src/main/content/META-INF/vault/filter.xml`，並包含將隨ui.content套件一起包含和安裝的路徑。 請注意，`mode="merge"`屬性已新增至路徑。 這可確保使用程式碼部署所部署的組態不會自動覆寫直接在執行個體上編寫的內容AEM或組態。

## ui.content/pom.xml

ui.content模組與ui.apps模組一樣，使用FileVault Package外掛程式。 但ui.content pom(`<src>/<project>/ui.content/pom.xml`)包含名為`acHandling`的額外配置屬性，設為`merge_preserve`。 其中包含此項是因為ui.content模組包含屬於權限的存取控制清單(ACL)，這些權限決定哪些人可以編輯範本。 為了使這些ACL導入到AEM`acHandling`屬性中，需要。
