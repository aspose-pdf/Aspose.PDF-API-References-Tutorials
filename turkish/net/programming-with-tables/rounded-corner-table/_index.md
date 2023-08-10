---
title: PDF Belgesinde Yuvarlak Köşe Sehpa
linktitle: PDF Belgesinde Yuvarlak Köşe Sehpa
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF belgesinde yuvarlak köşeli tablo oluşturmayı öğrenin.
type: docs
weight: 190
url: /tr/net/programming-with-tables/rounded-corner-table/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF belgesinde yuvarlatılmış köşe tablosu oluşturmanız için adım adım rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve nasıl uygulayacağınızı göstereceğiz.

## 1. Adım: Tabloyu oluşturma
İlk olarak aşağıdaki kodu kullanarak tabloyu oluşturacağız:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Adım 2: Yuvarlatılmış Köşe Stili Kurulumu
Ardından, tablo için yuvarlatılmış köşe stilini yapılandıracağız:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## 3. Adım: Tablo Kenarlığı Kurulumu
Tabloya yuvarlatılmış köşe kenarlığı vermek için, bir BorderInfo nesnesi oluşturmamız ve onu uygun parametrelerle yapılandırmamız gerekir:

```csharp
// Kenarlık rengini ayarlamak için bir GraphInfo nesnesi oluşturun
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Boş bir BorderInfo nesnesi oluşturun
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Yuvarlatılmış kenarlığın yarıçapını 15 olarak ayarlayın
bInfo.RoundedBorderRadius = 15;

// Kenarlık bilgilerini tabloya uygula
tab1.Border = bInfo;
```

### Aspose.PDF for .NET kullanan Yuvarlatılmış Köşe Tablosu için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Boş bir BorderInfo nesnesi oluşturun
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Kenarlığı, yuvarlak yarıçapı 15 olan daha yuvarlak bir kenarlık olarak ayarlayın
bInfo.RoundedBorderRadius = 15;
// Tablo Köşe stilini Yuvarlak olarak ayarlayın.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Tablo sınır bilgilerini ayarlayın
tab1.Border = bInfo;
```

## Çözüm
Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF belgesinde yuvarlak köşeli tablo oluşturmayı öğrendiniz. Bu adım adım kılavuz size yuvarlak köşe stilini ve masa kenarlığını nasıl ayarlayacağınızı gösterdi. Artık bu bilgiyi kendi projelerinize uygulayabilirsiniz.

### PDF belgesinde yuvarlatılmış köşe tablosu için SSS

#### S: Tablonun yuvarlatılmış köşelerinin yarıçapını özelleştirebilir miyim?

C: Evet, tablonun yuvarlatılmış köşelerinin yarıçapını, değerini değiştirerek özelleştirebilirsiniz.`bInfo.RoundedBorderRadius` sağlanan C# kaynak kodundaki özellik. İstenen yuvarlatılmış köşe görünümünü elde etmek için istenen yarıçap değerini (nokta cinsinden) ayarlamanız yeterlidir.

#### S: Tablodaki tek tek hücrelere yuvarlatılmış köşeler uygulayabilir miyim?

C: Hayır, yuvarlatılmış köşe stili tüm tabloya bir bütün olarak uygulanır. Aspose.PDF for .NET şu anda tablodaki tek tek hücrelere yuvarlatılmış köşeler uygulamak için yerleşik destek sağlamamaktadır.

#### S: Yuvarlatılmış köşe kenarlığının rengini değiştirebilir miyim?

 C: Evet, yuvarlatılmış köşe kenarlığının rengini, kenarlığın değerini değiştirerek değiştirebilirsiniz.`graph.Color` C# kaynak kodundaki özellik. Sadece istediğiniz rengi sağlayın, örneğin`Aspose.Pdf.Color.Red` veya başka herhangi bir geçerli renk gösterimi.

#### S: Aynı PDF belgesinde farklı tablolara farklı köşe stilleri (ör. kare ve yuvarlak) uygulamak mümkün müdür?

C: Evet, aynı PDF belgesinde farklı tablolara farklı köşe stilleri uygulamak mümkündür. Birden çok tablo oluşturabilir ve köşe stillerini gereksinimlerinize göre ayrı ayrı yapılandırabilirsiniz.

#### S: Yuvarlatılmış köşe kenarlığının kalınlığını ayarlayabilir miyim?

 C: Evet, yuvarlatılmış köşe kenarlığının kalınlığını değiştirerek ayarlayabilirsiniz.`BorderInfo` C# kaynak kodundaki nesnenin özellikleri. Örneğin,`bInfo.Width` kenarlığın kalınlığını ayarlama özelliği.