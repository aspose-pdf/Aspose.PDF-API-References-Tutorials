---
title: 在 PDF 檔案中新增圖像
linktitle: 在 PDF 檔案中新增圖像
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 在 PDF 檔案中輕鬆新增影像。
type: docs
weight: 10
url: /zh-hant/net/programming-with-images/add-image/
---
本指南將逐步指導您如何使用 Aspose.PDF for .NET 在 PDF 文件中新增圖像。確保您已設定環境並按照以下步驟操作：

## 步驟1：定義文檔目錄

開始之前，請確保為文件設定正確的目錄。代替`"YOUR DOCUMENT DIRECTORY"`在程式碼中新增 PDF 文件所在目錄的路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步驟 2：開啟文檔

在此步驟中，我們將使用以下命令開啟 PDF 文檔`Document` Aspose.PDF 類別。使用`Document`建構函數並傳遞 PDF 文件的路徑。

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## 第三步：設定圖像座標

設定要新增的圖像的座標。變數`lowerLeftX`, `lowerLeftY`, `upperRightX`和`upperRightY`分別表示影像的左下角和右上角的座標。

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## 第四步：取得要新增圖片的頁面

要將圖像新增至 PDF 文件的特定頁面，我們首先需要檢索該頁面。在此範例中，我們將圖像新增至文件的第二頁（索引 1）。

```csharp
Page page = pdfDocument.Pages[1];
```

## 第 5 步：從流中載入圖像

現在我們將載入要新增到 PDF 文件中的圖像。此範例假設您有一個名為`aspose-logo.jpg`與您的文件位於同一目錄中。如有必要，請替換檔案名稱。

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## 第 6 步：將圖像新增至頁面資源

要使用PDF文件中的圖像，我們需要將其新增到頁面的資源圖像集合中。

```csharp
page.Resources.Images.Add(imageStream);
```

## 步驟7：儲存目前圖形狀態

在繪製圖像之前，我們需要使用以下命令保存當前圖形狀態`GSave`操作員。這確保了對圖形狀態的變更可以稍後回滾。

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## 第8步：建立矩形和矩陣對象

我們現在將創建一個`Rectangle`物件和一個`Matrix`目的。矩形代表影像的位置和大小，而矩陣定義影像的放置方式。

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## 第 9 步：連接影像放置矩陣

為了指定圖像應如何放置在矩形中，我們使用`ConcatenateMatrix`操作員。此運算符定義將影像的座標空間對應到頁面的座標空間的變換矩陣。

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## 第10步：繪製影像

在此步驟中，我們將使用以下方法在頁面上繪製圖像`Do`操作員。這`Do`運算符從資源中獲取圖像名稱並將其繪製到頁面上。

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## 步驟11：恢復圖形狀態

繪製圖像後，我們需要使用以下命令恢復先前的圖形狀態`GRestore`操作員。

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## 第12步：儲存更新後的文檔

最後，我們將更新的文檔儲存到新文件中。更新`dataDir`具有所需輸出目錄和檔案名稱的變數。

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 新增影像的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir+ "AddImage.pdf");
//設定座標
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
//取得需要新增圖片的頁面
Page page = pdfDocument.Pages[1];
//將圖像載入到流中
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
//將圖像新增至頁面資源的圖像集合
page.Resources.Images.Add(imageStream);
//使用GSave運算子：此運算子儲存目前圖形狀態
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
//建立矩形和矩陣對象
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
//使用ConcatenateMatrix（連接矩陣）運算子：定義影像的放置方式
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
//使用 Do 運算子：此運算子繪製影像
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
//使用GRestore運算子：此運算子恢復圖形狀態
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
//儲存更新的文檔
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 將影像新增至 PDF 文件。我們詳細介紹了從開啟文件到保存更新版本的每個步驟。透過遵循本指南，您現在應該能夠使用 C# 和 Aspose.PDF 以程式設計方式將圖像嵌入到 PDF 文件中。

### 在 PDF 文件中添加圖像的常見問題解答

#### Q：為什麼我要為 PDF 文件添加圖像？

答：將圖像新增至 PDF 文件可以增強視覺內容、提供附加上下文或在 PDF 文件中包含徽標和圖形。

#### Q：我可以將圖像新增到 PDF 文件中的特定頁面嗎？

答：是的，您可以指定要新增圖像的頁面。在提供的程式碼中，圖像被加入到 PDF 文件的第二頁。

#### Q：如何調整新增圖片的位置和大小？

答：您可以修改`lowerLeftX`, `lowerLeftY`, `upperRightX`， 和`upperRightY`程式碼中的變數用於設定圖像的座標並控制其大小和在頁面上的位置。

#### Q：使用此方法可以新增什麼類型的圖像格式？

答：提供的程式碼範例假設您正在載入 JPG 圖像（`aspose-logo.jpg`）。 Aspose.PDF for .NET 支援各種影像格式，包括 PNG、BMP、GIF 等。

#### Q：如何確保新增的影像符合指定的座標？

 A：一定要調整好座標和大小`Rectangle`目的 （`rectangle`以符合影像的尺寸及其在頁面上所需的位置。

#### Q：我可以將多個圖像新增到單一 PDF 頁面嗎？

答：是的，您可以透過對每個影像重複該過程並相應地調整座標和其他參數，將多個影像新增至單一 PDF 頁面。

#### 問：如何`GSave` and `GRestore` operator work in the code?

答： 的`GSave`操作符保存目前圖形狀態，讓您在不影響整體圖形上下文的情況下進行變更。這`GRestore`操作員在進行變更後恢復先前的圖形狀態。

#### Q：如果在指定路徑下找不到鏡像檔怎麼辦？

答：如果在指定路徑下沒有找到圖像文件，程式碼在嘗試載入圖像流時會拋出異常。確保圖像檔案位於正確的目錄中。

#### Q：我可以進一步自訂影像位置和外觀嗎？

答：是的，您可以透過修改`Matrix`物件並調整程式碼中的其他運算子。請參閱 Aspose.PDF 文件以進行進階自訂。

#### Q：如何測試影像是否成功加入PDF？

答：套用提供的程式碼新增影像後，開啟修改後的 PDF 檔案並驗證影像是否以正確的位置顯示在指定頁面上。

#### Q：新增圖片是否會影響PDF文件的原始內容？

答：新增影像不會影響PDF文件的原始內容。它透過包含視覺元素來增強文件。