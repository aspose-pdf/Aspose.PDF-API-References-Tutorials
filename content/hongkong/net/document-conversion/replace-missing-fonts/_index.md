---
title: 替換遺失的字體
linktitle: 替換遺失的字體
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 取代 PDF 檔案中缺少字體的逐步指南。
type: docs
weight: 260
url: /zh-hant/net/document-conversion/replace-missing-fonts/
---
在本教學中，我們將引導您完成使用 Aspose.PDF for .NET 取代 PDF 檔案中缺少字體的過程。當您在缺少特定字體的電腦上開啟 PDF 檔案時，可能會出現字體顯示問題。在這種情況下，可以用機器上可用的另一種字體替換丟失的字體。透過執行以下步驟，您將能夠替換 PDF 檔案中遺失的字體。

## 先決條件
在開始之前，請確保滿足以下先決條件：

- C# 程式語言的基礎知識。
- 您的系統上安裝了適用於 .NET 的 Aspose.PDF 庫。
- 開發環境，例如 Visual Studio。

## 第 1 步：找到遺失的字體
第一步是找到 PDF 文件中遺失的字體。使用以下程式碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
     //找到原始的字體
     originalFont = FontRepository.FindFont("AgencyFB");
}
catch(Exception)
{
     //目標計算機上缺少字體
     //添加簡單的字體替換
     FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

一定要更換`"YOUR DOCUMENTS DIRECTORY"`與您的 PDF 檔案所在的實際目錄。

## 第 2 步：替換缺少的字體
接下來，我們將用另一種可用字體替換缺少的字體。使用以下程式碼：

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");

//將 PDF 文件轉換為 PDF/A 格式並消除錯誤
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

//儲存生成的 PDF 文件
pdf.Save(fileNew.FullName);
```

一定要更換`"input.pdf"`原始 PDF 檔案的實際路徑以及`"newfile_out.pdf"`以及產生的 PDF 檔案所需的名稱。

## 步驟 3：儲存產生的 PDF 文件
最後，我們將使用替換的字體保存生成的 PDF 文件。使用以下程式碼：

```csharp
//儲存生成的 PDF 文件
pdf.Save(fileNew.FullName);
```

確保您已為生成的 PDF 檔案設定正確的目標路徑。

### 使用 Aspose.PDF for .NET 取代缺少字體的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
	originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
	//目標計算機上缺少字體
	FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
pdf.Convert( dataDir +  "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
pdf.Save(fileNew.FullName);
```

## 結論
在本教學中，我們介紹了使用 Aspose.PDF for .NET 取代 PDF 檔案中缺少字體的逐步過程。按照上述說明操作，您將能夠成功替換 PDF 檔案中遺失的字體。

### 常見問題解答

#### Q：什麼是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員在 C# 應用程式中處理 PDF 文件。它提供各種功能，包括替換 PDF 文件中遺失的字體的能力。

#### Q：為什麼我會遇到 PDF 檔案中缺少字體的情況？

答：當在未安裝必要字體的電腦上開啟 PDF 檔案時，可能會出現 PDF 檔案遺失字體的情況。這可能會導致字體替換，影響文件的視覺外觀。

#### Q：如何使用 Aspose.PDF for .NET 尋找並取代 PDF 檔案中缺少的字型？

答：要尋找並取代遺失的字體，您可以使用`FontRepository.FindFont`檢查所需字體是否存在的方法。如果字體遺失，您可以使用以下命令新增字體替換`FontRepository.Substitutions`財產。

#### Q：我可以自訂字體替換流程嗎？

答：是的，您可以透過指定不同的字體進行替換來自訂字體替換過程。在提供的程式碼中，我們使用 Arial 作為缺少的「AgencyFB」字體的替代品，但您可以根據自己的喜好選擇不同的字體。

#### Q：替換後如何確保字體渲染的準確性？

答：Aspose.PDF for .NET 提供強大的字體處理功能，確保替換後準確的字體渲染。您可以預覽生成的 PDF 檔案以驗證字體替換。