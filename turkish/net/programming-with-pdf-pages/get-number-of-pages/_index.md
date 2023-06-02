---
title: Sayfa Sayısı Al
linktitle: Sayfa Sayısı Al
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF'nin sayfa sayısını almak için adım adım kılavuz. Uygulaması basit, projeleriniz için ideal.
type: docs
weight: 70
url: /tr/net/programming-with-pdf-pages/get-number-of-pages/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasının sayfa sayısını alma sürecini adım adım anlatacağız. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, Aspose.PDF for .NET kullanarak bir PDF dosyasının sayfa sayısını nasıl alacağınızı öğreneceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Aspose.PDF for .NET geliştirme ortamınızda yüklü

## 1. Adım: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Bu, sayfa sayısını almak istediğiniz PDF dosyanızın konumudur. "BELGELER DİZİNİNİZİ" uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: PDF belgesini açın
 Ardından, PDF dosyasını kullanarak açabilirsiniz.`Document` Aspose.PDF sınıfı. PDF dosyasının doğru yolunu belirttiğinizden emin olun.

```csharp
Document pdfDocument = new Document(dataDir + "GetNumberofPages.pdf");
```

## 3. Adım: Sayfa sayısını alın
 Artık belgedeki sayfa sayısını aşağıdakini kullanarak alabilirsiniz:`Count`belgenin özelliği`s `Sayfaların koleksiyonu. Bu size PDF dosyasındaki toplam sayfa sayısını verecektir.

```csharp
System.Console.WriteLine("Number of pages: {0}", pdfDocument.Pages.Count);
```

### Aspose.PDF for .NET kullanarak Get Numberof Pages için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "GetNumberofPages.pdf");
// Sayfa sayısını al
System.Console.WriteLine("Page Count : {0}", pdfDocument.Pages.Count);

```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasının sayfa sayısını nasıl alacağımızı öğrendik. Yukarıda özetlenen adımları izleyerek, bu işlevi kendi projelerinize kolayca uygulayabilirsiniz. PDF dosyalarıyla çalışmaya yönelik diğer yararlı özellikleri keşfetmek için Aspose.PDF belgelerini daha fazla keşfetmekten çekinmeyin.
