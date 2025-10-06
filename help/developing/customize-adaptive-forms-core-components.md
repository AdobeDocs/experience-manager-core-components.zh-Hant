---
title: 自訂自適應表單核心元件
description: 進一步了解擴充或建立自適應表單核心元件，以實施根據組織需求量身打造的功能。
role: Architect, Developer, Admin
exl-id: f3ab12aa-d48d-47e9-a965-15052cac6f18
source-git-commit: 5994133947ff697f7c866fe61598c58e37e77008
workflow-type: ht
source-wordcount: '562'
ht-degree: 100%

---

# 自訂自適應表單核心元件

自訂自適應表單核心元件可讓您根據特定需求量身打造立即可用的功能。本指南會逐步引導您完成這些元件的自訂流程，以建立更個人化的體驗。

{{traditional-aem}}

## 必要條件

在深入進行自訂自適應表單核心元件之前，

* 了解[核心元件的架構](customizing.md#customizing-the-markup-customizing-the-markup)，並詳閱[Adobe Experience Manager 核心元件官方文件](customizing.md)。這些詳盡的資源將在整個自訂流程中為您提供指引。
* 設定您的開發環境，以確保在修改核心元件時能順利進行工作流程。設定開發環境時，請使用以最新 AEM 原型專案為基礎的 AEM 原型專案。根據您的環境，您可以：

   * [設定 Forms as a Cloud Service 的本機開發環境](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/setup-local-development-environment.html?lang=zh-Hant)。
   * [設定 AEM 6.5 Forms 的本機開發環境](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html?lang=zh-Hant)

## 自訂自適應表單核心元件

請依照下列步驟，修改自適應表單核心元件的外觀、行為和功能。

1. **識別並複製核心元件**

   在設定開發環境的同時，您已建立以原型為基礎的專案。在 AEM 原型專案中，識別您要自訂的特定核心元件。識別出資訊後，請在以 AEM 原型為基礎的專案中建立元件的副本。請使此元件與其他自適應表單核心元件可並行使用。此步驟可確保您的自訂工作不會影響原始元件，讓您能安心實驗。

1. **自訂複製的元件**

   開啟副本元件，並根據您的要求開始進行必要的修改：

   * **自訂 HTML 結構**：根據您的設計需求量身打造 HTML 結構，同時遵循 [BEM (區塊元素修飾元)](https://github.com/adobe/aem-core-wcm-components/wiki/css-coding-conventions) 樣式規範，以維持程式碼的可維護性與可擴充性。
   * **更新標籤**：更新元件的標籤，為自訂版本的名稱明確且具有敘述性。請參閱所提供的 [OOTB (立即可用) 標籤範本](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/af-commons/v1/fieldTemplates/label.html)以維持一致性。
   * **自訂小工具**：調整元件內使用的小工具 (下拉式清單、核取方塊)，以符合您的特定使用案例。請參閱[範例小工具實施](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput/textinput.html)深入了解。
   * **說明文字和工具提示**：將元件相關的說明文字或工具提示進行個人化，為使用者提供內容脈絡與指南。使用 [OOTB 說明文字範本](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/af-commons/v1/fieldTemplates/questionMark.html)作為起點。
   * **資料屬性**：在元件的 HTML 元素中整合所有必要的資料屬性。這些屬性對於元件在執行階段的正常運作至關重要。請參閱[此文件](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput)了解資料屬性在自適應表單核心元件中的角色。

1. **實施後端邏輯**

   如果您的自訂需要後端邏輯，則可以擴充現有的 Sling 模型。請參閱提供的[範例](https://github.com/adobe/aem-core-forms-components/blob/master/bundles/af-core/src/main/java/com/adobe/cq/forms/core/components/internal/models/v1/form/TextInputImpl.java)，將所需的功能順暢地整合至您的自訂元件中。

1. **設定元件的對話框**

   設定與自訂元件關聯的對話框。使用文件中提供的範例[元件對話框](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput/_cq_dialog/.content.xml)，確保使用者互動和設定受到適當的管理。

1. **在本機開發環境中部署及測試元件**

   在您的本機開發環境中使用 [Maven 建置和部署元件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html?lang=zh-Hant#building-and-installing)。部署元件後，建立自適應表單以測試自訂元件。

1. **在您的生產環境中部署自訂元件**

   在本機開發環境中測試元件後，請在生產環境中部署元件。
