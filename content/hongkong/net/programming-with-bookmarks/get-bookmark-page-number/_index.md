---
title: 取得 PDF 檔案中的書籤頁碼
linktitle: 取得 PDF 檔案中的書籤頁碼
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 輕鬆取得 PDF 檔案中的書籤頁碼。
type: docs
weight: 60
url: /zh-hant/net/programming-with-bookmarks/get-bookmark-page-number/
---
檢索與 PDF 文件中的書籤關聯的頁碼對於導航非常有用。使用Aspose.PDF for .NET，您可以透過以下原始碼輕鬆取得書籤的頁碼：

## 步驟1：導入所需的庫

在開始之前，您需要為 C# 專案匯入必要的程式庫。這是必要的導入指令：

```csharp
using Aspose.Pdf.Facades;
```

## 步驟 2：設定文件資料夾路徑

在此步驟中，您需要指定包含要從中提取書籤頁碼的 PDF 檔案的資料夾的路徑。代替`"YOUR DOCUMENT DIRECTORY"`在以下程式碼中使用文件資料夾的實際路徑：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第三步：建立書籤編輯器

現在我們將創建一個`PdfBookmarkEditor`物件來操作文檔的書籤。使用以下程式碼：

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## 第 4 步：開啟 PDF 文件

在此步驟中，我們使用以下命令開啟 PDF 文件`BindPdf`書籤編輯器的方法。這是對應的程式碼：

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## 步驟5：提取書籤

現在我們將使用以下命令從文件中提取書籤`ExtractBookmarks`書籤編輯器的方法。這是對應的程式碼：

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## 第 6 步：瀏覽書籤並取得頁碼

最後，我們循環遍歷提取的書籤，並使用以下方法獲取與每個書籤關聯的頁碼：`foreach`環形。這是對應的程式碼：

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### 使用 Aspose.PDF for .NET 取得書籤頁碼的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//建立Pdf書籤編輯器
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
//開啟 PDF 文件
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
//提取書籤
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## 結論

恭喜！現在您有了使用 Aspose.PDF for .NET 取得書籤頁碼的逐步指南。您可以使用此程式碼檢索與 PDF 文件中每個書籤關聯的導覽資訊。

請務必查看官方 Aspose.PDF 文檔，以獲取有關高級書籤操作功能的更多資訊。

### 取得 PDF 檔案中書籤頁碼的常見問題解答

#### Q：PDF 文件中的書籤是什麼？

答：PDF 文件中的書籤是一種導航輔助工具，允許使用者快速跳到文件中的特定部分或頁面。它們透過提供相關內容的快捷方式來增強用戶體驗。

#### Q：為什麼我要從 PDF 檔案中檢索書籤頁碼？

答：檢索書籤頁碼可以幫助使用者更有效地瀏覽文檔，並清楚指示每個書籤的位置。這對於具有多個部分的較長文件特別有用。

#### Q：如何導入 C# 專案所需的庫？

答：要匯入 C# 專案所需的函式庫，請使用下列導入指令：

```csharp
using Aspose.Pdf.Facades;
```

此指令可讓您利用 Aspose.PDF for .NET 提供的類別和方法。

#### Q：如何指定文件資料夾的路徑？

 A：在提供的源代碼中，替換`"YOUR DOCUMENT DIRECTORY"`包含要從中提取書籤頁碼的 PDF 檔案的資料夾的實際路徑。這可確保程式碼可以找到目標 PDF 檔案。

#### Q：如何建立書籤編輯器？

答：要建立書籤編輯器，請使用以下程式碼：

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### Q：如何開啟 PDF 檔案進行書籤操作？

A：要開啟PDF檔案以提取書籤信息，請使用以下程式碼：

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

代替`"GetBookmarks.pdf"`與實際的檔案名稱。

#### Q：如何從 PDF 文件中提取書籤？

答：若要從 PDF 檔案中提取書籤，請使用`ExtractBookmarks`書籤編輯器方法：

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### Q：如何檢索和顯示書籤頁碼？

 A：使用循環遍歷提取的書籤`foreach`循環並訪問`PageNumber`每個書籤的屬性來檢索並顯示其關聯的頁碼：

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### Q：我可以使用這種方法修改書籤屬性嗎？

答：雖然本教學重點介紹檢索書籤頁碼，但您可以使用相同的方法修改其他書籤屬性`Bookmark`對象和相關屬性。

#### Q：提取書籤資訊後如何保存更新的PDF檔案？

答：書籤提取不會修改原始 PDF 檔案。如果您想要儲存任何更改，可以使用 Aspose.PDF for .NET 提供的其他方法來完成。