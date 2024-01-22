---
title: 在 PDF 檔案中使用文字段落和生成器旋轉文字
linktitle: 在 PDF 檔案中使用文字段落和生成器旋轉文字
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中使用文字段落和生成器旋轉文字。
type: docs
weight: 410
url: /zh-hant/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---
本教學課程說明如何使用 Aspose.PDF for .NET 使用 PDF 檔案中的文字段落和建構器來旋轉文字。提供的 C# 原始程式碼逐步演示了該過程。

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

## 第 5 步：建立並旋轉文字段落

創建一個`for`循環產生具有不同旋轉的多個文字段落：

```csharp
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	paragraph.Rotation = i * 90 + 45;
```

根據您的要求調整位置和旋轉值。

## 第 6 步：建立並配置文字片段

創建多個`TextFragment`對象，設定它們的文字和屬性：

```csharp
TextFragment textFragment1 = new TextFragment("Paragraph Text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment2 = new TextFragment("Second line of text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment3 = new TextFragment("And some more text...");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
textFragment3.TextState.Underline = true;
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
}
```

## 第9步：儲存PDF文檔

使用以下命令將修改後的 PDF 文件儲存到文件中`Save`方法：

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

確保更換`"TextFragmentTests_Rotated4_out.pdf"`與所需的輸出檔名。

### 使用 Aspose.PDF for .NET 使用文字段落和生成器旋轉文字的範例原始程式碼 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
//初始化文檔對象
Document pdfDocument = new Document();
//取得特定頁面
Page pdfPage = (Page)pdfDocument.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	//指定旋轉
	paragraph.Rotation = i * 90 + 45;
	//建立文字片段
	TextFragment textFragment1 = new TextFragment("Paragraph Text");
	//建立文字片段
	textFragment1.TextState.FontSize = 12;
	textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	//建立文字片段
	TextFragment textFragment2 = new TextFragment("Second line of text");
	//設定文字屬性
	textFragment2.TextState.FontSize = 12;
	textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	//建立文字片段
	TextFragment textFragment3 = new TextFragment("And some more text...");
	//設定文字屬性
	textFragment3.TextState.FontSize = 12;
	textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	textFragment3.TextState.Underline = true;
	paragraph.AppendLine(textFragment1);
	paragraph.AppendLine(textFragment2);
	paragraph.AppendLine(textFragment3);
	//建立 TextBuilder 對象
	TextBuilder textBuilder = new TextBuilder(pdfPage);
	//將文字片段附加到 PDF 頁面
	textBuilder.AppendParagraph(paragraph);
}
//儲存文件
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

## 結論

恭喜！您已成功學習如何使用 Aspose.PDF for .NET 在 PDF 文件中使用文字段落和建構器來旋轉文字。本教學提供了從建立文件到儲存修改版本的逐步指南。現在，您可以將此程式碼合併到您自己的 C# 專案中，以操作 PDF 文件中的文字旋轉。

### 常見問題解答

#### Q：「使用文字段落和生成器旋轉文字」教學的目的是什麼？

答：「使用文字段落和生成器旋轉文字」教學提供了有關如何使用 Aspose.PDF .NET 庫在 PDF 文件中使用文字段落和生成器旋轉文字的全面指南。本教程示範了逐步說明，並包含用於透過段落和自訂格式實現文字旋轉的範例 C# 程式碼。

#### Q：本教學與之前的文字旋轉教學有何不同？

A：與先前的教學不同，本教學結合了文字段落、建構器和旋轉角度的使用，實現了更進階的文字旋轉效果。它示範如何產生具有不同旋轉角度的多個文字段落並將自訂格式套用至個別文字片段。

#### Q：使用文字段落和建構器進行文字旋轉有何意義？

答：使用文字段落和建構器可以增強對文字旋轉和格式設定的控制。文字段落提供了組織文字片段的結構化方式，而建構器則有助於在 PDF 文件中建立和操作文字內容。

#### Q：我可以對每個文字段落應用不同的旋轉角度嗎？

答：是的，您可以透過設定對每個文字段落套用不同的旋轉角度`Rotation`的財產`TextParagraph`目的。這允許您在 PDF 文件中建立多樣化的動態文字旋轉效果。

#### Q：如何自訂文字段落中文字片段的格式？

答：您可以透過設定文字片段的各種屬性來自訂文字片段的格式。`TextState`每個內`TextFragment`目的。可以調整字體大小、字體類型、前景色和背景色以及底線等屬性，以達到所需的視覺效果。

#### Q：我可以使用此方法創建更複雜的文字旋轉效果嗎？

答：當然。透過迭代建立具有不同旋轉角度和格式選項的多個文字段落，您可以實現複雜且具有視覺吸引力的文字旋轉效果，從而增強 PDF 文件的可讀性和美觀性。

#### Q：是否可以將文字旋轉與其他文字操作技術結合？

答：是的，您可以將文字旋轉與 Aspose.PDF 庫提供的其他文字操作技術結合。這包括添加表格、圖像、超連結等以建立豐富且資訊豐富的 PDF 文件。

#### Q：我需要特殊許可證才能在我的專案中使用 Aspose.PDF 庫嗎？

答：是的，您需要有效的 Aspose 許可證才能在專案中使用 Aspose.PDF 庫。您可以從 Aspose 網站取得許可證，該網站將為您提供有效整合和使用該庫所需的憑證。