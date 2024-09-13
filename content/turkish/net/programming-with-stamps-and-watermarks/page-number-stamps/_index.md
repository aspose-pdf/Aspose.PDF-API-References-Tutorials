---
title: PDF Dosyasında Sayfa Numarası Damgaları
linktitle: PDF Dosyasında Sayfa Numarası Damgaları
second_title: Aspose.PDF for .NET API Referansı
description: Kolay takip edilebilen, kod örnekleri de içeren kılavuzumuzla, Aspose.PDF for .NET'i kullanarak PDF dosyalarına sayfa numarası damgalarının nasıl ekleneceğini öğrenin.
type: docs
weight: 160
url: /tr/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
## giriiş

Hiç kendinizi bir PDF belgesiyle boğuşurken buldunuz mu, daha kolay gezinme için sayfa numaraları olmasını istediniz mi? İster not paylaşan bir öğrenci, ister rapor sunan bir profesyonel veya çok sayfalı belgeleri yöneten biri olun, sayfa numaraları eklemek PDF dosyalarınızın netliğini gerçekten artırabilir. Neyse ki, güçlü Aspose.PDF for .NET kitaplığıyla PDF belgelerinize sayfa numarası damgalarını kolaylıkla ekleyebilirsiniz. Bu kılavuzda, tüm süreci adım adım anlatarak ihtiyacınız olan tüm bilgilere sahip olmanızı sağlayacağız. Hadi başlayalım!

## Ön koşullar

PDF belgelerinize sayfa numarası damgası eklemeye başlamadan önce, aşağıdaki ön koşulların mevcut olduğundan emin olun:

