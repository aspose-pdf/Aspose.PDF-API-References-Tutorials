---
title: 提取簽名資訊
linktitle: 提取簽名資訊
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 擷取簽章資訊。
type: docs
weight: 80
url: /zh-hant/net/programming-with-security-and-signatures/extract-signature-info/
---
從 PDF 文件中提取簽名資訊的過程在各種場景中都非常有用。無論您需要驗證簽署文件的真實性還是分析用於簽署的證書，Aspose.PDF for .NET 程式庫都提供了方便的解決方案。在本教程中，我們將指導您使用提供的 C# 原始程式碼逐步完成提取簽名資訊的過程。

## 要求

在我們開始之前，請確保您具備以下先決條件：

1. C# 程式語言的基礎知識。
2. Aspose.PDF for .NET 程式庫安裝在您的系統上。
3. 具有一個或多個簽名字段的有效 PDF 文件。

現在，讓我們深入了解實作細節。

## 第 1 步：導入所需的庫

首先，您需要將必要的庫匯入到您的 C# 專案中。在這種情況下，我們需要導入`Aspose.Pdf`和`System.IO`命名空間。這可以透過在 C# 檔案的開頭添加以下程式碼來完成：

```csharp
using Aspose.Pdf;
using System.IO;
```

## 第二步：設定文檔路徑

接下來，您需要設定要從中提取簽名資訊的 PDF 文件的路徑。代替`"YOUR DOCUMENTS DIRECTORY"`在以下程式碼片段中包含文件的實際路徑：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## 第三步：提取簽名資訊

