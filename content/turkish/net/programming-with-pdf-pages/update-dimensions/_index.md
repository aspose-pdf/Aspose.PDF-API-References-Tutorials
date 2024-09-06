---
title: PDF Sayfa Boyutlarını Güncelle
linktitle: PDF Sayfa Boyutlarını Güncelle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF sayfa boyutlarını güncellemek için adım adım kılavuz. Boyutları ihtiyaçlarınıza göre kontrol edin.
type: docs
weight: 150
url: /tr/net/programming-with-pdf-pages/update-dimensions/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesindeki sayfa boyutlarını güncellemek için adım adım süreci adım adım anlatacağız. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği kendi projelerinizde anlamanıza ve uygulamanıza yardımcı olacak kapsamlı bir kılavuz sunacağız. Bu eğitimin sonunda, .NET için Aspose.PDF kullanarak bir PDF belgesindeki sayfa boyutlarını nasıl değiştireceğinizi öğreneceksiniz.

## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dilinin temel bilgisi
- Geliştirme ortamınıza .NET için Aspose.PDF yüklendi

## Adım 1: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Bu, düzenlediğiniz PDF belgenizi kaydetmek istediğiniz konumdur. "YOUR DOCUMENTS DIRECTORY" ifadesini uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: PDF belgesini açın
 Daha sonra mevcut PDF belgesini kullanarak açabilirsiniz.`Document` Aspose.PDF sınıfı. Doğru belge yolunu belirttiğinizden emin olun.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Adım 3: Sayfa Koleksiyonunu Alın
 Artık PDF belgesinin sayfa koleksiyonuna şu şekilde erişebilirsiniz:`Pages` mülkiyeti`Document` sınıf.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Adım 4: Belirli bir sayfayı alın
Daha sonra koleksiyondaki sayfanın dizinini kullanarak belgenin belirli bir sayfasını seçebilirsiniz. Bu örnekte, ikinci sayfayı (dizin 1) kullanıyoruz.

```csharp
Page pdfPage = pageCollection[1];
```

## Adım 5: Yeni sayfa boyutlarını tanımlayın
 Artık yeni sayfa boyutunu şu şekilde ayarlayabilirsiniz:`SetPageSize()` yöntemi`Page`nesne. Bu örnekte, sayfa boyutlarını A4'e (11,7 x 8,3 inç) ayarlıyoruz, bunu noktalara dönüştürüyoruz (1 inç = 72 nokta).

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## Adım 6: Güncellenen belgeyi kaydedin
 Son olarak, güncellenen PDF belgesini kullanarak bir dosyaya kaydedebilirsiniz.`Save()` yöntemi`Document`sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### .NET için Aspose.PDF kullanarak Güncelleme Boyutları için örnek kaynak kodu 

```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Sayfa koleksiyonunu al
PageCollection pageCollection = pdfDocument.Pages;
// Belirli sayfayı al
Page pdfPage = pageCollection[1];
// Sayfa boyutunu A4 (11,7 x 8,3 inç) olarak ayarlayın ve Aspose.Pdf'de 1 inç = 72 puan
// Yani A4 boyutları nokta cinsinden (842.4, 597.6) olacaktır.
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## Çözüm
Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesindeki bir sayfanın boyutlarını nasıl güncelleyeceğinizi öğrendik. Bu adım adım kılavuzu izleyerek, bir PDF belgesindeki bir sayfanın boyutlarını gerektiği gibi kolayca değiştirebilirsiniz. Aspose.PDF, PDF dosyalarıyla çalışmak ve sayfa boyutlarını değiştirmek de dahil olmak üzere çeşitli manipülasyonlar yapmak için güçlü ve esnek bir API sunar. Bu bilgiyle, PDF sayfalarınızın boyutlarını belirli ihtiyaçlarınızı karşılayacak şekilde kontrol edebilir ve özelleştirebilirsiniz.

### PDF sayfa boyutlarını güncellemeye ilişkin SSS

#### S: Aspose.PDF for .NET kullanarak PDF belgesindeki belirli bir sayfanın boyutlarını nasıl güncelleyebilirim?

A: Aspose.PDF for .NET kullanarak PDF belgesindeki belirli bir sayfanın boyutlarını güncellemek için şu adımları izleyebilirsiniz:

1. Orijinal PDF dosyanızın bulunduğu yolu ve güncellenmiş PDF dosyasını kaydetmek istediğiniz yeri belirterek belge dizinini ayarlayın. "YOUR DOCUMENTS DIRECTORY" ifadesini uygun yol ile değiştirin.
2.  Mevcut PDF belgesini güncellemek için açın`Document` Aspose.PDF sınıfı. Orijinal PDF belgesine doğru yolu belirttiğinizden emin olun.
3.  PDF belgesinin sayfa koleksiyonuna erişmek için şunu kullanın:`Pages` mülkiyeti`Document` sınıf.
4. Sayfa koleksiyonundan güncellemek istediğiniz belirli sayfayı, sayfanın dizinini kullanarak seçin. Sağlanan C# kaynak kodunda, ikinci sayfayı (dizin 1) kullanıyoruz.
5.  Yeni sayfa boyutunu kullanarak tanımlayın`SetPageSize()` yöntemi`Page` nesne. Örnekte, sayfa boyutlarını A4 boyutuna (11,7 x 8,3 inç) ayarladık, noktalara (1 inç = 72 nokta) dönüştürdük.
6.  Güncellenen PDF belgesini kullanarak bir dosyaya kaydedin`Save()` yöntemi`Document`sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

#### S: PDF belgesinde birden fazla sayfanın boyutlarını aynı anda güncelleyebilir miyim?

A: Evet, PDF belgesindeki birden fazla sayfanın boyutlarını aynı anda güncellemek için sağlanan kaynak kodunu değiştirebilirsiniz. Belirli bir sayfayı seçmek yerine (4. adımda gösterildiği gibi), sayfa koleksiyonundaki tüm sayfalar arasında dolaşabilir ve her sayfa için istenen sayfa boyutunu ayarlayabilirsiniz.

#### S: Aspose.PDF for .NET kullanırken sayfa boyutlarını inçten noktaya nasıl dönüştürebilirim?

 A: .NET için Aspose.PDF'de sayfa boyutları için kullanılan ölçüm birimi noktadır ve 1 inç 72 noktaya eşittir. İnçleri noktalara dönüştürmek için şu formülü kullanabilirsiniz:`points = inches * 72`Örneğin, 11,7 x 8,3 inçlik bir sayfa boyutu belirlemek için, karşılık gelen boyutları nokta cinsinden (11,7 * 72) ve (8,3 * 72) olarak hesaplayabilirsiniz.

#### S: Bir sayfanın boyutlarını güncellemek PDF belgesinin içerik düzenini etkiler mi?

A: Evet, bir sayfanın boyutlarını güncellemek, o belirli sayfadaki PDF belgesinin içerik düzenini etkileyecektir. Sayfa boyutlarını değiştirdiğinizde, sayfadaki içerik yeni boyutlara uyacak şekilde ayarlanacaktır.

#### S: Değişiklikleri geri almak ve sayfa boyutlarını güncelledikten sonra orijinal sayfa boyutlarına geri döndürmek mümkün müdür?

A: Evet, değişiklikleri geri almak ve orijinal sayfa boyutlarını geri yüklemek istiyorsanız, değişiklik yapmadan önce orijinal PDF belgesinin bir kopyasını saklayabilir veya değişiklikleri kaydetmeden orijinal PDF belgesini yeniden açabilirsiniz. Bu şekilde, orijinal boyutlar korunacaktır.