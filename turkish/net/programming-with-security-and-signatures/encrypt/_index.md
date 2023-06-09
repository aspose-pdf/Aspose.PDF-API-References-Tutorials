---
title: Şifrele
linktitle: Şifrele
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyalarınızı güvenli bir şekilde şifreleyin.
type: docs
weight: 60
url: /tr/net/programming-with-security-and-signatures/encrypt/
---

PDF dosyalarını şifrelemek, gizli bilgileri korumak için önemli bir güvenlik önlemidir. Aspose.PDF for .NET ile PDF dosyalarınızı aşağıdaki kaynak kodunu kullanarak kolayca şifreleyebilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat direktifleri:

```csharp
using Aspose.Pdf;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, şifrelenecek PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 3. Adım: PDF belgesini açın

Ardından, şifrelemek istediğiniz PDF belgesini açmanız gerekir. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
Document document = new Document(dataDir + "Encrypt.pdf");
```

## 4. Adım: PDF'yi şifreleyin

Artık PDF'yi aşağıdaki kodu kullanarak şifreleyebilirsiniz:

```csharp
document. Encrypt("user", "owner", 0, CryptoAlgorithm.RC4x128);
```

Bu örnekte "kullanıcı" ve "sahip" şifreleri ile RC4x128 şifreleme algoritmasını kullanıyoruz. Bu ayarları gerektiği gibi değiştirebilirsiniz.

## 5. Adım: Şifrelenmiş PDF'yi Yedekleyin

Son olarak, şifrelenmiş PDF'yi aşağıdaki kodu kullanarak belirtilen konuma kaydedebilirsiniz:

```csharp
dataDir = dataDir + "Encrypt_out.pdf";
document. Save(dataDir);
```

Şifrelenmiş PDF için istenen yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.PDF for .NET kullanarak Encrypt için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Belgeyi aç
Document document = new Document(dataDir+ "Encrypt.pdf");
// PDF'yi şifrele
document.Encrypt("user", "owner", 0, CryptoAlgorithm.RC4x128);
dataDir = dataDir + "Encrypt_out.pdf";
// Güncellenmiş PDF'yi kaydet
document.Save(dataDir);
Console.WriteLine("\nPDF file encrypted successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET kullanarak PDF dosyalarını şifrelemeye yönelik adım adım bir genel bakışa sahipsiniz. PDF dosyalarınızı kolaylıkla güvence altına almak için bu kodu kendi projelerinize gömebilirsiniz.

Gelişmiş şifreleme ve güvenlik özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.