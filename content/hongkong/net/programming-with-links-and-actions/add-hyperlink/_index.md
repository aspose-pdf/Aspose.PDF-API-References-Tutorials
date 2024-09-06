---
title: 在 PDF 文件中添加超鏈接
linktitle: 在 PDF 文件中添加超鏈接
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 在 PDF 檔案中輕鬆新增互動式超連結。
type: docs
weight: 10
url: /zh-hant/net/programming-with-links-and-actions/add-hyperlink/
---
在 PDF 文件中新增超連結可讓您建立指向文件中其他頁面、網站或目標的互動式超連結。使用Aspose.PDF for .NET，您可以輕鬆地依照以下原始程式碼新增超連結：

## 步驟1：導入所需的庫

在開始之前，您需要為 C# 專案匯入必要的程式庫。這是必要的導入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

## 步驟 2：設定文件資料夾路徑

在此步驟中，您需要指定包含要新增超連結的 PDF 檔案的資料夾的路徑。代替`"YOUR DOCUMENT DIRECTORY"`在以下程式碼中使用文件資料夾的實際路徑：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步驟 3：開啟 PDF 文檔

現在我們將使用以下程式碼開啟要新增超連結的 PDF 文件：

```csharp
Document document = new Document(dataDir + "AddHyperlink.pdf");
```

## 第 4 步：建立連結

在此步驟中，我們將使用以下命令建立超鏈接`LinkAnnotation`註解。我們將指定聯絡方式和連結區域、連結類型和連結內容。這是對應的程式碼：

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
Border border = new Border(link);
border. Width = 0;
link. Border = border;
link. Action = new GoToURIAction("www.aspose.com");
page.Annotations.Add(link);
```

## 第 5 步：新增附加文本

除了超連結之外，我們還可以使用以下命令添加其他文本`FreeTextAnnotation`註解。我們將指定座標、文字外觀和文字內容。這是對應的程式碼：

```csharp
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System .Drawing.Color.Blue));
textAnnotation.Contents = "Link to Aspose website";
textAnnotation. Border = border;
document.Pages[1].Annotations.Add(textAnnotation);
```

## 第 6 步：儲存更新的文件

現在讓我們使用以下命令儲存更新後的 PDF 文件`Save`的方法`document`目的。這是對應的程式碼：

```csharp
dataDir = dataDir + "AddHyperlink_out.pdf";
document. Save(dataDir);
```

### 使用 Aspose.PDF for .NET 新增超連結的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document document = new Document(dataDir + "AddHyperlink.pdf");
//建立連結
Page page = document.Pages[1];
//建立連結註釋對象
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
//為 LinkAnnotation 建立邊框對象
Border border = new Border(link);
//將邊框寬度值設為0
border.Width = 0;
//設定 LinkAnnotation 的邊框
link.Border = border;
//將連結類型指定為遠端 URI
link.Action = new GoToURIAction("www.aspose.com");
//將連結註解加入PDF文件第一頁的註解集合中
page.Annotations.Add(link);
//創作自由文字註釋
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System.Drawing.Color.Blue));
//要添加為自由文本的字串
textAnnotation.Contents = "Link to Aspose website";
//設定自由文字註釋的邊框
textAnnotation.Border = border;
//將 FreeText 註解新增至文件首頁的註解集合中
document.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddHyperlink_out.pdf";
//儲存更新的文檔
document.Save(dataDir);
Console.WriteLine("\nHyperlink added successfully.\nFile saved at " + dataDir);            
```

## 結論

恭喜！現在您已經有了使用 Aspose.PDF for .NET 新增超連結的逐步指南。您可以使用此程式碼在 PDF 文件中建立互動式連結。

### 在 PDF 文件中添加超連結的常見問題解答

#### Q：為什麼我應該考慮在 PDF 文件中添加超連結？

答：在 PDF 文件中新增超連結可以讓讀者輕鬆導覽到文件中的其他頁面、網站或目的地，從而增強使用者體驗。它提供了一種無縫的方式來存取其他資源或相關資訊。

#### Q：Aspose.PDF for .NET 適合初學者嗎？

答：是的，Aspose.PDF for .NET 適合初學者。本指南中提供的逐步教學簡化了在 PDF 文件中添加超連結的過程，使不同技能水平的開發人員都可以使用它。

#### Q：我可以自訂超連結的外觀嗎？

答：當然！ Aspose.PDF for .NET 提供超連結外觀的自訂選項，包括文字顏色、樣式和格式。這使您可以將超連結與文件的整體設計相匹配。

#### Q：所有類型的 PDF 文件都支援超連結嗎？

答：是的，可以將超連結新增到各種類型的 PDF 文件中，包括基於文字的文件、圖像和富含多媒體的文件。 Aspose.PDF for .NET 確保超連結在不同的 PDF 格式中都能正常運作。

#### Q：Aspose.PDF for .NET 還提供哪些其他功能？

答：Aspose.PDF for .NET 是一個強大的函式庫，提供了廣泛的功能，包括 PDF 產生、操作、轉換和提取。它支援處理文字、圖像、註釋等，使其成為執行 PDF 相關任務的多功能工具。

#### Q：可以將超連結新增到文件中的特定部分嗎？

答：是的，使用`LinkAnnotation`透過註釋，您可以建立超鏈接，將使用者引導至 PDF 文件中的特定部分。此功能對於建立互動式目錄或參考連結特別有用。

#### Q：在 PDF 檔案中新增超連結有什麼限制嗎？

答：雖然 Aspose.PDF for .NET 提供了全面的超連結功能，但確保連結內容保持可存取且最新也很重要。應定期驗證外部網站的超鏈接，以避免連結損壞。

#### Q：我可以使用 Aspose.PDF for .NET 建立指向外部文件的超連結嗎？

答：是的，除了 Web URL 之外，您還可以建立指向外部文件的超鏈接，例如其他 PDF 文件、圖像或多媒體文件。 Aspose.PDF for .NET 提供了連結到各種類型資源的彈性。