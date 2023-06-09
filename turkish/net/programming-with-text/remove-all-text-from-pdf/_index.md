---
title: PDF'den Tüm Metni Kaldır
linktitle: PDF'den Tüm Metni Kaldır
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesindeki tüm metni nasıl kaldıracağınızı öğrenin.
type: docs
weight: 290
url: /tr/net/programming-with-text/remove-all-text-from-pdf/
---

 Bu öğreticide, Aspose.PDF kitaplığı .NET kullanılarak bir PDF belgesindeki tüm metnin nasıl kaldırılacağını açıklayacağız. Bir PDF'yi açma sürecini adım adım inceleyeceğiz.`TextFragmentAbsorber` tüm metni kaldırmak ve değiştirilen PDF'yi sağlanan C# kaynak kodunu kullanarak kaydetmek için.

## Gereksinimler

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kitaplığı yüklendi.
- Temel bir C# programlama anlayışı.

## 1. Adım: Belge Dizinini kurun

 Öncelikle, PDF dosyalarınızın bulunduğu dizinin yolunu belirlemeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` PDF dosyalarınızın yolu ile değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: PDF Belgesini Açın

 Ardından, PDF belgesini kullanarak açıyoruz.`Document` Aspose.PDF kitaplığından sınıf.

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## 3. Adım: Tüm Metni Kaldır

 bir başlatıyoruz`TextFragmentAbsorber` nesneyi seçin ve PDF belgesinden emilen tüm metni kaldırmak için kullanın.

```csharp
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb. RemoveAllText(pdfDocument);
```

## 4. Adım: Değiştirilmiş PDF'yi kaydedin

Son olarak, değiştirilen PDF belgesini belirtilen çıktı dosyasına kaydediyoruz.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Aspose.PDF for .NET kullanarak PDF'den Tüm Metni Kaldır için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// TextFragmentAbsorber'ı Başlat
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
// Emilen tüm metni kaldır
absorber.RemoveAllText(pdfDocument);
// belgeyi kaydet
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Çözüm

Bu öğreticide, Aspose.PDF kitaplığını .NET kullanarak bir PDF belgesindeki tüm metni nasıl kaldıracağınızı öğrendiniz. Adım adım kılavuzu izleyerek ve verilen C# kodunu çalıştırarak bir PDF açabilir, bir PDF dosyası kullanarak tüm metni kaldırabilirsiniz.`TextFragmentAbsorber`, ve değiştirilen PDF'yi kaydedin.