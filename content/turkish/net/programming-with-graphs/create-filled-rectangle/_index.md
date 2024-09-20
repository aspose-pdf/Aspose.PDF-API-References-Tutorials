---
title: Dolu Dikdörtgen Oluştur
linktitle: Dolu Dikdörtgen Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım eğitimle .NET için Aspose.PDF kullanarak PDF'de dolu bir dikdörtgenin nasıl oluşturulacağını öğrenin. Her seviyedeki geliştirici için mükemmel.
type: docs
weight: 50
url: /tr/net/programming-with-graphs/create-filled-rectangle/
---
## giriiş

Görsel olarak çekici PDF'leri programatik olarak oluşturmak istediniz mi hiç? Eğer öyleyse, doğru yerdesiniz! Bu eğitimde, PDF belgelerini kolaylıkla düzenlemenize olanak tanıyan güçlü bir kütüphane olan .NET için Aspose.PDF dünyasına dalacağız. Bugün, bir PDF dosyası içinde dolu bir dikdörtgen oluşturmaya odaklanacağız. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu kılavuz sizi her adımda dostça ve ilgi çekici bir şekilde yönlendirecektir. O halde, kodlama şapkanızı alın ve başlayalım!

## Ön koşullar

Koda geçmeden önce, yerinde olması gereken birkaç şey var:

