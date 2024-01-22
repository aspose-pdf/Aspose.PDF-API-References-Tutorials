---
title: 維護權利
linktitle: 維護權利
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 保留 PDF 文件中的表單權限。
type: docs
weight: 210
url: /zh-hant/net/programming-with-forms/preserve-rights/
---
在本教學中，我們將向您展示如何使用 Aspose.PDF for .NET 保留 PDF 文件中的表單權限。我們將逐步解釋 C# 原始程式碼，以引導您完成此過程。

## 第 1 步：準備

確保您已匯入必要的庫並設定文件目錄的路徑：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步驟 2：開啟文檔

使用以下命令開啟來源 PDF 文檔`FileStream`具有讀寫權限：

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## 第 3 步：編輯表單字段

瀏覽文件中的所有表單欄位並進行必要的變更。在此範例中，我們將變更名稱中包含「A1」的表單欄位的值：

```csharp
foreach(Field formField in pdfDocument.Form)
{
if (formField.FullName.Contains("A1"))
{
TextBoxField textBoxField = formField as TextBoxField;
textBoxField.Value = "Testing";
}
}
```

## 步驟 4：儲存更新後的文檔

儲存修改後的PDF文件：

```csharp
pdfDocument.Save();
```

## 第 5 步：關閉`FileStream`

不要忘記關閉`FileStream`完成後對象：

```csharp
fs. Close();
```

### 使用 Aspose.PDF for .NET 保留權利的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//使用 Read 和 Write 的 FileAccess 讀取來源 PDF 表單。
//我們需要讀寫權限，因為修改後，
//我們需要將更新的內容保存在同一個文件/文件中。
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
//實例化文件實例
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
//從所有欄位獲取值
foreach (Field formField in pdfDocument.Form)
{
	//如果欄位全名包含A1，則執行操作
	if (formField.FullName.Contains("A1"))
	{
		//將表單欄位轉換為文字框
		TextBoxField textBoxField = formField as TextBoxField;
		//修改欄位值
		textBoxField.Value = "Testing";
	}
}
//將更新後的文件儲存在 save FileStream 中
pdfDocument.Save();
//關閉文件流對象
fs.Close();
```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 保留 PDF 文件中表單的權限。透過執行這些步驟，您可以輕鬆存取表單欄位並進行特定更改，同時保留存取和寫入權限。


### 常見問題解答

#### Q：我可以保留特定表單欄位的權利而不影響 PDF 文件中的其他欄位嗎？

答：是的，透過使用`FullName`表單欄位的屬性，您可以針對特定的表單欄位進行儲存，同時使其他欄位不受影響。

#### Q：我可以保留受密碼保護的 PDF 文件中表單的權利嗎？

答：是的，Aspose.PDF for .NET 允許您保留表單的權利，即使在受密碼保護的 PDF 文件中，只要您提供正確的密碼來存取和修改文件。

#### Q：如果我嘗試在沒有適當存取權限的情況下修改表單字段，會發生什麼情況？

答：如果您在沒有適當存取權限的情況下嘗試修改表單字段，所做的變更將不會保存在 PDF 文件中，並且您可能會收到異常或錯誤訊息。

#### Q：Aspose.PDF for .NET 是否與所有版本的 .NET Framework 相容？

答：是的，Aspose.PDF for .NET 與所有版本的 .NET Framework 相容，包括 .NET Core 和 .NET Standard。

#### Q：除了 C# 之外，我還可以使用其他程式語言以程式設計方式保留 PDF 文件中的表單權限嗎？

答：是的，除了 C# 之外，Aspose.PDF for .NET 還支援各種程式語言，例如 VB.NET 和 ASP.NET。