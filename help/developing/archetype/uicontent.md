---
title: AEM專案原型的ui.content模組
description: AEM專案原型的ui.content模組
feature: 核心元件、AEM專案原型
role: Architect, Developer, Administrator
exl-id: af019cd8-c733-4b53-bb57-321dd9451178
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---

# AEM專案原型的ui.content模組{#uicontent-module}

ui.content maven模組(`<src-directory>/<project>/ui.content`)包含基線內容和`/content`和`/conf`下的設定。 ui.content會編譯至AEM套件，就像ui.apps一樣。 主要差異在於，儲存在ui.content中的節點可以直接在AEM例項上修改。 包括頁面、DAM資產和可編輯的範本。 ui.content模組可用來儲存乾淨執行個體的範例內容，和/或建立要在原始碼控制項中管理的一些基線設定。

## filter.xml {#filter}

ui.content模組的`filter.xml`檔案位於`<src>/<project>/ui.content/src/main/content/META-INF/vault/filter.xml`，其中包含將隨ui.content套件一併安裝的路徑。 請注意，`mode="merge"`屬性已新增至路徑。 這可確保透過程式碼部署部署的設定不會自動覆寫直接在AEM執行個體上撰寫的內容或設定。

## ui.content/pom.xml

ui.content模組（如ui.apps模組）使用FileVault包插件。 但ui.content pom(`<src>/<project>/ui.content/pom.xml`)包含稱為`acHandling`的額外設定屬性，並設為`merge_preserve`。 其中包括這項，因為ui.content模組包含屬於權限的存取控制清單(ACL)，這些權限將決定哪些人可以編輯範本。 為了將這些ACL導入AEM，需要`acHandling`屬性。
