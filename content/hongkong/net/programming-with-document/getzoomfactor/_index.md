---
title: 取得 PDF 檔案中的縮放係數
linktitle: 取得 PDF 檔案中的縮放係數
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南，了解如何使用 Aspose.PDF for .NET 取得 PDF 檔案中的縮放係數。
type: docs
weight: 210
url: /zh-hant/net/programming-with-document/getzoomfactor/
---
Aspose.PDF for .NET 是一個 PDF 操作庫，它提供了許多功能來對 PDF 文件執行各種操作。這些功能之一是能夠取得 PDF 檔案中的縮放係數。在本教學中，我們將說明如何使用 Aspose.PDF for .NET 使用 C# 原始碼取得 PDF 檔案中的縮放係數。


## 步驟 1：實例化新的 Document 對象

使用 Aspose.PDF for .NET 取得 PDF 檔案的縮放係數的第一步是實例化一個新的`Document`目的。這`Document`物件表示可以從文件或流載入的 PDF 文件。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//實例化新的 Document 對象
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

在上面的程式碼中，我們創建了一個`Document`物件透過將 PDF 檔案的路徑傳遞給建構函數`Document`班級。您需要將「您的文件目錄」替換為 PDF 檔案所在目錄的實際路徑。

## 步驟2：建立GoToAction對象

下一步是創建一個`GoToAction`目的。一個`GoToAction`物件表示前往 PDF 文件中特定目的地的操作。在我們的例子中，我們想要取得 PDF 檔案的縮放係數，因此我們將使用`OpenAction`的財產`Document`對象得到`GoToAction`目的。

```csharp
//建立GoToAction對象
GoToAction action = doc.OpenAction as GoToAction;
```

在上面的程式碼中，我們創建了一個`GoToAction`透過投射對象`OpenAction`的財產`Document`反對`GoToAction`.

## 步驟3：取得PDF檔案的縮放係數

第三步是取得PDF檔案的縮放係數。我們可以透過存取來取得PDF檔案的縮放係數`Destination`的財產`GoToAction`對象，然後將其投射到`XYZExplicitDestination` 。這`XYZExplicitDestination`類別表示 PDF 文件中的目的地，指定要轉到的座標和縮放係數。

```csharp
//取得PDF檔案的縮放係數
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); //文檔縮放值；
```

在上面的程式碼中，我們訪問了`Destination`的財產`GoToAction`對象，然後將其投射到`XYZExplicitDestination`。之後我們就可以訪問到了`Zoom`的財產`XYZExplicitDestination`物件取得 PDF 檔案的縮放係數。

## 第四步：輸出縮放係數

最後一步是輸出 PDF 檔案的縮放係數。我們可以使用`System.Console.WriteLine`

```csharp
//取得PDF檔案的縮放係數
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); //文檔縮放值；
```        

### 使用 Aspose.PDF for .NET 取得縮放係數的範例原始碼

以下是使用 Aspose.PDF for .NET 取得縮放係數的完整範例原始碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//實例化新的 Document 對象
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

//建立GoToAction對象
GoToAction action = doc.OpenAction as GoToAction;

//取得PDF檔案的縮放係數
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); //文檔縮放值；
```

## 結論

在本教學中，我們探討如何使用 Aspose.PDF for .NET 來取得 PDF 檔案的縮放係數。縮放係數是 PDF 文件的一個重要方面，因為它決定了在檢視器中開啟時的初始顯示大小。透過存取和利用縮放係數，開發人員可以為最終用戶客製化觀看體驗。 Aspose.PDF for .NET提供了一個簡單而有效的API來從PDF文件中檢索縮放係數和其他與導航相關的信息，使開發人員能夠構建功能豐富的交互式PDF應用程式。

### 取得 PDF 檔案縮放係數的常見問題解答

#### Q：PDF 文件的縮放係數是多少？

答：PDF 文件中的縮放係數是指查看文件時所應用的放大等級。它決定 PDF 文件在螢幕上的初始顯示大小。縮放係數為1.0表示實際尺寸（100%縮放），大於1.0表示放大，小於1.0表示縮小。

#### Q：如何在我的應用程式中使用縮放係數資訊？

答：您可以使用縮放係數資訊來自訂 PDF 文件在檢視器中開啟時的初始顯示大小。例如，您可以設定特定的縮放係數以確保 PDF 以特定尺寸顯示或使整個頁面適合檢視器的視窗。

#### Q：我可以使用 Aspose.PDF for .NET 以程式設計方式修改 PDF 文件的縮放係數嗎？

答：是的，您可以使用 Aspose.PDF for .NET 以程式設計方式修改 PDF 文件的縮放係數。您可以為特定操作設定縮放係數，例如`GoToAction`或者`GoToRemoteAction`，控制當使用者與連結或書籤互動時文件的顯示方式。

#### Q：是否有其他方法可以使用 Aspose.PDF for .NET 導覽至 PDF 文件中的特定位置？

答：是的，Aspose.PDF for .NET 提供了各種功能來導航到 PDF 文件中的特定位置。除了使用`GoToAction`，您可以使用其他操作，例如`GoToURIAction`開啟一個 URL，`GoToEmbeddedAction`導航到嵌入文件，以及`GoToNamedAction`前往 PDF 文件中的指定目的地。