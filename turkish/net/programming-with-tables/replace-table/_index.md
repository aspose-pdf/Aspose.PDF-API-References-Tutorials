---
title: Tabloyu Değiştir
linktitle: Tabloyu Değiştir
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesindeki tabloyu nasıl değiştireceğinizi öğrenin.
type: docs
weight: 180
url: /tr/net/programming-with-tables/replace-table/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki tabloyu değiştirmek için adım adım size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve nasıl uygulayacağınızı göstereceğiz.

## 1. Adım: Mevcut PDF belgesini yükleme
Öncelikle, mevcut PDF belgesini aşağıdaki kodu kullanarak yüklemeniz gerekir:

```csharp
// Belgeler dizinine giden yol
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Mevcut PDF belgesini yükleyin
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");
```

## Adım 2: Tabloları bulmak için TableAbsorber nesnesini oluşturma
Ardından, PDF belgesindeki tabloları bulmak için bir TableAbsorber nesnesi oluşturacağız:

```csharp
// Tabloları bulmak için bir TableAbsorber nesnesi oluşturun
TableAbsorber absorber = new TableAbsorber();
```

## 3. Adım: Emici ile ilk sayfayı ziyaret edin
Şimdi emiciyi kullanarak PDF belgesinin ilk sayfasını ziyaret edeceğiz:

```csharp
//Emici ile ilk sayfayı ziyaret edin
absorb.Visit(pdfDocument.Pages[1]);
```

## Adım 4: Sayfadaki ilk tabloyu alma
Tabloyu değiştirebilmek için sayfanın ilk tablosunu elde edeceğiz:

```csharp
// Sayfadaki ilk tabloyu al
AbsorbedTable table = absorb.TableList[0];
```

## Adım 5: Yeni bir tablo oluşturma
Şimdi istenen sütunlar ve hücrelerle yeni bir tablo oluşturacağız:

```csharp
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row. Cells. Add("Col 1");
row. Cells. Add("Col 2");
row. Cells. Add("Col 3");
```

## Adım 6: Mevcut tabloyu yeni tabloyla değiştirme
Şimdi mevcut tabloyu belgenin ilk sayfasındaki yeni tabloyla değiştireceğiz:

```csharp
// Tabloyu yeni tabloyla değiştirin
absorb.Replace(pdfDocument.Pages[1], table, newTable);
```

## 7. Adım: Belgeyi kaydetme
Son olarak, değiştirilen PDF belgesini kaydediyoruz:

```csharp
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

### Aspose.Words for .NET kullanan Tablo Değiştir için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mevcut PDF belgesini yükle
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");

// Tabloları bulmak için TableAbsorber nesnesi oluşturun
TableAbsorber absorber = new TableAbsorber();

// Emici ile ilk sayfayı ziyaret edin
absorber.Visit(pdfDocument.Pages[1]);

// Sayfadaki ilk tabloyu al
AbsorbedTable table = absorber.TableList[0];

// Yeni tablo oluştur
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row.Cells.Add("Col 1");
row.Cells.Add("Col 2");
row.Cells.Add("Col 3");

// Tabloyu yenisiyle değiştirin
absorber.Replace(pdfDocument.Pages[1], table, newTable);

// Belgeyi kaydet
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

## Çözüm
Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF belgesindeki tabloyu nasıl değiştireceğinizi öğrendiniz. Bu adım adım kılavuz size belgeyi nasıl yükleyeceğinizi, mevcut tabloyu nasıl bulacağınızı, yeni bir tablo oluşturacağınızı ve değiştireceğinizi gösterdi. Artık bu bilgiyi kendi projelerinize uygulayabilirsiniz.