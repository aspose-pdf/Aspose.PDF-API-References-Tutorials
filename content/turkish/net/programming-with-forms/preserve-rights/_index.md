---
title: Hakları Koruyun
linktitle: Hakları Koruyun
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF belgelerinizdeki form haklarını koruyun.
type: docs
weight: 210
url: /tr/net/programming-with-forms/preserve-rights/
---
Bu eğitimde size Aspose.PDF for .NET kullanarak bir PDF belgesinde form haklarını nasıl koruyacağınızı göstereceğiz. Bu süreçte size yol göstermek için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kitaplıkları içe aktardığınızdan ve belgeler dizininizin yolunu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi açın

 Kaynak PDF belgesini bir kullanarak açın.`FileStream` okuma ve yazma izniyle:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## 3. Adım: Form Alanlarını Düzenleyin

Belgedeki tüm form alanlarını inceleyin ve gerekli değişiklikleri yapın. Bu örnekte adında "A1" bulunan bir form alanının değerini değiştiriyoruz:

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

 kapatmayı unutmayın`FileStream` işiniz bittiğinde itiraz edin:

```csharp
fs. Close();
```

### Aspose.PDF for .NET kullanarak Hakları Koru için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Kaynak PDF formunu FileAccess of Read and Write ile okuyun.
// Okuma Yazma iznine ihtiyacımız var çünkü değişiklikten sonra
// Güncellenen içerikleri aynı belgeye/dosyaya kaydetmemiz gerekiyor.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Belge örneğini oluştur
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Tüm alanlardan değer alın
foreach (Field formField in pdfDocument.Form)
{
	// Alanın tam adı A1 içeriyorsa işlemi gerçekleştirin
	if (formField.FullName.Contains("A1"))
	{
		// Form alanını TextBox olarak yayınla
		TextBoxField textBoxField = formField as TextBoxField;
		// Alan değerini değiştir
		textBoxField.Value = "Testing";
	}
}
// Güncellenen belgeyi FileStream'i kaydet'e kaydedin
pdfDocument.Save();
// Dosya Akışı nesnesini kapatın
fs.Close();
```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF belgesindeki formun haklarını nasıl koruyacağımızı öğrendik. Bu adımları izleyerek form alanlarına kolayca erişebilir ve erişim ve yazma izinlerini korurken belirli değişiklikler yapabilirsiniz.


### SSS'ler

#### S: PDF belgesindeki diğer form alanlarını etkilemeden belirli form alanlarının haklarını koruyabilir miyim?

 C: Evet, kullanarak`FullName` Form alanlarının özelliği sayesinde, diğerlerini etkilenmeden korurken belirli form alanlarını korumak için hedefleyebilirsiniz.

#### S: Parola korumalı bir PDF belgesindeki formun haklarını koruyabilir miyim?

C: Evet, Aspose.PDF for .NET, dosyaya erişmek ve değişiklik yapmak için doğru şifreyi sağladığınız sürece, şifre korumalı PDF belgelerinde bile bir formun haklarını korumanıza olanak tanır.

#### S: Form alanlarını uygun erişim hakları olmadan değiştirmeye çalışırsam ne olur?

C: Uygun erişim hakları olmadan form alanlarını değiştirmeye çalışırsanız, değişiklikler PDF belgesine kaydedilmez ve bir istisna veya hata mesajı alabilirsiniz.

#### S: Aspose.PDF for .NET, .NET Framework'ün tüm sürümleriyle uyumlu mudur?

C: Evet, Aspose.PDF for .NET, .NET Core ve .NET Standard da dahil olmak üzere .NET Framework'ün tüm sürümleriyle uyumludur.

#### S: Bir PDF belgesindeki form haklarını C# dışında diğer programlama dillerinde programlı olarak koruyabilir miyim?

C: Evet, Aspose.PDF for .NET, C#'ın yanı sıra VB.NET ve ASP.NET gibi çeşitli programlama dillerini de destekler.