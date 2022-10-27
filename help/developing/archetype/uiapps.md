---
title: AEM專案原型的ui.apps模組
description: AEM專案原型的ui.apps模組
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: fc63a19a-3253-44ee-96e2-bb5544c2235b
source-git-commit: 19bceb1d8ba07c70798f2e7203db957d3e8b3d03
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 0%

---

# AEM專案原型的ui.apps模組 {#uiapps-module}

ui.apps maven模組(`<src-directory>/<project>/ui.apps`)包含下方網站所需的所有轉譯程式碼 `/apps`. 這包括將以AEM格式儲存的CSS/JS，稱為 [clientlibs 。](uifrontend.md#clientlibs) 這也包含用於轉譯動態HTML的HTL指令碼。 您可以將ui.apps模組視為JCR中結構的對應，但格式可儲存在檔案系統上並提交至原始碼控制項。

Apache Jackrabbit FileVault套件外掛程式用於將ui.apps模組的內容編譯為可部署至AEM的AEM套件。 外掛程式的全域設定是在上層pom.xml中定義。

## 父POM {#parent-pom}

[父POM](/help/developing/archetype/using.md#parent-pom) (`<src>/<project>/pom.xml`)包括 `<plugin>` 為專案中使用的外掛程式定義各種設定的區段。 這包括 `filterSource` Jackrabbit FileVault套件外掛程式。 此 `filterSource` 指向 `filter.xml` 用於定義包中包含的jcr路徑的檔案。

除了Jackrabbit FileVault套件外掛程式外，還有內容套件外掛程式的定義，用於將套件推送至AEM。 請注意 `aem.host`, `aem.port`, `vault.user`，和 `vault.password` 是用來對應於相同父POM中定義的全域屬性。

## ui.apps/pom.xml {#uiapps-pom}

請注意，core.wcm.components.all和core.wcm.components.examples套件是以子套件的形式包含。 每次都會部署核心元件套件及WKND程式碼。

core.wcm.components.all和core.wcm.components.examples在相依性清單中包含為相依性。 不過，根據最佳實務，此處會忽略相依性的版本，並在 [上層pom檔案](/help/developing/archetype/using.md#core-components).

## filter.xml {#filter}

此 `filter.xml` ui.apps模組的檔案位於 `<src>/<project>/ui.apps/src/main/content/META-INF/vault/filter.xml` 和包含將隨ui.apps套件包含和安裝的路徑。
