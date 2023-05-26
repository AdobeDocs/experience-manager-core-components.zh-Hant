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

ui.apps maven模組(`<src-directory>/<project>/ui.apps`)包含下方網站所需的所有轉譯程式碼 `/apps`. 這包括將以名為的AEM格式儲存的CSS/JS [clientlibs。](uifrontend.md#clientlibs) 這也包括用於呈現動態HTML的HTL指令碼。 您可以將ui.apps模組視為JCR中結構的對應，但採用可儲存在檔案系統上並認可至原始檔控制的格式。

Apache Jackrabbit FileVault套件外掛程式可用來將ui.apps模組的內容編譯成可部署至AEM的AEM套件。 外掛程式的全域設定是在父系pom.xml中定義。

## 父級POM {#parent-pom}

[父級POM](/help/developing/archetype/using.md#parent-pom) (`<src>/<project>/pom.xml`)包含 `<plugin>` 區段，定義專案中使用之外掛程式的各種設定。 這包括「 」的設定 `filterSource` 適用於Jackrabbit FileVault套件外掛程式。 此 `filterSource` 指向 `filter.xml` 用來定義包含在封裝中的jcr路徑的檔案。

除了Jackrabbit FileVault套件外掛程式之外，還定義了內容套件外掛程式，用於隨後將套件推送至AEM。 請注意，的變數 `aem.host`， `aem.port`， `vault.user`、和 `vault.password` 會使用與相同父項POM中定義的全域屬性相對應的。

## ui.apps/pom.xml {#uiapps-pom}

請注意，core.wcm.components.all和core.wcm.components.examples套件會以子套件的形式納入。 這將每次部署核心元件套件以及WKND程式碼。

core.wcm.components.all和core.wcm.components.examples在相依性清單中作為相依性包含。 然而，作為最佳實務，相依性版本在此處會省略，並在中管理 [上層pom檔案](/help/developing/archetype/using.md#core-components).

## filter.xml {#filter}

此 `filter.xml` ui.apps模組的檔案位於 `<src>/<project>/ui.apps/src/main/content/META-INF/vault/filter.xml` 和包含將隨ui.apps套件一起包含和安裝的路徑。
