---
title: 取得PDF文件中的所有附件
linktitle: 取得PDF文件中的所有附件
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 取得 PDF 檔案中的所有附件。逐步指南，方便操作。
type: docs
weight: 40
url: /zh-hant/net/programming-with-attachments/get-all-the-attachments/
---
在本教學中，我們將引導您逐步完成以下 C# 原始程式碼，以使用 Aspose.PDF for .NET 取得 PDF 檔案中的所有附件。

在開始之前，請確保您已經安裝了 Aspose.PDF 庫並設定了開發環境。也具備 C# 程式設計的基礎知識。

### 第 1 步：文檔目錄設置

在提供的原始程式碼中，您需要指定要從中取得附件的 PDF 檔案所在的目錄。將“dataDir”變數變更為所需的目錄。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 步驟 2：開啟現有 PDF 文檔

我們使用指定的路徑開啟現有的 PDF 文件。

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### 第三步：取得附件集合

我們從文件中取得附件集合。

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### 第 4 步：檢索附件

我們瀏覽集合以獲取所有附件並顯示它們的資訊。我們還將附件保存在單獨的文件中。

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

//檢查物件參數是否包含附加資訊
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

//檢索附件並保存在文件中
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### 使用 Aspose.PDF for .NET 取得所有附件的範例原始碼 

```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
//取得嵌入檔案集合
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
//取得嵌入檔案的數量
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
//循環遍歷集合以取得所有附件
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
	Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
	//檢查參數物件是否包含參數
	if (fileSpecification.Params != null)
	{
		Console.WriteLine("CheckSum: {0}",
		fileSpecification.Params.CheckSum);
		Console.WriteLine("Creation Date: {0}",
		fileSpecification.Params.CreationDate);
		Console.WriteLine("Modification Date: {0}",
		fileSpecification.Params.ModDate);
		Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
	}
	//取得附件並寫入檔案或串流
	byte[] fileContent = new byte[fileSpecification.Contents.Length];
	fileSpecification.Contents.Read(fileContent, 0,
	fileContent.Length);
	FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt",
	FileMode.Create);
	fileStream.Write(fileContent, 0, fileContent.Length);
	fileStream.Close();
	count+=1;
}

```

## 結論

在本教學中，我們說明如何使用 Aspose.PDF for .NET 從 PDF 檔案中取得所有附件。現在您可以使用這些知識從 PDF 文件中提取和操作附件。

## 取得 PDF 文件中所有附件的常見問題解答

#### Q：為什麼我需要從 PDF 文件中檢索所有附件？

答：檢索附件可讓您存取和操作 PDF 中嵌入的其他文件，這對於存檔、共用或進一步處理非常有用。

#### Q：PDF 文件中可以附加哪些類型的文件？

答：PDF 文件可以包含各種附加文件，包括影像、文件、電子表格、音訊檔案等。

#### Q：本教學如何幫助我使用 Aspose.PDF for .NET 從 PDF 擷取附件？

答：本教學提供了存取和檢索 PDF 文件中所有附件的逐步說明和 C# 原始碼。

#### Q：我可以使用本教學檢索特定附件而不是所有附件嗎？

答：是的，您可以修改提供的程式碼以根據您的要求選擇性地檢索附件。

#### Q：使用本教程我可以獲得有關每個附件的哪些資訊？

答：本教學課程示範如何擷取和顯示附件的名稱、描述、MIME 類型、建立日期、修改日期和大小等詳細資訊。

#### Q：如何使用本教學保存檢索到的附件？

答：本教學將指導您將每個檢索到的附件儲存為指定目錄中的單獨檔案。

#### Q：我可以使用這些知識從受密碼保護的 PDF 檔案中提取附件嗎？

答：是的，您可以套用類似的原理，使用 Aspose.PDF for .NET 從受密碼保護的 PDF 檔案中檢索附件。

#### Q：Aspose.PDF for .NET 如何促進附件檢索？

答：Aspose.PDF for .NET 提供了直覺的 API，讓您可以輕鬆存取和操作 PDF 文件中的附件。

#### Q：是否有建議檢索附件的特定場景？

答：當您需要存取 PDF 中嵌入的文件（例如提取影像、音訊檔案或其他文件）時，檢索附件非常有用。