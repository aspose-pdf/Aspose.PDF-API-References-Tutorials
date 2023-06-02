---
title: Hakları Koru
linktitle: Hakları Koru
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinizdeki form haklarını koruyun.
type: docs
weight: 210
url: /tr/net/programming-with-forms/preserve-rights/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinde form haklarını nasıl koruyacağınızı göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kitaplıkları içe aktardığınızdan emin olun ve yolu belgeler dizininize ayarlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi açın

 Bir kullanarak kaynak PDF belgesini açın.`FileStream` okuma ve yazma izni ile:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## 3. Adım: Form Alanlarını Düzenleyin

Belgedeki tüm form alanlarını gözden geçirin ve gerekli değişiklikleri yapın. Bu örnekte, adında "A1" bulunan bir form alanının değerini değiştiriyoruz:

```csharp
foreach(Field formField in pdfDocument.Form)
{
if (formField.FullName.Contains("A1"))
{
TextBoxField textBoxField = formField as TextBoxField;
textBoxField.Value = "Testing";
}
}
```

## 4. Adım: Güncellenen belgeyi kaydedin

Değiştirilen PDF belgesini kaydedin:

```csharp
pdfDocument.Save();
```

##  Adım 5: Kapatın`FileStream`

 kapatmayı unutma`FileStream` işiniz bittiğinde itiraz edin:

```csharp
fs. Close();
```

### Aspose.Words for .NET kullanan Preserve Rights için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Okuma ve Yazma FileAccess ile kaynak PDF formunu okuyun.
// ReadWrite iznine ihtiyacımız var çünkü değişiklikten sonra,
// Güncellenen içerikleri aynı belgeye/dosyaya kaydetmemiz gerekiyor.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Belge örneği örneği
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Tüm alanlardan değerleri al
foreach (Field formField in pdfDocument.Form)
{
	// Alanın tam adı A1 içeriyorsa, işlemi gerçekleştirin
	if (formField.FullName.Contains("A1"))
	{
		// Form alanını TextBox olarak yayınla
		TextBoxField textBoxField = formField as TextBoxField;
		// Alan değerini değiştir
		textBoxField.Value = "Testing";
	}
}
// Güncellenen belgeyi Save FileStream'e kaydedin
pdfDocument.Save();
// Dosya Akışı nesnesini kapatın
fs.Close();
```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki formun haklarını nasıl koruyacağımızı öğrendik. Bu adımları izleyerek, erişim ve yazma izinlerini korurken form alanlarına kolayca erişebilir ve belirli değişiklikler yapabilirsiniz.
