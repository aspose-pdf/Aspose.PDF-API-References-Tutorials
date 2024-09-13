---
title: PDF Dosyasına PDF Sayfa Damgası Ekle
linktitle: PDF Dosyasına PDF Sayfa Damgası Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Bu detaylı kılavuzla Aspose.PDF for .NET kullanarak PDF sayfa damgası eklemeyi öğrenin. PDF belgelerinizin etkisini artırın.
type: docs
weight: 40
url: /tr/net/programming-with-stamps-and-watermarks/add-pdf-page-stamp/
---
## giriiş

PDF dosyaları, ister raporları, ister eğitim materyallerini veya yasal belgeleri paylaşmak olsun, günlük dijital etkileşimlerimizin ayrılmaz bir parçası haline geldi. PDF formatlarına bu kadar çok güvenildiğinden, bunları nasıl değiştireceğinizi ve özelleştireceğinizi anlamak önemlidir. Kişisel bir dokunuş eklemenin veya gerekli bilgileri eklemenin etkili bir yolu, bir PDF'deki sayfaları damgalamaktır. Bu kılavuzda, .NET için Aspose.PDF kullanarak bir PDF sayfa damgası ekleme adımlarında size yol göstereceğiz. O halde kemerlerinizi bağlayın! İster yeni başlayan ister deneyimli bir geliştirici olun, sizi bir ziyafet bekliyor.

## Ön koşullar

Sayfa damgası eklemenin inceliklerine dalmadan önce, ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım. İşte .NET için Aspose.PDF'yi etkili bir şekilde kullanmak için ön koşullar:

### .NET Çerçevesi
Bilgisayarınızda .NET Framework yüklü olmalıdır. Aspose.PDF, .NET Core, .NET Framework ve daha fazlasını destekler, bu yüzden projenize bağlı olarak uyumluluklarını kontrol edin.

