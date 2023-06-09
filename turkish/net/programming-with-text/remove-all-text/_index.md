---
title: Tüm Metni Kaldır
linktitle: Tüm Metni Kaldır
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesindeki tüm metni nasıl kaldıracağınızı öğrenin.
type: docs
weight: 280
url: /tr/net/programming-with-text/remove-all-text/
---

Bu öğreticide, Aspose.PDF kitaplığı .NET kullanılarak bir PDF belgesindeki tüm metnin nasıl kaldırılacağını açıklayacağız. PDF açma, her sayfadan metin seçme ve silme ve sağlanan C# kaynak kodunu kullanarak değiştirilen PDF'yi kaydetme sürecini adım adım inceleyeceğiz.

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

## 3. Adım: Her Sayfadan Metni Kaldırın

 PDF belgesinin tüm sayfaları arasında dolaşıyoruz ve bir`OperatorSelector` her sayfadaki tüm metni seçmek için Ardından seçilen metni siliyoruz.

```csharp
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
     Page page = pdfDocument.Pages[i];
     OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
     page.Contents.Accept(operatorSelector);
     page.Contents.Delete(operatorSelector.Selected);
}
```

## 4. Adım: Değiştirilmiş PDF'yi kaydedin

Son olarak, değiştirilen PDF belgesini belirtilen çıktı dosyasına kaydediyoruz.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Aspose.PDF for .NET kullanarak Remove All Text için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// PDF Belgesinin tüm sayfaları arasında dolaşın
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
	Page page = pdfDocument.Pages[i];
	OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
	// Sayfadaki tüm metni seç
	page.Contents.Accept(operatorSelector);
	// Tüm metni sil
	page.Contents.Delete(operatorSelector.Selected);
}
// belgeyi kaydet
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Çözüm

Bu öğreticide, Aspose.PDF kitaplığını .NET kullanarak bir PDF belgesindeki tüm metni nasıl kaldıracağınızı öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan C# kodunu yürüterek bir PDF açabilir, her sayfadan metin seçip silebilir ve değiştirilen PDF'yi kaydedebilirsiniz.