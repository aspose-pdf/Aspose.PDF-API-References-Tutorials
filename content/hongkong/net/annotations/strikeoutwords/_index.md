---
title: 刪除單字
linktitle: 刪除單字
second_title: Aspose.PDF for .NET API 參考
description: 本文提供了使用 Aspose.PDF for .NET 的刪除單字功能的逐步指南，包括逐步指南和說明
type: docs
weight: 150
url: /zh-hant/net/annotations/strikeoutwords/
---
Aspose.PDF for .NET 是一個 PDF 文件操作和處理庫，它提供了創建、修改和轉換 PDF 文件的各種功能。 Aspose.PDF 提供的實用功能之一是能夠使用 C# 原始碼刪除 PDF 文件中的單字或短語。在本文中，我們將提供有關如何使用 Aspose.PDF for .NET 刪除單字的逐步指南。

## 第 1 步：載入 PDF 文檔
第一步是載入要修改的 PDF 文件。在本教學中，我們將從「您的文件目錄」資料夾中載入名為「input.pdf」的 PDF 文件。 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## 第二步：搜尋文字片段
要刪除 PDF 文件中的特定單字或短語，您首先需要搜尋它們。 Aspose.PDF提供了一個TextFragmentAbsorber類，可用來搜尋PDF文件中的特定文字片段。

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

在上面的程式碼中，我們正在 PDF 文件中搜尋文字片段“Estoque”。您可以修改此選項以搜尋您想要刪除的任何其他單字或短語。

## 第三步：刪除文字片段
找到文字片段後，下一步就是將它們刪除。 Aspose.PDF提供了一個StrikeOutAnnotation類，可用於為文字片段建立刪除線註解。 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

在上面的程式碼中，我們為找到的每個文字片段建立刪除線註解。我們還設定刪除線註釋的不透明度、邊框和顏色。

## 第四步：儲存修改後的PDF文檔
刪除文字片段後，儲存修改後的文件。

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 刪除單字的範例原始碼


```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟文件
Document document = new Document(dataDir + "input.pdf");

//建立 TextFragment Absorber 實例來搜尋特定文字片段
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
//遍歷 PDF 文件的頁面
for (int i = 1; i <= document.Pages.Count; i++)
{
	//取得PDF文件的第一頁
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

//建立吸收文字的集合
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//迭代上面的集合
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	//取得 TextFragment 物件的矩形尺寸
	Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
				(float)textFragment.Position.XIndent,
				(float)textFragment.Position.YIndent,
				(float)textFragment.Position.XIndent +
				(float)textFragment.Rectangle.Width,
				(float)textFragment.Position.YIndent +
				(float)textFragment.Rectangle.Height);

	//實例化刪除線註解實例
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	//設定註釋的不透明度
	strikeOut.Opacity = .80f;
	//設定註解實例的邊框
	strikeOut.Border = new Border(strikeOut);
	//設定註釋顏色
	strikeOut.Color = Aspose.Pdf.Color.Red;
	//將註解加入 TextFragment 的註解集合中
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 刪除 PDF 文件中的特定單字。透過遵循逐步指南並使用提供的 C# 原始程式碼，您可以輕鬆載入 PDF 文件、搜尋特定文字片段並建立刪除線註釋以直觀地標記和刪除這些單字。 Aspose.PDF for .NET 提供了一種簡單有效的方法來以程式設計方式操作 PDF 文檔，使其成為開發人員在 .NET 應用程式中處理 PDF 文件的寶貴工具。

### 常見問題解答

#### Q：什麼是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員在 .NET 應用程式中以程式設計方式建立、編輯和操作 PDF 文件。它提供了廣泛的處理 PDF 文件的功能，包括文字提取、註釋處理、表單填寫等等。

#### Q：我可以使用 Aspose.PDF for .NET 刪除 PDF 文件中的特定單字嗎？

答：是的，Aspose.PDF for .NET 提供了在 PDF 文件中搜尋特定文字片段的功能，然後建立刪除線註解以直觀地標記和刪除這些單字。

#### Q：如何在 PDF 文件中指定要刪除的文字？

答：要指定要刪除的文本，可以使用`TextFragmentAbsorber`Aspose.PDF for .NET 提供的類別。它允許您根據所需的條件在 PDF 文件中搜尋特定的文字片段。

#### Q：我可以自訂刪除線註解的外觀嗎？

答：是的，您可以自訂刪除線註解的各種屬性，例如不透明度、邊框樣式和顏色。這使您可以根據您的特定要求自訂刪除線註釋的外觀。