現在，讓我們繼續程式碼的主要部分，從 PDF 文件中提取簽名資訊。我們遍歷文件表單中的每個欄位並檢查它是否為簽名欄位。如果找到簽名字段，我們將繼續提取憑證。新增以下程式碼片段：

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             //提取證書
             Stream cerStream = sf.ExtractCertificate();
             if (cerStream != null)
             {
                 using (cerStream)
                 {
                     byte[] bytes = new byte[cerStream.Length];
                     using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
                     {
                         cerStream.Read(bytes, 0, bytes.Length);
                         fs.Write(bytes, 0, bytes.Length);
                     }
                 }
             }
         }
     }
}
```

## 第四步：提取證書

在此步驟中，我們從簽名欄位中提取憑證並將其儲存為檔案。提取的證書可以進一步分析或用於驗證目的。下面的程式碼片段演示了提取和保存過程：

```csharp
Stream cerStream = sf.ExtractCertificate();
if (cerStream != null)
{
     using (cerStream)
     {
         byte[] bytes = new byte[cerStream.Length];
         using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
         {
             cerStream.Read(bytes, 0, bytes.Length);
             fs.Write(bytes, 0, bytes.Length);
         }
     }
}
```

## 步驟5

：保存證書

最後，我們將提取的憑證儲存為檔案。在此範例中，憑證以名稱「input.cer」儲存在指定目錄中。您可以修改程式碼以滿足您的要求。這是保存證書的程式碼片段：

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

就是這樣！您已使用 Aspose.PDF for .NET 成功擷取簽章資訊。請隨意將此程式碼整合到您自己的應用程式中或根據您的需求進行修改。

### 使用 Aspose.PDF for .NET 擷取簽章資訊的範例原始碼 
```csharp
try
{
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string input = dataDir + "ExtractSignatureInfo.pdf";
	using (Document pdfDocument = new Document(input))
	{
		foreach (Field field in pdfDocument.Form)
		{
			SignatureField sf = field as SignatureField;
			if (sf != null)
			{
				Stream cerStream = sf.ExtractCertificate();
				if (cerStream != null)
				{
					using (cerStream)
					{
						byte[] bytes = new byte[cerStream.Length];
						using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
						{
							cerStream.Read(bytes, 0, bytes.Length);
							fs.Write(bytes, 0, bytes.Length);
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

在本教學中，我們逐步介紹如何使用 Aspose.PDF for .NET 函式庫從 PDF 文件中提取簽名資訊。我們介紹了導入所需庫、設定文件路徑、提取簽名資訊、提取證書並將其保存到文件的過程。透過執行這些步驟，您可以輕鬆檢索簽名詳細資訊並根據需要使用它們。

### 常見問題解答

#### Q：為什麼我需要從 PDF 文件中提取簽名資訊？

答：從 PDF 文件中提取簽名資訊對於驗證簽名文件的真實性和分析用於簽名的證書非常有用。此過程有助於確保簽名內容的完整性，並且對於法律和安全目的至關重要。

#### Q：什麼是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一個函式庫，讓開發人員能夠在 .NET 應用程式中處理 PDF 文件。它提供了廣泛的功能，用於以程式設計方式建立、修改 PDF 檔案並與之互動。

#### Q：使用 Aspose.PDF for .NET 擷取簽章資訊有哪些先決條件？

答：要提取簽名信息，您需要具備 C# 程式語言的基本知識、系統上安裝的 Aspose.PDF for .NET 庫以及包含一個或多個簽名字段的有效 PDF 文件。

#### Q：如何匯入提取過程所需的庫？

答：您可以透過新增以下內容來匯入必要的庫`using`指令`Aspose.Pdf`和`System.IO`在 C# 檔案的開頭。這些指令使您能夠使用提取簽名資訊所需的類別和方法。

#### Q：如何指定擷取簽名資訊的PDF文件？

 A：您可以透過替換來設定PDF文件的路徑`"YOUR DOCUMENTS DIRECTORY"`以及所提供的程式碼片段中文件的實際路徑。此路徑用於載入要從中提取簽名資訊的 PDF 文件。

#### Q：從PDF文件中提取簽名資訊的過程是怎麼樣的？

答：提取過程涉及遍歷 PDF 文件的表單字段，檢查每個字段是否為簽名字段，如果是，則提取關聯的證書。提取的證書可以保存為文件以進行進一步分析或驗證。

#### Q：如何從簽名欄位中提取憑證？

答：證書是使用以下方法從簽名字段中提取的：`ExtractCertificate()`提供的方法`SignatureField` Aspose.PDF for .NET 中的類別。此方法傳回包含憑證資料的流。

#### Q：如何將提取的憑證儲存為檔案？

答：您可以透過讀取憑證流並將其內容寫入檔案來將提取的憑證儲存為文件`FileStream`班級。本教程中提供的程式碼演示了此過程。

#### Q：我可以使用提取的憑證進行簽名驗證嗎？

答：是的，提取的憑證可以用於簽名驗證。您可以分析證書的詳細資訊並驗證其真實性，以確保簽署文件的完整性。

#### Q：如何將此程式碼整合到我自己的應用程式中？

答：您可以按照逐步指南將提供的程式碼整合到您自己的 C# 應用程式中。根據需要修改路徑和檔案名，並將程式碼合併到現有專案中。

#### Q：Aspose.PDF for .NET 中還有其他與簽章管理相關的功能嗎？

答：是的，Aspose.PDF for .NET 提供了一系列用於處理數位簽章的功能，包括簽署文件、驗證簽名和新增時間戳資訊。您可以瀏覽官方文件以獲取有關這些功能的更多詳細資訊。

#### Q：在哪裡可以找到使用 Aspose.PDF for .NET 的其他資源？

答：有關使用 .NET 的 Aspose.PDF 的更多資訊、教學課程和資源，[Aspose.PDF for .NET](https://reference.aspose.com/pdf/net/).

#### Q：是否可以從加密的 PDF 文件中提取簽名？

答：從加密的 PDF 文件中提取簽名的能力可能取決於文件的加密設定和權限。您可能需要確保您擁有存取和提取簽名資訊所需的權限。

#### Q：我可以從單一 PDF 文件中提取多個簽名嗎？

答：是的，您可以修改提供的程式碼以迭代 PDF 文件中的所有簽名欄位並從每個欄位中提取簽名資訊。這允許您提取有關文件中存在的多個簽名的資訊。

#### Q：提取簽名資訊有哪些實際用例？

答：提取簽名資訊的一些實際用例包括驗證數位簽章文件的真實性、出於合規性目的分析證書詳細資訊以及出於審計目的維護簽名和簽署者的記錄。

#### Q：提取簽名資訊時有什麼法律考慮嗎？

答：提取簽名資訊可能會產生法律影響，尤其是在處理具有法律約束力的文件時。確保您遵守您所在司法管轄區有關電子簽名和文件真實性的相關法規和法律。