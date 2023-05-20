---
title: 預編譯的捆綁指令碼
description: 瞭解如何通過OSGi捆綁包將元件指令碼部署到Adobe Experience ManagerCloud Service。
exl-id: 3edc388f-01b2-45cc-bd56-f22e5a5a8624
source-git-commit: 767f83fbad11a108aab25be2b77759af3c08b864
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# 預編譯的捆綁指令碼

AEMas a Cloud Service支援 [`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#code-packages-%2F-osgi-bundles) 元件指令碼作為預編譯的捆綁指令碼。 這允許開發人員在生成時預編譯指令碼，並將其打包為OSGi捆綁包。

## 通過OSGi捆綁包部署預編譯指令碼的優勢

將指令碼部署為預編譯的捆綁指令碼具有以下優點：

+ 在生成時編譯指令碼允許開發人員在開發過程早期發現錯誤
+ 通過 `Import-Package` 和 `Export-Package` 包頭
+ 繼承（通過） `sling:resourceSuperType`)和委派到其他資源類型(通過HTL `data-sly-resource` 塊元素或通過 `sling:include` 例如，JSP標籤可以通過捆綁包的元資料進行映射
+ 資源類型版本控制可以以類似於Java API的方式實施

## 預編譯和包導入

的 [`htl-maven-plugin`](https://sling.apache.org/components/htl-maven-plugin/index.html) 可以驗證HTL指令碼的語法，但也可以將HTL指令碼傳輸到Java類中。 然後，這些內容將添加到Maven項目 `generated-sources` 資料夾和由 `maven-compiler-plugin`。

的 [`bnd-maven-plugin`](https://github.com/bndtools/bnd/tree/master/maven/bnd-maven-plugin) 可以添加以生成用於Java API導入的OSGi捆綁包的元資料。

## 繼承和委派

OSGi框架為定義OSGi框架提供了有力的方法 [要求和功能](https://docs.osgi.org/specification/osgi.core/7.0.0/framework.module.html#framework.module.dependencies) 不同部份之間訂立合約。 這些資訊通過元資料描述，並在運行時強制執行。 捆綁的指令碼使用此機制來表示它們的繼承關係(`sling:resourceSuperType`)，以及委派（包括呈現過程中的其他資源類型）。

的 `bnd` 插件 [指令碼捆綁 — maven插件](https://sling.apache.org/components/scriptingbundle-maven-plugin/bnd.html) 項目可用於提取與由 [`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#code-packages-%2F-osgi-bundles) 內容包。

## 項AEM目原型支援

從版本31開始， [項AEM目原型](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html) 可用於正確設定as a Cloud Service項AEM目以使用預編譯的捆綁指令碼。 此外，「項AEM目原型」配置 [AEMas a Cloud ServiceSDK生成Analyzer Maven插件](/help/developing/archetype/build-analyzer-maven-plugin.md) 驗證Java包級別以及指令碼級別依賴關係。
