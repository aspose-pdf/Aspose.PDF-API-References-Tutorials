---
title: 提取 PDF 文件中突出顯示的文本
linktitle: 提取 PDF 文件中突出顯示的文本
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南，了解如何使用 Aspose.PDF for .NET 擷取 PDF 檔案中所反白的文字。
type: docs
weight: 60
url: /zh-hant/net/annotations/extracthighlightedtext/
---
要提取 PDF 文件中反白的文本，您可以使用 Aspose.PDF for .NET API。此 API 提供了一種簡單的方法來檢索文件中突出顯示的所有文字。

## 第 1 步：載入 PDF 文檔

提取 PDF 文件中反白的文字的第一步是使用 Aspose.PDF for .NET API 載入文件。您可以透過建立一個新實例來完成此操作`Document`類別並將 PDF 文件的路徑作為參數傳遞。 

```csharp
//文檔目錄的路徑。
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## 第 2 步：循環遍歷所有註釋

下一步是循環遍歷 PDF 文件中的所有註釋。您可以使用`foreach`循環，像這樣：

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	//代碼放在這裡
}
```

## 步驟 3：過濾文字標記註釋

在 - 的裡面`foreach`循環中，您需要過濾掉所有不是文字標記註解的註解。您可以透過檢查註釋是否是`TextMarkupAnnotation`班級。

```csharp
if (annotation is TextMarkupAnnotation)
{
	//代碼放在這裡
}
```

## 步驟 4：擷取反白的文字片段

過濾掉所有文字標記註解後，您可以檢索每個註解的突出顯示的文字片段。您可以透過呼叫來做到這一點`GetMarkedTextFragments()`方法上的`TextMarkupAnnotation`目的。

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## 第 5 步：顯示突出顯示的文本

最後，您可以向使用者顯示突出顯示的文字。您可以透過循環遍歷每個來完成此操作`TextFragment`對像在`TextFragmentCollection`並調用`Text`財產。

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### 使用 Aspose.PDF for .NET 擷取反白文字的範例原始程式碼

```csharp
//文檔目錄的路徑。
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");

foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	if (annotation is TextMarkupAnnotation)
	{
		TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
		TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
		foreach (TextFragment tf in collection)
		{
			Console.WriteLine(tf.Text);
		}
	}
}
```

## 結論

在本教學中，我們探討如何使用 Aspose.PDF for .NET 從 PDF 文件中提取反白的文字。透過遵循逐步指南並使用提供的 C# 原始程式碼，開發人員可以輕鬆提取和管理 PDF 文件中突出顯示的文字。

### 提取 PDF 文件中突出顯示文字的常見問題解答

#### Q：什麼是 PDF 文件中的文字標記註釋？

答：文字標記註解是反白或標記 PDF 文件中特定文字的註解。文字標記註解的範例包括突出顯示、底線和刪除線。

#### Q：我可以使用 Aspose.PDF for .NET 從其他類型的註解中提取文字嗎？

答：是的，Aspose.PDF for .NET 提供了多種方法從不同類型的註釋中提取文本，包括文本標記註釋、自由文本註釋等。

#### Q：Aspose.PDF for .NET 支援從受密碼保護的 PDF 檔案中提取文字嗎？

答：是的，Aspose.PDF for .NET 支援從受密碼保護的 PDF 檔案中提取文字。使用以下方式載入 PDF 文件時需要提供正確的密碼`Document`班級。

#### Q：我可以根據其他條件（例如顏色或作者）過濾突出顯示的文字嗎？

答：是的，您可以根據其他條件（例如顏色、作者或建立日期）過濾突出顯示的文字。 Aspose.PDF for .NET 提供了一種根據屬性存取和過濾註解的方法。

#### Q：是否可以將提取的突出顯示文字儲存到單獨的文件中？

答：是的，您可以將提取的突出顯示文字儲存到單獨的文件中或將其儲存在資料結構中以供進一步處理或分析。
