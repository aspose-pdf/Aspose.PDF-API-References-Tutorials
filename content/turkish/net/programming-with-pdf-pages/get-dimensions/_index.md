---
title: PDF Sayfa Boyutlarını Alın
linktitle: PDF Sayfa Boyutlarını Alın
second_title: Aspose.PDF for .NET API Referansı
description: Bu eğitimde, .NET için Aspose.PDF kullanarak PDF sayfa boyutlarının nasıl alınacağını ve düzenlemelerin nasıl yapılacağını açıklıyoruz. İşlem boyunca size rehberlik etmek için ayrıntılı adımlar sağlanmıştır.
type: docs
weight: 60
url: /tr/net/programming-with-pdf-pages/get-dimensions/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasında sayfa boyutlarını almanın adım adım sürecini size göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği kendi projelerinizde anlamanıza ve uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, Aspose.PDF for .NET kullanarak bir PDF dosyasındaki bir sayfanın boyutlarını nasıl alacağınızı öğreneceksiniz.

## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dilinin temel bilgisi
- Geliştirme ortamınıza .NET için Aspose.PDF yüklendi

## Adım 1: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Bu, PDF dosyanızın bulunduğu konumdur. "YOUR DOCUMENTS DIRECTORY" ifadesini uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: PDF belgesini açın
 Daha sonra PDF dosyasını şu şekilde açabilirsiniz:`Document` Aspose.PDF sınıfı. PDF dosyasına doğru yolu belirttiğinizden emin olun.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Adım 3: Boş bir sayfa ekleyin (gerekirse)
 PDF belgesinde zaten sayfalar varsa, dizini kullanarak mevcut bir sayfaya atlayabilirsiniz`1` (ilk sayfanın indeksi 1'dir). Aksi takdirde, belgeye yeni bir sayfa ekleyebilirsiniz.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## Adım 4: Sayfa boyutlarını alın
 Artık sayfa boyutlarını kullanarak alabilirsiniz`GetPageRect()` yöntemi`Page` nesne. Bu yöntem bir`Rectangle` sayfanın boyutlarını içeren nesne. Genişlik ve yüksekliğe erişmek için`Width` Ve`Height` özellikler.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## Adım 5: Sayfayı döndürün
 Sayfayı döndürmek istiyorsanız, şunu kullanabilirsiniz:`Rotate` mülkiyeti`Page`nesne. Bu örnekte, sayfa 90 derece döndürülmüştür.

```csharp
page. Rotate = Rotate. on90;
```

## Adım 6: Sayfa boyutlarını tekrar alın
 Sayfa döndürüldükten sonra, sayfa boyutlarını tekrar şu şekilde alabilirsiniz:`GetPageRect()` Yöntem.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### .NET için Aspose.PDF kullanarak Boyutları Almak için örnek kaynak kodu 

```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// PDF belgesine boş bir sayfa ekler
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Sayfa yüksekliği ve genişlik bilgilerini al
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Sayfayı 90 derecelik açıyla döndür
page.Rotate = Rotation.on90;
// Sayfa yüksekliği ve genişlik bilgilerini al
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasındaki bir sayfanın boyutlarını nasıl elde edeceğimizi öğrendik. Sağlanan adımları izleyerek, sayfa boyutlarını kolayca çıkarabilir ve diğer PDF düzenleme işlemlerini gerçekleştirebilirsiniz. Aspose.PDF for .NET, PDF dosyalarıyla çalışmak için büyük esneklik sunar ve güçlü ve özelleştirilmiş çözümler geliştirmenize olanak tanır.

Bu kütüphanenin sunduğu tüm özellikleri keşfetmek için Aspose.PDF belgelerini incelemeye devam edin.

### PDF sayfa boyutlarını almak için SSS

#### S: PDF dosyasındaki belirli bir sayfanın boyutlarını nasıl alabilirim?

A: PDF dosyasındaki belirli bir sayfanın boyutlarını almak için şunu kullanabilirsiniz:`GetPageRect()` yöntemi`Page` .NET için Aspose.PDF'deki nesne. Bu yöntem bir`Rectangle` Sayfanın boyutlarını (genişlik ve yükseklik) içeren nesne.

####  S: Ne anlama geliyor?`GetPageRect(true)` method do in the provided C# source code?

 A:`GetPageRect(true)` Sağlanan C# kaynak kodundaki yöntem, herhangi bir döndürme uygulandıktan sonra sayfanın boyutlarını döndürür. Sayfa döndürülürse, yöntem döndürülen sayfanın boyutlarını döndürür; bu boyut orijinal boyutlardan farklı olabilir.

#### S: Aspose.PDF for .NET kullanarak PDF belgesindeki tüm sayfaların boyutlarını alabilir miyim?

 A: Evet, PDF belgesindeki tüm sayfaların boyutlarını,`Pages` koleksiyonu`Document` nesne ve kullanımı`GetPageRect(true)` Her sayfa için bir yöntem.

#### S: Bir sayfanın yönünü (dikey veya yatay) boyutlarına göre nasıl belirleyebilirim?

A: Bir sayfanın yönünü boyutlarına göre belirlemek için sayfanın genişliğini ve yüksekliğini karşılaştırabilirsiniz. Genişlik yükseklikten büyükse sayfa yatay yöndedir ve yükseklik genişlikten büyükse sayfa dikey yöndedir.

#### S: Aspose.PDF for .NET kullanarak bir sayfanın boyutlarını değiştirebilir miyim?

 A: Evet, .NET için Aspose.PDF'de bir sayfanın boyutlarını değiştirebilirsiniz.`Rectangle` Sayfa boyutlarını temsil eden nesne, ihtiyaçlarınıza göre genişliğini ve yüksekliğini ayarlayabilir ve ardından değişiklikleri sayfaya uygulayabilirsiniz.