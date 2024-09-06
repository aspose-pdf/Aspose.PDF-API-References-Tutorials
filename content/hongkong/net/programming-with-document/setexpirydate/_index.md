---
title: 在 PDF 文件中設定到期日期
linktitle: 在 PDF 文件中設定到期日期
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南，了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中設定到期日。
type: docs
weight: 300
url: /zh-hant/net/programming-with-document/setexpirydate/
---
Aspose.PDF for .NET 是一個功能強大的程式庫，提供了處理 PDF 檔案的各種功能。其中一項功能是能夠為 PDF 文件設定到期日。在本教學中，我們將引導您完成使用 Aspose.PDF for .NET 設定 PDF 文件到期日的過程。 

## 第一步：設定文檔目錄路徑

在開始之前，我們需要設定 PDF 文件所在目錄的路徑。我們將該路徑儲存在名為「dataDir」的變數中。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：建立新的 PDF 文檔

要建立一個新的 PDF 文檔，我們需要實例化一個新的`Aspose.Pdf.Document`目的。我們可以使用以下程式碼來做到這一點：

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## 步驟 3：在 PDF 文件中新增頁面

建立 PDF 文件後，我們可以向其中新增頁面。我們可以使用以下程式碼來做到這一點：

```csharp
doc.Pages.Add();
```

## 步驟 4：將文字新增至 PDF 文檔

將頁面新增至 PDF 文件後，我們可以使用以下命令向其添加文本`Paragraphs`收藏。我們可以使用以下程式碼來做到這一點：

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## 第 5 步：使用 JavaScript 設定 PDF 到期日期

要設定 PDF 到期日期，我們需要建立一個 JavaScript 物件。我們可以使用以下程式碼來做到這一點：

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

//將 JavaScript 設定為 PDF 開啟操作
doc.OpenAction = javaScript;
```

在此代碼中，我們將到期日期設定為 2017 年 5 月。

## 步驟 6：儲存 PDF 文件

設定到期日期後，您需要儲存 PDF 檔案。為此，您可以使用`Save`的方法`Document`物件並傳入要儲存更新的 PDF 檔案的路徑。

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
//儲存 PDF 文件
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 設定到期日期的範例原始碼

以下是使用 Aspose.PDF for .NET 設定到期日期的完整範例原始碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//實例化文檔對象
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
//將頁面新增至 PDF 檔案的頁面集合
doc.Pages.Add();
//將文字片段加入到頁面物件的段落集合中
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
//建立 JavaScript 物件來設定 PDF 到期日期
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
//將 JavaScript 設定為 PDF 開啟操作
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
//儲存 PDF 文件
doc.Save(dataDir);
```

## 結論

使用 Aspose.PDF for .NET 設定 PDF 文件的到期日是一項有用的功能，可確保文件僅在指定期限內有效。透過遵循逐步指南並使用提供的 C# 原始程式碼，開發人員可以輕鬆設定到期日期並建立具有有時效性的 PDF。此功能對於需要在有限時間內存取或分發的文件特別有用。

### 有關在 PDF 文件中設定到期日期的常見問題解答

#### Q：我可以為 PDF 文件設定不同的到期日嗎？

答：是的，您可以透過修改步驟5 中的JavaScript 程式碼來為PDF 文件設定不同的到期日。您需要修改`year`和`month`JavaScript 程式碼中的變數設定為所需的年份和月份。

#### Q：PDF 文件過期後會發生什麼狀況？

答：當 PDF 文件已過期（如 JavaScript 程式碼中所指定）時，檢視器將顯示警報訊息，指示該檔案已過期且使用者需要新的檔案。開啟 PDF 時將顯示此警告訊息。

#### Q：我可以使用具體時間而不是僅使用日期作為到期日嗎？

答：是的，您可以在 JavaScript 程式碼中設定到期日的具體時間。透過修改`expiry`如果您在 JavaScript 程式碼中包含所需時間的變量，則可以設定到期日的特定時間。