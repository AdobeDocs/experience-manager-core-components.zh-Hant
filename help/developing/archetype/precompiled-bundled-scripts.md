---
title: 預先編譯的套件指令碼
description: 瞭解如何透過OSGi套件組合將元件指令碼部署至Adobe Experience ManagerCloud Service。
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 3edc388f-01b2-45cc-bd56-f22e5a5a8624
source-git-commit: 554be9539428cd75462a38fc45f1bece04baf066
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 0%

---


# 預先編譯的套件指令碼 {#precompiled-bundled-scripts}

AEM as a Cloud Service支援將[`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#code-packages-%2F-osgi-bundles)元件指令碼部署為預先編譯的套裝指令碼。 如此一來，開發人員就能在建置階段預先編譯指令碼，並將這些指令碼封裝為OSGi套件組合。

## 透過OSGi套件組合部署預先編譯的指令碼的優點 {#advantages}

將指令碼部署為預先編譯的隨附指令碼具有以下優點：

+ 在建置時間編譯指令碼可讓開發人員在開發過程的早期發現錯誤。
+ Java API指令碼相依性是透過`Import-Package`和`Export-Package`套件組合標題明確定義。
+ 繼承（透過`sling:resourceSuperType`）和委派給其他資源型別（例如，透過HTL的`data-sly-resource`區塊元素或透過`sling:include` JSP標籤）可透過套件的中繼資料進行對應。
+ 資源型別版本設定能以類似於Java API的方式強制執行。

## 預先編譯和封裝匯入 {#precompilation}

[`htl-maven-plugin`](https://sling.apache.org/components/htl-maven-plugin/index.html)可以驗證HTL指令碼的語法，但也可用來將HTL指令碼轉譯成Java類別。 然後這些檔案會新增到您Maven專案的`generated-sources`資料夾，並由`maven-compiler-plugin`擷取。

可以新增[`bnd-maven-plugin`](https://github.com/bndtools/bnd/tree/master/maven/bnd-maven-plugin)來產生Java API匯入的OSGi套件組合中繼資料。

## 繼承與委派 {#inheritance-delegation}

OSGi架構提供強大的方式來定義[需求和功能](https://docs.osgi.org/specification/osgi.core/7.0.0/framework.module.html#framework.module.dependencies)，以表示不同元件之間的合約。 這些會透過中繼資料進行說明，並在執行階段強制執行。 套裝指令碼使用此機制來表示其繼承關係(`sling:resourceSuperType`)以及委派（包括轉譯程式中的其他資源型別）。

[scriptingbundle-maven-plugin](https://sling.apache.org/components/scriptingbundle-maven-plugin/bnd.html)專案中的`bnd`外掛程式可用來擷取對應於[`ui.apps`所提供之指令碼的需求和功能。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#code-packages-%2F-osgi-bundles)個內容封裝

## AEM專案原型支援 {#support}

從版本31開始，[AEM專案原型](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html)可用於正確設定AEM as a Cloud Service專案，以使用預先編譯的套件指令碼。

此外，AEM專案原型會設定[AEM as a Cloud Service SDK Build Analyzer Maven外掛程式](/help/developing/archetype/build-analyzer-maven-plugin.md)，以驗證Java套件層級以及指令碼層級的相依性。
