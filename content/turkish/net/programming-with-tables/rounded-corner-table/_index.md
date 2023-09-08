---
title: PDF Belgesinde Yuvarlatılmış Köşe Tablosu
linktitle: PDF Belgesinde Yuvarlatılmış Köşe Tablosu
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF belgesinde nasıl yuvarlak köşeli tablo oluşturulacağını öğrenin.
type: docs
weight: 190
url: /tr/net/programming-with-tables/rounded-corner-table/
---
Bu eğitimde, Aspose.PDF for .NET'i kullanarak PDF belgesinde yuvarlatılmış köşeli bir tablo oluşturmak için size adım adım rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve size nasıl uygulayacağınızı göstereceğiz.

## 1. Adım: Tabloyu oluşturma
Öncelikle aşağıdaki kodu kullanarak tabloyu oluşturacağız:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Adım 2: Yuvarlak Köşe Stili Kurulumu
Daha sonra tablonun yuvarlatılmış köşe stilini yapılandıracağız:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Adım 3: Tablo Kenarlığı Kurulumu
Tabloya yuvarlatılmış köşeli bir kenarlık vermek için bir BorderInfo nesnesi oluşturmamız ve onu uygun parametrelerle yapılandırmamız gerekir:

```csharp
// Kenarlık rengini ayarlamak için bir GraphInfo nesnesi oluşturun
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Boş bir BorderInfo nesnesi oluşturun
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Yuvarlatılmış kenarlığın yarıçapını 15 olarak ayarlayın
bInfo.RoundedBorderRadius = 15;

// Kenarlık bilgilerini tabloya uygulama
tab1.Border = bInfo;
```

### Aspose.PDF for .NET kullanan Yuvarlak Köşe Tablosu için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Boş bir BorderInfo nesnesi oluşturun
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Kenarlığı, yuvarlak yarıçapın 15 olduğu daha yuvarlak bir kenarlık olarak ayarlayın
bInfo.RoundedBorderRadius = 15;
// Tablo Köşe stilini Yuvarlak olarak ayarlayın.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Tablo kenarlığı bilgilerini ayarlama
tab1.Border = bInfo;
```

## Çözüm
Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF belgesinde nasıl yuvarlak köşeli bir tablo oluşturulacağını öğrendiniz. Bu adım adım kılavuz, yuvarlak köşe stilini ve masa kenarlığını nasıl ayarlayacağınızı gösterdi. Artık bu bilgiyi kendi projelerinize uygulayabilirsiniz.

### PDF belgesindeki yuvarlatılmış köşe tablosu için SSS

#### S: Masanın yuvarlatılmış köşelerinin yarıçapını özelleştirebilir miyim?

C: Evet, değerini değiştirerek tablonun yuvarlatılmış köşelerinin yarıçapını özelleştirebilirsiniz.`bInfo.RoundedBorderRadius` Sağlanan C# kaynak kodundaki özellik. İstenilen yuvarlak köşe görünümünü elde etmek için istenen yarıçap değerini (nokta olarak) ayarlamanız yeterlidir.

#### S: Tablodaki tek tek hücrelere yuvarlatılmış köşeler uygulayabilir miyim?

C: Hayır, yuvarlak köşe stili tablonun tamamına bir bütün olarak uygulanır. Aspose.PDF for .NET şu anda tablodaki ayrı ayrı hücrelere yuvarlatılmış köşeler uygulamak için yerleşik destek sağlamamaktadır.

#### S: Yuvarlatılmış köşe kenarlığının rengini değiştirebilir miyim?

 C: Evet, yuvarlatılmış köşe kenarlığının rengini, değerini değiştirerek değiştirebilirsiniz.`graph.Color` C# kaynak kodundaki özellik. Basitçe istediğiniz rengi sağlayın, örneğin`Aspose.Pdf.Color.Red` veya başka herhangi bir geçerli renk gösterimi.

#### S: Aynı PDF belgesindeki farklı tablolara farklı köşe stilleri (örn. kare ve yuvarlak) uygulamak mümkün müdür?

C: Evet, aynı PDF belgesindeki farklı tablolara farklı köşe stilleri uygulamak mümkündür. Birden fazla tablo oluşturabilir ve köşe stillerini gereksinimlerinize göre ayrı ayrı yapılandırabilirsiniz.

#### S: Yuvarlatılmış köşe kenarlığının kalınlığını ayarlayabilir miyim?

 C: Evet, yuvarlatılmış köşe kenarlığının kalınlığını,`BorderInfo` C# kaynak kodundaki nesnenin özellikleri. Örneğin,`bInfo.Width` Kenarlığın kalınlığını ayarlama özelliği.