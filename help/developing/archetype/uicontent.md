---
title: AEM Project Archetype的ui.content模組
description: AEM Project Archetype的ui.content模組
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 0%

---


# AEM Project Archetype {#uicontent-module}的ui.content模組

ui.content maven模組(`<src-directory>/<project>/ui.content`)包含`/content`和`/conf`下方的基準內容和配置。 ui.content會編譯為AEM套件，就像ui.apps。 主要差異在於，儲存在ui.content中的節點可直接在AEM例項上修改。 這包括頁面、DAM資產和可編輯的範本。 ui.content模組可用來儲存簡潔例項的範例內容，和／或建立一些要在來源控制項中管理的基準組態。

## filter.xml {#filter}

ui.content模組的`filter.xml`檔案位於`<src>/<project>/ui.content/src/main/content/META-INF/vault/filter.xml`，並包含將隨ui.content套件一起包含和安裝的路徑。 請注意，`mode="merge"`屬性已新增至路徑。 如此可確保以程式碼部署所部署的組態不會自動覆寫已在AEM例項上編寫的內容或組態。

## ui.content/pom.xml

ui.content模組與ui.apps模組一樣，使用FileVault Package外掛程式。 但ui.content pom(`<src>/<project>/ui.content/pom.xml`)包含名為`acHandling`的額外配置屬性，設為`merge_preserve`。 其中包含此項是因為ui.content模組包含屬於權限的存取控制清單(ACL)，這些權限決定哪些人可以編輯範本。 為了將這些ACL導入AEM，需要`acHandling`屬性。
