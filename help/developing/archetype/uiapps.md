---
title: 項目原型的ui.appAEMs模組
description: 項目原型的ui.appAEMs模組
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: fc63a19a-3253-44ee-96e2-bb5544c2235b
source-git-commit: 19bceb1d8ba07c70798f2e7203db957d3e8b3d03
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 0%

---

# 項目原型的ui.appAEMs模組 {#uiapps-module}

ui.apps maven模組(`<src-directory>/<project>/ui.apps`)包含下面站點所需的所有呈現代碼 `/apps`。 這包括將以名為的格式儲存AEM的CSS/JS [客戶端。](uifrontend.md#clientlibs) 這還包括用於呈現動態HTML的HTL指令碼。 您可以將ui.apps模組視為JCR中結構的映射，但格式可以儲存在檔案系統上並提交到原始碼管理。

Apache Jackrabbit FileVault包插件用於將ui.apps模組的內容編譯到可部署到AEM的包中AEM。 插件的全局配置在父pom.xml中定義。

## 父POM {#parent-pom}

[父POM](/help/developing/archetype/using.md#parent-pom) (`<src>/<project>/pom.xml`包括 `<plugin>` 定義項目中使用的插件的各種配置的部分。 這包括 `filterSource` Jackrabbit FileVault包插件。 的 `filterSource` 指向 `filter.xml` 用於定義包中包含的jcr路徑的檔案。

除了Jackrabbit FileVault包插件外，還定義了內容包插件，該插件用於將包推入AEM。 請注意， `aem.host`。 `aem.port`。 `vault.user`, `vault.password` 與同一父POM中定義的全局屬性相對應。

## ui.apps/pom.xml {#uiapps-pom}

請注意，core.wcm.components.all和core.wcm.components.examples軟體包都作為子軟體包提供。 這將每次部署核心元件包和WKND代碼。

core.wcm.components.all和core.wcm.components.examples作為依賴關係清單中的依賴項包括在內。 但是，作為最佳做法，此處省略了相關性的版本，並在 [父pom檔案](/help/developing/archetype/using.md#core-components)。

## filter.xml {#filter}

的 `filter.xml` 在以下位置找到ui.apps模組的檔案： `<src>/<project>/ui.apps/src/main/content/META-INF/vault/filter.xml` 並包含將隨ui.apps包一起安裝的路徑。
