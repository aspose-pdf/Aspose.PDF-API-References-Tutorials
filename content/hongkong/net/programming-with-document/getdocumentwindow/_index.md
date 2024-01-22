---
title: 取得文檔視窗
linktitle: 取得文檔視窗
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 的 GetDocumentWindow 功能來擷取 PDF 文件視窗屬性的資訊。
type: docs
weight: 170
url: /zh-hant/net/programming-with-document/getdocumentwindow/
---
 Aspose.PDF for .NET 是一個功能強大的 PDF 操作庫，可讓開發人員在其 .NET 應用程式中建立、編輯和轉換 PDF 檔案。該庫提供的功能之一是能夠檢索有關文件視窗屬性的資訊。本教學將引導您完成使用`GetDocumentWindow`Aspose.PDF for .NET 的功能可擷取 PDF 文件視窗屬性的資訊。

## 第 1 步：安裝 Aspose.PDF for .NET

要在 .NET 應用程式中使用 Aspose.PDF for .NET，您必須先安裝程式庫。您可以從以下位置下載該庫的最新版本[Aspose.PDF for .NET 下載頁面](https://releases.aspose.com/pdf/net).

下載該庫後，將 ZIP 檔案的內容解壓縮到電腦上的資料夾中。然後，您需要在 .NET 專案中新增對 Aspose.PDF for .NET DLL 的參考。

## 第 2 步：載入 PDF 文檔

安裝 Aspose.PDF for .NET 並在 .NET 專案中新增對 DLL 的參考後，您就可以開始使用`GetDocumentWindow`檢索有關 PDF 文件視窗屬性的資訊的功能。

使用此功能的第一步是載入您想要檢索其資訊的 PDF 文件。為此，您可以使用以下程式碼：

```csharp
// PDF文件的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟 PDF 文檔
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

在上面的程式碼中，替換`"YOUR DOCUMENT DIRECTORY"`以及 PDF 文件所在目錄的路徑。此程式碼會將 PDF 文件載入到`Document`對象，然後您可以使用該對象檢索有關文檔視窗屬性的資訊。

## 步驟 3：檢索文件的視窗屬性

要檢索有關 PDF 文件視窗屬性的信息，您可以使用以下程式碼：

```csharp
//檢索文檔的視窗屬性
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

在上面的程式碼中，每一行會檢索 PDF 文件的不同視窗屬性並將其輸出到控制台。您可以自訂此程式碼以僅檢索您感興趣的屬性。

### 使用 Aspose.PDF for .NET 取得 PDF 文件的文件視窗的範例原始碼 

以下是使用以下命令檢索 PDF 文件視窗屬性的完整原始碼：`GetDocumentWindow` Aspose.PDF for .NET 的功能：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟文件
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

//取得不同的文件屬性
//文檔視窗的位置 - 預設值： false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

//主要閱讀順序；確定頁面的位置
//並排顯示時 - 預設：L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

//視窗標題列是否顯示文件標題
//如果為 false，標題列將顯示 PDF 檔案名稱 - 預設值：false
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

//是否調整文檔視窗的大小以適合
//第一個顯示的頁面 - 預設值： false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

//是否隱藏檢視器應用程式的選單列 - 預設： false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//是否隱藏檢視器應用程式的工具列 - 預設： false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

//是否隱藏捲軸等UI元素
//並且只保留顯示的頁面內容 - 預設值： false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

//文檔的頁面模式。如何在退出全螢幕模式時顯示文件。
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

//頁面版面即單頁、一欄
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

//文件開啟時應如何顯示
//即顯示縮圖、全螢幕、顯示附件面板
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 擷取 PDF 文件視窗屬性的資訊。透過載入 PDF 文件並存取其視窗屬性，您可以收集有關文件在檢視器應用程式中開啟時應如何顯示的資訊。 Aspose.PDF for .NET 提供了一組強大的功能，以程式設計方式處理 PDF 文件，使其成為 .NET 應用程式中 PDF 操作的寶貴工具。

### 常見問題解答

#### Q：檢索 PDF 文件的視窗屬性的目的是什麼？

答：透過檢索 PDF 文件的視窗屬性，您可以收集有關在檢視器應用程式中開啟 PDF 文件時應如何顯示的資訊。這些屬性控制各個方面，例如視窗位置、顯示模式和 UI 元素的可見性。

#### Q：如何在我的 .NET 專案中安裝 Aspose.PDF for .NET？

答：要安裝 Aspose.PDF for .NET，您需要從以下位置下載該程式庫：[Aspose.PDF for .NET 下載頁面](https://releases.aspose.com/pdf/net)。下載後，解壓縮 ZIP 檔案的內容並在 .NET 專案中新增對 Aspose.PDF for .NET DLL 的參考。

#### Q：我可以自訂程式碼以僅檢索特定視窗屬性嗎？

答：是的，您可以透過註解掉不需要的行來自訂程式碼以擷取特定的視窗屬性。程式碼中的每一行都對應一個特定的視窗屬性，因此您可以根據需要包含或排除屬性。

#### Q：我可以使用 Aspose.PDF for .NET 檢索哪些類型的視窗屬性？

答：使用Aspose.PDF for .NET，您可以擷取PDF文件的各種視窗屬性，包括視窗置中、設定頁面佈局、控制工具列和功能表列的顯示等。