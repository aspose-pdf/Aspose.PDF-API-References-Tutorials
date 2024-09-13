---
title: Çizgi Çizimi
linktitle: Çizgi Çizimi
second_title: Aspose.PDF for .NET API Referansı
description: .NET için Aspose.PDF kullanarak bir PDF belgesinde çizgilerin nasıl çizileceğini öğrenin. Bu adım adım kılavuz, belgenizi ayarlamayı, çizgiler eklemeyi ve dosyayı kaydetmeyi kapsar.
type: docs
weight: 80
url: /tr/net/programming-with-graphs/drawing-line/
---
## giriiş

PDF belgesinde çizgi çizmek basit bir görev gibi görünebilir, ancak görsel yardımcılar, diyagramlar oluşturmak ve önemli alanları vurgulamak için güçlü bir araç olabilir. Bu kılavuzda, .NET için Aspose.PDF kullanarak PDF belgesinde çizgi çizme sürecini adım adım ele alacağız. Bu eğitim, ortamınızı kurmaktan, üzerinde çizgiler çizilmiş bir PDF üretmek için kodu yürütmeye kadar her şeyi kapsayacaktır.

## Ön koşullar

Koda dalmadan önce ihtiyacınız olacak birkaç şey var:

1.  Aspose.PDF for .NET: Aspose.PDF for .NET'in yüklü olması gerekir. Bunu şuradan indirebilirsiniz:[Aspose web sitesi](https://releases.aspose.com/pdf/net/).
2. .NET Geliştirme Ortamı: .NET uygulamaları için bir geliştirme ortamı kurduğunuzdan emin olun. Visual Studio bunun için iyi bir seçimdir.
3. Temel C# Bilgisi: Bu eğitimde yer alan kod parçacıklarını ve örnekleri anlamak için C# programlamaya aşina olmak faydalı olacaktır.

## Paketleri İçe Aktar

Aspose.PDF for .NET ile çalışmak için ilgili ad alanlarını içe aktarmanız gerekir. Aşağıdaki using yönergesini C# dosyanızın en üstüne ekleyin:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Bu ad alanları, PDF belgelerini düzenlemek ve şekiller çizmek için gereken sınıflara ve yöntemlere erişim sağlar.

Çizgi çizme sürecini bir dizi adıma bölelim. Her adım, istenen sonucu nasıl elde edeceğinizi anlamanıza yardımcı olmak için kodun belirli bir bölümünde size rehberlik edecektir.

## Adım 1: Belgenizi ve Sayfanızı Ayarlayın

İlk adım yeni bir PDF belgesi oluşturmak ve ona bir sayfa eklemektir. Bunu şu şekilde yapabilirsiniz:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge örneği oluştur
Document pDoc = new Document();

// PDF belgesinin sayfa sayfa koleksiyonunu ekle
Page pg = pDoc.Pages.Add();
```

 Burada,`dataDir` çıktı PDF'inizin kaydedileceği yoldur.`Document` PDF'leri işlemek için ana sınıftır ve`Page` PDF belgesinde tek bir sayfayı temsil eder.

## Adım 2: Sayfa Kenar Boşluklarını Yapılandırın

Satırlarınızın kenardan kenara uzanmasını sağlamak için sayfa kenar boşluklarını sıfıra ayarlamanız gerekir:

```csharp
// Sayfa kenar boşluğunu tüm kenarlarda 0 olarak ayarla
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

Bu, varsayılan tüm kenar boşluklarını kaldırarak çizim için tam sayfa bir tuval sağlar.

## Adım 3: Grafik Nesnesini Oluşturun

 Sonra, bir tane oluşturun`Graph` sayfanın boyutlarına uyan nesne. Bu nesne şekilleriniz için bir kapsayıcı görevi görecektir:

```csharp
// Genişliği ve Yüksekliği sayfa boyutlarına eşit olan Grafik nesnesi oluşturun
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(pg.PageInfo.Width, pg.PageInfo.Height);
```

 The`Graph` nesnesi sayfaya şekiller eklemenize ve onları düzenlemenize olanak tanır.

## Adım 4: İlk Çizgiyi Çizin

