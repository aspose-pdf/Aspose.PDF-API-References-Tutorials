---
title: PDF Sayfa Boyutlarını Güncelle
linktitle: PDF Sayfa Boyutlarını Güncelle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF sayfa boyutlarını güncellemek için adım adım kılavuz. İhtiyaçlarınıza göre boyutları kontrol edin.
type: docs
weight: 150
url: /tr/net/programming-with-pdf-pages/update-dimensions/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesindeki sayfa boyutlarını güncelleme sürecini adım adım anlatacağız. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, Aspose.PDF for .NET kullanarak bir PDF belgesindeki sayfa boyutlarını nasıl değiştireceğinizi öğreneceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Aspose.PDF for .NET geliştirme ortamınızda yüklü

## 1. Adım: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Bu, düzenlenmiş PDF belgenizi kaydetmek istediğiniz konumdur. "BELGELER DİZİNİNİZİ" uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: PDF belgesini açın
 Ardından mevcut PDF belgesini kullanarak açabilirsiniz.`Document` Aspose.PDF sınıfı. Doğru belge yolunu belirttiğinizden emin olun.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## 3. Adım: Sayfa Koleksiyonunu Alın
 Artık PDF belgesinin sayfalar koleksiyonuna aşağıdakileri kullanarak erişebilirsiniz:`Pages` mülkiyeti`Document` sınıf.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## 4. Adım: Belirli bir sayfa edinin
Ardından, koleksiyondaki sayfanın dizinini kullanarak belgenin belirli bir sayfasını seçebilirsiniz. Bu örnekte ikinci sayfayı (dizin 1) kullanıyoruz.

```csharp
Page pdfPage = pageCollection[1];
```

## 5. Adım: Yeni sayfa boyutlarını tanımlayın
 Artık yeni sayfa boyutunu kullanarak ayarlayabilirsiniz.`SetPageSize()` yöntemi`Page`nesne. Bu örnekte, sayfa boyutlarını A4 (11,7 x 8,3 inç) olarak ayarlıyoruz ve puntoya çeviriyoruz (1 inç = 72 punto).

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## 6. Adım: Güncellenen belgeyi kaydedin
 Son olarak, güncellenmiş PDF belgesini kullanarak bir dosyaya kaydedebilirsiniz.`Save()` yöntemi`Document`sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Update Dimensions için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Sayfa koleksiyonunu al
PageCollection pageCollection = pdfDocument.Pages;
// Belirli bir sayfayı al
Page pdfPage = pageCollection[1];
// Sayfa boyutunu A4 (11,7 x 8,3 inç) olarak ayarlayın ve Aspose.Pdf'te 1 inç = 72 punto
// Yani punto cinsinden A4 boyutları (842.4, 597.6) olacaktır.
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// Güncellenen belgeyi kaydedin
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## Çözüm
Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesindeki sayfanın boyutlarının nasıl güncelleneceğini öğrendik. Bu adım adım kılavuzu izleyerek, bir PDF belgesindeki sayfanın boyutlarını gerektiği gibi kolayca değiştirebilirsiniz. Aspose.PDF, PDF dosyalarıyla çalışmak ve sayfa boyutlarını değiştirmek de dahil olmak üzere çeşitli manipülasyonlar gerçekleştirmek için güçlü ve esnek bir API sunar. Bu bilgiyle, özel ihtiyaçlarınızı karşılamak için PDF sayfalarınızın boyutlarını kontrol edebilir ve özelleştirebilirsiniz.

### PDF sayfası boyutlarının güncellenmesiyle ilgili SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesindeki belirli bir sayfanın boyutlarını nasıl güncelleyebilirim?

C: Aspose.PDF for .NET kullanarak bir PDF belgesindeki belirli bir sayfanın boyutlarını güncellemek için şu adımları takip edebilirsiniz:

1. Orijinal PDF dosyanızın bulunduğu yolu ve güncellenmiş PDF dosyasını nereye kaydetmek istediğinizi belirterek belge dizinini ayarlayın. "BELGELER DİZİNİNİZİ" uygun yolla değiştirin.
2.  kullanarak güncellemek için mevcut PDF belgesini açın.`Document` Aspose.PDF sınıfı. Orijinal PDF belgesine giden doğru yolu belirttiğinizden emin olun.
3.  kullanarak PDF belgesinin sayfa koleksiyonuna erişin.`Pages` mülkiyeti`Document` sınıf.
4. Sayfa dizinini kullanarak sayfa koleksiyonundan güncellemek istediğiniz sayfayı seçin. Sağlanan C# kaynak kodunda ikinci sayfayı (dizin 1) kullanıyoruz.
5.  kullanarak yeni sayfa boyutunu tanımlayın.`SetPageSize()` yöntemi`Page` nesne. Örnekte, sayfa boyutlarını A4 boyutuna (11,7 x 8,3 inç) ayarlayarak puntoya (1 inç = 72 punto) dönüştürdük.
6.  Güncellenmiş PDF belgesini kullanarak bir dosyaya kaydedin.`Save()` yöntemi`Document`sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

#### S: PDF belgesindeki birden çok sayfanın boyutlarını aynı anda güncelleyebilir miyim?

C: Evet, PDF belgesindeki birden çok sayfanın boyutlarını aynı anda güncellemek için sağlanan kaynak kodunu değiştirebilirsiniz. Belirli bir sayfayı seçmek yerine (4. adımda gösterildiği gibi), sayfa koleksiyonundaki tüm sayfalar arasında dolaşabilir ve her sayfa için istediğiniz sayfa boyutunu ayarlayabilirsiniz.

#### S: Aspose.PDF for .NET kullanırken sayfa boyutlarını inçten puntoya nasıl dönüştürebilirim?

 C: Aspose.PDF for .NET'te sayfa boyutları için kullanılan ölçüm birimi puntodur ve 1 inç 72 puntoya eşittir. İnçleri noktalara dönüştürmek için aşağıdaki formülü kullanabilirsiniz:`points = inches * 72`. Örneğin, 11,7 x 8,3 inç bir sayfa boyutu ayarlamak için karşılık gelen boyutları (11,7 * 72) ve (8,3 * 72) olarak punto olarak hesaplayabilirsiniz.

#### S: Bir sayfanın boyutlarının güncellenmesi, PDF belgesinin içerik düzenini etkiler mi?

C: Evet, bir sayfanın boyutlarının güncellenmesi, söz konusu sayfadaki PDF belgesinin içerik düzenini etkileyecektir. Sayfa boyutlarını değiştirdiğinizde, sayfadaki içerik yeni boyutlara sığacak şekilde ayarlanacaktır.

#### S: Değişiklikleri geri almak ve orijinal sayfa boyutlarını güncelledikten sonra geri yüklemek mümkün müdür?

C: Evet, değişiklikleri geri almak ve orijinal sayfa boyutlarını geri yüklemek isterseniz, değişiklik yapmadan önce orijinal PDF belgesinin bir kopyasını saklayabilir veya orijinal PDF belgesini değişiklikleri kaydetmeden yeniden açabilirsiniz. Bu şekilde, orijinal boyutlar korunacaktır.