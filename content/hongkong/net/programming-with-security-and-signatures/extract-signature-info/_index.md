---
title: 提取簽名資訊
linktitle: 提取簽名資訊
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 從 PDF 文件中提取數位簽章和憑證資訊。面向 C# 開發人員的完整逐步指南。
type: docs
weight: 80
url: /zh-hant/net/programming-with-security-and-signatures/extract-signature-info/
---
## 介紹

在當今的數位世界中，確保文件的安全性和完整性至關重要。用於保護 PDF 的常用方法之一是新增數位簽章。然而，檢索和驗證簽名的詳細資訊有時可能是一個挑戰，特別是當您處理各種證書時。在本指南中，我們將引導您完成使用 Aspose.PDF for .NET 從 PDF 文件中提取簽名資訊的過程，使該任務變得輕而易舉。您將了解如何存取簽名欄位、提取憑證資訊並將其儲存到文件中。

## 先決條件

在我們開始之前，讓我們確保您已準備好開始的一切。

-  Aspose.PDF for .NET Library：如果您還沒有，您可以從[Aspose.PDF for .NET 下載頁面](https://releases.aspose.com/pdf/net/). 
- .NET 開發環境：您需要一個像 Visual Studio 這樣的 IDE。
- 基本 C# 知識：熟悉 C# 有助於理解本教學中的程式碼片段。
- 帶有數位簽章的 PDF 文件：出於測試目的，請確保您擁有至少包含一個數位簽章的 PDF 文件。

## 導入所需的命名空間

在開始編寫程式碼之前，導入必要的命名空間非常重要。這些命名空間將允許您存取 Aspose.PDF 功能並使用 PDF 文件。

```csharp
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
using System;
```

現在您已經完成了必要的設置，讓我們繼續從 PDF 中提取簽名資訊的實際流程。

## 第 1 步：設定文檔目錄

在處理 PDF 文件之前，您需要指定要使用的文件的位置。您可以更換`"YOUR DOCUMENT DIRECTORY"`與儲存 PDF 的目錄的實際路徑。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

在這裡，我們指定包含 PDF 檔案的目錄和檔案名稱本身。確保該檔案存在於該目錄中！

## 步驟2：載入PDF文檔

現在您已經設定了目錄，下一步是使用以下命令載入 PDF 文檔`Document`來自 Aspose.PDF 的類別。

```csharp
using (Document pdfDocument = new Document(input))
{
    //在此處理 PDF。
}
```

這行程式碼初始化了一個`Document`代表 PDF 檔案的對象。這`using`語句確保在處理文件後清理資源。

## 第 3 步：存取表單字段

在此步驟中，我們將循環遍歷 PDF 文件中的所有表單欄位。由於簽名通常儲存為表單字段，因此此步驟將幫助我們識別簽名字段。

```csharp
foreach (Field field in pdfDocument.Form)
{
    //在此確定簽名字段。
}
```

透過迭代`Form`的財產`Document`對象，我們可以檢查每個表單欄位以檢查它是否是簽名欄位。

## 第 4 步：識別簽名字段

存取表單欄位後，下一步是確定哪些是簽名欄位。我們可以透過將每個欄位轉換為`SignatureField`目的。

```csharp
SignatureField sf = field as SignatureField;
if (sf != null)
{
    //提取簽名資訊。
}
```

在這裡，我們使用`as`關鍵字嘗試將每個表單欄位轉換為`SignatureField`。如果轉換成功，我們就知道該欄位是簽名。

## 第5步：提取證書

現在您已經確定了簽名字段，下一個任務是從簽名中提取證書。證書包含有關簽署者和簽名有效性的重要資訊。

```csharp
Stream cerStream = sf.ExtractCertificate();
```

這`ExtractCertificate`方法回傳一個`Stream`包含證書資料的物件。此流可用於保存證書以供進一步分析或儲存。

## 步驟 6：將證書儲存到文件中

提取證書後，最後一步是將其儲存到文件中。在這種情況下，我們將證書儲存為`.cer`文件。

```csharp
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

在這段程式碼中，我們：

1. 檢查證書流是否不為空。
2. 將證書資料讀入位元組數組。
3. 將位元組數組寫入`.cer`文檔目錄中的檔案。

## 結論

使用 Aspose.PDF for .NET 從 PDF 文件中提取數位簽章及其相關憑證資訊在分解為簡單步驟時非常簡單。無論您是在審核文件、驗證簽名，還是只是儲存憑證以進行妥善保管，本教學都會為您提供高效完成任務所需的知識。請記住，保護和驗證文件在當今的數位世界中至關重要，而使用 Aspose.PDF for .NET 等工具可以使其更容易處理。

## 常見問題解答

### 我可以使用 Aspose.PDF for .NET 從 PDF 中擷取多個簽章嗎？
是的，程式碼循環遍歷文件中的所有表單字段，允許您提取多個簽名（如果存在）。

### 如果 PDF 中沒有找到簽名會怎樣？
如果不存在簽名字段，程式碼將簡單地跳過它們而不會引發錯誤。

### 我可以使用這種方法來驗證簽章的有效性嗎？
雖然您可以提取證書，但驗證簽名的有效性需要額外的步驟，例如檢查證書的信任鏈。

### 是否可以使用 Aspose.PDF for .NET 擷取其他表單欄位資料？
是的，Aspose.PDF 允許您存取和操作 PDF 中的各種類型的表單字段，而不僅僅是簽名字段。

### 如何查看提取的證書的詳細資訊？
將證書另存為`.cer`文件，您可以使用任何憑證檢視器開啟它或將其匯入系統憑證儲存中以供進一步檢查。