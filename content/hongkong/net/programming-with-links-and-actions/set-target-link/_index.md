---
title: 在 PDF 文件中設定目標鏈接
linktitle: 在 PDF 文件中設定目標鏈接
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中設定目標連結。
type: docs
weight: 100
url: /zh-hant/net/programming-with-links-and-actions/set-target-link/
---
透過此逐步指南，了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中設定目標連結。

## 第一步：建構環境

請確定您已使用 C# 專案和適當的 Aspose.PDF 參考設定開發環境。

## 第 2 步：載入 PDF 文件

使用以下程式碼設定文件的目錄路徑並上傳 PDF 檔案：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//載入 PDF 文件
Document document = new Document(dataDir + "UpdateLinks.pdf");
```

## 步驟 3：編輯目標鏈接

使用以下程式碼取得要修改的連結註解：

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
```

您可以調整`[1]`用於選擇特定頁面或註釋的索引。

接下來，更新目標而不更新文件：

```csharp
goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
```

如果您還想更新該文件：

```csharp
goToR.File = new FileSpecification(dataDir + "input.pdf");
```

## 步驟 4：使用更新後的連結儲存文檔

使用以下命令儲存包含更新連結的文檔`Save`方法：

```csharp
dataDir = dataDir + "SetTargetLink_out.pdf";
document. Save(dataDir);
```

## 第5步：顯示結果

顯示一則訊息，指示目標連結已成功配置並指定儲存檔案的位置：

```csharp
Console.WriteLine("\nConfiguration of target link successful.\nFile saved at location: " + dataDir);
```

### 使用 Aspose.PDF for .NET 設定目標連結的範例原始碼 
```csharp
try
{
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//載入 PDF 文件
	Document document = new Document(dataDir + "UpdateLinks.pdf");
	LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
	GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
	//下一行更新目標，不更新文件
	goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
	//下一行更新文件
	goToR.File = new FileSpecification(dataDir +  "input.pdf");
	dataDir = dataDir + "SetTargetLink_out.pdf";
	//使用更新的連結儲存文檔
	document.Save(dataDir);
	Console.WriteLine("\nTarget link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

恭喜！現在您知道如何使用 Aspose.PDF for .NET 在 PDF 檔案中設定目標連結。使用這些知識來自訂 PDF 文件中的連結並為使用者建立互動式體驗。

現在您已經完成了本指南，您可以將這些概念應用到您自己的專案中，並進一步探索 Aspose.PDF for .NET 提供的功能。

### PDF 檔案中設定目標連結的常見問題解答

#### Q：PDF 文件中的目標連結是什麼？

答：PDF 文件中的目標鏈接是可單擊的鏈接，可將讀者導航到同一文件中的特定目標或另一個 PDF 文件。

#### Q：為什麼要在 PDF 文件中設定目標連結？

答：設定目標連結可讓您在 PDF 文件中建立無縫導航體驗，或連結到其他 PDF 文件中的特定部分或頁面。

#### Q：Aspose.PDF for .NET 如何協助設定目標連結？

答：Aspose.PDF for .NET 提供 API 來操作 PDF 檔案的各個方面，包括建立和修改連結。本教學示範如何使用 C# 程式碼設定目標連結。

#### Q：我可以設定目標連結來導覽到同一文件中的特定頁面嗎？

答：是的，Aspose.PDF for .NET 可讓您設定目標連結以導覽至相同文件中的特定頁面。

#### Q：我可以設定目標連結來導覽到另一個 PDF 檔案中的特定頁面嗎？

答：是的，您可以使用 Aspose.PDF for .NET 設定目標連結以導覽至另一個 PDF 檔案中的特定頁面。

#### Q：設定目標連結有什麼限制嗎？

答：目標連結只能在同一文件中導覽或導覽到其他 PDF 文件中的特定頁面。它們無法直接連結到其他文件中的特定內容。

#### Q：如何自訂目標連結的外觀？

答：可以使用 Aspose.PDF for .NET 提供的屬性來自訂目標連結的外觀，例如其顏色和樣式。

#### Q：我可以在同一個PDF文件中設定多個目標連結嗎？

答：是的，您可以在同一個 PDF 文件中設定多個目標連結。只需對您要建立的每個連結重複此過程即可。

#### Q：我可以使用特定形狀或文字設定目標連結嗎？

答：是的，您可以使用 Aspose.PDF for .NET 提供的適當屬性和方法將目標連結附加到 PDF 文件中的特定形狀或文字。

#### Q：如何測試目標連結是否如預期運作？

答：使用提供的程式碼設定目標連結後，打開修改後的 PDF 並點擊連結以確保其導航到所需的目的地。

#### Q：我可以在受密碼保護的 PDF 中設定目標連結嗎？

答：是的，只要您提供適當的憑證來存取和修改文檔，您就可以在受密碼保護的 PDF 中設定目標連結。