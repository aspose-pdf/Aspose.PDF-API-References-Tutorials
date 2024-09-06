---
title: Form Alanı Yazı Tipi 14
linktitle: Form Alanı Yazı Tipi 14
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinizdeki form alanlarının yazı tiplerini kolayca yapılandırın.
type: docs
weight: 110
url: /tr/net/programming-with-forms/form-field-font-14/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak bir form alanının yazı tipini nasıl yapılandıracağınızı göstereceğiz. Bu süreçte size rehberlik etmek için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Öncelikle gerekli kütüphaneleri içeri aktardığınızdan ve belgeler dizinine giden yolu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Belgeyi açın

Mevcut PDF belgesini açın:

```csharp
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
```

## Adım 3: Belirli bir form alanını alın

İstenilen form alanını alın (bu örnekte "textbox1" alanını kullanıyoruz):

```csharp
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
```

## Adım 4: Bir yazı tipi nesnesi oluşturun

Kullanmak istediğiniz yeni yazı tipi için bir yazı tipi nesnesi oluşturun (örneğin, "ComicSansMS"):

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
```

## Adım 5: Form alanı için yazı tipi bilgilerini yapılandırın

Daha önce oluşturulan yazı tipini kullanarak form alanı için yazı tipi bilgilerini yapılandırın:

```csharp
field.DefaultAppearance = new Aspose.Pdf.Forms.DefaultAppearance(font, 14, System.Drawing.Color.Black);
```

## Adım 6: Güncellenen belgeyi kaydedin

Güncellenen PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "FormFieldFont14_out.pdf";
pdfDocument.Save(dataDir);
```


### .NET için Aspose.PDF kullanılarak Form Field Font 14 için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
// Belgeden belirli form alanını al
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
// Yazı tipi nesnesi oluştur
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
// Form alanı için yazı tipi bilgilerini ayarlayın
// Alan.VarsayılanGörünüm = new Aspose.Pdf.Forms.in.VarsayılanGörünüm(yazı tipi, 10, Sistem.Çizim.Renk.Siyah);
dataDir = dataDir + "FormFieldFont14_out.pdf";
// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field font setup successfully.\nFile saved at " + dataDir);
```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak bir form alanının yazı tipini nasıl yapılandıracağımızı öğrendik. Bu adımları izleyerek, Aspose.PDF kullanarak PDF belgelerinizdeki form alanları için yazı tipini ve yazı tipi boyutunu kolayca belirtebilirsiniz.

### SSS

#### S: Aspose.PDF for .NET'te form alanları için herhangi bir yazı tipini kullanabilir miyim?

A: Evet, Aspose.PDF for .NET'te form alanları için herhangi bir TrueType veya OpenType yazı tipini kullanabilirsiniz. Yazı tipi sistemde mevcut ve yüklü olduğu veya FontRepository aracılığıyla erişilebilir olduğu sürece, form alanı metninin görünümünü özelleştirmek için kullanabilirsiniz.

#### S: Aspose.PDF for .NET'te mevcut yazı tiplerini nasıl bulabilirim?

 A: .NET için Aspose.PDF'de mevcut yazı tiplerini bulmak için şunu kullanabilirsiniz:`FontRepository.GetAvailableFonts()`yöntem. Bu yöntem, PDF belgenizdeki form alanları veya diğer metinle ilgili işlemler için kullanabileceğiniz kullanılabilir yazı tiplerinin bir dizisini döndürür.

#### S: Form alanlarının yazı tipi boyutunu herhangi bir değere değiştirebilir miyim?

A: Evet, Aspose.PDF for .NET kullanarak form alanları için yazı tipi boyutunu herhangi bir pozitif sayısal değere değiştirebilirsiniz. Ancak, yazı tipi boyutunun belirli form alanı için uygun olduğundan ve metin kesilmesine veya belgedeki diğer öğelerle çakışmaya yol açmadığından emin olmak önemlidir.

#### S: Form alanlarının yazı rengini değiştirebilir miyim?

A: Evet, .NET için Aspose.PDF'yi kullanarak form alanlarının yazı tipi rengini değiştirebilirsiniz. Sağlanan C# kaynak kodunda yazı tipi rengi siyah olarak ayarlanmıştır (`System.Drawing.Color.Black`), ancak bunu herhangi bir geçerli renk değerine göre özelleştirebilirsiniz.

#### S: Form alanındaki metni nasıl hizalayabilirim?

 A: Form alanındaki metni hizalamak için şunu kullanabilirsiniz:`Multiline`form alanının özelliğini etkinleştirin ve bunu true olarak ayarlayın. Bu özellik, form alanı içinde çok satırlı metinleri etkinleştirir ve satır sonları ve satırbaşı dönüşleriyle metin hizalamasını kontrol etmenize olanak tanır.