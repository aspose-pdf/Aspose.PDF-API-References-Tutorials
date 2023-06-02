---
title: Birden Çok Tabloyu Kaldır
linktitle: Birden Çok Tabloyu Kaldır
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesindeki birden çok tabloyu nasıl kaldıracağınızı öğrenin.
type: docs
weight: 150
url: /tr/net/programming-with-tables/remove-multiple-tables/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki birden fazla tabloyu kaldırmanız için adım adım rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve nasıl uygulayacağınızı göstereceğiz.

## 1. Adım: Mevcut PDF belgesini yükleme
Öncelikle, mevcut PDF belgesini aşağıdaki kodu kullanarak yüklemeniz gerekir:

```csharp
// Belgeler dizinine giden yol
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Mevcut PDF belgesini yükleyin
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");
```

## Adım 2: Tabloları bulmak için TableAbsorber nesnesini oluşturma
Ardından, PDF belgesindeki tabloları bulmak için bir TableAbsorber nesnesi oluşturacağız:

```csharp
// Tabloları bulmak için bir TableAbsorber nesnesi oluşturun
TableAbsorber absorber = new TableAbsorber();
```

## 3. Adım: Emici ile ikinci sayfayı ziyaret edin
Şimdi emiciyi kullanarak PDF belgesinin ikinci sayfasını ziyaret edeceğiz:

```csharp
// Emici ile ikinci sayfayı ziyaret edin
absorb.Visit(pdfDocument.Pages[1]);
```

## 4. Adım: Tablo koleksiyonunun bir kopyasını alma
Tabloları bırakabilmek için, tablo koleksiyonunun bir kopyasını almamız gerekir:

```csharp
// Tablo koleksiyonunun bir kopyasını alın
AbsorbedTable[] tables = new AbsorbedTable[absorb.TableList.Count];
absorb.TableList.CopyTo(tables, 0);
```

## 5. Adım: Koleksiyonun kopyasına göz atın ve tabloları kaldırın
Şimdi tablo koleksiyonunun kopyalarını tekrarlayalım ve bunları birer birer kaldıralım:

```csharp
// Koleksiyonun kopyasına göz atın ve tabloları kaldırın
foreach(AbsorbedTable table in tables)
     absorb.Remove(table);
```

## 6. Adım: Belgeyi kaydetme
Son olarak, değiştirilen PDF belgesini kaydediyoruz:

```csharp
// belgeyi kaydet
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

### Aspose.Words for .NET kullanarak Birden Çok Tabloyu Kaldır için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mevcut PDF belgesini yükle
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");

// Tabloları bulmak için TableAbsorber nesnesi oluşturun
TableAbsorber absorber = new TableAbsorber();

// Emici ile ikinci sayfayı ziyaret edin
absorber.Visit(pdfDocument.Pages[1]);

// Tablo koleksiyonunun kopyasını alın
AbsorbedTable[] tables = new AbsorbedTable[absorber.TableList.Count];
absorber.TableList.CopyTo(tables, 0);

// Koleksiyonun kopyasında dolaşın ve tabloları kaldırın
foreach (AbsorbedTable table in tables)
	absorber.Remove(table);

// Belgeyi kaydet
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

## Çözüm
Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF belgesindeki birden çok tabloyu nasıl kaldıracağınızı öğrendiniz. Bu adım adım kılavuz size belgeyi nasıl yükleyeceğinizi, tabloları nasıl bulacağınızı ve kaldıracağınızı gösterdi. Artık bu bilgiyi kendi projelerinize uygulayabilirsiniz.