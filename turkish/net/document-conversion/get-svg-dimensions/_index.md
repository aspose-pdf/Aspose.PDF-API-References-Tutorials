---
title: SVG Boyutlarını Alın
linktitle: SVG Boyutlarını Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak SVG boyutlarını elde etmek için adım adım kılavuz.
type: docs
weight: 40
url: /tr/net/document-conversion/get-svg-dimensions/
---
## giriiş
Bu eğitimde, Aspose.PDF for .NET kullanarak bir SVG dosyasının boyutlarını alma sürecinde size yol göstereceğiz. SVG (Scalable Vector Graphics), vektör grafiklerini temsil etmek için kullanılan XML tabanlı bir görüntü formatıdır. Aşağıdaki adımları kullanarak bir SVG dosyasının boyutlarını alabilecek ve bunları PDF olarak kaydedebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgi.
- Sisteminizde kurulu .NET için Aspose.PDF kitaplığı.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: SVG dosyasını yükleme
Bu adımda Aspose.PDF for .NET kullanarak SVG dosyasını yükleyeceğiz. Aşağıdaki kodu izleyin:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` SVG dosyanızın bulunduğu gerçek dizinle.

## 2. Adım: Sayfa boyutu ayarı
Artık SVG dosyasını yüklediğimize göre, sayfa boyutunu SVG içeriğine uyacak şekilde ayarlayabiliriz. Aşağıdaki kodu kullanın:

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

Yukarıdaki kod, sayfa kenar boşluklarını sıfıra ayarlayarak sayfa boyutunun SVG içeriğine göre ayarlanmasını sağlar.

## 3. Adım: Ortaya çıkan PDF'yi kaydetme
Sayfa boyutunu ayarladıktan sonra, artık ortaya çıkan PDF belgesini kaydedebiliriz. İşte son adım:

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` Çıktı PDF dosyasını kaydetmek istediğiniz istediğiniz dizinle.
  
### Aspose.PDF for .NET kullanarak Get SVG Dimensions için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir SVG dosyasının boyutlarını alma sürecini adım adım ele aldık. Yukarıda özetlenen talimatları izleyerek, artık bir SVG dosyasının boyutlarını alabilmeli ve bunları PDF Formatında kaydedebilmelisiniz. Bu özellik, bir vektör grafiğinin boyutlarını ölçmeniz gerektiğinde yararlı olabilir.

### SSS

#### S: SVG nedir?

A: SVG (Scalable Vector Graphics), vektör grafiklerini temsil etmek için kullanılan XML tabanlı bir görüntü formatıdır. Raster görüntülerin aksine, SVG dosyaları çözünürlükten bağımsızdır ve kalite kaybı olmadan ölçeklenebilir. SVG, web'de grafikleri görüntülemek için yaygın olarak kullanılır ve kolaylıkla düzenlenebilir ve manipüle edilebilir.

#### S: SVG'den PDF'e dönüştürme için neden Aspose.PDF for .NET'i kullanıyorsunuz?

Y: Aspose.PDF for .NET, SVG dosyalarını işlemek ve bunları PDF formatına dönüştürmek için güvenilir ve verimli bir yol sağlar. PDF'de doğru gösterimi sağlamak için sayfa boyutunu, kenar boşluklarını ve diğer özellikleri ayarlamak gibi dönüştürme sürecini özelleştirmek için çeşitli seçenekler ve ayarlar sunar.

#### S: Karmaşık grafikler ve metin içeren SVG dosyalarını dönüştürebilir miyim?

C: Evet, Aspose.PDF for .NET karmaşık grafikler, metin ve vektör öğeleri içeren SVG dosyalarını işleyebilir. Dönüştürme işlemi sırasında SVG içeriğinin ayrıntılarını ve kalitesini doğru bir şekilde koruyarak yüksek kaliteli PDF belgeleri sağlar.

#### S: Aspose.PDF for .NET ile SVG dosyalarından metin çıkarmak mümkün mü?

C: Evet, Aspose.PDF for .NET, SVG dosyalarından metin çıkarmanıza izin verir. Metin öğelerini SVG'den ayıklamak ve daha sonraki işlemler için ayrı olarak kaydetmek için kitaplığın metin çıkarma özelliklerini kullanabilirsiniz.