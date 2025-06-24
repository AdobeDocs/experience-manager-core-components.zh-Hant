---
title: 自訂最適化Forms核心元件
description: 瞭解如何擴充或建立最適化Forms核心元件，以實作為您的組織量身打造的功能。
role: Architect, Developer, Admin
exl-id: f3ab12aa-d48d-47e9-a965-15052cac6f18
source-git-commit: 5994133947ff697f7c866fe61598c58e37e77008
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 0%

---

# 自訂最適化Forms核心元件

自訂最適化Forms核心元件可讓您根據特定需求量身打造現成可用的功能。 本指南會逐步引導您完成自訂這些元件的程式，以建立更個人化的體驗。

{{traditional-aem}}

## 先決條件

開始自訂最適化Forms核心元件之前，

* 瞭解核心元件[&#128279;](customizing.md#customizing-the-markup-customizing-the-markup)的架構，並參閱[Adobe Experience Manager核心元件官方檔案](customizing.md)。 這些全方位的資源在整個自訂程式中都是您的指南。
* 設定您的開發環境這可確保順利進行工作流程，以變更核心元件。 設定開發環境時，請使用以最新AEM原型專案為基礎的AEM原型專案。 根據您的環境，您可以：

   * [設定Forms as a Cloud Service的本機開發環境](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/setup-local-development-environment.html)。
   * [為AEM 6.5 Forms設定本機開發環境](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html)

## 自訂最適化Forms核心元件

請依照下列步驟，修改最適化Forms核心元件的外觀、行為和功能。

1. **識別並複製核心元件**

   在設定開發環境時，您已建立原型型專案。 在AEM原型專案中，識別您要自訂的特定核心元件。 在識別之後，請在以AEM原型為基礎的專案中建立元件的復本。 使其與其他最適化Forms核心元件並行。 此步驟可確保您的自訂工作不會影響原始元件，讓您自由實驗。

1. **自訂複製的元件**

   開啟重複的元件，並根據您的需求開始進行必要的修改：

   * **自訂HTML結構**：根據您的設計需求量身打造HTML結構，同時遵循[BEM （區塊元素修飾元）](https://github.com/adobe/aem-core-wcm-components/wiki/css-coding-conventions)可維護且可擴充程式碼的樣式作法。
   * **更新標籤**：更新元件的標籤，為自訂版本提供清楚且描述性的名稱。 請參閱提供的[OOTB （現成可用）標籤範本](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/af-commons/v1/fieldTemplates/label.html)以取得一致性。
   * **自訂Widget**：調整元件內使用的Widget （下拉選單、核取方塊），以符合您的特定使用案例。 請參閱[範例Widget實作](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput/textinput.html)以取得參考。
   * **說明文字和工具提示**：個人化與元件相關的說明文字或工具提示，以提供內容與指引給使用者。 使用[OOTB說明文字範本](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/af-commons/v1/fieldTemplates/questionMark.html)作為起點。
   * **資料屬性**：在元件的HTML元素中合併所有必要的資料屬性。 這些屬性對於元件在執行階段的正常運作至關重要。 請參閱[檔案](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput)以瞭解資料屬性在調適型Forms核心元件中的角色。

1. **實作後端邏輯**

   如果您的自訂需要後端邏輯，則可以擴充現有的Sling模型。 請參閱提供的[範例](https://github.com/adobe/aem-core-forms-components/blob/master/bundles/af-core/src/main/java/com/adobe/cq/forms/core/components/internal/models/v1/form/TextInputImpl.java)，將所需的功能順暢地整合至您的自訂元件中。

1. **設定元件的對話方塊**

   設定與自訂元件關聯的對話方塊。 使用檔案中提供的範例[元件對話方塊](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput/_cq_dialog/.content.xml)，確保使用者互動和設定受到適當的管理。

1. **在本機開發環境中部署及測試元件**

   使用[maven在您的本機開發環境中建置和部署元件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html#building-and-installing)。 部署元件後，建立最適化表單以測試自訂元件。

1. **在您的生產環境中部署自訂元件**

   在本機開發環境中測試元件後，請在生產環境中部署元件。
