---
title: Kenarlığı Ayarla
linktitle: Kenarlığı Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF tablosunda kenarlık belirlemeyi öğrenin.
type: docs
weight: 200
url: /tr/net/programming-with-tables/set-border/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinin tablosunda kenarlık belirlemeniz için size adım adım rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve nasıl uygulayacağınızı göstereceğiz.

## 1. Adım: Document nesnesinin örneğini oluşturma
İlk olarak, bir Document nesnesi başlatacağız:

```csharp
Document doc = new Document();
```

## 2. Adım: PDF belgesine sayfa ekleme
Ardından, PDF belgesine bir sayfa ekleyeceğiz:

```csharp
Page page = doc.Pages.Add();
```

## 3. Adım: BorderInfo nesnesini oluşturma
Şimdi tablonun kenarlığını tanımlamak için bir BorderInfo nesnesi oluşturacağız:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## 4. Adım: Üst ve alt kenarlıkları belirleme
Üst ve alt kenarlıkların çift olacağını belirteceğiz:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## 5. Adım: Tablo nesnesini başlatma
Şimdi bir Table nesnesini başlatalım:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Adım 6: Sütun genişliklerini belirleme
Tablonun sütunlarının genişliklerini belirteceğiz:

```csharp
table. ColumnWidths = "100";
```

## Adım 7: Satır Nesnesini Oluşturma
Bir Row nesnesi oluşturacağız:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Adım 8: Satıra hücre ekleme
Ardından, satıra bir hücre ekleyeceğiz:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## 9. Adım: Hücre kenarlığının ayarlanması
Hücrenin kenarlığını (double border) tanımlayacağız:

```csharp
cell. Border = border;
```

## Adım 10: Tabloyu sayfaya ekleme
Şimdi tabloyu belge sayfasına ekleyelim:

```csharp
page.Paragraphs.Add(table);
```

## 11. Adım: PDF belgesini kaydedin
Son olarak, PDF belgesini kaydedeceğiz:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanarak Set Border için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge nesnesini örneklendir
Document doc = new Document();
// PDF belgesine sayfa ekle
Page page = doc.Pages.Add();
// BorderInfo nesnesi oluştur
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
// Üst kenarlığın çift olacağını belirtin
border.Top.IsDoubled = true;
// Alt kenarlığın çift olacağını belirtin
border.Bottom.IsDoubled = true;
// Örnek Tablo nesnesi
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Sütun genişlik bilgilerini belirtin
table.ColumnWidths = "100";
// Satır nesnesi oluştur
Aspose.Pdf.Row row = table.Rows.Add();
// Satırın hücre koleksiyonuna Tablo hücresi ekleme
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Hücre nesnesi için kenarlığı ayarla (çift kenarlık)
cell.Border = border;
// Sayfanın paragraf koleksiyonuna tablo ekleme
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// PDF belgesini kaydedin
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Çözüm
Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF belgesinin tablosunda kenarlık belirlemeyi öğrendiniz. Bu adım adım kılavuz size belge oluşturmayı, sayfa eklemeyi, tablo kenarlığını yapılandırmayı ve PDF belgesini kaydetmeyi gösterdi. Artık bu bilgiyi kendi projelerinize uygulayabilirsiniz.