---
title: Doküman Oluşturma Sırasında Yazı Tipini Göm
linktitle: Doküman Oluşturma Sırasında Yazı Tipini Göm
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesi oluştururken bir yazı tipini nasıl gömeceğinizi öğrenin. Farklı cihazlarda doğru görüntülemeyi sağlayın.
type: docs
weight: 140
url: /tr/net/programming-with-document/embedfontwhiledoccreation/
---

Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesi oluştururken bir yazı tipinin nasıl gömüleceğini tartışacağız. Aspose.PDF for .NET, geliştiricilerin PDF belgelerini program aracılığıyla oluşturmasına, düzenlemesine ve işlemesine olanak sağlayan güçlü bir kitaplıktır. Bu kitaplık, metin, resim, tablo ve çok daha fazlasını ekleme dahil olmak üzere PDF belgeleriyle çalışmak için çok çeşitli özellikler sağlar. Bir PDF belgesi oluştururken yazı tiplerini gömmek, gerekli yazı tiplerinin bu aygıtlarda yüklü olup olmadığına bakılmaksızın, PDF belgesinin farklı aygıtlarda doğru şekilde görüntülendiğinden emin olmak isteyen geliştiriciler için ortak bir gerekliliktir.

## 1. Adım: Yeni bir C# Konsol Uygulaması oluşturun
Başlamak için Visual Studio'da yeni bir C# Konsol Uygulaması oluşturun. Adını ne istersen koyabilirsin. Proje oluşturulduktan sonra Aspose.PDF for .NET kitaplığına bir referans eklemeniz gerekir.

## Adım 2: Aspose.PDF Ad Alanını İçeri Aktarın
Aspose.PDF ad alanını içe aktarmak için C# dosyanızın en üstüne aşağıdaki kod satırını ekleyin:

```csharp
using Aspose.Pdf;
```

## 3. Adım: Bir Pdf Nesnesi Oluşturun
Boş oluşturucusunu çağırarak bir Pdf nesnesinin örneğini oluşturun:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Adım 4: Pdf Nesnesinde Bir Bölüm Oluşturun
Pdf nesnesinde bir bölüm oluşturun:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Adım 5: Bölüme Metin Ekleyin
bölüme metin ekleyin:

```csharp
Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");
Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment(" This is a sample text using Custom font.");
```

## 6. Adım: Yazı Tipini Ayarlayın ve Gömün
Yazı tipini ayarlayın ve gömün:

```csharp
Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
ts.Font = FontRepository.FindFont("Arial");
ts.Font.IsEmbedded = true;
segment.TextState = ts;
fragment.Segments.Add(segment);
page.Paragraphs.Add(fragment);
```

## 7. Adım: PDF Belgesini Kaydedin
PDF belgesini oluştururken yazı tipini gömdükten sonra belgeyi kaydetmeniz gerekir:

```csharp
dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
// PDF Belgesini Kaydet
doc.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Belge Oluşturma Sırasında Yazı Tipini Gömmek için Örnek Kaynak Kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Boş oluşturucusunu çağırarak Pdf nesnesinin örneğini oluşturun
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Pdf nesnesinde bir bölüm oluşturun
Aspose.Pdf.Page page = doc.Pages.Add();

Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");

Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment(" This is a sample text using Custom font.");
Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
ts.Font = FontRepository.FindFont("Arial");
ts.Font.IsEmbedded = true;
segment.TextState = ts;
fragment.Segments.Add(segment);
page.Paragraphs.Add(fragment);

dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
// PDF Belgesini Kaydet
doc.Save(dataDir);
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesi oluştururken bir yazı tipinin nasıl gömüleceğini ele aldık. Aspose.PDF for .NET, yazı tipi ekleme ve gömme de dahil olmak üzere PDF belgeleriyle çalışmak için basit ve kullanımı kolay bir API sağlar. Bir PDF belgesi oluştururken yazı tiplerini gömmek, bu cihazlarda gerekli yazı tiplerinin kurulu olup olmadığına bakılmaksızın, belgenin farklı cihazlarda doğru şekilde görüntülenmesini sağlamak için önemli bir adımdır.

