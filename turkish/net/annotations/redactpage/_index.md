---
title: Sayfayı Reddet
linktitle: Sayfayı Reddet
second_title: Aspose.PDF for .NET API Referansı
description: Bu makale, adım adım talimatlar ve örnek kaynak kodu dahil olmak üzere Aspose.PDF for .NET kullanarak bir PDF sayfasının nasıl yeniden düzenleneceğini açıklamaktadır.
type: docs
weight: 120
url: /tr/net/annotations/redactpage/
---
Aspose.PDF for .NET kullanarak bir PDF belgesindeki hassas bilgileri yeniden düzenlemek istiyorsanız, şanslısınız! İşte başlamanız için adım adım bir kılavuz:

## Adım 1: Kodda, PDF belgenizin bulunduğu dizinin yolunu ayarlayın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: PDF belgesini açın:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 3. Adım: Belirli bir sayfa bölgesi için bir RedactionAnnotation örneği oluşturun:

```csharp
RedactionAnnotation annot = new RedactionAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(200, 500, 300, 600));
```

## Adım 4: Redaksiyon notunun dolgu rengini, kenarlık rengini ve metin rengini ayarlayın:

```csharp
annot.FillColor = Aspose.Pdf.Color.Green;
annot.BorderColor = Aspose.Pdf.Color.Yellow;
annot.Color = Aspose.Pdf.Color.Blue;
```

## Adım 5: Redaksiyon açıklamasına yazdırılacak metni ve hizalamasını ayarlayın:

```csharp
annot.OverlayText = "REDACTED";
annot.TextAlignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Adım 6: Bindirme metnini redaksiyon notunun üzerinde tekrarlayın:

```csharp
annot.Repeat = true;
```

## Adım 7: Ek açıklamayı ilk sayfanın ek açıklamalar koleksiyonuna ekleyin:

```csharp
doc.Pages[1].Annotations.Add(annot);
```

## 8. Adım: Ek açıklamayı düzleştirin ve sayfa içeriğini yeniden düzenleyin, yani, düzeltilen açıklamanın altındaki metin ve resimleri kaldırın:

```csharp
annot.Redact();
```

## 9. Adım: Çıktı PDF dosyasının yolunu ve adını ayarlayın:

```csharp
dataDir = dataDir + "RedactPage_out.pdf";
```

## 10. Adım: PDF belgesini düzeltilmiş sayfayla kaydedin:

```csharp
doc.Save(dataDir);
```

Bu kadar! Aspose.PDF for .NET'i kullanarak PDF belgenizin bir sayfasını başarıyla yeniden düzenlediniz.

### Aspose.PDF for .NET kullanan Redact Page için örnek kaynak kodu:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document doc = new Document(dataDir + "input.pdf");

// Belirli sayfa bölgesi için RedactionAnnotation örneği oluşturun
RedactionAnnotation annot = new RedactionAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(200, 500, 300, 600));
annot.FillColor = Aspose.Pdf.Color.Green;
annot.BorderColor = Aspose.Pdf.Color.Yellow;
annot.Color = Aspose.Pdf.Color.Blue;
// Düzeltme ek açıklamasına yazdırılacak metin
annot.OverlayText = "REDACTED";
annot.TextAlignment = Aspose.Pdf.HorizontalAlignment.Center;
// Metni redakt üzerine tekrarla Bindirme Ek Açıklama
annot.Repeat = true;
// İlk sayfanın ek açıklamalar koleksiyonuna ek açıklama ekleyin
doc.Pages[1].Annotations.Add(annot);
//Ek açıklamayı düzleştirir ve sayfa içeriğini düzeltir (yani metin ve resmi kaldırır)
// Düzenlenmiş ek açıklama altında)
annot.Redact();
dataDir = dataDir + "RedactPage_out.pdf";
doc.Save(dataDir);
```