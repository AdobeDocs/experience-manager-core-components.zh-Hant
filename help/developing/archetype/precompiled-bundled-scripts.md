---
title: 預先編譯的套件指令碼
description: 了解如何透過 OSGi 套件組合將元件指令碼部署至 Adobe Experience Manager Cloud Service。
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 3edc388f-01b2-45cc-bd56-f22e5a5a8624
source-git-commit: 554be9539428cd75462a38fc45f1bece04baf066
workflow-type: ht
source-wordcount: '335'
ht-degree: 100%

---


# 預先編譯的套件指令碼 {#precompiled-bundled-scripts}

AEM as a Cloud Service 支援將 [`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=zh-Hant#code-packages-%2F-osgi-bundles) 元件指令碼部署為預先編譯的套件指令碼。如此一來，開發人員就能在建置階段預先編譯指令碼，並將這些指令碼封裝為 OSGi 套件組合。

## 透過 OSGi 套件組合部署預先編譯的指令碼的優點 {#advantages}

將指令碼部署為預先編譯的套件指令碼具有以下優點：

+ 在建置時間編譯指令碼可讓開發人員在開發過程的早期發現錯誤。
+ Java API 指令碼相依性是透過 `Import-Package` 和 `Export-Package` 套件組合標題明確定義。
+ 繼承 (透過 `sling:resourceSuperType`) 和委派給其他資源類型 (例如透過 HTL 的 `data-sly-resource` 區塊元素或透過 `sling:include` JSP 標記) 可利用套件組合的後設資料進行對應。
+ 資源類型版本設定能以類似於 Java API 的方式強制執行。

## 預先編譯和套件匯入 {#precompilation}

[`htl-maven-plugin`](https://sling.apache.org/components/htl-maven-plugin/index.html) 可以驗證 HTL 指令碼的語法，但也可用來將 HTL 指令碼轉譯成 Java 類別。然後這些檔案會新增到您 Maven 專案的 `generated-sources` 資料夾，並由 `maven-compiler-plugin` 擷取。

可以新增 [`bnd-maven-plugin`](https://github.com/bndtools/bnd/tree/master/maven/bnd-maven-plugin) 來產生 Java API 匯入用的 OSGi 套件組合後設資料。

## 繼承與委派 {#inheritance-delegation}

OSGi 架構提供強大的方式來定義[要求和功能](https://docs.osgi.org/specification/osgi.core/7.0.0/framework.module.html#framework.module.dependencies)，以表示不同元件之間的合約。這些會透過後設資料進行說明，並在執行階段強制執行。套裝指令碼使用此機制來表示其繼承關係 (`sling:resourceSuperType`) 以及委派 (包括轉譯過程中的其他資源)。

[scriptingbundle-maven-plugin](https://sling.apache.org/components/scriptingbundle-maven-plugin/bnd.html) 專案中的 `bnd` 外掛程式可用來擷取與 [`ui.apps`.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=zh-Hant#code-packages-%2F-osgi-bundles) 內容套件所提供之指令碼相對應的要求和功能

## AEM 專案原型支援 {#support}

從版本 31 開始，[ AEM 專案原型](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html?lang=zh-Hant)可用於正確設定 AEM as a Cloud Service 專案，以使用預先編譯的套件指令碼。

此外，AEM 專案原型會設定 [AEM as a Cloud Service SDK 建置分析器 Maven 外掛程式](/help/developing/archetype/build-analyzer-maven-plugin.md)，以驗證 Java 套件層級以及指令碼層級的相依性。
