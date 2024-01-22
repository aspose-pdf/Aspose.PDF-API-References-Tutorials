---
title: 刪除已開啟的操作
linktitle: 刪除已開啟的操作
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 從 PDF 中刪除開啟操作。
type: docs
weight: 80
url: /zh-hant/net/programming-with-links-and-actions/remove-open-action/
---
透過此逐步指南，了解如何使用 Aspose.PDF for .NET 從 PDF 檔案中刪除開啟操作。

## 第一步：建構環境

請確定您已使用 C# 專案和適當的 Aspose.PDF 參考設定開發環境。

## 第 2 步：載入 PDF 文件

使用以下程式碼設定文件的目錄路徑並上傳 PDF 檔案：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//開啟文件
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## 第三步：刪除打開的動作

透過設定從文件中刪除開啟操作`OpenAction`屬性為空：

```csharp
document. OpenAction = null;
```

## 步驟 4：儲存更新後的文檔

使用儲存更新的文檔`Save`方法：

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## 第5步：顯示結果

顯示一則訊息，指示開啟操作已成功刪除並指定儲存檔案的位置：

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### 使用 Aspose.PDF for .NET 刪除開啟操作的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
//刪除文件開啟操作
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
//儲存更新的文檔
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## 結論

恭喜！現在您知道如何使用 Aspose.PDF for .NET 從 PDF 中刪除開啟操作。使用這些知識來自訂專案中 PDF 文件的屬性和行為。

現在您已經完成了本指南，您可以將這些概念應用到您自己的專案中，並進一步探索 Aspose.PDF for .NET 提供的功能。

### 常見問題解答 

#### Q：PDF 文件中的「開啟操作」是什麼？

答：PDF 文件中的「開啟操作」是一條指令，指定開啟 PDF 時會發生什麼情況。它可以包括導航到文件中的特定頁面或位置、啟動外部應用程式或顯示特定視圖等操作。

#### Q：為什麼我要從 PDF 檔案中刪除開啟操作？

答：刪除開啟操作可以增強安全性、使用者體驗以及對開啟 PDF 時呈現方式的控制。例如，您可能希望在開啟文件時阻止自動導航或停用某些操作。

#### Q：Aspose.PDF for .NET 如何協助刪除開啟操作？

答：Aspose.PDF for .NET 提供 API 來操作 PDF 檔案的各個面向。本教學課程示範如何使用 C# 程式碼刪除開啟操作。

#### Q：取消開放動作是否有潛在的風險或註意事項？

答：刪除開啟操作可能會改變 PDF 的預設行為，因此請確保它符合預期的使用者體驗。徹底測試修改後的 PDF，以確認刪除不會影響其他功能。

#### Q：我可以自訂開啟動作來執行其他操作嗎？

答：是的，Aspose.PDF for .NET 可讓您透過將開啟操作設定為各種類型的操作來自訂開啟操作，例如導航至特定頁面或執行 JavaScript。

#### Q：我可以從受密碼保護的 PDF 中刪除開啟的操作嗎？
答：是的，只要您提供適當的憑證來存取和修改文檔，您就可以從受密碼保護的 PDF 中刪除開啟操作。

#### Q：打開動作移除是否可逆？

答：不可以，一旦開啟操作被刪除並儲存 PDF，則無法從修改後的 PDF 還原原始開啟操作。

#### Q：如何驗證開啟操作是否已成功刪除？

A：使用提供的代碼移除開啟操作後，開啟修改後的PDF並確認開啟時沒有發生任何特定操作。

#### Q：我可以同時從多個 PDF 檔案中刪除開啟的操作嗎？

答：是的，您可以使用相同的方法在批次場景中從多個 PDF 檔案中刪除開啟的操作。