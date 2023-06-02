---
title: Sayfa Sayısını Alın
linktitle: Sayfa Sayısını Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF dosyasının sayfa sayısını almak için adım adım kılavuz. Takip etmesi ve projelerinizde uygulaması kolaydır.
type: docs
weight: 80
url: /tr/net/programming-with-pdf-pages/get-page-count/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasının sayfa sayısını alma sürecini adım adım anlatacağız. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, Aspose.PDF for .NET kullanarak bir PDF dosyasının sayfa sayısını nasıl alacağınızı öğreneceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Aspose.PDF for .NET geliştirme ortamınızda yüklü

## 1. Adım: Bir Document nesnesinin örneğini oluşturun
Öncelikle, Aspose.PDF'nin Document sınıfını kullanarak bir Document nesnesi başlatmanız gerekir.

```csharp
Document doc = new Document();
```

## 2. Adım: Belgeye bir sayfa ekleyin
 Ardından, kullanarak belgeye bir sayfa ekleyebilirsiniz.`Add()` belgenin Pages koleksiyonunun yöntemi.

```csharp
Page page = doc.Pages.Add();
```

## 3. Adım: Sayfa içeriği oluşturun
Artık Page nesnesinin Paragraphs koleksiyonuna TextFragment nesneleri ekleyerek sayfa içeriği oluşturabilirsiniz. Bu örnekte, daha uzun içeriğe sahip bir belgeyi simüle etmek için 300 kez tekrarlanan bir TextFragment ekliyoruz.

```csharp
for (int i = 0; i < 300; i++)
page.Paragraphs.Add(new TextFragment("Page count test"));
```

## 4. Adım: Paragrafları İşleme ve Sayfa Sayısını Alma
 İçeriği sayfaya ekledikten sonra, belge paragraflarını çağırarak işlemeniz gerekir.`ProcessParagraphs()` yöntem. Bu, Aspose.PDF'nin sayfa sayısını doğru bir şekilde hesaplamasını sağlar.

```csharp
doc.ProcessParagraphs();
```

## Adım 5: Sayfa sayısını görüntüleme
 Son olarak, belgedeki sayfa sayısını görüntüleyebilirsiniz.`Count` Pages koleksiyonunun özelliği.

```csharp
Console.WriteLine("Number of pages in document = " + doc.Pages.Count);
```

### Aspose.PDF for .NET kullanarak Get Page Count için örnek kaynak kodu 

```csharp

// Belge örneği örneği
Document doc = new Document();
// PDF dosyasının sayfa koleksiyonuna sayfa ekle
Page page = doc.Pages.Add();
// Döngü örneği oluştur
for (int i = 0; i < 300; i++)
	// Sayfa nesnesinin paragraf koleksiyonuna TextFragment ekleyin
	page.Paragraphs.Add(new TextFragment("Pages count test"));
// Doğru sayfa sayısını elde etmek için PDF dosyasındaki paragrafları işleyin
doc.ProcessParagraphs();
// Belgedeki sayfa sayısını yazdır
Console.WriteLine("Number of pages in document = " + doc.Pages.Count);

```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasının sayfa sayısını nasıl alacağımızı öğrendik. Yukarıda özetlenen adımları izleyerek, bu işlevi kendi projelerinize kolayca uygulayabilirsiniz. PDF dosyalarıyla çalışmaya yönelik diğer yararlı özellikleri keşfetmek için Aspose.PDF belgelerini daha fazla keşfetmekten çekinmeyin.
