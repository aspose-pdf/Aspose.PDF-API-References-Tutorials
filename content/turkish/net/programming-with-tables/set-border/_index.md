---
title: PDF'deki Kenarlığı Tabloya Ayarla
linktitle: PDF'deki Kenarlığı Tabloya Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF'de tabloya kenarlık eklemeyi öğrenin.
type: docs
weight: 200
url: /tr/net/programming-with-tables/set-border/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesinin tablosunda bir kenarlık ayarlamanız için size adım adım rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve nasıl uygulayacağınızı göstereceğiz.

## Adım 1: Belge nesnesini örnekleme
İlk olarak bir Document nesnesi oluşturacağız:

```csharp
Document doc = new Document();
```

## Adım 2: PDF belgesine bir sayfa ekleme
Şimdi PDF belgesine bir sayfa ekleyeceğiz:

```csharp
Page page = doc.Pages.Add();
```

## Adım 3: BorderInfo nesnesini oluşturma
Şimdi tablonun sınırını tanımlamak için bir BorderInfo nesnesi oluşturacağız:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## Adım 4: Üst ve alt sınırların belirlenmesi
Üst ve alt sınırların çift olacağını belirtelim:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Adım 5: Tablo nesnesini örneklendirme
Şimdi bir Table nesnesi oluşturalım:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Adım 6: Sütun genişliklerini belirtme
Tablonun sütun genişliklerini belirleyeceğiz:

```csharp
table. ColumnWidths = "100";
```

## Adım 7: Satır Nesnesini Oluşturma
Bir Row nesnesi oluşturacağız:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Adım 8: Satıra bir hücre ekleme
Daha sonra satıra bir hücre ekleyeceğiz:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Adım 9: Hücre kenarlığını ayarlama
Hücrenin sınırını (çift kenarlık) tanımlayacağız:

```csharp
cell. Border = border;
```

## Adım 10: Tabloyu sayfaya ekleme
Şimdi tabloyu belge sayfasına ekleyelim:

```csharp
page.Paragraphs.Add(table);
```

## Adım 11: PDF belgesini kaydedin
Son olarak PDF dokümanını kaydedeceğiz:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### .NET için Aspose.PDF kullanarak Set Border için örnek kaynak kodu

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge nesnesini örnekle
Document doc = new Document();
// PDF belgesine sayfa ekle
Page page = doc.Pages.Add();
// BorderInfo nesnesini oluştur
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
//Üst sınırın çift olacağını belirtin
border.Top.IsDoubled = true;
// Alt sınırın çift olacağını belirtin
border.Bottom.IsDoubled = true;
// Tablo nesnesini örnekle
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Sütun genişliği bilgilerini belirtin
table.ColumnWidths = "100";
// Satır nesnesi oluştur
Aspose.Pdf.Row row = table.Rows.Add();
// Satır hücre koleksiyonuna bir Tablo hücresi ekleyin
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Hücre nesnesi için kenarlığı ayarlayın (çift kenarlık)
cell.Border = border;
// Sayfanın paragraf koleksiyonuna tablo ekle
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// PDF belgesini kaydedin
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Çözüm
Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF belgesinin tablosuna kenarlık koymayı öğrendiniz. Bu adım adım kılavuz size bir belge oluşturmayı, bir sayfa eklemeyi, tablo kenarlığını yapılandırmayı ve PDF belgesini kaydetmeyi gösterdi. Artık bu bilgiyi kendi projelerinize uygulayabilirsiniz.

### SSS

#### S: Tablonun üst ve alt kenarları için farklı kenarlık stilleri (örneğin kesikli veya noktalı) belirleyebilir miyim?

 A: Evet, tablonun üst ve alt sınırları için farklı sınır stilleri belirleyebilirsiniz.`border.Top.Style` Ve`border.Bottom.Style`Sağlanan C# kaynak kodundaki özellikler. Aspose.PDF for .NET, Katı, Kesikli, Noktalı, Çift ve daha fazlası dahil olmak üzere çeşitli kenarlık stilleri arasından seçim yapmanıza olanak tanır.

#### S: Tablonun kenarlık rengini nasıl ayarlayabilirim?

 A: Tablonun kenarlığının rengini,`border.Color` C# kaynak kodundaki özellik. Sadece istediğiniz rengi sağlayın, örneğin`Aspose.Pdf.Color.Red` veya herhangi bir geçerli renk gösterimini kullanarak, kenarlık rengini özelleştirebilirsiniz.

#### S: Tablo içindeki her bir hücreye farklı ayarlarla (örneğin farklı renkler veya kenarlık stilleri) kenarlık uygulamak mümkün müdür?

 A: Evet, tablo içindeki ayrı hücrelere farklı ayarlarla kenarlıklar uygulayabilirsiniz.`cell.Border` her hücre için ayrı ayrı özellik. Bu, gereksinimlerinize göre hücreye özgü kenarlık stilleri ve renklerine sahip olmanızı sağlar.

#### S: Masanın belirli taraflarındaki (örneğin sol ve sağ kenarlıklar) kenarları kaldırabilir miyim?

 A: Evet, tablonun belirli taraflarındaki kenarlıkları,`border.Left`, `border.Right`, `border.Top` , Ve`border.Bottom`C# kaynak kodundaki özellikler. Bu özellikleri şu şekilde ayarlayın:`null` Tablonun ilgili kenarlarındaki sınırı kaldıracaktır.

#### S: Tablonun kenarlık kalınlığını nasıl ayarlayabilirim?

 A: Tablonun kenarlığının kalınlığını,`border.Width` C# kaynak kodundaki özellik. İstenilen kalınlığı elde etmek için istenilen kenarlık genişliğini (nokta cinsinden) ayarlamanız yeterlidir.