Şimdi ilk çizginizi çizme zamanı. Bu örnek, sayfanın sol alt köşesinden sağ üst köşesine bir çizgi çizecektir:

```csharp
// Sayfanın Sol Alt köşesinden Sağ Üst köşesine kadar ilk satır nesnesini oluşturun
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });

// Grafik nesnesinin şekiller koleksiyonuna çizgi ekle
graph.Shapes.Add(line);
```

 The`Line` sınıf, çizginin başlangıç ve bitiş noktaları için koordinatlar alır. Burada,`pg.Rect.LLX` Ve`pg.Rect.URY` sırasıyla sayfanın sol alt ve sağ üst köşelerini temsil eder.

## Adım 5: İkinci Çizgiyi Çizin

İkinci çizgi için sol üst köşeden sağ alt köşeye doğru çizeceğiz:

```csharp
// Sayfanın sol üst köşesinden sayfanın sağ alt köşesine çizgi çizin
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });

// Grafik nesnesinin şekiller koleksiyonuna çizgi ekle
graph.Shapes.Add(line2);
```

Bu çizgi sayfayı çapraz olarak ters yönde kesecektir.

## Adım 6: Grafiği Sayfaya Ekleyin

 Çizgiler çizildikten sonra artık şunu eklemeniz gerekiyor:`Graph` sayfanın paragraf koleksiyonuna nesne:

```csharp
// Sayfanın paragraf koleksiyonuna Grafik nesnesi ekle
pg.Paragraphs.Add(graph);
```

 Bu adım, şunları entegre eder:`Graph` nesneyi (satırlarınızla birlikte) PDF sayfasına aktarın.

## Adım 7: Belgeyi Kaydedin

Son olarak belgenizi bir dosyaya kaydedin:

```csharp
dataDir = dataDir + "DrawingLine_out.pdf";

// PDF dosyasını kaydet
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);
```

 Bu, çizdiğiniz çizgilerle PDF'yi kaydeder ve`Console.WriteLine` ifadesi işlemin başarılı olduğunu teyit eder.

## Çözüm

Aspose.PDF for .NET kullanarak bir PDF belgesinde çizgiler çizmek, yönetilebilir adımlara böldüğünüzde basit bir işlemdir. Bu öğreticiyi takip ederek, bir PDF belgesini nasıl ayarlayacağınızı, üzerine çizgiler nasıl çizeceğinizi ve nihai ürünü nasıl kaydedeceğinizi öğrendiniz. İster diyagramlar oluşturun, ister metni vurgulayın veya sadece PDF düzenlemeyle deneyler yapın, bu kılavuz PDF'lerdeki çizgilerle çalışmak için sağlam bir temel sağlar.

 Herhangi bir sorunuz varsa veya daha fazla yardıma ihtiyacınız varsa, lütfen bizimle iletişime geçmekten çekinmeyin.[Aspose.PDF belgeleri](https://reference.aspose.com/pdf/net/) veya ziyaret edin[Aspose destek forumu](https://forum.aspose.com/c/pdf/10).

## SSS

### Çizgilerin dışında farklı şekiller çizebilir miyim?
 Evet, dikdörtgenler, elipsler ve çokgenler gibi çeşitli şekiller çizebilirsiniz.`Aspose.Pdf.Drawing` ad alanı.

### Çizgilerin rengini ve kalınlığını nasıl ayarlarım?
 Ayarlayabilirsiniz`Line` nesnenin`StrokeColor` Ve`LineWidth` Satırlarınızın görünümünü özelleştirmek için özellikler.

### Sayfanın belirli bölgelerine çizgi çizmek mümkün müdür?
 Kesinlikle! Sadece koordinatları ayarlayın`Line` satırları gerektiği gibi konumlandırmak için nesne.

### Satırlara metin ekleyebilir miyim?
 Evet, oluşturarak metin ekleyebilirsiniz`TextFragment` nesneleri ve onları yerleştirme`Paragraphs` Sayfanın koleksiyonu.

### Yeni bir PDF oluşturmak yerine mevcut bir PDF'e satır eklemek istersem ne olur?
 Mevcut bir PDF'yi kullanarak yükleyebilirsiniz`Document` ve daha sonra benzer yöntemleri kullanarak mevcut sayfalara satırlar ekleyin.