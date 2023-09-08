---
title: PDF'deki Kenarlığı Tabloya Ayarla
linktitle: PDF'deki Kenarlığı Tabloya Ayarla
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF'de tabloya nasıl kenarlık ayarlayacağınızı öğrenin.
type: docs
weight: 200
url: /tr/net/programming-with-tables/set-border/
---
Bu eğitimde, Aspose.PDF for .NET'i kullanarak bir PDF belgesinin tablosunda kenarlık ayarlama konusunda size adım adım rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve size nasıl uygulayacağınızı göstereceğiz.

## Adım 1: Belge nesnesini örneklendirme
İlk olarak bir Document nesnesini başlatacağız:

```csharp
Document doc = new Document();
```

## Adım 2: PDF belgesine sayfa ekleme
Daha sonra PDF belgesine bir sayfa ekleyeceğiz:

```csharp
Page page = doc.Pages.Add();
```

## Adım 3: BorderInfo nesnesini oluşturma
Şimdi tablonun kenarlığını tanımlamak için bir BorderInfo nesnesi oluşturacağız:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## 4. Adım: Üst ve alt kenarlıkları belirtme
Üst ve alt kenarlıkların çift olacağını belirteceğiz:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Adım 5: Tablo nesnesini örneklendirme
Şimdi bir Table nesnesini başlatalım:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Adım 6: Sütun genişliklerini belirtme
Tablonun sütunlarının genişliklerini belirleyeceğiz:

```csharp
table. ColumnWidths = "100";
```

## Adım 7: Satır Nesnesini Oluşturma
Bir Row nesnesi oluşturacağız:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Adım 8: Satıra hücre ekleme
Daha sonra satıra bir hücre ekleyeceğiz:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Adım 9: Hücre kenarlığını ayarlama
Hücrenin kenarlığını (çift kenarlık) tanımlayacağız:

```csharp
cell. Border = border;
```

## Adım 10: Tabloyu sayfaya ekleme
Şimdi tabloyu belge sayfasına ekleyelim:

```csharp
page.Paragraphs.Add(table);
```

## Adım 11: PDF belgesini kaydedin
Son olarak PDF belgesini kaydedeceğiz:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanarak Set Border için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge nesnesini somutlaştır
Document doc = new Document();
// PDF belgesine sayfa ekle
Page page = doc.Pages.Add();
// BorderInfo nesnesi oluştur
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
//Üst sınırın çift olacağını belirtin
border.Top.IsDoubled = true;
// Alt kenarlığın çift olacağını belirtin
border.Bottom.IsDoubled = true;
// Tablo nesnesini somutlaştır
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Sütun genişliği bilgisini belirtin
table.ColumnWidths = "100";
// Satır nesnesi oluştur
Aspose.Pdf.Row row = table.Rows.Add();
// Satırın hücre koleksiyonuna bir Tablo hücresi ekleme
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Hücre nesnesinin kenarlığını ayarlayın (çift kenarlık)
cell.Border = border;
// Sayfanın paragraf koleksiyonuna tablo ekleyin
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// PDF belgesini kaydedin
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Çözüm
Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF belgesinin tablosunda nasıl kenarlık ayarlayacağınızı öğrendiniz. Bu adım adım kılavuz size nasıl belge oluşturacağınızı, sayfa ekleyeceğinizi, tablo kenarlığını nasıl yapılandıracağınızı ve PDF belgesini nasıl kaydedeceğinizi gösterdi. Artık bu bilgiyi kendi projelerinize uygulayabilirsiniz.

### SSS'ler

#### S: Tablonun üst ve alt kenarları için farklı kenarlık stilleri (ör. kesikli veya noktalı) ayarlayabilir miyim?

 C: Evet, tablonun üst ve alt kenarlıkları için farklı kenar stilleri ayarlayabilirsiniz.`border.Top.Style` Ve`border.Bottom.Style`Sağlanan C# kaynak kodundaki özellikler. Aspose.PDF for .NET, Düz, Kesikli, Noktalı, Çift ve daha fazlası dahil olmak üzere çeşitli kenarlık stilleri arasından seçim yapmanızı sağlar.

#### S: Tablonun kenarlığının rengini nasıl ayarlayabilirim?

 C: Tablonun kenarlığının rengini değiştirerek ayarlayabilirsiniz.`border.Color` C# kaynak kodundaki özellik. Basitçe istediğiniz rengi sağlayın, örneğin`Aspose.Pdf.Color.Red` veya kenarlık rengini özelleştirmek için geçerli herhangi bir renk gösterimi.

#### S: Tablo içindeki tek tek hücrelere farklı ayarlarla (örneğin, farklı renkler veya kenarlık stilleri) kenarlıklar uygulamak mümkün müdür?

 C: Evet, tablodaki ayrı ayrı hücrelere farklı ayarlarla kenarlıklar uygulayabilirsiniz.`cell.Border` Her hücre için ayrı ayrı özellik. Bu, gereksinimlerinize göre hücreye özgü kenarlık stillerine ve renklerine sahip olmanızı sağlar.

#### S: Tablonun belirli taraflarındaki kenarlığı kaldırabilir miyim (örn. sol ve sağ kenarlıklar)?

 C: Evet, tablonun belirli taraflarındaki kenarlığı, kenarlığı değiştirerek kaldırabilirsiniz.`border.Left`, `border.Right`, `border.Top` , Ve`border.Bottom`C# kaynak kodundaki özellikler. Bu özelliklerin ayarlanması`null` tablonun karşılık gelen kenarlarındaki kenarlığı kaldıracaktır.

#### S: Tablonun kenarlığının kalınlığını nasıl ayarlayabilirim?

 C: Tablonun kenarlığının kalınlığını değiştirerek ayarlayabilirsiniz.`border.Width` C# kaynak kodundaki özellik. İstenilen kalınlığı elde etmek için istenilen kenar genişliğini (nokta olarak) ayarlamanız yeterlidir.