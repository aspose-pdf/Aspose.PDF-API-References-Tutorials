---
title: PDF Dosyasındaki Tüm Metni Çıkar
linktitle: Metni AllIn PDF Dosyasından Çıkar
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım eğitimle Aspose.PDF for .NET kullanarak PDF dosyalarından metni nasıl kolayca çıkaracağınızı öğrenin.
type: docs
weight: 180
url: /tr/net/programming-with-text/extract-text-all/
---
## giriiş

Bu dijital çağda, PDF belgeleriyle uğraşmak yaygın bir görev haline geldi. İster bir belge işleme uygulaması oluşturmak isteyen bir geliştirici olun, ister önemli verileri çıkarması gereken bir iş profesyoneli olun, PDF dosyalarından metni etkili bir şekilde nasıl çıkaracağınızı bilmek size bir ton zaman ve enerji kazandırabilir. Bu makalede, PDF dosyalarından metni hızlı ve kolay bir şekilde çekmenize yardımcı olabilecek güçlü bir araç olan Aspose.PDF for .NET kitaplığını kullanmaya dalacağız.

## Ön koşullar

PDF dosyalarından metin çıkarmanın inceliklerine girmeden önce, yerine getirmeniz gereken birkaç temel gereksinim vardır:

1. .NET Framework: Geliştirme makinenizde .NET Framework'ün yüklü olduğundan emin olun. Aspose.PDF, .NET ile sorunsuz bir şekilde çalışır, bu nedenle en son sürüme sahip olmak bir artıdır.
2. Aspose.PDF Kütüphanesi: PDF düzenlemelerini işlemek için Aspose.PDF for .NET kütüphanesine ihtiyacınız olacak.[buradan indirin](https://releases.aspose.com/pdf/net/).
3. Geliştirme Ortamı: Visual Studio gibi bir IDE şiddetle tavsiye edilir. Kodunuzu yazmak, derlemek ve hata ayıklamak için kullanıcı dostu bir arayüz sağlar.
4. C# Temel Bilgisi: C# programlama diline aşina olmak, inceleyeceğimiz kod parçacıklarını daha iyi anlamanıza yardımcı olacaktır.

Artık ön koşullarımız tamam olduğuna göre, gerekli paketleri içe aktaralım!

## Paketleri İçe Aktar

Çıkarım sürecimize başlamak için öncelikle C# projenize gerekli ad alanlarını içe aktarmanız gerekir. Bunu şu şekilde yapabilirsiniz:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Bu ad alanları PDF işlemleri için gerekli sınıflara ve yöntemlere erişim sağlayacaktır. 

Çıkarma sürecini kolay takip edilebilir adımlara bölelim. Bu kılavuzun sonunda, herhangi bir PDF dosyasından metni sorunsuz bir şekilde çıkarabileceksiniz.

## Adım 1: Belge Dizininizi Ayarlayın

Yapmak isteyeceğiniz ilk şey PDF dosyanızın bulunduğu dizini belirtmektir. Bu, çalışmak istediğiniz dosyayı bulmak için önemlidir.

Kod Örneği:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Bu kod parçacığında, sadece şunu değiştirin:`"YOUR DOCUMENT DIRECTORY"` PDF dosyanızın bulunduğu gerçek yol ile. Örneğin, dosyanız şu konumdaysa`C:\Documents` , sen ayarlayacaksın`dataDir` o yola.

## Adım 2: PDF Belgesini açın

 Dizininizi ayarladıktan sonra, metni çıkarmak istediğiniz PDF belgesini açmanız gerekir. Bu, şu şekilde yapılır:`Document` Aspose.PDF ad alanından sınıf.

Kod Örneği:

```csharp
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

 Burada, dosya adının doğru olduğundan emin olun`ExtractTextAll.pdf` doğrudur. Bu, metni çıkarmak için çalışacağınız dosyadır.

## Adım 3: Bir Metin Emici Nesne Oluşturun

 Bir sonraki adım, bir tane oluşturmaktır`TextAbsorber` nesne. Bu, PDF'de bulunan tüm metni özümsemenize yardımcı olacak sihirli araçtır.

Kod Örneği:

```csharp
// Metni çıkarmak için TextAbsorber nesnesi oluşturun
TextAbsorber textAbsorber = new TextAbsorber();
```

 Başlatma ile`TextAbsorber`, PDF sayfalarındaki tüm metin içeriğini çıkarmaya hazırlanıyorsunuz.

## Adım 4: Tüm Sayfalar için Absorber'ı Kabul Edin

Artık metin emiciniz hazır olduğuna göre, onu PDF belgesinin tüm sayfalarında çalıştırmanız gerekir. Bu, her sayfadaki metnin yakalanmasını sağlar.

Kod Örneği:

```csharp
// Tüm sayfalar için emiciyi kabul et
pdfDocument.Pages.Accept(textAbsorber);
```

Bu adımla temelde şunu söylüyorsunuz: "Hey, metin emici, devam et ve bu belgedeki her sayfadaki tüm metni topla!"

## Adım 5: Çıkarılan Metni Alın

Metin emildiğinde, onu çıkarma zamanı gelir. Çıkarılan metne basit bir özellik kullanarak erişebilirsiniz.

Kod Örneği:

```csharp
// Çıkarılan metni alın
string extractedText = textAbsorber.Text;
```

 Şimdi değişken`extractedText` PDF'inizden toplanan tüm metni içerir. Ne kadar harika?

## Adım 6: Çıkarılan Metni Bir Dosyaya Yazma

Son olarak, daha sonra kolayca erişebilmek için çıkarılan metni yeni bir metin dosyasına kaydetmek isteyebilirsiniz. İşte bunu nasıl yapacağınız.

Kod Örneği:

```csharp
// Bir yazar oluşturun ve dosyayı açın
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Dosyaya bir satır metin yaz
tw.WriteLine(extractedText);
// Akışı kapat
tw.Close();
```

 Bu kod, adında yeni bir dosya açar`extracted-text.txt`çıkarılan tüm içeriği içine yazar ve sonra dosyayı kapatır. Yani şimdi, çıkarılan metni görmek istediğinizde, sadece belgeler dizininize bakın!

## Çözüm

 İşte bu kadar! Sadece birkaç kolay adımda, Aspose.PDF for .NET kullanarak herhangi bir PDF dosyasından metin çıkarabilirsiniz. Belgeleri analiz etmek için bir uygulama oluşturuyor olun veya sadece bir PDF'den birkaç not almanız gerekiyorsa, Aspose.PDF hayatınızı kolaylaştıran sağlam, kullanımı kolay bir API sağlar. Şuraya göz atmayı unutmayın:[belgeleme](https://reference.aspose.com/pdf/net/) Bu güçlü kütüphanenin sunduğu daha fazla özellik ve yetenek için.

## SSS

### Aspose.PDF for .NET'i ücretsiz kullanabilir miyim?
 Evet, Aspose ücretsiz deneme sunuyor. İndirebilirsiniz[Burada](https://releases.aspose.com/).

### Ya PDF'imde resim ve grafikler varsa?
Aspose.PDF metin çıkarmaya odaklanır. PDF'niz görseller içeriyorsa, bunları işlemek için farklı bir yaklaşıma ihtiyacınız olabilir.

### Geçici lisans var mı?
 Kesinlikle! Geçici bir lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

### Aspose.PDF için desteği nereden alabilirim?
 Destek ve topluluk tartışmalarını şu adreste bulabilirsiniz:[Aspose forumu](https://forum.aspose.com/c/pdf/10).

### Çıkarılan metni hangi formatlarda kaydedebilirim?
 Metni çeşitli biçimlerde kaydedebilirsiniz:`.txt`, `.docx`veya doğrudan bir veritabanına aktarılabilir.