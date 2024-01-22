---
title: 在 PDF 文件中建立本地超鏈接
linktitle: 在 PDF 文件中建立本地超鏈接
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 在 PDF 檔案中輕鬆建立本機超連結。
type: docs
weight: 40
url: /zh-hant/net/programming-with-links-and-actions/create-local-hyperlink/
---
在 PDF 文件中建立本地超鏈接可讓您創建可單擊的鏈接，將用戶帶到同一 PDF 文件中的其他頁面。使用 Aspose.PDF for .NET，您可以輕鬆地按照以下原始程式碼建立此類連結：

## 第 1 步：導入所需的庫

在開始之前，您需要為 C# 專案匯入必要的程式庫。這是必要的導入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## 步驟 2：設定文件資料夾路徑

在此步驟中，您需要指定要儲存產生的 PDF 檔案的資料夾的路徑。代替`"YOUR DOCUMENT DIRECTORY"`在以下程式碼中使用文件資料夾的實際路徑：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步驟 3：建立 Document 實例

我們將建立一個實例`Document`類別來表示我們的 PDF 文件。這是對應的程式碼：

```csharp
Document doc = new Document();
```

## 步驟 4：新增帶有超連結的頁面和文本

在此步驟中，我們將向 PDF 文件新增頁面並新增一些包含本機超連結的文字。我們將為每個連結定義目標頁面。這是對應的程式碼：

```csharp
Page page = doc.Pages.Add();

TextFragment text = new TextFragment("Link to page 7");
LocalHyperlink link = new LocalHyperlink();
link.TargetPageNumber = 7;
text. Hyperlink = link;
page.Paragraphs.Add(text);

text = new TextFragment("Link to page 1");
text. IsInNewPage = true;
link = new LocalHyperlink();
link.TargetPageNumber = 1;
text. Hyperlink = link;
page.Paragraphs.Add(text);
```

## 步驟 5：儲存更新後的文檔

現在讓我們使用以下命令儲存更新後的 PDF 文件`Save`的方法`doc`目的。這是對應的程式碼：

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 建立本機超連結的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//建立文件實例
Document doc = new Document();
//將頁面新增至 PDF 檔案的頁面集合
Page page = doc.Pages.Add();
//建立文字片段實例
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
//建立本地超連結實例
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
//設定連結實例的目標頁面
link.TargetPageNumber = 7;
//設定 TextFragment 超鏈接
text.Hyperlink = link;
//將文字加入頁面的段落集合中
page.Paragraphs.Add(text);
//建立新的 TextFragment 實例
text = new TextFragment("link page number test to page 1");
//TextFragment 應新增到新頁面上
text.IsInNewPage = true;
//建立另一個本地超連結實例
link = new LocalHyperlink();
//設定第二個超連結的目標頁面
link.TargetPageNumber = 1;
//設定第二個 TextFragment 的鏈接
text.Hyperlink = link;
//將文字加入到頁面物件的段落集合中
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
//儲存更新的文檔
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## 結論

恭喜！現在您有了使用 Aspose.PDF for .NET 在 PDF 中建立本機超連結的逐步指南。您可以使用此程式碼建立可點擊的鏈接，將使用者帶到同一文件中的其他頁面。

請務必查看官方 Aspose.PDF 文檔，以獲取有關高級超連結功能的更多資訊。

### 在 PDF 檔案中建立本地超連結的常見問題解答

#### Q：什麼是 PDF 檔案中的本地超連結？

答：PDF 文件中的本機超鏈接是可單擊的鏈接，可將使用者導航到同一文件中的不同頁面。這些連結增強了導航功能，使讀者能夠快速存取相關部分。

#### Q：本地超連結對我的 PDF 文件有何好處？

答：本機超連結提供了一種有效的方式來連接同一 PDF 文件中的相關內容。它們使讀者能夠快速跳到特定部分，而無需滾動瀏覽整個文檔，從而改善用戶體驗。

#### Q：Aspose.PDF for .NET 如何支援本機超連結的建立？
答：Aspose.PDF for .NET 為建立本機超連結提供全面支援。本指南中提供的逐步教學示範如何使用 C# 將本機超連結新增至 PDF 文件。

#### Q：我可以自訂本地超連結的外觀嗎？

答：是的，您可以自訂本地超連結的外觀，包括文字顏色和樣式，以確保它們符合文件的設計並提供一致的視覺體驗。

#### Q：是否可以在單一 PDF 頁面中建立多個本地超連結？

答：當然！您可以在單一 PDF 頁面中建立多個本地超鏈接，讓讀者可以根據需要跳到各個部分或頁面。每個本地超連結都可以根據其各自的目標進行自訂。

#### Q：我可以使用本地超連結連結到頁面的特定部分嗎？

答：雖然本機超連結通常會導航到整個頁面，但您可以在 PDF 文件中建立錨點或書籤以實現有針對性的連結。 Aspose.PDF for .NET 支援各種超連結選項。

#### Q：如何驗證本機超連結是否正常運作？

答：按照提供的教學和範例程式碼，您可以自信地建立功能性本地超連結。您可以透過開啟產生的 PDF 文件並點擊超連結文字來測試連結。

#### Q：使用本地超連結有什麼限制嗎？

答：本機超連結是增強文件導覽的有效方法，但確保文件結構保持清晰直覺也很重要。正確標記的超連結和錨點有助於提供正面的使用者體驗。

#### Q：我可以在表格或圖像中建立本地超連結嗎？

答：是的，您可以在 PDF 文件的各種元素（包括表格、圖像和文字）中建立本機超連結。 Aspose.PDF for .NET 可以靈活地在不同類型的內容中新增超連結。