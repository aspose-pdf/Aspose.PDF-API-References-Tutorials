---
title: Pdf Dosyalarını Birleştirme
linktitle: Pdf Dosyalarını Birleştirme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyalarını birleştirmek için adım adım kılavuz. Takip etmesi ve projelerinizde uygulaması kolaydır.
type: docs
weight: 20
url: /tr/net/programming-with-pdf-pages/concatenate-pdf-files/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF dosyalarını birleştirme sürecini adım adım anlatacağız. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, Aspose.PDF for .NET kullanarak PDF dosyalarını nasıl birleştireceğinizi öğreneceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Aspose.PDF for .NET geliştirme ortamınızda yüklü

## 1. Adım: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Bu, birleştirilecek PDF dosyalarınızın bulunduğu yerdir. "BELGELER DİZİNİNİZİ" uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: PDF Dosyalarını Açın
 Ardından, kullanarak birleştirmek için PDF dosyalarını açabilirsiniz.`Document` Aspose.PDF sınıfı. Her bir PDF dosyası için doğru yolu belirttiğinizden emin olun.

```csharp
Document pdfDocument1 = new Document(dataDir + "Concat1.pdf");
Document pdfDocument2 = new Document(dataDir + "Concat2.pdf");
```

## 3. Adım: Sayfaları birleştirin
 Artık ikinci belgedeki sayfaları kullanarak ilk belgeye ekleyebilirsiniz.`Add()` belgenin yöntemi`Pages` Toplamak. Bu, her iki belgenin sayfalarını tek bir belgede birleştirecektir.

```csharp
pdfDocument1.Pages.Add(pdfDocument2.Pages);
```

## 4. Adım: Birleştirilmiş PDF dosyasını kaydedin
 Son olarak, birleştirilmiş PDF belgesini, belgenin`Save()` yöntem. Doğru yolu ve dosya adını belirttiğinizden emin olun.

```csharp
dataDir = dataDir + "ConcatenatePdfFiles_out.pdf";
pdfDocument1.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Pdf Dosyalarını Birleştir için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// İlk belgeyi aç
Document pdfDocument1 = new Document(dataDir + "Concat1.pdf");
// İkinci belgeyi aç
Document pdfDocument2 = new Document(dataDir + "Concat2.pdf");
// İkinci belgenin sayfalarını birinciye ekle
pdfDocument1.Pages.Add(pdfDocument2.Pages);
dataDir = dataDir + "ConcatenatePdfFiles_out.pdf";
// Birleştirilmiş çıktı dosyasını kaydet
pdfDocument1.Save(dataDir);
System.Console.WriteLine("\nPDFs are concatenated successfully.\nFile saved at " + dataDir);

```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF dosyalarını birleştirmeyi öğrendik. Yukarıda özetlenen adımları izleyerek, bu işlevi kendi projelerinize kolayca uygulayabilirsiniz. PDF dosyalarıyla çalışmaya yönelik diğer yararlı özellikleri keşfetmek için Aspose.PDF belgelerini daha fazla keşfetmekten çekinmeyin.
