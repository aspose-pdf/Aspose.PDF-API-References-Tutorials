---
title: 提取 PDF 檔案中的段落
linktitle: 提取 PDF 檔案中的段落
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 擷取 PDF 檔案中的段落。
type: docs
weight: 160
url: /zh-hant/net/programming-with-text/extract-paragraphs/
---
本教學將引導您完成使用 Aspose.PDF for .NET 提取 PDF 文件中的段落的過程。提供的 C# 原始程式碼演示了必要的步驟。

## 要求
在開始之前，請確保您具備以下條件：

- Visual Studio 或電腦上安裝的任何其他 C# 編譯器。
- Aspose.PDF for .NET 函式庫。您可以從 Aspose 官方網站下載它或使用 NuGet 等套件管理器來安裝它。

## 第 1 步：設定項目
1. 在您首選的開發環境中建立一個新的 C# 專案。
2. 新增對 Aspose.PDF for .NET 函式庫的參考。

## 步驟2：導入所需的命名空間
在要提取段落的程式碼檔案中，在檔案頂部加入以下 using 指令：

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## 第三步：設定文檔目錄
在程式碼中，找到顯示以下內容的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`以及儲存文檔的目錄的路徑。

## 步驟 4：開啟 PDF 文檔
使用以下命令開啟現有 PDF 文檔`Document`建構函數並將路徑傳遞給輸入 PDF 檔案。

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 第五步：提取段落
實例化`ParagraphAbsorber`類別並使用它的`Visit`從文件中提取段落的方法。

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## 第 6 步：遍歷段落
循環瀏覽提取的段落以存取文字內容。使用巢狀循環遍歷每個段落中的部分和行。

```csharp
foreach(PageMarkup markup in absorber.PageMarkups)
{
     int i = 1;
     foreach(MarkupSection section in markup.Sections)
     {
         int j = 1;
         foreach(MarkupParagraph paragraph in section.Paragraphs)
         {
             StringBuilder paragraphText = new StringBuilder();
             foreach(List<TextFragment> line in paragraph.Lines)
             {
                 foreach(TextFragment fragment in line)
                 {
                     paragraphText.Append(fragment.Text);
                 }
                 paragraphText. Append("\r\n");
             }
             paragraphText. Append("\r\n");
             Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
             Console.WriteLine(paragraphText.ToString());
             j++;
         }
         i++;
     }
}
```

### 使用 Aspose.PDF for .NET 擷取段落的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟現有的 PDF 文件
Document doc = new Document(dataDir + "input.pdf");
//實例化 ParagraphAbsorber
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
foreach (PageMarkup markup in absorber.PageMarkups)
{
	int i = 1;
	foreach (MarkupSection section in markup.Sections)
	{
		int j = 1;
		foreach (MarkupParagraph paragraph in section.Paragraphs)
		{
			StringBuilder paragraphText = new StringBuilder();
			foreach (List<TextFragment> line in paragraph.Lines)
			{
				foreach (TextFragment fragment in line)
				{
					paragraphText.Append(fragment.Text);
				}
				paragraphText.Append("\r\n");
			}
			paragraphText.Append("\r\n");
			Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
			Console.WriteLine(paragraphText.ToString());
			j++;
		}
		i++;
	}
}
```

## 結論
您已使用 Aspose.PDF for .NET 成功從 PDF 文件中擷取段落。提取的段落已顯示在控制台視窗中。

### 常見問題解答

#### Q：本教學的目的是什麼？

答：本教學課程旨在引導您完成使用 Aspose.PDF for .NET 從 PDF 檔案中擷取段落的過程。隨附的 C# 原始程式碼提供了實現此任務的實用步驟。

#### Q：我應該導入哪些命名空間？

答：在要擷取段落的程式碼檔案中，在檔案開頭包含以下 using 指令：

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### Q：如何指定文檔目錄？

答：找到該線`string dataDir = "YOUR DOCUMENT DIRECTORY";`在代碼中並替換`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

#### Q：如何開啟現有的 PDF 文件？

答：在步驟 4 中，您將使用以下命令開啟現有的 PDF 文件：`Document`建構函數並提供輸入 PDF 檔案的路徑。

#### Q：如何從文件中提取段落？

答：第 5 步涉及建立一個實例`ParagraphAbsorber`類別並使用它的`Visit`從 PDF 文件中提取段落的方法。

#### 問：如何迭代擷取的段落？

答：第 6 步將引導您循環瀏覽提取的段落。巢狀循環用於遍歷每個段落中的節和行，最終存取和顯示文字內容。

#### Q：本教程的主要內容是什麼？

答：透過學習本教學課程，您已經了解如何使用 Aspose.PDF for .NET 從 PDF 文件中擷取段落。提取的段落已顯示在控制台視窗中，為您提供對文件內容結構的寶貴見解。