---
title: Parola Korumalı mı
linktitle: Parola Korumalı mı
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF belgesinin parola korumalı olup olmadığını kolayca kontrol edin.
type: docs
weight: 90
url: /tr/net/programming-with-security-and-signatures/is-password-protected/
---

Bir PDF belgesini işlemeden önce parola korumalı olup olmadığını bilmek genellikle önemlidir. Aspose.PDF for .NET ile, aşağıdaki kaynak kodu kullanarak bir PDF belgesinin korunup korunmadığını kolayca kontrol edebilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat direktifleri:

```csharp
using Aspose.Pdf;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, kontrol etmek istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 3. Adım: Kaynak PDF belgesini yükleyin

Şimdi kaynak PDF belgesini yükleyeceğiz ve aşağıdaki kodu kullanarak parola korumalı olup olmadığını kontrol edeceğiz:

```csharp
PdfFileInfo fileInfo = new PdfFileInfo(dataDir + @"IsPasswordProtected.pdf");
```

## 4. Adım: PDF'nin korumalı olup olmadığını kontrol edin

 Bu adımda, PDF belgesinin parola korumalı olup olmadığını belirleyeceğiz.`IsEncrypted` yöntemi`PdfFileInfo` nesne. İşte ilgili kod:

```csharp
bool encrypted = fileInfo.IsEncrypted;
```

## 5. Adım: Şifreleme Durumunu Görüntüleyin

 Son olarak, PDF'nin mevcut şifreleme durumunu şunu kullanarak görüntüleyebiliriz:`Console.WriteLine` yöntem. İşte ilgili kod:

```csharp
Console.WriteLine(encrypted.ToString());
```

Görüntülenen mesaj, PDF belgesinin parola korumalı olup olmadığını gösterecektir.

### Aspose.PDF for .NET kullanılarak Is Password Protected için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Kaynak PDF belgesini yükleyin
PdfFileInfo fileInfo = new PdfFileInfo(dataDir+ @"IsPasswordProtected.pdf");
//Kaynak PDF dosyasının parola ile şifrelendiğini belirleyin
bool encrypted = fileInfo.IsEncrypted;
// MessageBox, PDF şifrelemeyle ilgili mevcut durumu görüntüler
Console.WriteLine(encrypted.ToString());
```

## Çözüm

Tebrikler! Artık bir PDF belgesinin Aspose.PDF for .NET kullanarak parola korumalı olup olmadığını kontrol etmek için adım adım bir kılavuzunuz var. PDF'nin koruma durumuna bağlı olarak belirli işlemleri gerçekleştirmek için bu kodu kendi projelerinize entegre edebilirsiniz.

Gelişmiş PDF belge güvenliği ve parola yönetimi özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.