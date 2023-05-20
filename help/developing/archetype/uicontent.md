---
title: ui.項目原型的內AEM容模組
description: ui.項目原型的內AEM容模組
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: af019cd8-c733-4b53-bb57-321dd9451178
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 0%

---

# ui.項目原型的內AEM容模組 {#uicontent-module}

ui.content命令模組(`<src-directory>/<project>/ui.content`)包括下面的基線內容和配置 `/content` 和 `/conf`。 ui.content被編譯到與ui.appsAEM非常相似的包中。 主要區別在於，可以直接在實例上修改ui.content中儲存的節AEM點。 這包括頁面、DAM資產和可編輯模板。 ui.content模組可用於儲存清潔實例的示例內容和/或建立一些要在原始碼管理中管理的基線配置。

## filter.xml {#filter}

的 `filter.xml` 在以下位置找到ui.content模組的檔案： `<src>/<project>/ui.content/src/main/content/META-INF/vault/filter.xml` 並包含將隨ui.content包一起包含和安裝的路徑。 請注意 `mode="merge"` 屬性將添加到路徑。 這可確保使用代碼部署部署的配置不會自動覆蓋在實例上直接創作的內容AEM或配置。

## ui.content/pom.xml

ui.content模組與ui.apps模組一樣，使用FileVault包插件。 但是ui.content pom(`<src>/<project>/ui.content/pom.xml`)包含名為的額外配置屬性 `acHandling`，設定為 `merge_preserve`。 這包括在內，因為ui.content模組包括作為權限的訪問控制清單(ACL)，這些權限決定了哪些人可以編輯模板。 為了將這些ACL導入AEM到 `acHandling` 需要屬性。
