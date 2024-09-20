---
title: İmza Bilgilerini Çıkar
linktitle: İmza Bilgilerini Çıkar
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF belgelerinden dijital imzaları ve sertifika bilgilerini nasıl çıkaracağınızı öğrenin. C# geliştiricileri için eksiksiz bir adım adım kılavuz.
type: docs
weight: 80
url: /tr/net/programming-with-security-and-signatures/extract-signature-info/
---
## giriiş

Günümüzün dijital dünyasında, belgelerin güvenliğini ve bütünlüğünü sağlamak hayati önem taşır. PDF'leri güvence altına almak için kullanılan yaygın yöntemlerden biri dijital imza eklemektir. Ancak, imzanın ayrıntılarını almak ve doğrulamak bazen zor olabilir, özellikle de çeşitli sertifikalarla uğraşırken. Bu kılavuzda, .NET için Aspose.PDF kullanarak PDF belgelerinden imza bilgilerini çıkarma sürecini adım adım anlatacağız ve bu görevi kolaylaştıracağız. İmza alanlarına nasıl erişeceğinizi, sertifika bilgilerini nasıl çıkaracağınızı ve bunları bir dosyaya nasıl kaydedeceğinizi öğreneceksiniz.

## Ön koşullar

Başlamadan önce, başlamak için her şeyin hazır olduğundan emin olalım.

