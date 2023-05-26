---
title: 促銷活動變數
description: 使用Campaign變數做為預留位置，以撰寫個人化的電子郵件內容。
role: Architect, Developer, Admin, User
exl-id: 124ff5bf-6612-4baf-b0ff-6b1a95b455c1
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 0%

---


# 促銷活動變數 {#campaign-variables}

使用Campaign變數來撰寫個人化電子郵件內容。 行銷活動變數會當作Adobe Campaign值的預留位置，您可將其插入電子郵件內容。 透過Adobe Campaign傳送內容時，Campaign會以收件者的個人化內容取代這些變數。

## 使用狀況 {#usage}

電子郵件核心元件可讓您透過常見文字欄位旁的個人化按鈕，輕鬆存取行銷活動變數。 按下時，會出現一個對話方塊，您可以從中選擇個人化欄位。

可用個人化欄位的清單會與您的Adobe Campaign執行個體同步。 這些欄位在結構描述中的Adobe Campaign中管理 `nms:seedMember`. 所有欄位 `nms:seedMember` 也必須出現在您的收件者表格中。

## 選取Adobe Campaign變數對話方塊 {#dialog}

「選取Adobe Campaign變數」對話方塊可用於電子郵件核心元件的許多編輯對話方塊。 若要使用，只要按一下 **選取Adobe Campaign變數** 圖示加以選取。 此圖示有兩種形式。

![Adobe Campaign按鈕](/help/email/assets/campaign-button.png)
![選取Adobe Campaign變數圖示](/help/email/assets/select-adobe-campaign-variable-icon.png)

按一下這兩個圖示會開啟 **選取Adobe Campaign變數** 對話方塊。

![選取Adobe Campaign變數對話方塊](assets/select-campaign-variable-dialog.png)

使用欄檢視來找出您要插入的變數。 按一下欄中的節點，會在右側的新欄中顯示其子系。 如此一來，您就可以導覽可變內容結構。

選取您要插入的變數，然後按一下對話方塊右上角的核取記號。

![已選取Adobe Campaign變數](assets/select-campaign-variable-dialog-selected.png)

然後，變數會插入電子郵件核心元件之編輯對話方塊的欄位中。

![行銷活動變數已插入編輯對話方塊中](assets/campaign-variable.png)

隨時按一下對話方塊左上方的X可取消並關閉對話方塊。
