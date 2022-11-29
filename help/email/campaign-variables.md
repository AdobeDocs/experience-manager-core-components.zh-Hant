---
title: 促銷活動變數
description: 使用促銷活動變數作為預留位置，以撰寫個人化電子郵件內容。
role: Architect, Developer, Admin, User
exl-id: 124ff5bf-6612-4baf-b0ff-6b1a95b455c1
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 0%

---


# 促銷活動變數 {#campaign-variables}

使用促銷活動變數來撰寫個人化電子郵件內容。 促銷活動變數可作為Adobe Campaign值的預留位置，您可將其插入電子郵件內容中。 透過Adobe Campaign傳送內容時，Campaign會以收件者的個人化內容取代這些變數。

## 使用狀況 {#usage}

電子郵件核心元件可讓行銷活動變數透過一般文字欄位旁的個人化按鈕輕鬆存取。 按下時，會出現對話方塊，您可從中選取個人化欄位。

可用的個人化欄位清單會與您的Adobe Campaign執行個體同步。 這些欄位在結構的Adobe Campaign中管理 `nms:seedMember`. 中的所有欄位 `nms:seedMember` 收件者表格中也必須有。

## 選取Adobe Campaign變數對話方塊 {#dialog}

電子郵件核心元件的許多編輯對話方塊中都提供選取Adobe Campaign變數對話方塊。 若要使用它，只需按一下 **選取Adobe Campaign變數** 圖示。 此表徵圖可以採用兩種形式。

![Adobe Campaign按鈕](/help/email/assets/campaign-button.png)
![選取Adobe Campaign變數圖示](/help/email/assets/select-adobe-campaign-variable-icon.png)

按一下兩個圖示會開啟 **選取Adobe Campaign變數** 對話框。

![選取Adobe Campaign變數對話方塊](assets/select-campaign-variable-dialog.png)

使用欄檢視來找出您要插入的變數。 按一下欄中的節點會在右側的新欄中顯示其子項。 如此一來，您就可以導覽變數內容結構。

選取您要插入的變數，然後按一下對話方塊右上角的核取記號。

![已選取Adobe Campaign變數](assets/select-campaign-variable-dialog-selected.png)

變數會插入至電子郵件核心元件的編輯對話方塊的欄位中。

![插入編輯對話方塊的促銷活動變數](assets/campaign-variable.png)

隨時按一下對話方塊左上角的X，取消並關閉對話方塊。
