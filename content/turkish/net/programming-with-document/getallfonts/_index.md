---
title: Tüm Yazı Tiplerini PDF Dosyasına Alın
linktitle: Tüm Yazı Tiplerini PDF Dosyasına Alın
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım eğitimde Aspose.PDF for .NET kullanarak bir PDF dosyasından tüm yazı tiplerini nasıl çıkaracağınızı öğrenin. Geliştiriciler ve PDF meraklıları için mükemmel.
type: docs
weight: 160
url: /tr/net/programming-with-document/getallfonts/
---
## giriiş

Bir PDF dosyasında kullanılan tüm yazı tiplerini nasıl çıkaracağınızı hiç merak ettiniz mi? İster PDF belgelerini analiz etmek isteyen bir geliştirici olun, ister sadece en sevdiğiniz e-kitabınızdaki yazı tiplerini merak ediyor olun, yazı tipi bilgilerinin nasıl alınacağını anlamak inanılmaz derecede faydalı olabilir. Bu eğitimde, PDF dosyalarını kolaylıkla düzenlemenizi sağlayan güçlü bir kütüphane olan Aspose.PDF for .NET dünyasına dalacağız. Bu kılavuzun sonunda, herhangi bir PDF belgesinde kullanılan tüm yazı tiplerini çıkarabilecek ve listeleyebileceksiniz. Hadi başlayalım!

## Ön koşullar

Koda geçmeden önce, yerinde olması gereken birkaç şey var:

1. Visual Studio: Makinenizde Visual Studio'nun yüklü olduğundan emin olun. Bu eğitim için kullanacağımız IDE bu.
2.  .NET için Aspose.PDF: Aspose.PDF kütüphanesine sahip olmanız gerekir. Bunu şuradan indirebilirsiniz:[web sitesi](https://releases.aspose.com/pdf/net/).
3. Temel C# Bilgisi: C# programlamaya aşina olmak, kod parçacıklarını daha iyi anlamanıza yardımcı olacaktır.

## Paketleri İçe Aktar

Başlamak için, C# projenize gerekli paketleri içe aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

### Yeni Bir Proje Oluştur

Visual Studio'yu açın ve yeni bir C# Konsol Uygulaması projesi oluşturun. Bu, kodumuzu yazacağımız ortam olacak.

### Aspose.PDF Referansını Ekle

1. Çözüm Gezgini’nde projenizin üzerine sağ tıklayın.
2. "NuGet Paketlerini Yönet" seçeneğini seçin.
3. "Aspose.PDF" dosyasını arayın ve en son sürümü yükleyin.

### Gerekli Ad Alanlarını İçe Aktar

C# dosyanızın en üstüne, aşağıdaki satırları ekleyerek gerekli ad alanlarını içe aktarın:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Artık her şeyi ayarladığımıza göre koda geçebiliriz!

## Adım 1: Belge Dizininizi Ayarlayın

İlk önce, PDF belgenizin yolunu belirtmeniz gerekir. Aspose.PDF'in analiz etmek istediğiniz dosyayı arayacağı yer burasıdır.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF dosyanızın bulunduğu gerçek yol ile. Bu, şuna benzer bir şey olabilir`@"C:\Documents\"`.

## Adım 2: PDF Belgesini Yükleyin

 Sonra, PDF belgesini uygulamanıza yüklemek isteyeceksiniz. Bu, şu şekilde yapılır:`Document` Sınıf Aspose.PDF tarafından sağlanmıştır.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Burada, değiştirin`"input.pdf"` PDF dosyanızın adıyla. Bu kod satırı yeni bir`Document` PDF'nizi temsil eden nesne.

## Adım 3: Tüm Yazı Tiplerini Alın

 Şimdi heyecan verici kısım geliyor! Şunu kullanacaksınız:`FontUtilities` Belgede kullanılan tüm yazı tiplerini almak için kullanılan sınıf.

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

 Bu satır bir diziyi alır`Font` PDF'de kullanılan bir yazı tipini temsil eden nesneler.

## Adım 4: Yazı Tipleri Arasında Döngü

Son olarak, fontların adlarını görüntülemek isteyeceksiniz. Bu, basit bir döngü kullanılarak yapılır.

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

Bu döngü dizideki her yazı tipini yineler ve adını konsola yazdırır. PDF'nizde hangi yazı tiplerinin mevcut olduğunu görmenin basit bir yoludur.

## Çözüm

İşte karşınızda! Aspose.PDF for .NET kullanarak bir PDF dosyasından tüm yazı tiplerini başarıyla çıkardınız. Bu güçlü kütüphane PDF belgelerini düzenlemeyi kolaylaştırır ve sadece birkaç satır kodla yazı tipi adları gibi değerli bilgilere erişebilirsiniz. İster bir PDF görüntüleyici geliştiriyor olun, ister belgeleri analiz ediyor olun veya sadece meraklı olun, bu bilgi işinize yarayacaktır.

## SSS

### Aspose.PDF for .NET nedir?
Aspose.PDF for .NET, geliştiricilerin PDF belgelerini programlı bir şekilde oluşturmalarına, düzenlemelerine ve dönüştürmelerine olanak tanıyan bir kütüphanedir.

### Aspose.PDF'yi ücretsiz kullanabilir miyim?
 Evet, Aspose kütüphaneyi değerlendirmek için kullanabileceğiniz ücretsiz bir deneme sürümü sunuyor. İndirebilirsiniz[Burada](https://releases.aspose.com/).

### Daha fazla dokümanı nerede bulabilirim?
 Kapsamlı belgeleri şurada bulabilirsiniz:[Aspose web sitesi](https://reference.aspose.com/pdf/net/).

### PDF'den başka bilgiler çıkarmak mümkün müdür?
Kesinlikle! Aspose.PDF, diğer şeylerin yanı sıra metin, resim ve meta verileri çıkarmanıza olanak tanır.

### Aspose.PDF için nasıl destek alabilirim?
 Destek almak için şu adresi ziyaret edebilirsiniz:[Aspose forumu](https://forum.aspose.com/c/pdf/10).