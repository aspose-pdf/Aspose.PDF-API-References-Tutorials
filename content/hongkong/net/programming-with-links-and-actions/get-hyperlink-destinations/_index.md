---
title: 取得 PDF 檔案中的超連結目標
linktitle: 取得 PDF 檔案中的超連結目標
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 提取 PDF 檔案中的超連結目標。
type: docs
weight: 60
url: /zh-hant/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF for .NET 是一個功能強大的程式庫，用於使用 C# 程式語言操作和提取 PDF 文件中的資訊。在本教學中，我們將重點放在使用 Aspose.PDF for .NET 從 PDF 檔案中提取超連結目標。

## 先決條件

在開始之前，請確保您具備以下條件：

- 整合開發環境 (IDE)，例如 Visual Studio。
- 您的電腦上安裝了適用於 .NET 的 Aspose.PDF 庫。

## 第一步：建構開發環境

在開始編寫程式碼之前，您需要透過在您最喜歡的 IDE 中建立新的 C# 專案來設定開發環境。

## 第 2 步：導入 Aspose.PDF 參考文獻

若要使用 Aspose.PDF for .NET，您需要在您的專案中新增適當的參考。請依照以下步驟匯入必要的參考：

1. 在您的專案中，右鍵單擊“引用”並選擇“新增引用”。
2. 在「新增參考」視窗中，找到並選擇 Aspose.PDF for .NET 的 DLL 檔案。
3. 按一下「確定」將引用匯入到您的專案中。

## 第 3 步：載入 PDF 文件

在提取超連結目標之前，必須將 PDF 檔案載入到應用程式中。使用以下程式碼載入 PDF 檔案：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//載入 PDF 文件
Document document = new Document(dataDir + "input.pdf");
```

請務必指定文件目錄和要處理的 PDF 檔案的正確路徑。

## 步驟 4：瀏覽文件頁面

現在 PDF 文件已加載，您需要瀏覽文件的所有頁面。這將使您獲得

每個頁面上都有超連結註解。使用以下程式碼遍歷文件的頁面：

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     //取得特定頁面的連結註釋
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     //建立一個列表來儲存所有鏈接
     IList<Annotation> list = selector. Selected;
     //循環遍歷清單中的每個項目
     foreach(LinkAnnotation a in list)
     {
         //列印目標 URL
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

此程式碼循環遍歷文件的每個頁面並選擇每個頁面上存在的超連結註解。然後它將這些註釋儲存在清單中並列印每個連結的目標 URL。

## 步驟5：取得超連結目標

最後一步是從超連結註釋中提取超連結目的地。以下程式碼向您展示如何執行此操作：

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         //根據您的意願使用目的地
     }
}
```

在此程式碼中，我們從連結註解中取得每個超連結目標並將目標儲存在變數中。然後，您可以根據需要在應用程式中使用該目標。

### 使用 Aspose.PDF for .NET 取得超連結目標的範例原始碼 
```csharp
try
{
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//載入 PDF 文件
	Document document = new Document(dataDir + "input.pdf");
	//遍歷PDF的所有頁面
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		//取得特定頁面的連結註釋
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		//建立包含所有連結的列表
		IList<Annotation> list = selector.Selected;
		//遍歷列表中的單一項目
		foreach (LinkAnnotation a in list)
		{
			//列印目標 URL
			Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

### 在 PDF 文件中獲取超連結目標的常見問題解答

#### Q：PDF 文件中的超連結目標是什麼？

答：PDF 文件中的超連結目標是超連結指向的特定位置或目標。它可以是 URL、同一文檔中的頁面或外部文檔。

#### Q：提取超連結目標對我的 PDF 文件分析有何幫助？

答：提取超連結目標可讓您識別和編目 PDF 文件中超連結指向的所有目標。此資訊可用於內容驗證、連結驗證和資料分析。

#### Q：Aspose.PDF for .NET 如何協助擷取超連結目標？

答：Aspose.PDF for .NET 提供了強大的 API 來輕鬆擷取超連結目標。本教學逐步示範如何使用 C# 擷取超連結目標。

#### Q：我可以根據特定條件選擇性地提取超連結目的地嗎？

答：是的，您可以透過迭代 PDF 文件的頁面並根據您的條件過濾所需的超連結註釋來選擇性地提取超連結目標。

#### Q：是否可以從受密碼保護的 PDF 文件中提取超連結目標？

答：只要您在開啟文件時提供必要的驗證憑證，Aspose.PDF for .NET 就可以從受密碼保護的 PDF 文件中提取超連結目標。

#### Q：如何在我的應用程式中使用提取的超連結目標？

答：提取超連結目標後，您可以使用它們執行各種操作，例如驗證連結 URL、建立報告或實施自訂導覽。

#### Q：提取超連結目標時有什麼限制嗎？

答：雖然超連結目標提取功能很強大，但必須考慮 PDF 文件的結構。嵌入複雜圖形或多媒體內容中的超連結可能需要額外的處理。

#### Q：我可以提取超連結的其他屬性，例如連結類型或座標嗎？

答：本教學重點在於提取超連結目標。不過，您可以參考 Aspose.PDF 官方文件來探索進階功能，包括擷取連結類型和座標。