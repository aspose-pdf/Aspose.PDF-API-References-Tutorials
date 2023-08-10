---
title: PDF Sayfa Boyutlarını Alın
linktitle: PDF Sayfa Boyutlarını Alın
second_title: Aspose.PDF for .NET API Referansı
description: Bu eğitimde, Aspose.PDF for .NET kullanarak PDF sayfa boyutlarının nasıl alınacağını ve manipülasyonların nasıl gerçekleştirileceğini açıklıyoruz. Süreç boyunca size rehberlik etmek için ayrıntılı adımlar sağlanmıştır.
type: docs
weight: 60
url: /tr/net/programming-with-pdf-pages/get-dimensions/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF dosyasında sayfa boyutlarını alma sürecini adım adım anlatacağız. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, Aspose.PDF for .NET kullanarak bir PDF dosyasındaki sayfanın boyutlarını nasıl alacağınızı öğreneceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Aspose.PDF for .NET geliştirme ortamınızda yüklü

## 1. Adım: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Bu, PDF dosyanızın bulunduğu konumdur. "BELGELER DİZİNİNİZİ" uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: PDF belgesini açın
 Ardından, PDF dosyasını kullanarak açabilirsiniz.`Document` Aspose.PDF sınıfı. PDF dosyasının doğru yolunu belirttiğinizden emin olun.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## 3. Adım: Boş bir sayfa ekleyin (gerekirse)
 PDF belgesinde zaten sayfalar varsa, dizini kullanarak mevcut bir sayfaya atlayabilirsiniz.`1` (ilk sayfanın indeksi 1'dir). Aksi takdirde, belgeye yeni bir sayfa ekleyebilirsiniz.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## 4. Adım: Sayfa boyutlarını alın
 Artık sayfa boyutlarını kullanarak alabilirsiniz.`GetPageRect()` yöntemi`Page` nesne. Bu yöntem bir döndürür`Rectangle` sayfanın boyutlarını içeren nesne. kullanarak genişlik ve yüksekliğe erişebilirsiniz.`Width` Ve`Height` özellikler.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## 5. Adım: Sayfayı döndürün
 Sayfayı döndürmek isterseniz,`Rotate` mülkiyeti`Page`nesne. Bu örnekte, sayfa 90 derece döndürülmüştür.

```csharp
page. Rotate = Rotate. on90;
```

## 6. Adım: Sayfa boyutlarını tekrar alın
 Sayfa döndürme işleminden sonra, sayfa boyutlarını kullanarak tekrar elde edebilirsiniz.`GetPageRect()` yöntem.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Aspose.PDF for .NET kullanarak Get Dimensions için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Pdf belgesine boş bir sayfa ekler
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Sayfa yükseklik ve genişlik bilgilerini alın
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Sayfayı 90 derecelik açıyla döndür
page.Rotate = Rotation.on90;
// Sayfa yükseklik ve genişlik bilgilerini alın
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasındaki sayfanın boyutlarını nasıl alacağımızı öğrendik. Sağlanan adımları izleyerek sayfa boyutlarını kolayca çıkarabilir ve diğer PDF işleme işlemlerini gerçekleştirebilirsiniz. Aspose.PDF for .NET, PDF dosyalarıyla çalışmak için büyük esneklik sunar ve güçlü ve özelleştirilmiş çözümler geliştirmenize olanak tanır.

Bu kitaplığın sunduğu tüm özellikleri keşfetmek için Aspose.PDF belgelerini daha fazla keşfetmekten çekinmeyin.

### PDF sayfası boyutlarını almayla ilgili SSS

#### S: Bir PDF dosyasındaki belirli bir sayfanın boyutlarını nasıl alabilirim?

A: Bir PDF dosyasındaki belirli bir sayfanın boyutlarını almak için`GetPageRect()` yöntemi`Page` Aspose.PDF for .NET'te nesne. Bu yöntem bir döndürür`Rectangle` sayfanın boyutlarını (genişlik ve yükseklik) içeren nesne.

####  S: ne yapar`GetPageRect(true)` method do in the provided C# source code?

 C:`GetPageRect(true)` sağlanan C# kaynak kodundaki yöntem, herhangi bir döndürme uygulandıktan sonra sayfanın boyutlarını döndürür. Sayfa döndürülürse, yöntem döndürülen sayfanın orijinal boyutlarından farklı olabilecek boyutlarını döndürür.

#### S: Aspose.PDF for .NET kullanarak PDF belgesindeki tüm sayfaların boyutlarını alabilir miyim?

 C: Evet, PDF belgesindeki tüm sayfaların boyutlarını,`Pages` koleksiyonu`Document` nesne ve kullanarak`GetPageRect(true)` Her sayfa için yöntem.

#### S: Boyutlarına göre bir sayfanın yönünü (dikey veya yatay) nasıl belirleyebilirim?

C: Boyutlarına göre bir sayfanın yönünü belirlemek için sayfanın genişliğini ve yüksekliğini karşılaştırabilirsiniz. Genişlik yükseklikten büyükse sayfa yatay yöndedir ve yükseklik genişlikten büyükse sayfa dikey yöndedir.

#### S: Aspose.PDF for .NET kullanarak bir sayfanın boyutlarını değiştirebilir miyim?

 C: Evet, bir sayfanın boyutlarını Aspose.PDF for .NET'te değiştirebilirsiniz. aldıktan sonra`Rectangle` sayfa boyutlarını temsil eden bir nesne, gereksinimlerinize göre genişlik ve yüksekliği ayarlayabilir ve ardından değişiklikleri sayfaya uygulayabilirsiniz.