---
title: AEM專案原型的ui.content模組
description: AEM專案原型的ui.content模組
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: af019cd8-c733-4b53-bb57-321dd9451178
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 0%

---

# AEM專案原型的ui.content模組 {#uicontent-module}

ui.content maven模組(`<src-directory>/<project>/ui.content`)包括底下的基準線內容和設定 `/content` 和 `/conf`. ui.content會編譯成AEM套件，很像ui.apps。 主要差異在於儲存在ui.content中的節點可以直接在AEM執行個體上修改。 這包括頁面、DAM資產和可編輯的範本。 ui.content模組可用來儲存乾淨執行個體的範例內容和/或建立一些要在原始檔控制中管理的基準設定。

## filter.xml {#filter}

此 `filter.xml` ui.content模組的檔案位於 `<src>/<project>/ui.content/src/main/content/META-INF/vault/filter.xml` 和包含將隨ui.content套件一起包含和安裝的路徑。 請注意 `mode="merge"` 屬性會新增至路徑。 這可確保使用程式碼部署來部署的設定不會自動覆寫已直接在AEM執行個體上編寫的內容或設定。

## ui.content/pom.xml

ui.content模組與ui.apps模組類似，都使用FileVault封裝外掛程式。 但是ui.content pom (`<src>/<project>/ui.content/pom.xml`)包含名為的額外設定屬性 `acHandling`，設定為 `merge_preserve`. 之所以包括此項，是因為ui.content模組包含存取控制清單(ACL)，這些許可權會決定誰可以編輯範本。 為了將這些ACL匯入AEM， `acHandling` 屬性為必要項。
