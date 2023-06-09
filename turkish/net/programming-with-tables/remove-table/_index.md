---
title: Tabloyu Kaldır
linktitle: Tabloyu Kaldır
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesindeki tabloyu nasıl kaldıracağınızı öğrenin.
type: docs
weight: 160
url: /tr/net/programming-with-tables/remove-table/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki bir tabloyu kaldırmak için adım adım rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve nasıl uygulayacağınızı göstereceğiz.

## 1. Adım: Mevcut PDF belgesini yükleme
Öncelikle, mevcut PDF belgesini aşağıdaki kodu kullanarak yüklemeniz gerekir:

```csharp
// Belgeler dizinine giden yol
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Mevcut PDF belgesini yükleyin
Document pdfDocument = new Document(dataDir + "Table_input.pdf");
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
// Emici ile ilk sayfayı ziyaret edin
absorb.Visit(pdfDocument.Pages[1]);
```

## Adım 4: Sayfadaki ilk tabloyu alma
Tabloyu kaldırabilmek için sayfanın ilk tablosunu elde edeceğiz:

```csharp
// Sayfadaki ilk tabloyu al
AbsorbedTable table = absorb.TableList[0];
```

## 5. Adım: Tablonun silinmesi
Şimdi emiciyi kullanarak masayı kaldıralım:

```csharp
//masayı kaldır
absorb.Remove(table);
```

## 6. Adım: PDF'yi kaydedin
Son olarak, değiştirilen PDF belgesini kaydediyoruz:

```csharp
// PDF'yi kaydet
pdfDocument.Save(dataDir + "Table_out.pdf");
```

### Aspose.PDF for .NET kullanarak Tabloyu Kaldır için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mevcut PDF belgesini yükle
Document pdfDocument = new Document(dataDir + "Table_input.pdf");

// Tabloları bulmak için TableAbsorber nesnesi oluşturun
TableAbsorber absorber = new TableAbsorber();

// Emici ile ilk sayfayı ziyaret edin
absorber.Visit(pdfDocument.Pages[1]);

// Sayfadaki ilk tabloyu al
AbsorbedTable table = absorber.TableList[0];

// tabloyu kaldır
absorber.Remove(table);

// PDF'yi kaydet
pdfDocument.Save(dataDir + "Table_out.pdf");
```

## Çözüm
Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF belgesindeki tabloyu nasıl kaldıracağınızı öğrendiniz. Bu adım adım kılavuz size belgeyi nasıl yükleyeceğinizi, tabloyu nasıl bulacağınızı ve kaldıracağınızı gösterdi. Artık bu bilgiyi kendi projelerinize uygulayabilirsiniz.