1. Visual Studio: Makinenizde Visual Studio'nun yüklü olduğundan emin olun. .NET geliştirme için harika bir IDE'dir.
2.  .NET için Aspose.PDF: Aspose.PDF kütüphanesini indirip yüklemeniz gerekecek. Bunu bulabilirsiniz[Burada](https://releases.aspose.com/pdf/net/).
3. Temel C# Bilgisi: C# programlamaya dair biraz bilgi sahibi olmak, kod parçacıklarını daha iyi anlamanıza yardımcı olacaktır.

## Paketleri İçe Aktar

Başlamak için, C# projenize gerekli paketleri içe aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

### Yeni Bir Proje Oluştur

Visual Studio'yu açın ve yeni bir C# projesi oluşturun. Basitlik için bir Konsol Uygulaması seçebilirsiniz.

### Aspose.PDF Referansını Ekle

1. Çözüm Gezgini’nde projenizin üzerine sağ tıklayın.
2. "NuGet Paketlerini Yönet" seçeneğini seçin.
3. "Aspose.PDF" dosyasını arayın ve en son sürümü yükleyin.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Artık her şeyi ayarladığımıza göre koda geçelim!

## Adım 1: Belge Dizininizi Ayarlayın

İlk önce, PDF'nizin kaydedileceği yolu belirtmeniz gerekir. Bu önemlidir çünkü programa dosyayı nerede oluşturacağını söyler.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF'yi kaydetmek istediğiniz makinenizdeki gerçek yol ile.

## Adım 2: Bir Belge Örneği Oluşturun

 Daha sonra, bir örnek oluşturacağız`Document`sınıf. Bu sınıf, üzerinde çalışacağınız PDF belgesini temsil eder.

```csharp
// Belge örneği oluştur
Document doc = new Document();
```

Bu satır, üzerinde değişiklik yapabileceğimiz yeni bir PDF belgesi başlatır.

## Adım 3: Belgeye Bir Sayfa Ekleyin

Şimdi, belgemize bir sayfa ekleyelim. Her PDF'in en az bir sayfaya ihtiyacı vardır, değil mi?

```csharp
// PDF dosyasının sayfa sayfa koleksiyonunu ekle
Page page = doc.Pages.Add();
```

Bu kod, belgeye yeni bir sayfa ekleyerek üzerine şekiller çizmemize olanak tanır.

## Adım 4: Bir Grafik Örneği Oluşturun

 Şekilleri çizmek için bir tane oluşturmamız gerekiyor`Graph` Örneğin. Bir grafiği çeşitli şekiller çizebileceğiniz bir tuval olarak düşünün.

```csharp
// Grafik örneği oluştur
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

Burada genişliği 100, yüksekliği 400 olan bir grafik oluşturuyoruz.

## Adım 5: Grafiği Sayfaya Ekleyin

Artık grafiğimiz hazır, şimdi bunu daha önce oluşturduğumuz sayfaya ekleyelim.

```csharp
// Sayfa örneğinin paragraf koleksiyonuna grafik nesnesi ekle
page.Paragraphs.Add(graph);
```

Bu çizgi grafiği sayfaya iliştirerek çizime hazır hale getirir.

## Adım 6: Dikdörtgen Örneği Oluşturun

Daha sonra renkle doldurmak istediğimiz bir dikdörtgen oluşturacağız.

```csharp
// Dikdörtgen örneği oluştur
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

Bu kodda dikdörtgenin konumunu ve boyutunu tanımlıyoruz. Parametreler x ve y koordinatlarını, genişliği ve yüksekliği temsil eder.

## Adım 7: Dolgu Rengini Belirleyin

Şimdi dikdörtgenimiz için bir renk seçelim. Bu örnekte onu kırmızıyla dolduracağız.

```csharp
// Grafik nesnesi için dolgu rengini belirtin
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

Bu satır dikdörtgenin dolgu rengini kırmızıya ayarlar. İstediğiniz rengi seçebilirsiniz!

## Adım 8: Grafiğe Dikdörtgeni Ekleyin

Dikdörtgenimiz hazır olduğuna göre, onu grafiğe eklemenin zamanı geldi.

```csharp
// Grafik nesnesinin şekiller koleksiyonuna dikdörtgen nesnesi ekle
graph.Shapes.Add(rect);
```

Bu kod dikdörtgeni grafiğe ekleyerek onu çizimimizin bir parçası haline getirir.

## Adım 9: PDF Belgesini Kaydedin

Son olarak belgemizi belirtilen dizine kaydetmemiz gerekiyor.

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// PDF dosyasını kaydet
doc.Save(dataDir);
```

 Bu kod PDF dosyasını şu adla kaydeder:`CreateFilledRectangle_out.pdf` daha önce belirttiğiniz dizinde.

## Adım 10: Onay Mesajı

Her şeyin yolunda gittiğini bize bildirmek için bir onay mesajı yazdırabiliriz.

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

Bu satır, konsolda doldurulmuş dikdörtgenin başarıyla oluşturulduğunu doğrulayan bir mesaj çıktısı verecektir.

## Çözüm

Ve işte karşınızda! .NET için Aspose.PDF kullanarak bir PDF belgesinde doldurulmuş bir dikdörtgeni başarıyla oluşturdunuz. Bu güçlü kütüphane, PDF düzenleme için bir olasılıklar dünyası açarak, çarpıcı belgeleri programatik olarak oluşturmanıza olanak tanır. İster raporlar, ister faturalar veya başka bir PDF türü oluşturun, Aspose.PDF sizin için her şeyi yapar.

## SSS

### Aspose.PDF for .NET nedir?
Aspose.PDF for .NET, geliştiricilerin PDF belgelerini programlı bir şekilde oluşturmalarına, düzenlemelerine ve dönüştürmelerine olanak tanıyan bir kütüphanedir.

### Aspose.PDF'yi ücretsiz kullanabilir miyim?
 Evet, Aspose kütüphanenin özelliklerini keşfetmeniz için kullanabileceğiniz ücretsiz bir deneme sürümü sunuyor. İndirebilirsiniz[Burada](https://releases.aspose.com/).

### Aspose.PDF desteği almanın bir yolu var mı?
 Kesinlikle! Aspose forumundan destek alabilirsiniz[Burada](https://forum.aspose.com/c/pdf/10).

### Aspose.PDF'i nasıl satın alabilirim?
 Aspose.PDF'yi satın alma sayfasını ziyaret ederek satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).

### Aspose.PDF ile hangi tür şekiller oluşturabilirim?
Aspose.PDF kütüphanesini kullanarak dikdörtgenler, daireler, çizgiler ve daha fazlası dahil olmak üzere çeşitli şekiller oluşturabilirsiniz.