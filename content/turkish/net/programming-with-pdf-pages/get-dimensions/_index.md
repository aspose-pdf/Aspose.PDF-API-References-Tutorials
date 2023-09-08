---
title: PDF Sayfa Boyutlarını Al
linktitle: PDF Sayfa Boyutlarını Al
second_title: .NET API Referansı için Aspose.PDF
description: Bu eğitimde Aspose.PDF for .NET kullanarak PDF sayfa boyutlarının nasıl alınacağını ve manipülasyonların nasıl gerçekleştirileceğini açıklıyoruz. Süreç boyunca size yol gösterecek ayrıntılı adımlar sağlanmıştır.
type: docs
weight: 60
url: /tr/net/programming-with-pdf-pages/get-dimensions/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasında sayfa boyutlarını alma sürecini adım adım anlatacağız. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sunacağız. Bu eğitimin sonunda Aspose.PDF for .NET kullanarak PDF dosyasındaki bir sayfanın boyutlarını nasıl alacağınızı öğreneceksiniz.

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Aspose.PDF for .NET, geliştirme ortamınızda yüklü

## 1. Adım: Belge dizinini tanımlayın
Öncelikle belgeler dizininizin yolunu ayarlamanız gerekir. Bu, PDF dosyanızın bulunduğu konumdur. "BELGELERİNİZ DİZİNİ"ni uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: PDF belgesini açın
 Daha sonra PDF dosyasını kullanarak açabilirsiniz.`Document` Aspose.PDF sınıfı. PDF dosyasının doğru yolunu belirttiğinizden emin olun.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## 3. Adım: Boş bir sayfa ekleyin (gerekirse)
 PDF belgesinde zaten sayfalar varsa, dizini kullanarak mevcut bir sayfaya atlayabilirsiniz.`1` (ilk sayfanın dizini 1'dir). Aksi takdirde belgeye yeni bir sayfa ekleyebilirsiniz.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## 4. Adım: Sayfa boyutlarını alın
 Artık sayfa boyutlarını aşağıdakileri kullanarak alabilirsiniz:`GetPageRect()` yöntemi`Page` nesne. Bu yöntem bir döndürür`Rectangle` sayfanın boyutlarını içeren nesne. Genişlik ve yüksekliğe aşağıdakileri kullanarak erişebilirsiniz:`Width` Ve`Height` özellikler.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## 5. Adım: Sayfayı döndürün
 Sayfayı döndürmek istiyorsanız,`Rotate` mülkiyeti`Page`nesne. Bu örnekte sayfa 90 derece döndürülmüştür.

```csharp
page. Rotate = Rotate. on90;
```

## 6. Adım: Sayfa boyutlarını tekrar alın
 Sayfa döndürmeden sonra sayfa boyutlarını tekrar kullanarak alabilirsiniz.`GetPageRect()` yöntem.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Aspose.PDF for .NET kullanarak Boyutları Al için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// PDF belgesine boş bir sayfa ekler
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Sayfa yüksekliği ve genişliği bilgilerini alın
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Sayfayı 90 derece açıyla döndür
page.Rotate = Rotation.on90;
// Sayfa yüksekliği ve genişliği bilgilerini alın
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Çözüm
Bu eğitimde Aspose.PDF for .NET kullanarak PDF dosyasındaki bir sayfanın boyutlarını nasıl elde edeceğimizi öğrendik. Verilen adımları takip ederek sayfa boyutlarını kolayca çıkarabilir ve diğer PDF düzenleme işlemlerini gerçekleştirebilirsiniz. Aspose.PDF for .NET, PDF dosyalarıyla çalışma konusunda büyük esneklik sunar ve güçlü ve özelleştirilmiş çözümler geliştirmenize olanak tanır.

Bu kütüphanenin sunduğu tüm özellikleri keşfetmek için Aspose.PDF belgelerini daha fazla incelemekten çekinmeyin.

### PDF sayfa boyutları almayla ilgili SSS

#### S: Bir PDF dosyasındaki belirli bir sayfanın boyutlarını nasıl edinebilirim?

C: Bir PDF dosyasındaki belirli bir sayfanın boyutlarını almak için`GetPageRect()` yöntemi`Page` Aspose.PDF for .NET'teki nesne. Bu yöntem bir döndürür`Rectangle` sayfanın boyutlarını (genişlik ve yükseklik) içeren nesne.

####  S: Ne işe yarar?`GetPageRect(true)` method do in the provided C# source code?

 C:`GetPageRect(true)` Sağlanan C# kaynak kodundaki yöntem, herhangi bir döndürme uygulandıktan sonra sayfanın boyutlarını döndürür. Sayfa döndürülürse yöntem, döndürülen sayfanın orijinal boyutlarından farklı olabilecek boyutlarını döndürür.

#### S: Aspose.PDF for .NET'i kullanarak PDF belgesindeki tüm sayfaların boyutlarını alabilir miyim?

 C: Evet, PDF belgesindeki tüm sayfaların boyutlarını, PDF belgesindeki tüm sayfaların boyutlarını yineleyerek alabilirsiniz.`Pages` koleksiyonu`Document` nesneyi kullanmak ve`GetPageRect(true)` Her sayfa için yöntem.

#### S: Bir sayfanın yönünü (dikey veya yatay) boyutlarına göre nasıl belirleyebilirim?

C: Bir sayfanın yönünü boyutlarına göre belirlemek için sayfanın genişliğini ve yüksekliğini karşılaştırabilirsiniz. Genişlik yükseklikten büyükse sayfa yatay yöndedir; yükseklik genişlikten büyükse sayfa dikey yöndedir.

#### S: Aspose.PDF for .NET'i kullanarak bir sayfanın boyutlarını değiştirebilir miyim?

 C: Evet, Aspose.PDF for .NET'te bir sayfanın boyutlarını değiştirebilirsiniz. Aldıktan sonra`Rectangle` Sayfa boyutlarını temsil eden nesneyi kullanarak genişlik ve yüksekliği ihtiyaçlarınıza göre ayarlayabilir ve ardından değişiklikleri sayfaya uygulayabilirsiniz.