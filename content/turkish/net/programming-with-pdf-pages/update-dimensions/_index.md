---
title: PDF Sayfa Boyutlarını Güncelle
linktitle: PDF Sayfa Boyutlarını Güncelle
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF sayfa boyutlarını güncellemek için adım adım kılavuz. İhtiyaçlarınıza göre boyutları kontrol edin.
type: docs
weight: 150
url: /tr/net/programming-with-pdf-pages/update-dimensions/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki sayfa boyutlarını güncellemek için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sunacağız. Bu eğitimin sonunda Aspose.PDF for .NET kullanarak bir PDF belgesinde sayfa boyutlarını nasıl değiştireceğinizi öğreneceksiniz.

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Aspose.PDF for .NET, geliştirme ortamınızda yüklü

## 1. Adım: Belge dizinini tanımlayın
Öncelikle belgeler dizininizin yolunu ayarlamanız gerekir. Bu, düzenlenmiş PDF belgenizi kaydetmek istediğiniz konumdur. "BELGELERİNİZ DİZİNİ"ni uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: PDF belgesini açın
 Daha sonra mevcut PDF belgesini aşağıdaki komutu kullanarak açabilirsiniz:`Document` Aspose.PDF sınıfı. Doğru belge yolunu belirttiğinizden emin olun.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## 3. Adım: Sayfa Koleksiyonunu Alın
 Artık PDF belgesinin sayfa koleksiyonuna şu düğmeyi kullanarak erişebilirsiniz:`Pages` mülkiyeti`Document` sınıf.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## 4. Adım: Belirli bir sayfayı edinin
Daha sonra koleksiyondaki sayfanın dizinini kullanarak belgenin belirli bir sayfasını seçebilirsiniz. Bu örnekte ikinci sayfayı kullanıyoruz (indeks 1).

```csharp
Page pdfPage = pageCollection[1];
```

## 5. Adım: Yeni sayfa boyutlarını tanımlayın
 Artık yeni sayfa boyutunu aşağıdaki düğmeyi kullanarak ayarlayabilirsiniz:`SetPageSize()` yöntemi`Page`nesne. Bu örnekte sayfa boyutlarını A4 (11,7 x 8,3 inç) olarak ayarlıyoruz ve noktalara (1 inç = 72 punto) dönüştürülüyor.

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## 6. Adım: Güncellenen belgeyi kaydedin
 Son olarak, güncellenen PDF belgesini kullanarak bir dosyaya kaydedebilirsiniz.`Save()` yöntemi`Document`sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Boyutları Güncelle için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Sayfa koleksiyonunu alın
PageCollection pageCollection = pdfDocument.Pages;
// Belirli bir sayfayı al
Page pdfPage = pageCollection[1];
// Sayfa boyutunu A4 (11,7 x 8,3 inç) ve Aspose.Pdf'de 1 inç = 72 punto olarak ayarlayın
// Yani noktalardaki A4 boyutları (842,4, 597,6) olacaktır.
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## Çözüm
Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF belgesindeki sayfanın boyutlarını nasıl güncelleyeceğimizi öğrendik. Bu adım adım kılavuzu izleyerek PDF belgesindeki bir sayfanın boyutlarını gerektiği gibi kolayca değiştirebilirsiniz. Aspose.PDF, PDF dosyalarıyla çalışmak ve sayfa boyutlarını değiştirmek de dahil olmak üzere çeşitli manipülasyonlar gerçekleştirmek için güçlü ve esnek bir API sunar. Bu bilgiyle, PDF sayfalarınızın boyutlarını özel ihtiyaçlarınızı karşılayacak şekilde kontrol edebilir ve özelleştirebilirsiniz.

### Güncelleme PDF sayfa boyutlarına ilişkin SSS

#### S: Aspose.PDF for .NET'i kullanarak bir PDF belgesindeki belirli bir sayfanın boyutlarını nasıl güncelleyebilirim?

C: Aspose.PDF for .NET kullanarak bir PDF belgesindeki belirli bir sayfanın boyutlarını güncellemek için şu adımları takip edebilirsiniz:

1. Orijinal PDF dosyanızın bulunduğu yolu ve güncellenen PDF dosyasını kaydetmek istediğiniz yeri belirterek belge dizinini ayarlayın. "BELGELERİNİZ DİZİNİ"ni uygun yolla değiştirin.
2.  Güncellemek için mevcut PDF belgesini kullanarak`Document` Aspose.PDF sınıfı. Orijinal PDF belgesinin doğru yolunu belirttiğinizden emin olun.
3.  kullanarak PDF belgesinin sayfa koleksiyonuna erişin.`Pages` mülkiyeti`Document` sınıf.
4. Sayfanın dizinini kullanarak sayfa koleksiyonundan güncellemek istediğiniz sayfayı seçin. Sağlanan C# kaynak kodunda ikinci sayfayı kullanıyoruz (dizin 1).
5.  kullanarak yeni sayfa boyutunu tanımlayın.`SetPageSize()` yöntemi`Page` nesne. Örnekte sayfa boyutlarını A4 boyutuna (11,7 x 8,3 inç) ayarladık ve noktalara (1 inç = 72 punto) dönüştürdük.
6.  Güncellenen PDF belgesini kullanarak bir dosyaya kaydedin.`Save()` yöntemi`Document`sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

#### S: PDF belgesindeki birden fazla sayfanın boyutlarını aynı anda güncelleyebilir miyim?

C: Evet, PDF belgesindeki birden fazla sayfanın boyutlarını aynı anda güncellemek için sağlanan kaynak kodunu değiştirebilirsiniz. Belirli bir sayfayı seçmek yerine (4. adımda gösterildiği gibi), sayfa koleksiyonundaki tüm sayfalar arasında geçiş yapabilir ve her sayfa için istediğiniz sayfa boyutunu ayarlayabilirsiniz.

#### S: Aspose.PDF for .NET'i kullanırken sayfa boyutlarını inçten noktaya nasıl dönüştürebilirim?

 C: Aspose.PDF for .NET'te sayfa boyutları için kullanılan ölçü birimi noktadır; burada 1 inç, 72 noktaya eşittir. İnçleri noktalara dönüştürmek için aşağıdaki formülü kullanabilirsiniz:`points = inches * 72`. Örneğin, 11,7 x 8,3 inçlik bir sayfa boyutu ayarlamak için, karşılık gelen boyutları nokta cinsinden (11,7 * 72) ve (8,3 * 72) olarak hesaplayabilirsiniz.

#### S: Bir sayfanın boyutlarının güncellenmesi PDF belgesinin içerik düzenini etkiler mi?

C: Evet, bir sayfanın boyutlarının güncellenmesi söz konusu sayfadaki PDF belgesinin içerik düzenini etkileyecektir. Sayfa boyutlarını değiştirdiğinizde sayfadaki içerik yeni boyutlara uyacak şekilde ayarlanacaktır.

#### S: Güncellemeden sonra değişiklikleri geri almak ve orijinal sayfa boyutlarını geri yüklemek mümkün müdür?

C: Evet, değişiklikleri geri almak ve orijinal sayfa boyutlarını geri yüklemek istiyorsanız, değişiklik yapmadan önce orijinal PDF belgesinin bir kopyasını saklayabilir veya değişiklikleri kaydetmeden orijinal PDF belgesini yeniden açabilirsiniz. Bu şekilde orijinal boyutlar korunacaktır.