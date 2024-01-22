---
title: 在 PDF 檔案中設定權限
linktitle: 在 PDF 檔案中設定權限
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 輕鬆設定 PDF 檔案的存取權限。
type: docs
weight: 100
url: /zh-hant/net/programming-with-security-and-signatures/set-privileges/
---
通常需要在 PDF 文件中設定特定的存取權限。使用 Aspose.PDF for .NET，您可以使用以下原始程式碼輕鬆設定存取權限：

## 步驟1：導入所需的庫

在開始之前，您需要為 C# 專案匯入必要的程式庫。以下是必要的導入指令：

```csharp
using Aspose.Pdf;
```

## 步驟 2：設定文件資料夾路徑

在此步驟中，您需要指定包含要編輯的 PDF 檔案的資料夾的路徑。代替`"YOUR DOCUMENTS DIRECTORY"`在以下程式碼中使用文件資料夾的實際路徑：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 3 步：載入來源 PDF 文件

現在我們將使用以下程式碼載入來源 PDF 檔案：

```csharp
using (Document document = new Document(dataDir + "input.pdf"))
```

## 第 4 步：設定存取權限

在這一步驟中，我們將實例化`DocumentPrivilege`物件來設定所需的存取權限。您可以使用對所有權限套用限制`DocumentPrivilege.ForbidAll`。例如，如果您只想允許螢幕閱讀，您可以設定`AllowScreenReaders`到`true`。這是對應的程式碼：

```csharp
DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
documentPrivilege.AllowScreenReaders = true;
```

## 步驟5：加密並儲存文檔

最後，我們可以使用使用者和所有者密碼來加密 PDF 文檔`Encrypt`並指定所需的加密演算法。然後我們儲存更新後的文件。這是對應的程式碼：

```csharp
document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
document.Save(dataDir + "SetPrivileges_out.pdf");
```

### 使用 Aspose.PDF for .NET 設定權限的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//載入來源 PDF 文件
using (Document document = new Document(dataDir + "input.pdf"))
{
	//實例化文件權限對象
	//對所有權限應用限制
	DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
	//只允許螢幕閱讀
	documentPrivilege.AllowScreenReaders = true;
	//使用用戶和所有者密碼加密檔案。
	//需要設定密碼，以便用戶一旦用用戶密碼查看文件，
	//僅啟用螢幕閱讀選項
	document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
	//儲存更新的文檔
	document.Save(dataDir + "SetPrivileges_out.pdf");
}
```

## 結論

恭喜！您現在擁有使用 Aspose.PDF for .NET 設定 PDF 文件存取權的逐步指南。您可以使用此程式碼來套用特定限制並根據需要保護您的 PDF 檔案。

請務必查看官方 Aspose.PDF 文檔，以取得有關高級 PDF 文檔安全性和存取權限管理功能的更多資訊。

### PDF 檔案中設定權限的常見問題解答

#### Q：為什麼需要在 PDF 文件中設定存取權限？

答：設定存取權限可讓您控制使用者與 PDF 文件的互動方式。您可以限制列印、影印和編輯等操作以增強文件安全性。

#### Q：使用 Aspose.PDF for .NET 設定存取權限如何受益？

答：Aspose.PDF for .NET 提供了一種簡單的方法來實現存取權限，使您能夠自訂使用者權限並保護敏感內容。

#### Q：我可以為不同的使用者應用不同的權限嗎？

答：是的，您可以為不同的使用者群組設定特定的存取權限，使您能夠根據使用者角色微調文件存取權限。

#### Q：我可以設定哪些常見的存取權限？

答：常見的存取權限包括允許或禁止諸如列印、複製文字或圖像、修改文件以及填寫表單欄位等操作。

#### Q：設定螢幕閱讀權限如何增強文件的可存取性？

答：啟用螢幕閱讀權限可確保使用者可以使用螢幕閱讀器存取 PDF 內容，從而增強視障人士的可存取性。

#### Q：我可以設定密碼保護和存取權限嗎？

答：當然，您可以在應用存取權限的同時使用密碼加密您的 PDF 文件。這提供了額外的安全層。

#### Q：有沒有辦法在申請後撤銷存取權限？

答：應用存取權限並且文件加密後，使用者將需要適當的密碼才能存取內容。可以透過更改原始碼來修改權限。

#### Q：設定存取權限時是否有任何效能考量？

答：對效能的影響很小，因為存取權限設定是在加密過程中應用的，這是一個快速的過程。

#### Q：我可以對現有 PDF 文件套用存取權限嗎？

答：是的，您可以使用 Aspose.PDF for .NET 對新的和現有的 PDF 文件套用存取權。