-  Aspose.PDF for .NET Kütüphanesi: Eğer henüz sahip değilseniz, şu adresten indirebilirsiniz:[Aspose.PDF for .NET indirme sayfası](https://releases.aspose.com/pdf/net/). 
- .NET Geliştirme Ortamı: Visual Studio gibi bir IDE'ye ihtiyacınız olacak.
- Temel C# Bilgisi: Bu eğitimdeki kod parçacıklarını anlamak için C#'a aşina olmak faydalı olacaktır.
- Dijital İmzalı PDF Belgesi: Test amaçlı olarak, en az bir dijital imza içeren bir PDF dosyanız olduğundan emin olun.

## Gerekli Ad Alanlarını İçe Aktarma

Koda atlamadan önce, gerekli ad alanlarını içe aktarmak önemlidir. Bu ad alanları, Aspose.PDF işlevselliğine erişmenizi ve PDF belgeleriyle çalışmanızı sağlayacaktır.

```csharp
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
using System;
```

Artık temelleri kurduğumuza göre, PDF'den imza bilgilerini çıkarma sürecine geçelim.

## Adım 1: Belge Dizinini Ayarlama

 Bir PDF belgesi üzerinde çalışmaya başlamadan önce, kullanacağınız dosyanın konumunu belirtmeniz gerekir.`"YOUR DOCUMENT DIRECTORY"` PDF'lerinizin saklandığı dizinin gerçek yolu ile.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

Burada, PDF dosyasının bulunduğu dizini ve dosya adını belirtiyoruz. Dosyanın o dizinde bulunduğundan emin olun!

## Adım 2: PDF Belgesini Yükleme

 Artık dizininizi ayarladığınıza göre, bir sonraki adım PDF belgesini yüklemektir.`Document` Aspose.PDF'den sınıf.

```csharp
using (Document pdfDocument = new Document(input))
{
    // PDF'i burada işleyin.
}
```

 Bu kod satırı bir`Document`PDF dosyasını temsil eden nesne.`using` ifadesi, belge işlendikten sonra kaynakların temizlenmesini sağlar.

## Adım 3: Form Alanlarına Erişim

Bu adımda, PDF belgesindeki tüm form alanlarında döngü yapacağız. İmzalar genellikle form alanları olarak saklandığından, bu adım imza alanlarını tanımlamamıza yardımcı olacaktır.

```csharp
foreach (Field field in pdfDocument.Form)
{
    // İmza alanlarını burada tanımlayın.
}
```

 Yineleme yoluyla`Form` mülkiyeti`Document` nesne, her form alanını inceleyerek imza alanı olup olmadığını kontrol edebiliriz.

## Adım 4: İmza Alanlarını Tanımlama

 Form alanlarına eriştiğinizde, bir sonraki adım hangilerinin imza alanları olduğunu belirlemektir. Bunu, her alanı bir`SignatureField` nesne.

```csharp
SignatureField sf = field as SignatureField;
if (sf != null)
{
    // İmza bilgilerini ayıkla.
}
```

 Burada şunu kullanıyoruz:`as` her form alanını bir anahtar kelimeye dönüştürmeye çalışmak için`SignatureField`Eğer oyuncu seçimi başarılı olursa, sahanın bir imza olduğunu anlarız.

## Adım 5: Sertifikayı Çıkarma

İmza alanını tanımladığınıza göre, bir sonraki görev sertifikayı imzadan çıkarmaktır. Sertifikalar, imzalayan ve imzanın geçerliliği hakkında önemli bilgiler içerir.

```csharp
Stream cerStream = sf.ExtractCertificate();
```

 The`ExtractCertificate` yöntem bir döndürür`Stream` sertifika verilerini içeren nesne. Bu akış, sertifikayı daha ileri analiz veya depolama için kaydetmek için kullanılabilir.

## Adım 6: Sertifikayı Bir Dosyaya Kaydetme

 Sertifikayı çıkardıktan sonra, son adım onu bir dosyaya kaydetmektir. Bu durumda, sertifikayı bir`.cer` dosya.

```csharp
if (cerStream != null)
{
    using (cerStream)
    {
        byte[] bytes = new byte[cerStream.Length];
        using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
        {
            cerStream.Read(bytes, 0, bytes.Length);
            fs.Write(bytes, 0, bytes.Length);
        }
    }
}
```

Bu kod bloğunda:

1. Sertifika akışının boş olmadığını kontrol edin.
2. Sertifika verilerini bir bayt dizisine oku.
3.  Bayt dizisini bir diziye yazın`.cer` Belge dizinindeki dosya.

## Çözüm

Aspose.PDF for .NET kullanarak PDF belgelerinden dijital imzaları ve ilgili sertifika bilgilerini çıkarmak, basit adımlara bölündüğünde oldukça basittir. Belgeleri denetliyor, imzaları doğruluyor veya sadece güvenli saklama için sertifikaları saklıyor olun, bu eğitim size bunu verimli bir şekilde yapmanız için gereken bilgiyi sağlar. Unutmayın, belgeleri güvence altına almak ve doğrulamak günümüzün dijital dünyasında kritik öneme sahiptir ve Aspose.PDF for .NET gibi araçları kullanmak bunu çok daha kolay hale getirir.

## SSS

### Aspose.PDF for .NET kullanarak bir PDF'den birden fazla imza çıkarabilir miyim?
Evet, kod belgedeki tüm form alanlarında döngüye girerek, varsa birden fazla imzayı çıkarmanıza olanak tanır.

### PDF'de imza bulunamazsa ne olur?
İmza alanları mevcut değilse, kod herhangi bir hata vermeden bunları atlayacaktır.

### İmzanın geçerliliğini doğrulamak için bu yaklaşımı kullanabilir miyim?
Sertifikayı çıkarabilirsiniz ancak imzanın geçerliliğini doğrulamak, sertifikanın güven zincirini kontrol etmek gibi ek adımlar gerektirir.

### Aspose.PDF for .NET kullanarak diğer form alanı verilerini çıkarmak mümkün müdür?
Evet, Aspose.PDF yalnızca imza alanlarına değil, PDF'deki çeşitli form alanlarına erişmenize ve bunları değiştirmenize olanak tanır.

### Çıkarılan sertifikanın detaylarını nasıl görebilirim?
 Sertifika bir kez kaydedildiğinde`.cer` Dosyayı herhangi bir sertifika görüntüleyicisini kullanarak açabilir veya daha detaylı inceleme için bir sistem sertifika deposuna aktarabilirsiniz.