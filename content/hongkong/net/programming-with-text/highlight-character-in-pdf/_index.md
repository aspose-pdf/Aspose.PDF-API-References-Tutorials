---
title: 突出顯示 PDF 文件中的字符
linktitle: 突出顯示 PDF 文件中的字符
second_title: Aspose.PDF for .NET API 參考
description: 在這份全面的逐步指南中，學習使用 Aspose.PDF for .NET 來反白 PDF 中的字元。
type: docs
weight: 240
url: /zh-hant/net/programming-with-text/highlight-character-in-pdf/
---
## 介紹

在處理 PDF 時，經常需要突出顯示文字或字元 - 無論是出於學術目的、編輯還是只是提高可讀性。想像一下您有一份漂亮的文檔，但您想強調某些部分。這就是突出顯示的地方！在本教程中，我們將深入研究如何使用強大的 Aspose.PDF for .NET 庫突出顯示 PDF 文件中的字元。 

## 先決條件

在我們開始編寫程式碼之前，讓我們確保我們擁有所需的一切。這是您需要的：

1. 開發環境：本教學假設您正在使用 Visual Studio 或類似的 .NET IDE。
2.  Aspose.PDF for .NET Library：如果您還沒有，您可以[在這裡下載](https://releases.aspose.com/pdf/net/)並將其添加到您的項目中。 
3. C# 基礎知識：C# 程式設計入門將幫助您輕鬆理解其實現。
4. PDF 文件：您應該有一個可供使用的範例 PDF 文件。您可以建立一個或利用現有文件。

## 導入包

首先，我們需要導入必要的命名空間。為此，您需要將它們包含在 C# 檔案的頂部：

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Devices;
using Aspose.Pdf.Text;
using System;
using System.Drawing;
```

這些套件對於使用 Aspose 庫建立、操作和處理 PDF 文件至關重要。

現在，讓我們將該過程分解為易於理解的步驟，以突出顯示 PDF 中的字元。 

## 步驟1：初始化PDF文檔

第一步是初始化您的 PDF 文件。這涉及加載您將要使用的 PDF 文件。操作方法如下：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; //確保設定正確的路徑。
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```
在此程式碼片段中，替換`YOUR DOCUMENT DIRECTORY`輸入 PDF 檔案所在機器上的實際路徑。這`Aspose.Pdf.Document`類別被實例化以載入您的 PDF。

## 第 2 步：設定渲染過程

接下來，我們需要為文件準備渲染過程。這對於準確突出顯示頁面上的字元至關重要。

```csharp
int resolution = 150; //設定影像擷取的解析度。
using (MemoryStream ms = new MemoryStream())
{
    PdfConverter conv = new PdfConverter(pdfDocument);
    conv.Resolution = new Resolution(resolution, resolution);
    conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
    Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```
為了清晰起見，我們定義了一個分辨率，允許正確渲染文字。這`PdfConverter`將 PDF 頁面轉換為圖像，以便我們可以在上面繪圖。

## 第 3 步：建立用於繪圖的圖形對象

設定繪圖過程後，我們需要建立一個圖形對象，在其中執行突出顯示：

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
    float scale = resolution / 72f; //比例因子。
    gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
```
在這裡，我們從點陣圖影像創建圖形物件。此轉換有助於調整渲染以正確匹配所需的解析度。

## 第 4 步：循環瀏覽每一頁並突出顯示文本

現在，讓我們循環瀏覽 PDF 中的每個頁面，找到我們想要突出顯示的文字片段：

```csharp
for (int i = 0; i < pdfDocument.Pages.Count; i++)
{
    Page page = pdfDocument.Pages[i + 1]; // Aspose 中頁面的索引為 1。
    TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
    textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
    page.Accept(textFragmentAbsorber);
```
我們訪問每個頁面並使用以下命令查找所有文本`TextFragmentAbsorber`。正規表示式模式`@"[\S]+"`捕獲所有非空白字元。

## 步驟5：提取文字片段並反白顯示

現在是時候提取文字片段並突出顯示它們了。此過程涉及在我們想要突出顯示的字元周圍繪製矩形：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

foreach (TextFragment textFragment in textFragmentCollection)
{
    //此處突出邏輯
    for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
    {
        TextSegment segment = textFragment.Segments[segNum];
        for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
        {
            CharInfo characterInfo = segment.Characters[charNum];
            gr.DrawRectangle(Pens.Black, 
                (float)characterInfo.Rectangle.LLX, 
                (float)characterInfo.Rectangle.LLY, 
                (float)characterInfo.Rectangle.Width, 
                (float)characterInfo.Rectangle.Height);
        }
    }
}
```
我們循環遍歷每個文字片段、其片段和單個字符，並使用先前創建的圖形物件在它們周圍繪製矩形。

## 步驟6：儲存修改後的影像

突出顯示後，您需要將生成的圖像另存為新的 PNG 檔案：

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```
此行將修改後的點陣圖影像作為 PNG 檔案保存在指定目錄中。 

## 第 7 步：結束異常處理

最後，最好將程式碼包裝在 try-catch 區塊中，以確保我們優雅地處理任何意外錯誤：

```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get a 30-day temporary license from [here](https://buy.aspose.com/temporary-license/)。
}
```

此區塊捕獲過程中可能發生的任何異常，並向使用者提供資訊回饋。

## 結論

現在你就擁有了！您已使用 Aspose.PDF for .NET 成功地反白顯示了 PDF 檔案中的字元。這個強大的庫為 PDF 操作打開了無限可能的大門 - 無論您是在處理註釋、表單填寫，甚至文件轉換。當您繼續使用 Aspose 的旅程時，請記住練習是關鍵。不斷嘗試不同的功能，您很快就會成為 PDF 專家！

## 常見問題解答

### 什麼是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一個函式庫，允許在 .NET 應用程式中以程式設計方式建立、操作和轉換 PDF 文件。

### 我可以同時突出顯示多個文字片段嗎？
是的，所提供的程式碼可以透過循環瀏覽 PDF 中的所有文字來調整突出顯示多個片段。

### Aspose.PDF 有免費版嗎？
是的，Aspose 提供免費試用，因此您可以在購買之前測試該庫。

### 我需要任何許可證才能使用 Aspose.PDF 嗎？
是的，商業用途需要有效的許可證，但您可以獲得 30 天的臨時許可證進行測試。

### 在哪裡可以找到更多文件？
您可以參考[Aspose.PDF 文檔](https://reference.aspose.com/pdf/net/)有關實施和功能的更多詳細資訊。