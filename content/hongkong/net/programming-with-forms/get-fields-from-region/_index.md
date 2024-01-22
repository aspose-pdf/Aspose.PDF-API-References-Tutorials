---
title: 從 PDF 文件中的區域獲取字段
linktitle: 從 PDF 文件中的區域獲取字段
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 輕鬆取得 PDF 檔案中特定區域的欄位。
type: docs
weight: 130
url: /zh-hant/net/programming-with-forms/get-fields-from-region/
---
在本教學中，我們將向您展示如何使用 Aspose.PDF for .NET 取得 PDF 檔案中特定區域的欄位。我們將逐步解釋 C# 原始程式碼，以引導您完成此過程。

## 第 1 步：準備

確保您已匯入必要的庫並設定文件目錄的路徑：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：開啟 PDF 文件

開啟 PDF 檔案：

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## 步驟 3：建立一個矩形物件來界定區域

建立一個矩形物件來界定要取得欄位的區域：

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## 第4步：取得PDF表格

取得文件的 PDF 形式：

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## 步驟5：取得矩形區域中的字段

取得位於指定矩形區域的欄位：

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## 第 6 步：顯示欄位名稱和值

迭代結果欄位並顯示它們的名稱和值：

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### 使用 Aspose.PDF for .NET 從區域取得欄位的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟 pdf 文件
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
//建立矩形物件以取得該區域中的字段
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
//取得 PDF 表格
Aspose.Pdf.Forms.Form form = doc.Form;
//取得矩形區域內的字段
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
//顯示欄位名稱和值
foreach (Field field in fields)
{
	//顯示所有展示位置的圖片展示位置屬性
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 取得 PDF 文件中特定區域的欄位。透過執行這些步驟，您可以使用 Aspose.PDF 輕鬆提取 PDF 文件給定矩形區域中的欄位。

### 常見問題解答

#### Q：我可以使用此方法從 PDF 文件中的非矩形區域取得欄位嗎？

 A：不需要，提供的方法`GetFieldsInRect`專門設計用於擷取 PDF 文件中矩形區域內的欄位。如果您需要從非矩形區域提取字段，則需要實作自訂邏輯來根據其他條件（例如字段座標或名稱）識別和提取字段。

#### Q：如何修改矩形的大小或位置以取得不同區域的欄位？

 A：要取得不同地區的字段，可以修改`Aspose.Pdf.Rectangle`物件的參數用於定義邊界矩形。這`Rectangle`建構函數有四個參數：`x`, `y`, `width`， 和`height`，表示矩形的左上角座標和尺寸。調整這些參數將更改提取欄位的區域。

#### Q：如果指定的矩形區域內沒有欄位怎麼辦？

 A：如果指定的矩形區域內沒有字段，則`GetFieldsInRect`方法將傳回一個空數組。您可以檢查陣列的長度以確定該區域內是否有任何欄位。

#### Q：我可以從 PDF 文件中的重疊區域取得欄位嗎？

答：是的，您可以透過建立多個 PDF 文件中的重疊區域來取得字段`Aspose.Pdf.Rectangle`對象並調用`GetFieldsInRect`他們每個人的方法。重疊區域將被獨立處理，並且您將收到每個區域的單獨欄位陣列。

#### Q：是否可以從 PDF 文件中的特定頁面或多個頁面取得欄位？

答：是的，您可以從 PDF 文件中的特定頁面或多個頁面取得欄位。為此，您可以載入 PDF 文檔，使用`doc.Pages`集合，然後應用`GetFieldsInRect`方法到每個頁面的特定區域。