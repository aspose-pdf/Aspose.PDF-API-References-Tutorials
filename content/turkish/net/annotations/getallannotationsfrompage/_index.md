---
title: Tüm Ek Açıklamaları Sayfadan Al
linktitle: Tüm Ek Açıklamaları Sayfadan Al
second_title: .NET API Referansı için Aspose.PDF
description: Bu adım adım kılavuzla bir PDF sayfasındaki tüm açıklamaları almak için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 70
url: /tr/net/annotations/getallannotationsfrompage/
---
Bu makale, Aspose.PDF for .NET kullanarak bir PDF sayfasındaki tüm açıklamaları çıkarma sürecinde size rehberlik edecektir. Aspose.PDF for .NET, geliştiricilerin PDF belgeleri oluşturmasına, düzenlemesine ve dönüştürmesine olanak tanıyan bir kitaplıktır. Bu kılavuzun yardımıyla, sağlanan C# kaynak kodunu kullanarak belirli bir PDF sayfasındaki tüm ek açıklamaları alabileceksiniz.

Aspose.PDF for .NET kullanarak bir PDF sayfasındaki tüm Ek Açıklamaları almak için aşağıdaki adımları izleyin:

## Adım 1: Belgeler Dizininin Yolu

Aspose.PDF for .NET kullanarak bir PDF sayfasından tüm açıklamaları almanın ilk adımı, PDF dosyalarınızın depolandığı belgeler dizininin yolunu ayarlamaktır. Bunu aşağıdaki kod satırını değiştirerek yapabilirsiniz:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
## 2. Adım: PDF dosyalarınız saklanır

"BELGE DİZİNİNİZ" ifadesini, PDF dosyalarınızın depolandığı klasörün yolu ile değiştirin. Örneğin:

```csharp
string dataDir = @"C:\Users\JohnDoe\Documents\PDFs\";
```

## 3. Adım: Belgeyi Açın

Bir sonraki adım, çıkarmak istediğiniz ek açıklamaları içeren PDF belgesini açmaktır. Bunu aşağıdaki kodu ekleyerek yapabilirsiniz:

```csharp
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");
```

Bu kod satırı, Document sınıfının yeni bir örneğini başlatır ve "GetAllAnnotationsFromPage.pdf" PDF belgesini yükler. Bu dosya adını PDF dosyanızın adıyla değiştirin.

## Adım 4: Tüm Ek Açıklamalarda Döngü Yapın

PDF belgesini açtıktan sonra belirli bir sayfadaki tüm ek açıklamalar arasında geçiş yapabilirsiniz. Örneğin, PDF belgesinin ilk sayfasındaki tüm ek açıklamalar arasında geçiş yapmak için aşağıdaki kodu ekleyin:

```csharp
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
    // Kod buraya gelecek
}
```

Bu kod, PDF belgesinin ilk sayfasındaki tüm ek açıklamalar arasında geçiş yapar ve her ek açıklamayı "ek açıklama" değişkenine atar.

## Adım 5: Ek Açıklama Özelliklerini Alın

Her bir açıklamanın özelliklerini çıkarmak için foreach döngüsünün içine aşağıdaki kodu ekleyebilirsiniz:

```csharp
Console.WriteLine("Title : {0} ", annotation.Title);
Console.WriteLine("Subject : {0} ", annotation.Subject);
Console.WriteLine("Contents : {0} ", annotation.Contents);
```

Bu kod, her ek açıklamanın Başlığını, Konusunu ve İçeriğini konsola yazar.

### Aspose.PDF for .NET kullanarak Sayfadan Tüm Ek Açıklamaları Almak için Örnek Kaynak Kodu

Aspose.PDF for .NET kullanarak bir PDF sayfasındaki tüm açıklamaları almak için tam kaynak kodunu burada bulabilirsiniz:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");

// Tüm ek açıklamalar arasında dolaşın
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
	// Ek açıklama özelliklerini alma
	Console.WriteLine("Title : {0} ", annotation.Title);
	Console.WriteLine("Subject : {0} ", annotation.Subject);
	Console.WriteLine("Contents : {0} ", annotation.Contents);                
}
```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF belgesinin belirli bir sayfasındaki tüm açıklamaların nasıl alınacağını araştırdık. Geliştiriciler, adım adım kılavuzu izleyerek ve sağlanan C# kaynak kodunu kullanarak, PDF belgelerinden ek açıklamaları kolayca çıkarabilir ve yönetebilir.

### SSS'ler

#### S: PDF belgesindeki ek açıklamalar nelerdir?

C: Bir PDF belgesindeki ek açıklamalar, belgenin belirli bölümleri hakkında ek bilgi, yorum veya notlar sağlayan etkileşimli öğelerdir. Ek açıklamalar metin notlarını, yorumları, vurguları ve diğer etkileşimli öğeleri içerebilir.

#### S: Yalnızca belirli sayfalardan ek açıklamalar alabilir miyim?

C: Evet, Aspose.PDF for .NET ile gereksinimlerinize bağlı olarak belirli sayfalardan, hatta belgenin tamamından açıklamalar alabilirsiniz.

#### S: Aspose.PDF for .NET, parola korumalı PDF dosyalarından açıklamaların çıkarılmasını destekliyor mu?

 C: Evet, Aspose.PDF for .NET, parola korumalı PDF dosyalarından açıklamaların çıkarılmasını destekler. PDF belgesini kullanarak yüklerken doğru şifreyi girmeniz gerekir.`Document` sınıf.

#### S: Ek açıklamaları içerik veya yazar gibi özelliklerine göre filtreleyebilir miyim?

C: Evet, Aspose.PDF for .NET, içerik, yazar veya oluşturulma tarihi gibi özelliklerine göre açıklamalara erişme ve bunları filtreleme yöntemleri sağlar. Tüm ek açıklamalar arasında geçiş yapabilir ve filtrelemek istediğiniz belirli özellikleri kontrol edebilirsiniz.

#### S: Aspose.PDF for .NET, farklı türdeki PDF belgelerinden açıklamaların çıkarılmasını destekliyor mu?

C: Evet, Aspose.PDF for .NET, metin işaretleme açıklamaları, serbest metin açıklamaları ve daha fazlasını içeren, farklı PDF belge türlerinden açıklamaları çıkarmak için çeşitli yöntemler sağlar.