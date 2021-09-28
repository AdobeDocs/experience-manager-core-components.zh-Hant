---
title: 預編譯的套件指令碼
description: 了解如何透過OSGi套件組合部署元件指令碼至Adobe Experience ManagerCloud Service。
source-git-commit: 56464decc8d6ae3cef68d62bfe459bceda0539ef
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# 預編譯的套件指令碼

AEM as aCloud Service支援部署[`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#code-packages-%2F-osgi-bundles)元件指令碼，作為預編譯的捆綁指令碼。 這可讓開發人員在建置時預先編譯其指令碼，並以OSGi套件組合的形式封裝。

## 透過OSGi套件組合部署預編譯指令碼的優點

將指令碼部署為預編譯的捆綁指令碼具有以下優點：

+ 在建置時編譯指令碼可讓開發人員在開發程式早期發現錯誤
+ 透過`Import-Package`和`Export-Package`套件組合標題明確定義Java API指令碼相依性
+ 繼承（透過`sling:resourceSuperType`）和委派給其他資源類型（例如透過HTL的`data-sly-resource`區塊元素或透過`sling:include` JSP標籤）可透過套件的中繼資料來對應
+ 資源類型版本設定的執行方式與Java API類似

## 預編譯和包導入

[`htl-maven-plugin`](https://sling.apache.org/components/htl-maven-plugin/index.html)可驗證HTL指令碼的語法，但也可用來將HTL指令碼傳輸至Java類別。 然後，這些資料夾會新增至您Maven專案的`generated-sources`資料夾，並由`maven-compiler-plugin`擷取。

可新增[`bnd-maven-plugin`](https://github.com/bndtools/bnd/tree/master/maven/bnd-maven-plugin)以產生OSGi套件組合的Java API匯入中繼資料。

## 繼承與委派

OSGi框架提供了一種強大的定義[要求和功能](https://docs.osgi.org/specification/osgi.core/7.0.0/framework.module.html#framework.module.dependencies)以表示不同元件之間的合同的方法。 這些會透過中繼資料加以說明，並在執行階段強制執行。 套件指令碼使用此機制來表示其繼承關係(`sling:resourceSuperType`)以及委派（包括呈現過程中的其他資源類型）。

[scriptingbundle-maven-plugin](https://sling.apache.org/components/scriptingbundle-maven-plugin/bnd.html)專案的`bnd`外掛程式可用來擷取與[`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#code-packages-%2F-osgi-bundles)內容套件所提供指令碼相對應的需求和功能。

## AEM專案原型支援

從第31版開始，[AEM專案原型](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html)可用來正確將AEM設為Cloud Service專案，以使用預先編譯的套裝指令碼。 此外，AEM專案原型會將[AEM設定為Cloud ServiceSDK建置分析器Maven Plugin](/help/developing/archetype/build-analyzer-maven-plugin.md)，以驗證Java套件層級和指令碼層級的相依性。
