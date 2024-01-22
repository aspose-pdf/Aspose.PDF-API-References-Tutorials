---
title: 將 HTML 有序清單新增至文件中
linktitle: 將 HTMLOrdered 清單新增至文件中
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 將 HTML 有序清單新增至文件。
type: docs
weight: 30
url: /zh-hant/net/programming-with-text/add-html-ordered-list-into-documents/
---
在本教學中，您將學習如何使用 Aspose.PDF for .NET 函式庫將 HTML 有序清單新增至文件中。提供的程式碼示範了完成此任務的必要步驟。

## 要求
在開始之前，請確保您具備以下條件：

- Visual Studio 或電腦上安裝的任何其他 C# 編譯器。
- Aspose.PDF for .NET 函式庫。您可以從 Aspose 官方網站下載它或使用 NuGet 等套件管理器來安裝它。

## 第 1 步：設定項目
1. 在您首選的開發環境中建立一個新的 C# 專案。
2. 新增對 Aspose.PDF for .NET 函式庫的參考。

## 步驟2：導入所需的命名空間
在要新增 HTML 有序清單的程式碼檔案中，在檔案頂部新增以下 using 指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 第三步：設定文檔目錄和輸出檔案路徑
在程式碼中，找到顯示以下內容的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`以及儲存文檔的目錄的路徑。

接下來，找到顯示以下內容的行：`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";`並替換`"AddHTMLOrderedListIntoDocuments_out.pdf"`以及輸出 PDF 檔案所需的名稱。

## 步驟 4：建立一個新的 Document 對象
實例化一個新的`Document`對象，新增以下程式碼行：

```csharp
Document doc = new Document();
```

## 第 5 步：使用 HTML 內容建立 HtmlFragment 對象
實例化一個`HtmlFragment`包含要新增至文件中的 HTML 內容的物件。在提供的程式碼中，HTML 內容被指派給變數`t`。您可以根據需要修改 HTML 內容。

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## 步驟 6：新增頁面
使用以下命令將新頁面新增至文件中`Add`的方法`Pages`收藏。在提供的程式碼中，新頁面被分配給變數`page`.

```csharp
Page page = doc.Pages.Add();
```

## 步驟7：將HtmlFragment加入頁面
添加`HtmlFragment`透過使用來反對該頁面`Add`的方法`Paragraphs`收藏。

```csharp
page.Paragraphs.Add(t);
```

## 步驟8：儲存PDF文檔
使用以下命令儲存生成的 PDF 文件`Save`的方法`Document`目的。指定您在步驟 3 中設定的輸出檔案路徑。

```csharp
doc.Save(outFile);
```

### 使用 Aspose.PDF for .NET 將 HTMLOrdered List 新增至文件中的範例原始程式碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//輸出文檔的路徑。
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
//實例化文檔對象
Document doc = new Document();
//使用對應的 HTML 片段實例化 HtmlFragment 對象
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
//在頁面集合中新增頁面
Page page = doc.Pages.Add();
//在頁面內加入HtmlFragment
page.Paragraphs.Add(t);
//儲存生成的 PDF 文件
doc.Save(outFile);
```

## 結論
您已使用 Aspose.PDF for .NET 成功將 HTML 有序清單新增至文件。現在可以在指定的輸出檔案路徑中找到產生的 PDF 檔案。

請記住根據您的特定要求自訂 HTML 內容並調整程式碼。

### 常見問題解答

#### Q：本教學的目的是什麼？

答：本教學課程旨在引導您完成使用 Aspose.PDF for .NET 程式庫將 HTML 有序清單新增至文件的過程。它提供了逐步說明和程式碼片段來幫助您完成此任務。

#### Q：本教學需要導入哪些命名空間？

答：您需要在程式碼檔案頂部匯入以下命名空間：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q：如何指定文檔目錄和輸出檔案路徑？

 A：在程式碼中，找到行`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。另外，找到該行`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";`並替換`"AddHTMLOrderedListIntoDocuments_out.pdf"`以及您想要的輸出 PDF 檔案名稱。

#### Q：我可以自訂新增到文件中的 HTML 內容嗎？

答：當然！在第 5 步中，您將建立一個`HtmlFragment`對象命名`t`儲存 HTML 內容。您可以修改反引號內的 HTML 內容以滿足您的要求。

#### Q：如何將 HTML 有序清單新增至文件的頁面？

答：在步驟 7 中，您將會加入`HtmlFragment`目的 （`t`）到頁面使用`Add`的方法`Paragraphs`收藏。這會將 HTML 有序列表無縫整合到文件中。

#### Q：如何保存產生的 PDF 文件？

答：新增 HTML 內容並將其排列在頁面上後，您可以使用以下命令儲存 PDF 文件：`Save`的方法`Document`目的。確保提供您先前設定的正確輸出檔案路徑。

#### Q：您能否提供範例原始程式碼的摘要以供參考？

答：當然可以！以下是本教學中提供的範例原始程式碼的摘要版本：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### Q：本教程的主要內容是什麼？

答：透過學習本教學課程，您已經成功學習如何利用 Aspose.PDF for .NET 函式庫將 HTML 有序清單合併到文件中。這些新發現的知識可用於增強您的文件建立和操作流程。