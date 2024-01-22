---
title: 使用 PDF 檔案中的段落旋轉文字
linktitle: 使用 PDF 檔案中的段落旋轉文字
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 使用 PDF 檔案中的段落旋轉文字。
type: docs
weight: 380
url: /zh-hant/net/programming-with-text/rotate-text-using-paragraph/
---
本教學介紹如何使用 Aspose.PDF for .NET 透過段落旋轉文字。提供的 C# 原始程式碼逐步演示了該過程。

## 先決條件

在繼續學習本教學之前，請確保您具備以下條件：

- C# 程式語言的基礎知識。
- 安裝了 Aspose.PDF for .NET 函式庫。您可以從 Aspose 網站取得它或使用 NuGet 將其安裝到您的專案中。

## 第 1 步：設定項目

首先在您首選的整合開發環境 (IDE) 中建立一個新的 C# 項目，並新增對 Aspose.PDF for .NET 程式庫的參考。

## 步驟2：導入必要的命名空間

在 C# 檔案的開頭新增以下 using 指令以匯入所需的命名空間：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Text.TextBuilder;
```

## 步驟 3：建立 PDF 文檔

初始化`Document`物件建立一個新的 PDF 文件：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

確保更換`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

## 第 4 步：新增頁面

使用以下命令從文件中取得特定頁面`Pages.Add()`方法：

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## 第 5 步：建立文字段落

創建一個`TextParagraph`物件並設定其在頁面上的位置：

```csharp
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
```

根據您的要求調整位置值。

## 第 6 步：建立並配置文字片段

創建多個`TextFragment`物件並設定其文字和屬性：

```csharp
TextFragment textFragment1 = new TextFragment("rotated text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.Rotation = 45;

TextFragment textFragment2 = new TextFragment("main text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment3 = new TextFragment("another rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = -45;
```

根據需要調整文字和其他屬性。

## 步驟 7：將文字片段附加到段落中

使用以下命令將建立的文字片段附加到段落中`AppendLine`方法：

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## 第 8 步：建立 TextBuilder 並附加段落

創建一個`TextBuilder`物件使用`pdfPage`並將文字段落附加到 PDF 頁面：

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
```

## 第9步：儲存PDF文檔

使用以下命令將修改後的 PDF 文件儲存到文件中`Save`方法：

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```

確保更換`"TextFragmentTests_Rotated2_out.pdf"`與所需的輸出檔名。

### 使用 Aspose.PDF for .NET 使用段落旋轉文字的範例原始碼 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
//初始化文檔對象
Document pdfDocument = new Document();
//取得特定頁面
Page pdfPage = (Page)pdfDocument.Pages.Add();
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
//建立文字片段
TextFragment textFragment1 = new TextFragment("rotated text");
//設定文字屬性
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
//設定旋轉
textFragment1.TextState.Rotation = 45;
//建立文字片段
TextFragment textFragment2 = new TextFragment("main text");
//設定文字屬性
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
//建立文字片段
TextFragment textFragment3 = new TextFragment("another rotated text");
//設定文字屬性
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
//設定旋轉
textFragment3.TextState.Rotation = -45;
//將文字片段附加到段落中
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
//建立 TextBuilder 對象
TextBuilder textBuilder = new TextBuilder(pdfPage);
//將文字段落附加到 PDF 頁面
textBuilder.AppendParagraph(paragraph);
//儲存文件
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```


## 結論

恭喜！您已成功學習如何使用 Aspose.PDF for .NET 在 PDF 文件中使用段落旋轉文字。本教學提供了從建立文件到儲存修改版本的逐步指南。現在，您可以將此程式碼合併到您自己的 C# 專案中，以操作 PDF 文件中的文字旋轉。

### 常見問題解答

#### 問：「使用段落旋轉文字」教學的目的是什麼？

答：「使用段落旋轉文字」教學課程旨在引導您完成使用 .NET 的 Aspose.PDF 庫使用 PDF 文件中的文字段落旋轉文字的過程。本教學提供了實現此功能的逐步說明和範例程式碼。

#### Q：「使用段落旋轉文字」是什麼意思？

答：使用段落旋轉文字是指使用文字段落對 PDF 文件中的文字套用旋轉的功能。此技術可讓您在 PDF 內容中以不同角度或位置定位文字。

#### Q：為什麼我要旋轉 PDF 文件中的文字？

答：旋轉 PDF 文件中的文字可用於多種目的，例如強調特定內容、創建藝術設計或改進佈局和可讀性。

#### Q：如何建立新的 PDF 文件？

答：要建立一個新的 PDF 文檔，請初始化`Document`來自 Aspose.PDF 庫的物件。您可以使用此物件為 PDF 新增頁面和內容。

#### Q：如何使用段落旋轉文字？

A：要使用段落旋轉文字：

1. 創建一個`TextParagraph`目的。
2. 創造`TextFragment`具有所需文字和旋轉角度的物件。
3. 將文字片段附加到文字段落。
4. 創建一個`TextBuilder`物件並將文字段落附加到特定的 PDF 頁面。

#### Q：我可以控制單一文字片段的旋轉角度嗎？

 A：是的，您可以控制單一的旋轉角度`TextFragment`對象透過設定`TextState.Rotation`財產。正值表示順時針旋轉，負值表示逆時針旋轉。

#### Q：我可以對同一段落內的不同文字片段套用不同的旋轉角度嗎？

答：是的，您可以對不同的應用應用不同的旋轉角度`TextFragment`透過設定同一段落中的對象`TextState.Rotation`每個片段對應的屬性。

#### Q：如何儲存旋轉後的 PDF 文件？

答：若要儲存旋轉的 PDF 文檔，請使用`Save`的方法`Document`物件並提供所需的輸出檔案路徑和名稱。