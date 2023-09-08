---
title: SVG Boyutlarını Alın
linktitle: SVG Boyutlarını Alın
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak SVG boyutlarını alma konusunda adım adım kılavuz.
type: docs
weight: 40
url: /tr/net/document-conversion/get-svg-dimensions/
---
## giriiş
Bu eğitimde, Aspose.PDF for .NET'i kullanarak bir SVG dosyasının boyutlarını alma sürecinde size yol göstereceğiz. SVG (Ölçeklenebilir Vektör Grafikleri), vektör grafiklerini temsil etmek için kullanılan XML tabanlı bir görüntü formatıdır. Aşağıdaki adımları kullanarak bir SVG dosyasının boyutlarını alıp PDF olarak kaydedebileceksiniz.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgiler.
- Sisteminizde yüklü olan .NET için Aspose.PDF kütüphanesi.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: SVG dosyasını yükleme
Bu adımda Aspose.PDF for .NET'i kullanarak SVG dosyasını yükleyeceğiz. Aşağıdaki kodu izleyin:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` SVG dosyanızın bulunduğu gerçek dizinle.

## Adım 2: Sayfa boyutunu ayarlama
Artık SVG dosyasını yüklediğimize göre sayfa boyutunu SVG içeriğine uyacak şekilde ayarlayabiliriz. Aşağıdaki kodu kullanın:

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

Yukarıdaki kod, sayfa kenar boşluklarını sıfıra ayarlayarak sayfa boyutunun SVG içeriğine göre ayarlanmasına olanak tanır.

## 3. Adım: Ortaya çıkan PDF'yi kaydetme
Sayfa boyutunu ayarladıktan sonra artık ortaya çıkan PDF belgesini kaydedebiliriz. İşte son adım:

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` Çıktı PDF dosyasını kaydetmek istediğiniz dizini seçin.
  
### Aspose.PDF for .NET kullanarak SVG Boyutlarını Alma için örnek kaynak kodu

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
Bu eğitimde, Aspose.PDF for .NET kullanarak bir SVG dosyasının boyutlarını almanın adım adım sürecini ele aldık. Yukarıda özetlenen talimatları izleyerek artık bir SVG dosyasının boyutlarını alıp bunları PDF Formatında kaydedebilmelisiniz. Bu özellik, bir vektör grafiğinin boyutlarını ölçmeniz gerektiğinde yararlı olabilir.

### SSS'ler

#### S: SVG nedir?

C: SVG (Ölçeklenebilir Vektör Grafikleri), vektör grafiklerini temsil etmek için kullanılan XML tabanlı bir görüntü formatıdır. Raster görüntülerin aksine, SVG dosyaları çözünürlükten bağımsızdır ve kalite kaybı olmadan ölçeklenebilir. SVG, web'de grafikleri görüntülemek için yaygın olarak kullanılır ve kolaylıkla düzenlenebilir ve değiştirilebilir.

#### S: SVG'den PDF'ye dönüşüm için neden Aspose.PDF for .NET kullanmalısınız?

C: Aspose.PDF for .NET, SVG dosyalarını işlemek ve bunları PDF formatına dönüştürmek için güvenilir ve etkili bir yol sağlar. PDF'de doğru temsili sağlamak amacıyla sayfa boyutunu, kenar boşluklarını ve diğer özellikleri ayarlamak gibi dönüştürme sürecini özelleştirmek için çeşitli seçenekler ve ayarlar sunar.

#### S: Karmaşık grafik ve metin içeren SVG dosyalarını dönüştürebilir miyim?

C: Evet, Aspose.PDF for .NET, karmaşık grafikler, metin ve vektör öğeleri içeren SVG dosyalarını işleyebilir. Dönüştürme işlemi sırasında SVG içeriğinin ayrıntılarını ve kalitesini doğru bir şekilde koruyarak yüksek kaliteli PDF belgeleri elde edilmesini sağlar.

#### S: Aspose.PDF for .NET ile SVG dosyalarından metin çıkarmak mümkün müdür?

C: Evet, Aspose.PDF for .NET, SVG dosyalarından metin çıkarmanıza olanak tanır. SVG'den metin öğeleri çıkarmak ve bunları daha sonraki işlemler için ayrı ayrı kaydetmek için kitaplığın metin çıkarma özelliklerini kullanabilirsiniz.