1. Visual Studio: Sisteminizde Visual Studio'nun yüklü olduğundan emin olun. Kodunuzu burada yazıp çalıştıracaksınız.
2. .NET Framework: Aspose.PDF .NET uygulamaları için tasarlandığından, C# programlama ve .NET framework'e aşinalık şarttır.
3.  Aspose.PDF Kütüphanesi: Aspose.PDF kütüphanesini şu adresten indirebilirsiniz:[Aspose PDF Sürümleri](https://releases.aspose.com/pdf/net/). 
4. PDF'ler hakkında temel bilgi: Uzman olmanıza gerek yok ancak PDF dosyalarının nasıl çalıştığına dair temel bir anlayışa sahip olmak, eğitimi daha iyi anlamanıza yardımcı olacaktır.

Bu ön koşulları sağladığınızda, sayfa numaralarını damgalamaya başlayabilirsiniz!

## Paketleri İçe Aktar

Kodlamaya dalmadan önce, gerekli Aspose.PDF paketlerinin projenize aktarıldığından emin olmanız gerekir. Bu, kütüphane fonksiyonlarından sorunsuz bir şekilde yararlanmak için çok önemlidir. İşte nasıl yapılacağı:

### Yeni Bir Proje Oluştur

1. Visual Studio’yu açın.
2.  Tıkla`File` >`New` >`Project`.
3.  C# için uygun bir şablon seçin (örneğin Konsol Uygulaması), adını verin ve tıklayın`Create`.

### Aspose.PDF Referansını Ekle

1. Çözüm Gezgini’nde proje adına sağ tıklayın.
2.  Tıkla`Manage NuGet Packages`.
3.  Arama`Aspose.PDF` ve en son sürümü yükleyin.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Kütüphanemiz kullanıma hazır olduğuna göre, kodlamaya geçebiliriz!

Artık ortamımız kurulduğuna göre, bir PDF dosyasına sayfa numarası damgaları ekleme zamanı geldi. Daha iyi anlaşılması için bu süreci net adımlara böleceğiz.

## Adım 1: Belge Dizinini Belirleyin

Başlamak için PDF dosyanızın bulunduğu dizini belirtmeniz gerekir. Bu, projenizin başlangıç noktasıdır.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Bu yolu güncelle
```

 Açıklama: Değiştir`"YOUR DOCUMENT DIRECTORY"` PDF dosyanızı içeren dizine giden yol ile. Bu kritiktir çünkü kodunuza, düzenlemek istediğiniz dosyayı nerede bulacağını söyler.

## Adım 2: Belgeyi açın

Daha sonra sayfa numarası damgalarını eklemek istediğimiz mevcut PDF belgesini açacağız.

```csharp
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

 Açıklama: Burada, şunu kullanıyoruz:`Document` Aspose.PDF tarafından sağlanan sınıf, belirli PDF dosyamızı açmak için kullanılır. Dosya adının dizininizde bulunan gerçek dosyayla eşleştiğinden emin olun.

## Adım 3: Sayfa Numarası Damgası Oluşturun

Şimdi eğlenceli kısma geldik! PDF'imize eklemek için bir sayfa numarası damgası oluşturalım.

```csharp
PageNumberStamp pageNumberStamp = new PageNumberStamp();
```

 Açıklama:`PageNumberStamp`sınıf, belgedeki toplam sayfa sayısına göre geçerli sayfa numarasını gösterecek bir damga oluşturmamıza olanak tanır.

## Adım 4: Damgayı Yapılandırın

Şimdi, damga ayarlarınızı yapılandırmanız gerekecek. Damganın nasıl görüneceğini ve davranacağını burada tasarlarsınız.

```csharp
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;
```

Açıklama:
- `Background = false`: Bu, pulun ön planda görüneceği anlamına gelir.
- `Format`: Burada, belgedeki toplam sayfa sayısını dinamik olarak aldığınız "Sayfa X/Y"yi gösterecek biçimde biçimi ayarlıyorsunuz.
- `BottomMargin`: Sayfanın altından itibaren mesafeyi ayarlar.
- `HorizontalAlignment`: Pulun yatay olarak ortalanmasını sağlar.
- `StartingNumber`: Başlangıç sayfa numarasının ne olacağını ayarlar, genellikle 1'den başlar.

## Adım 5: Metin Özelliklerini Ayarlayın

Daha sonra puldaki metnin nasıl görüneceğini özelleştirebilirsiniz.

```csharp
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Açıklama: Bu nitelikler, damganın görsel olarak çekici olması için yazı tipini, yazı boyutunu, stilini (hem kalın hem de italik) ve metnin rengini yapılandırır.

## Adım 6: Damgayı Belirli Bir Sayfaya Ekleyin

Damganızı yapılandırdıktan sonra, onu belgenizdeki belirli bir sayfaya eklemenin zamanı geldi.

```csharp
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

 Açıklama: Bu satır, damgayı PDF'nin ilk sayfasına ekler. Bunu ayarlayabilirsiniz`Pages[1]` Gerektiğinde diğer sayfalar için dizin.

## Adım 7: Çıktı Belgesini Kaydedin

Son olarak, yaptığınız değişikliklerin kalıcı olması için değiştirdiğiniz PDF belgesini kaydedin.

```csharp
dataDir = dataDir + "PageNumberStamp_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);
```

Açıklama: Çıktı dosya yolunu tanımlıyor ve belgeyi kaydediyorsunuz. Konsol, damganın başarıyla eklendiğini ve dosyanın nereye kaydedildiğini size bildirecektir.

## Çözüm

Aspose.PDF for .NET kullanarak PDF dosyalarınıza sayfa numarası damgaları eklemek yalnızca basit değil, aynı zamanda oldukça özelleştirilebilirdir. Sayfa numarası damgası oluşturma sürecini adım adım ele aldık ve bu süreçte size net bir rehberlik sağladık. Artık PDF belgelerinizi geliştirmek, onları daha kullanıcı dostu ve profesyonel hale getirmek için gereken bilgiye sahipsiniz. 

## SSS

### Sayfa numaralarının görünümünü özelleştirebilir miyim?  
Evet! Sayfa numaralarının yazı tipini, boyutunu, rengini ve biçimlendirmesini kılavuzda gösterildiği gibi değiştirebilirsiniz.

### Aspose.PDF'i kullanmak ücretsiz mi?  
 Aspose.PDF ücretsiz deneme sunuyor ancak kapsamlı kullanım için bir lisansa ihtiyacınız olacak. Şuraya göz atın:[satın alma sayfası](https://purchase.aspose.com/buy) Daha fazla bilgi için.

### Uygulama sırasında sorunla karşılaşırsam ne olur?  
 Ziyaret edebilirsiniz[Aspose Destek Forumu](https://forum.aspose.com/c/pdf/10) yardım için.

### Birden fazla sayfa için sayfa numaralarını otomatik olarak nasıl oluşturabilirim?  
Rehberin kodu otomatik olarak toplam sayfa sayısını hesaplar, böylece birden fazla sayfa için özelleştirme yapmak kolaylaşır.

### Aspose.PDF'yi diğer programlama dillerinde kullanabilir miyim?  
Bu kılavuz .NET'e odaklansa da Aspose'un Java, Python ve daha fazlası için kütüphaneleri vardır.