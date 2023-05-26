---
title: 預先編譯的套件指令碼
description: 瞭解如何透過OSGi套件組合將元件指令碼部署到Adobe Experience ManagerCloud Service。
exl-id: 3edc388f-01b2-45cc-bd56-f22e5a5a8624
source-git-commit: 767f83fbad11a108aab25be2b77759af3c08b864
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# 預先編譯的套件指令碼

AEMas a Cloud Service支援部署 [`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#code-packages-%2F-osgi-bundles) 元件指令碼作為預先編譯的套件指令碼。 如此一來，開發人員就能在建置階段預先編譯指令碼，並將這些指令碼封裝為OSGi套件組合。

## 透過OSGi套件組合部署預先編譯的指令碼的優點

將指令碼部署為預先編譯的隨附指令碼具有以下優點：

+ 在建置時間編譯指令碼可讓開發人員在開發過程的早期發現錯誤
+ Java API指令碼相依性是透過 `Import-Package` 和 `Export-Package` 套件組合標頭
+ 繼承(透過 `sling:resourceSuperType`)和委派至其他資源型別(透過HTL的 `data-sly-resource` 區塊元素或透過 `sling:include` 例如，JSP標籤)可透過套件的中繼資料進行對應
+ 資源型別版本設定能以類似於Java API的方式強制執行

## 預先編譯和套件匯入

此 [`htl-maven-plugin`](https://sling.apache.org/components/htl-maven-plugin/index.html) 可驗證HTL指令碼的語法，但也可用來將HTL指令碼轉換為Java類別。 然後，這些會新增到您的Maven專案的 `generated-sources` 資料夾並由 `maven-compiler-plugin`.

此 [`bnd-maven-plugin`](https://github.com/bndtools/bnd/tree/master/maven/bnd-maven-plugin) 可新增以產生OSGi套件組合的中繼資料以用於Java API匯入。

## 繼承與委派

OSGi架構提供強大的定義方式 [需求和功能](https://docs.osgi.org/specification/osgi.core/7.0.0/framework.module.html#framework.module.dependencies) 以表示不同元件之間的合約。 這些會透過中繼資料進行說明，並在執行階段強制執行。 套件指令碼使用此機制來表示其繼承關係(`sling:resourceSuperType`)，以及委派（包括轉譯程式中的其他資源型別）。

此 `bnd` 外掛程式 [scriptingbundle-maven-plugin](https://sling.apache.org/components/scriptingbundle-maven-plugin/bnd.html) project可用於擷取與提供的指令碼對應的需求和功能 [`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#code-packages-%2F-osgi-bundles) 內容封裝。

## AEM專案原型支援

從第31版開始， [AEM專案原型](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html) 可用來正確設定AEMas a Cloud Service專案，以使用預先編譯的套件指令碼。 此外，AEM專案原型會設定 [AEMas a Cloud ServiceSDK建置分析器Maven外掛程式](/help/developing/archetype/build-analyzer-maven-plugin.md) 驗證Java套件層級以及指令碼層級的相依性。
