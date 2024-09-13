---
title: 在 PDF 檔案中新增圖像
linktitle: 在 PDF 檔案中新增圖像
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 以程式設計方式將影像新增至 PDF 檔案。包含逐步指南、範例程式碼和常見問題解答，可實現無縫實施。
type: docs
weight: 10
url: /zh-hant/net/programming-with-images/add-image/
---
## 介紹

有沒有想過如何以程式設計方式將影像插入 PDF 檔案？無論您是開發文件產生系統還是在 PDF 文件中新增品牌元素，Aspose.PDF for .NET 都能讓一切變得異常簡單。讓我們深入了解如何使用 Aspose.PDF for .NET 將影像新增至 PDF 的逐步教學。

## 先決條件

在開始編寫程式碼之前，讓我們快速瀏覽一下入門所需的基本要求：

- Aspose.PDF for .NET 函式庫：從下列位置下載並安裝最新版本[這裡](https://releases.aspose.com/pdf/net/).
- .NET 開發環境：Visual Studio 或您選擇的任何其他 IDE。
- C#基礎知識：熟悉基本的C#程式設計與物件導向原理。
- PDF 和圖像檔案：範例 PDF 檔案和要插入的圖像。

## 導入所需的套件

要開始使用 Aspose.PDF，您需要匯入必要的命名空間。您可以這樣做：

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

這些匯入將幫助您與 PDF 文件互動、操作其內容並有效處理文件流。

現在，讓我們將向 PDF 文件添加圖像的任務分解為易於執行的步驟。

## 步驟1：設定文檔路徑並開啟PDF

在添加圖像之前，您需要做的第一件事是找到您的 PDF 文件並將其打開。這是完成該任務的程式碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟文件
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```
這`Document`Aspose.PDF 中的類別用於開啟和處理現有的 PDF 檔案。您需要指定 PDF 所在的目錄路徑。

## 第 2 步：定義圖像座標

要在 PDF 中正確定位影像，您需要設定其顯示位置的座標。這可以透過指定影像矩形的左下角和右上角來完成。

```csharp
//設定座標
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```
這些座標定義了圖像在頁面上的放置位置。左下座標 (100, 100) 表示起點，右上座標 (200, 200) 定義影像的大小和終點。

## 步驟 3：選擇要插入影像的頁面

接下來，您需要指定要將影像新增至 PDF 中的哪一頁。 Aspose.PDF 允許您使用從零開始的索引來存取文件中的任何頁面。

```csharp
//取得需要新增圖片的頁面
Page page = pdfDocument.Pages[1];
```
在此範例中，我們將圖像新增至 PDF 的第一頁（頁面[1] 指的是第一頁，因為它是基於單的索引）。

## 第 4 步：將圖像載入到流中

現在，將圖像從目錄載入到流中，以便可以對其進行處理並將其插入到 PDF 中。

```csharp
//將圖像載入到流中
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```
這`FileStream`類別用於開啟圖像檔案。圖像檔（`aspose-logo.jpg`）從指定目錄載入並以讀取模式開啟（`FileMode.Open`）。

## 第5步：將影像新增至PDF頁面資源

將圖像載入到流中後，您可以將其新增至 PDF 的頁面資源。

```csharp
//將圖像新增至頁面資源的圖像集合
page.Resources.Images.Add(imageStream);
```
此步驟將圖像新增至頁面的資源集合。該圖像現在可用於在頁面上呈現。

## 第6步：儲存目前圖形狀態

在將圖像放置到頁面上之前，您應該使用以下命令保存當前圖形狀態`GSave`操作員。這可確保套用於影像的任何轉換不會影響文件的其餘部分。

```csharp
//使用GSave運算子：此運算子儲存目前圖形狀態
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```
這`GSave`操作員保存當前的圖形設置，稍後允許您恢復它們，確保圖像放置不會幹擾頁面上的其他內容。

## 步驟 7：使用矩形和矩陣定義影像位置

現在，建立一個`Rectangle`定義圖像在頁面上的位置的物件和`Matrix`來控制放置和縮放。

```csharp
//建立矩形和矩陣對象
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```
這`Rectangle`定義 PDF 頁面上圖像的座標，以及`Matrix`確保正確的縮放和定位。

## 步驟 8：連接影像放置矩陣

這`ConcatenateMatrix`運算子用於應用矩陣變換，確保影像放置正確。

```csharp
//使用ConcatenateMatrix（連接矩陣）運算子：定義影像的放置方式
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```
此轉換可確保使用定義的矩陣值將影像放置在頁面上的正確位置。

## 第 9 步：在 PDF 頁面上渲染圖像

最後，使用`Do`操作符將圖像實際渲染到 PDF 頁面上。

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
//使用 Do 運算子：此運算子繪製影像
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```
這`Do`運算子在先前矩陣變換定義的位置繪製影像。

## 步驟10：恢復圖形狀態

新增圖像後，使用以下命令恢復先前的圖形狀態`GRestore`操作員。

```csharp
//使用GRestore運算子：此運算子恢復圖形狀態
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```
此步驟可確保撤銷圖形狀態所做的任何變更（例如變換或縮放），從而保持文件的其餘部分不受影響。

## 第11步：儲存更新後的PDF文檔

最後，將帶有新添加圖像的 PDF 儲存到文件中。

```csharp
dataDir = dataDir + "AddImage_out.pdf";
//儲存更新的文檔
pdfDocument.Save(dataDir);
```
這`Save`方法用於保存新增了影像的PDF文檔，更新後的文件以「AddImage_out.pdf」名稱儲存。

## 結論

當您逐步分解時，使用 Aspose.PDF for .NET 將圖片插入 PDF 檔案是非常簡單的。透過使用各種運算符，例如`GSave`, `ConcatenateMatrix`， 和`Do`，您可以輕鬆控制 PDF 文件中影像的放置和渲染。此技術對於使用徽標、浮水印或任何其他圖像自訂和品牌化 PDF 文件至關重要。

## 常見問題解答

### 我可以將多個圖像新增到單一頁面嗎？  
是的，您可以透過重複載入和放置每個圖像的步驟來將多個圖像新增到同一頁面。

### 如何控制插入影像的大小？  
圖像大小由矩形座標控制（`lowerLeftX`, `lowerLeftY`, `upperRightX`, `upperRightY`）。

### 我可以插入其他文件類型（例如 PNG 或 GIF）嗎？  
是的，Aspose.PDF 支援各種圖片格式，包括 PNG、GIF、BMP 和 JPEG。

### 可以動態新增圖片嗎？  
是的，您可以透過提供檔案路徑或使用流來動態載入和插入圖像。

### Aspose.PDF是否允許將影像批次新增至多個頁面？  
是的，您可以循環瀏覽文件中的頁面，並使用相同的方法將圖像新增至多個頁面。