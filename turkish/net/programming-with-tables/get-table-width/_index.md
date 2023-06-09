---
title: Tablo Genişliğini Alın
linktitle: Tablo Genişliğini Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesinde tablo genişliğini nasıl alacağınızı öğrenin.
type: docs
weight: 90
url: /tr/net/programming-with-tables/get-table-width/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki tablonun genişliğini nasıl elde edeceğimizi öğreneceğiz. C#'ta kaynak kodunu adım adım anlatacağız. Bu eğitimin sonunda, bir PDF belgesinde bir tablonun genişliğini nasıl elde edeceğinizi öğreneceksiniz. Hadi başlayalım!

## 1. Adım: Ortamı ayarlama
Öncelikle Aspose.PDF for .NET ile C# geliştirme ortamınızı kurduğunuzdan emin olun. Referansı kitaplığa ekleyin ve gerekli ad alanlarını içe aktarın.

## 2. Adım: Yeni Belge ve Sayfa Oluşturma
Yeni bir PDF belgesi oluşturuyoruz ve bu belgeye bir sayfa ekliyoruz.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 3. Adım: Yeni bir tablo başlatma
Yeni bir tablo başlatıyoruz ve sütunu "AutoFitToContent" olarak ayarlıyoruz.

```csharp
Table table = new Table
{
ColumnAdjustment = ColumnAdjustment.AutoFitToContent
};
```

## 4. Adım: Tabloya satır ve hücre ekleyin
Tabloya bir satır ekliyoruz ve o satıra hücreler ekliyoruz.

```csharp
Row row = table.Rows.Add();
Cell cell = row.Cells.Add("Text of cell 1");
cell = row.Cells.Add("Text from cell 2");
```

## Adım 5: Tablo genişliğini alın
Tablonun genişliğini elde etmek için "GetWidth()" yöntemini kullanıyoruz.

```csharp
Console.WriteLine(table.GetWidth());
```

### Aspose.PDF for .NET kullanarak Tablo Genişliği almak için örnek kaynak kodu

```csharp
// Yeni bir belge oluştur
Document doc = new Document();
// Belgeye sayfa ekle
Page page = doc.Pages.Add();
// Yeni tabloyu başlat
Table table = new Table
{
	ColumnAdjustment = ColumnAdjustment.AutoFitToContent
};
// Tabloya satır ekle
Row row = table.Rows.Add();
// Tabloya hücre ekle
Cell cell = row.Cells.Add("Cell 1 text");
cell = row.Cells.Add("Cell 2 text");
// Tablo genişliğini al
Console.WriteLine(table.GetWidth());

System.Console.WriteLine("Extracted table width succesfully!");
```

## Çözüm
Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesindeki tablonun genişliğini nasıl elde edeceğimizi öğrendik. Kendi C# projelerinizde tablo genişliklerini elde etmek için bu adım adım kılavuzu kullanabilirsiniz.