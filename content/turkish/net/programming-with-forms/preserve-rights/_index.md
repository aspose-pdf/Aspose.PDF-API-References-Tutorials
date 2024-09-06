---
title: Hakları Koru
linktitle: Hakları Koru
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinizdeki biçim haklarını koruyun.
type: docs
weight: 210
url: /tr/net/programming-with-forms/preserve-rights/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesinde form haklarının nasıl korunacağını göstereceğiz. Bu süreçte size rehberlik etmek için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kütüphaneleri içe aktardığınızdan ve belgelerinizin dizinine giden yolu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Belgeyi açın

 Kaynak PDF belgesini bir`FileStream` okuma ve yazma izniyle:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Adım 3: Form Alanlarını Düzenle

Belgedeki tüm form alanlarını inceleyin ve gerekli değişiklikleri yapın. Bu örnekte, adında "A1" bulunan bir form alanının değerini değiştiriyoruz:

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

## Adım 4: Güncellenen belgeyi kaydedin

Değiştirilen PDF belgesini kaydedin:

```csharp
pdfDocument.Save();
```

##  Adım 5: Kapatın`FileStream`

 Kapatmayı unutmayın`FileStream` İşiniz bittiğinde nesne:

```csharp
fs. Close();
```

### .NET için Aspose.PDF kullanarak Hakları Koruma için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Kaynak PDF formunu Okuma ve Yazma FileAccess ile okuyun.
// Değişiklikten sonra ReadWrite iznine ihtiyacımız var çünkü
// Güncellenen içerikleri aynı belge/dosyaya kaydetmemiz gerekiyor.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Belge örneğini örneklendir
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Tüm alanlardan değerleri al
foreach (Field formField in pdfDocument.Form)
{
	// Alanın tam adı A1 içeriyorsa, işlemi gerçekleştirin
	if (formField.FullName.Contains("A1"))
	{
		// Form alanını TextBox olarak dönüştür
		TextBoxField textBoxField = formField as TextBoxField;
		// Alan değerini değiştir
		textBoxField.Value = "Testing";
	}
}
// Güncellenen belgeyi FileStream'e kaydedin
pdfDocument.Save();
// Dosya Akışı nesnesini kapatın
fs.Close();
```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesindeki formun haklarının nasıl korunacağını öğrendik. Bu adımları izleyerek, erişim ve yazma izinlerini korurken form alanlarına kolayca erişebilir ve belirli değişiklikler yapabilirsiniz.


### SSS

#### S: PDF belgesindeki diğer alanları etkilemeden belirli form alanlarının haklarını koruyabilir miyim?

 A: Evet, kullanarak`FullName` Form alanlarının özelliği, diğerlerini etkilemeden belirli form alanlarını korumayı hedefleyebilirsiniz.

#### S: Parola korumalı bir PDF belgesinde bir formun haklarını koruyabilir miyim?

C: Evet, Aspose.PDF for .NET, dosyaya erişmek ve değişiklik yapmak için doğru parolayı sağladığınız sürece, parola korumalı PDF belgelerinde bile bir formun haklarını korumanıza olanak tanır.

#### S: Uygun erişim haklarına sahip olmadan form alanlarını değiştirmeye çalışırsam ne olur?

A: Uygun erişim haklarına sahip olmadan form alanlarını değiştirmeye çalışırsanız, değişiklikler PDF belgesine kaydedilmez ve bir istisna veya hata mesajı alabilirsiniz.

#### S: Aspose.PDF for .NET, .NET Framework'ün tüm sürümleriyle uyumlu mudur?

C: Evet, Aspose.PDF for .NET, .NET Core ve .NET Standard dahil olmak üzere .NET Framework'ün tüm sürümleriyle uyumludur.

#### S: C# dışındaki programlama dillerinde PDF belgesinde form haklarını programatik olarak koruyabilir miyim?

C: Evet, Aspose.PDF for .NET, C#'ın yanı sıra VB.NET ve ASP.NET gibi çeşitli programlama dillerini de destekler.