---
title: 在 PDF 檔案中加入帶有底紋顏色的文本
linktitle: 在 PDF 檔案中加入帶有底紋顏色的文本
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中新增帶有底紋顏色的文字。
type: docs
weight: 80
url: /zh-hant/net/programming-with-text/add-text-with-shading-colors/
---
本教學將引導您使用 Aspose.PDF for .NET 在 PDF 檔案中新增帶有底紋顏色的文字的過程。提供的 C# 原始程式碼演示了必要的步驟。

## 要求
在開始之前，請確保您具備以下條件：

- Visual Studio 或電腦上安裝的任何其他 C# 編譯器。
- Aspose.PDF for .NET 函式庫。您可以從 Aspose 官方網站下載它或使用 NuGet 等套件管理器來安裝它。

## 第 1 步：設定項目
1. 在您首選的開發環境中建立一個新的 C# 專案。
2. 新增對 Aspose.PDF for .NET 函式庫的參考。

## 步驟2：導入所需的命名空間
在要新增有底紋顏色的文字的程式碼檔案中，在檔案頂部新增以下 using 指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## 第三步：設定文檔目錄
在程式碼中，找到顯示以下內容的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`以及儲存文檔的目錄的路徑。

## 第 4 步：載入 PDF 文檔
使用以下命令載入現有 PDF 文檔`Document`建構函數並提供文檔文件的路徑。

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     //代碼放在這裡...
}
```

## 第五步：找到要修改的文字
使用`TextFragmentAbsorber`在文件中尋找所需的文字。在提供的程式碼中，它會尋找文字“Lorem ipsum”。

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## 步驟6：設定文字的底紋顏色
創建一個新的`Color`具有圖案色彩空間的物件並指定漸層著色顏色。將此顏色指定給`ForegroundColor`的財產`TextState`的`TextFragment`目的。

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## 第 7 步：套用其他文字格式（可選）
您可以透過修改文字片段的屬性，對文字片段套用其他格式，例如底線。`TextState`目的。

```csharp
textFragment.TextState.Underline = true;
```

## 步驟8：儲存修改後的PDF文檔
使用以下命令儲存修改後的 PDF 文檔`Save`的方法`Document`目的。

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### 使用 Aspose.PDF for .NET 新增帶有底紋顏色的文字的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	//使用圖案色彩空間創造新顏色
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## 結論
您已使用 Aspose.PDF for .NET 成功將帶有底紋顏色的文字新增至 PDF 文件中。現在可以在指定的輸出檔案路徑中找到產生的 PDF 檔案。

### 常見問題解答

#### Q：本教程的主要重點是什麼？

答：本教學將引導您完成使用 Aspose.PDF for .NET 函式庫將帶有底紋顏色的文字新增至 PDF 檔案的過程。提供的 C# 原始程式碼演示了實現此目的的必要步驟。

#### Q：本教學需要導入哪些命名空間？

答：在要新增帶有底紋顏色的文字的程式碼檔案中，在檔案開頭匯入以下命名空間：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### Q：如何指定文檔目錄？

 A：在程式碼中，找到行`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

#### Q：如何載入現有的 PDF 文件？

答：在步驟 4 中，您將使用以下命令載入現有的 PDF 文件：`Document`建構函數並提供文檔文件的路徑：

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     //代碼放在這裡...
}
```

#### Q：如何尋找和修改 PDF 文件中的特定文字？

答：在步驟 5 中，您將使用`TextFragmentAbsorber`在文件中尋找所需的文字。然後，您可以修改其屬性：

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### Q：如何設定文字的底紋顏色？

答：在步驟 6 中，您將建立一個新的`Color`具有圖案色彩空間的物件並指定漸層著色顏色。將此顏色指定給`ForegroundColor`的財產`TextState`的`TextFragment`目的：

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### Q：我可以對修改後的文字套用其他文字格式嗎？

答：是的，在步驟 7 中，您可以透過修改文字的屬性來套用其他文字格式，例如底線。`TextState`目的：

```csharp
textFragment.TextState.Underline = true;
```

#### Q：如何儲存修改後的PDF文件？

答：在步驟 8 中，您將使用以下命令儲存修改後的 PDF 文件：`Save`的方法`Document`目的：

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### Q：本教程的主要內容是什麼？

答：透過學習本教學課程，您已經成功學會如何使用 Aspose.PDF for .NET 新增帶有底紋顏色的文字來增強 PDF 文件。這對於突出顯示和強調 PDF 文件中的特定文字內容特別有用。