### .NET Kütüphanesi için Aspose.PDF
 Geliştirme ortamınızda Aspose.PDF kütüphanesinin kurulu olması gerekir.[buradan indirin](https://releases.aspose.com/pdf/net/). 

### İDE
Herhangi bir metin düzenleyiciyi kullanabilirsiniz ancak verimli bir kodlama deneyimi için Visual Studio gibi bir Entegre Geliştirme Ortamı (IDE) kullanmanız şiddetle önerilir.

### C# Temel Bilgisi
C# kod parçacıklarıyla uğraştığımız için, dilin temellerini anlamak, takip etmenizi kolaylaştıracaktır.

### PDF Dosyası
 Damga eklemek istediğiniz bir örnek PDF dosyanız olsun. Buna şu şekilde atıfta bulunacağız:`PDFPageStamp.pdf`. 

## Paketleri İçe Aktar 

Kodumuzu yazmaya başlamadan önce, Aspose.PDF kütüphanesi için gerekli paketleri içe aktardığımızdan emin olmamız gerekir. İşte nasıl yapılacağı:

### Projenizi Açın
IDE'nizi başlatın ve mevcut projenizi açın veya yeni bir proje oluşturun.

### Aspose.PDF Ad Alanını İçe Aktar
C# dosyanızın en üstüne aşağıdaki using yönergesini ekleyerek başlamalısınız:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Bu ad alanları, damga ekleme de dahil olmak üzere PDF belgelerini düzenlemenize olanak tanıyan işlevler sunar.

Artık her şeyi ayarladığımıza göre, PDF sayfa damgası eklemenin ayrıntılı adımlarına geçelim. Süreci anlaşılır olması için parçalara ayırdık. 

## Adım 1: Belge Dizinini Tanımlayın

İlk önce, PDF belgeleri için yolu ayarlamanız gerekir. Bu değişken, dosyaları okumak ve kaydetmek için dizininiz olarak işlev görecektir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` dizininize giden gerçek yol ile.

## Adım 2: Mevcut PDF Belgesini Açın

 Daha sonra, damgalamak istediğiniz PDF dosyasını açmak isteyeceksiniz.`Document` Aspose.PDF'den sınıfa giderek PDF'nizi kolayca yükleyebilirsiniz.

```csharp
Document pdfDocument = new Document(dataDir + "PDFPageStamp.pdf");
```

 Burada yeni bir şey yaratıyoruz`Document` nesne ve onu yükleme`PDFPageStamp.pdf`. Dosyanın belirtilen dizinde olduğundan emin olun.

## Adım 3: Sayfa Damgasını Oluşturun

 Elinizde belge varken, bir belge oluşturmanın zamanı geldi`PdfPageStamp`Bu, PDF belgelerinde belirtilen sayfalara damga eklemekten sorumlu sınıftır.

```csharp
PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
```

Burada örnekledik`pageStamp` ve bunu ilk sayfaya uygulamak istediğimizi belirttik (indeksleme 1'den başlar).

## Adım 4: Sayfa Damgası Özelliklerini Yapılandırın

Pulunuza istediğiniz görünümü kazandırmak için birkaç özelliği yapılandırabilirsiniz:

- Arka Plan: Bu, pulun ön planda mı yoksa arka planda mı görüneceğine karar verir.
- XIndent ve YIndent: Pulun sayfadaki yerleşimini belirler.
- Döndür: Bu, pulunuzun dönüş açısını tanımlar.

Bu özellikleri şu şekilde ayarlayabilirsiniz:

```csharp
pageStamp.Background = true; // Arka plan için doğru
pageStamp.XIndent = 100; // Yatay pozisyonu ayarla
pageStamp.YIndent = 100; // Dikey pozisyonu ayarla
pageStamp.Rotate = Rotation.on180; // 180 derece döndür
```

 Ayarlamaktan çekinmeyin`XIndent` Ve`YIndent` Sayfada istediğiniz yere damganızı yerleştirmek için değerler.

## Adım 5: Sayfaya Damgayı Ekleyin

İşte tam bu noktada; yaratılan damgayı sayfaya uygulamamız gerekiyor.

```csharp
pdfDocument.Pages[1].AddStamp(pageStamp);
```

Bu komut yeni yapılandırdığınız damgayı belirtilen sayfaya ekleyecektir.

## Adım 6: Belgeyi Kaydedin

Damgalama işleminden sonra yeni damgalanmış PDF belgenizi kaydetme zamanı geldi. 

```csharp
dataDir = dataDir + "PDFPageStamp_out.pdf"; // Çıktı dosya yolu
pdfDocument.Save(dataDir); // Güncellenen belgeyi kaydet
```

Artık yeni damgalanan PDF aynı dizine yeni bir adla kaydedilecek.`PDFPageStamp_out.pdf`.

## Adım 7: Onay Mesajı

Sonuna bir dokunuş ekleyerek konsola bir onay mesajı yazdıralım.

```csharp
Console.WriteLine("\nPdf page stamp added successfully.\nFile saved at " + dataDir);
```

Bu satır yalnızca görevinizin başarıyla tamamlandığını doğrulamakla kalmaz, aynı zamanda damgalı PDF'in kaydedileceği yolu da sağlar.

## Çözüm

Ve işte karşınızda! Aspose.PDF for .NET kullanarak bir PDF sayfa damgası eklemeyi öğrendiniz. Belge dizininizi tanımlamaktan PDF'nizi damgalamaya ve kaydetmeye kadar, bu adım adım kılavuz size PDF dosyalarını kolayca düzenlemeniz için gereken bilgiyi sağladı. Aspose.PDF'nin neler yapabileceğini keşfetmeye devam ederken, PDF belgelerinizi geliştirme olasılıkları sonsuzdur. Öyleyse neden bekliyorsunuz? Bugün denemeye başlayın ve PDF'lerinizin öne çıkmasını sağlayın.

## SSS

### PDF'e hangi tür pulları ekleyebilirim?  
PDF belgelerinize metin damgaları, resim damgaları veya özel grafik damgaları ekleyebilirsiniz.

### Pulun görünümünü özelleştirebilir miyim?  
Kesinlikle! İstediğiniz görünümü elde etmek için renk, dönüş ve boyut gibi özellikleri ayarlayabilirsiniz.

### Aspose.PDF'i kullanmak için herhangi bir özel yazılıma ihtiyacım var mı?  
Hayır, ihtiyacınız olan tek şey Aspose.PDF kütüphanesi, .NET framework ve uygun bir IDE.

### Farklı sayfalara birden fazla pul ekleyebilir miyim?  
 Evet, istediğiniz kadar yaratabilirsiniz`PdfPageStamp` İhtiyacınız olan nesneleri seçip PDF'inizin çeşitli sayfalarına uygulayabilirsiniz.

### Daha fazla örnek veya dokümanı nerede bulabilirim?  
 Şunu kontrol edebilirsiniz:[Aspose.PDF Belgeleri](https://reference.aspose.com/pdf/net/) Daha fazla ayrıntı ve örnek için.