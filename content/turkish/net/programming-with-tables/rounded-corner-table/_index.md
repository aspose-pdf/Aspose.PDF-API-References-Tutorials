---
title: Yuvarlak Köşe Masası PDF Belgesinde
linktitle: Yuvarlak Köşe Masası PDF Belgesinde
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF belgesinde yuvarlak köşeli bir tablonun nasıl oluşturulacağını öğrenin.
type: docs
weight: 190
url: /tr/net/programming-with-tables/rounded-corner-table/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak PDF belgesinde yuvarlak köşeli bir tablo oluşturmanız için size adım adım rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve nasıl uygulayacağınızı göstereceğiz.

## Adım 1: Tablonun oluşturulması
Öncelikle aşağıdaki kodu kullanarak tabloyu oluşturacağız:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Adım 2: Yuvarlak Köşe Stili Kurulumu
Şimdi tablonun yuvarlatılmış köşe stilini yapılandıracağız:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Adım 3: Tablo Kenarlığı Kurulumu
Tabloya yuvarlatılmış köşeli bir kenarlık vermek için bir BorderInfo nesnesi oluşturmamız ve bunu uygun parametrelerle yapılandırmamız gerekir:

```csharp
// Sınır rengini ayarlamak için bir GraphInfo nesnesi oluşturun
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Boş bir BorderInfo nesnesi oluşturun
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Yuvarlatılmış kenarlığın yarıçapını 15 olarak ayarlayın
bInfo.RoundedBorderRadius = 15;

// Tabloya sınır bilgilerini uygulayın
tab1.Border = bInfo;
```

### .NET için Aspose.PDF kullanılarak Yuvarlak Köşeli Tablo için örnek kaynak kodu

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Boş bir BorderInfo nesnesi oluşturun
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Kenarlığı, yuvarlaklığın yarıçapının 15 olduğu daha yuvarlak bir kenarlık olarak ayarlayın
bInfo.RoundedBorderRadius = 15;
// Masanın köşe stilini Yuvarlak olarak ayarlayın.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Tablo sınır bilgilerini ayarlayın
tab1.Border = bInfo;
```

## Çözüm
Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF belgesinde yuvarlak köşeli bir tablo oluşturmayı öğrendiniz. Bu adım adım kılavuz, yuvarlak köşe stilini ve tablo kenarlığını nasıl ayarlayacağınızı gösterdi. Artık bu bilgiyi kendi projelerinize uygulayabilirsiniz.

### PDF belgesinde yuvarlak köşeli masa için SSS

#### S: Masanın yuvarlatılmış köşelerinin yarıçapını özelleştirebilir miyim?

A: Evet, tablonun yuvarlatılmış köşelerinin yarıçapını, değerini değiştirerek özelleştirebilirsiniz.`bInfo.RoundedBorderRadius` Sağlanan C# kaynak kodundaki özellik. İstenilen yuvarlak köşe görünümünü elde etmek için sadece istenen yarıçap değerini (nokta cinsinden) ayarlayın.

#### S: Tablodaki her bir hücreye yuvarlatılmış köşeler uygulayabilir miyim?

C: Hayır, yuvarlatılmış köşe stili tüm tabloya bir bütün olarak uygulanır. Aspose.PDF for .NET şu anda tablodaki tek tek hücrelere yuvarlatılmış köşeler uygulamak için yerleşik destek sağlamaz.

#### S: Yuvarlak köşeli kenarlığın rengini değiştirebilir miyim?

 A: Evet, yuvarlatılmış köşe kenarlığının rengini, değerini değiştirerek değiştirebilirsiniz.`graph.Color` C# kaynak kodundaki özellik. Sadece istediğiniz rengi sağlayın, örneğin`Aspose.Pdf.Color.Red` veya herhangi bir geçerli renk gösterimi.

#### S: Aynı PDF belgesindeki farklı tablolara farklı köşe stilleri (örneğin kare ve yuvarlak) uygulamak mümkün müdür?

C: Evet, aynı PDF belgesindeki farklı tablolara farklı köşe stilleri uygulamak mümkündür. Birden fazla tablo oluşturabilir ve köşe stillerini gereksinimlerinize göre ayrı ayrı yapılandırabilirsiniz.

#### S: Yuvarlak köşeli kenarlığın kalınlığını ayarlayabilir miyim?

 A: Evet, yuvarlatılmış köşe sınırının kalınlığını,`BorderInfo` C# kaynak kodundaki nesnenin özelliklerini ayarlayabilirsiniz. Örneğin,`bInfo.Width` kenarlığın kalınlığını ayarlama özelliği.