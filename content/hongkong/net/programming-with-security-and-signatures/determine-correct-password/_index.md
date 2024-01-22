---
title: 確定 PDF 檔案中的正確密碼
linktitle: 確定 PDF 檔案中的正確密碼
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 確定 PDF 檔案中的正確密碼。
type: docs
weight: 30
url: /zh-hant/net/programming-with-security-and-signatures/determine-correct-password/
---
在本教學中，我們將引導您完成使用 Aspose.PDF for .NET 確定 PDF 檔案中正確密碼的過程。此功能可讓您檢查 PDF 檔案是否受密碼保護，並從預定義清單中找到正確的密碼。

## 第 1 步：先決條件

在開始之前，請確保您具備以下先決條件：

- C# 程式語言的基礎知識
- 在您的電腦上安裝 Visual Studio
- 已安裝適用於 .NET 的 Aspose.PDF 庫

## 第2步：環境設定

首先，請按照以下步驟設定您的開發環境：

1. 開啟 Visual Studio 並建立一個新的 C# 專案。
2. 將所需的命名空間匯入到您的程式碼檔案中：

```csharp
using Aspose.Pdf;
```

## 第 3 步：載入來源 PDF 文件

第一步是上傳您要驗證的來源 PDF 檔案。在此範例中，我們假設您在指定目錄中有一個名為「IsPasswordProtected.pdf」的 PDF 檔案。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
```

請務必將佔位符替換為 PDF 檔案的實際位置。

## 步驟 4：確定來源 PDF 加密

上傳來源 PDF 檔案後，您可以使用以下命令確定它是否已加密`IsEncrypted`的方法`PdfFileInfo`目的。

```csharp
Console.WriteLine("The file is password protected: " + info.IsEncrypted);
```

此語句顯示 PDF 檔案是否受密碼保護。

## 第五步：找到正確的密碼

接下來，我們將使用預先定義的密碼清單搜尋正確的密碼。我們檢查清單中的每個密碼，並嘗試使用該密碼載入 PDF 文件。

```csharp
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
try
{
Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
if (doc.Pages.Count > 0)
Console.WriteLine("The document contains " + doc.Pages.Count + " pages.");
}
catch (InvalidPasswordException)
{
Console.WriteLine("The password " + passwords[passwordcount] + " is not correct.");
}
}
```

此循環測試列表中傳遞的每個單字。如果密碼正確，則會顯示文件的頁數。否則，會提示密碼不正確。


### 使用 Aspose.PDF for .NET 確定正確密碼的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";            
//載入來源 PDF 文件
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
//確定來源 PDF 是否已加密
Console.WriteLine("File is password protected " + info.IsEncrypted);
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
	try
	{
		Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
		if (doc.Pages.Count > 0)
			Console.WriteLine("Number of Page in document are = " + doc.Pages.Count);
	}
	catch (InvalidPasswordException)
	{
		Console.WriteLine("Password = " + passwords[passwordcount] + "  is not correct");
	}
}
```

## 結論

恭喜！您已使用 Aspose.PDF for .NET 成功地確定了 PDF 檔案的正確密碼。本教學介紹了從驗證檔案加密到從預定義清單中尋找正確密碼的逐步過程。現在您可以使用此功能來檢查並尋找 PDF 檔案的正確密碼。

### 確定 PDF 檔案中正確密碼的常見問題解答

#### Q：本教學的目的是什麼？

答：本教學課程旨在引導您完成使用 Aspose.PDF for .NET 確定 PDF 檔案的正確密碼的過程。此功能可讓您檢查 PDF 檔案是否受密碼保護，並嘗試從預定義清單中尋找正確的密碼。

#### Q：開始之前需要什麼先決條件？

答：在開始之前，請確保您對 C# 程式語言有基本的了解，並在您的電腦上安裝了 Visual Studio，並且安裝了適用於 .NET 的 Aspose.PDF 程式庫。

#### Q：如何建構開發環境？

答：請依照提供的步驟設定開發環境，包括在 Visual Studio 中建立新的 C# 項目，並匯入所需的命名空間。

#### Q：如何判斷PDF檔案是否加密？

答：使用`PdfFileInfo`類別來綁定來源 PDF 檔案。然後，使用`IsEncrypted`屬性來決定 PDF 檔案是否受密碼保護。

#### Q：如何找到 PDF 檔案的正確密碼？

答：確定 PDF 檔案已加密後，您可以嘗試使用預先定義的密碼清單來尋找正確的密碼。提供的範例程式碼示範如何循環遍歷清單、嘗試每個密碼並確定密碼是否正確。

#### Q：如果找到正確的密碼會怎樣？

A：如果找到正確的密碼，範例程式碼將顯示PDF文件的頁數。

#### Q：如果密碼不正確怎麼辦？

 A：如果密碼不正確，範例程式碼將捕獲`InvalidPasswordException`並顯示密碼不正確的資訊。

#### Q：我可以使用不同的密碼清單嗎？

答：是的，您可以修改`passwords`範例程式碼中的陣列以包含您要測試的密碼。

#### Q：如何知道密碼已成功確定？

A：如果範例程式碼成功載入帶有密碼的PDF文件並顯示頁數，則表示已確定正確的密碼。

#### Q：測試時如何確保密碼安全？

答：使用預先定義的密碼清單時要小心，並避免使用敏感或機密密碼進行測試。此外，在部署應用程式之前刪除或修改測試程式碼。