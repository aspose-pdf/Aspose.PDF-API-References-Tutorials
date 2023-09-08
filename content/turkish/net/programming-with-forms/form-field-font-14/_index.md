---
title: Form Alanı Yazı Tipi 14
linktitle: Form Alanı Yazı Tipi 14
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF belgelerinizdeki form alanlarının yazı tipini kolayca yapılandırın.
type: docs
weight: 110
url: /tr/net/programming-with-forms/form-field-font-14/
---
Bu eğitimde size Aspose.PDF for .NET kullanarak bir form alanının yazı tipini nasıl yapılandıracağınızı göstereceğiz. Bu süreçte size yol göstermek için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Öncelikle gerekli kitaplıkları içe aktardığınızdan ve belgeler dizininin yolunu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi açın

Mevcut PDF belgesini açın:

```csharp
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
```

## 3. Adım: Belirli bir form alanı edinin

İstediğiniz form alanını alın (bu örnekte "textbox1" alanını kullanıyoruz):

```csharp
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
```

## 4. Adım: Bir yazı tipi nesnesi oluşturun

Kullanmak istediğiniz yeni yazı tipi için bir yazı tipi nesnesi oluşturun (örneğin, "ComicSansMS"):

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
```

## 5. Adım: Form alanı için yazı tipi bilgilerini yapılandırma

Daha önce oluşturulan yazı tipini kullanarak form alanı için yazı tipi bilgilerini yapılandırın:

```csharp
field.DefaultAppearance = new Aspose.Pdf.Forms.DefaultAppearance(font, 14, System.Drawing.Color.Black);
```

## 6. Adım: Güncellenen belgeyi kaydedin

Güncellenen PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "FormFieldFont14_out.pdf";
pdfDocument.Save(dataDir);
```


### Aspose.PDF for .NET kullanan Form Field Font 14 için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
// Belgeden belirli bir form alanı alın
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
// Yazı tipi nesnesi oluştur
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
// Form alanı için yazı tipi bilgilerini ayarlama
// Field.DefaultAppearance = new Aspose.Pdf.Forms.in.DefaultAppearance(font, 10, System.Drawing.Color.Black);
dataDir = dataDir + "FormFieldFont14_out.pdf";
// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field font setup successfully.\nFile saved at " + dataDir);
```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak bir form alanının yazı tipini nasıl yapılandıracağımızı öğrendik. Bu adımları takip ederek Aspose.PDF'i kullanarak PDF belgelerinizdeki form alanları için yazı tipini ve yazı tipi boyutunu kolayca belirleyebilirsiniz.

### SSS'ler

#### S: Aspose.PDF for .NET'teki form alanları için herhangi bir yazı tipini kullanabilir miyim?

C: Evet, Aspose.PDF for .NET'teki form alanları için herhangi bir TrueType veya OpenType yazı tipini kullanabilirsiniz. Font mevcut olduğu ve sistemde yüklü olduğu veya FontRepository aracılığıyla erişilebilir olduğu sürece form alanı metninin görünümünü özelleştirmek için kullanabilirsiniz.

#### S: Aspose.PDF for .NET'te mevcut yazı tiplerini nasıl bulabilirim?

 C: Aspose.PDF for .NET'te mevcut yazı tiplerini bulmak için`FontRepository.GetAvailableFonts()`yöntem. Bu yöntem, form alanları veya PDF belgenizdeki metinle ilgili diğer işlemler için kullanabileceğiniz bir dizi mevcut yazı tipini döndürür.

#### S: Form alanlarının yazı tipi boyutunu herhangi bir değerle değiştirebilir miyim?

C: Evet, Aspose.PDF for .NET'i kullanarak form alanlarının yazı tipi boyutunu herhangi bir pozitif sayısal değerle değiştirebilirsiniz. Ancak yazı tipi boyutunun belirli form alanına uygun olduğundan ve metnin kesilmesine veya belgedeki diğer öğelerle çakışmasına yol açmadığından emin olmak önemlidir.

#### S: Form alanlarının yazı tipi rengini değiştirebilir miyim?

C: Evet, Aspose.PDF for .NET'i kullanarak form alanlarının yazı tipi rengini değiştirebilirsiniz. Sağlanan C# kaynak kodunda yazı tipi rengi siyah olarak ayarlanmıştır (`System.Drawing.Color.Black`), ancak bunu herhangi bir geçerli renk değerine göre özelleştirebilirsiniz.

#### S: Form alanı içindeki metni nasıl hizalayabilirim?

 C: Metni form alanı içinde hizalamak için`Multiline`form alanının özelliğini seçin ve true olarak ayarlayın. Bu özellik, form alanı içinde çok satırlı metni etkinleştirerek satır sonları ve satırbaşları ile metin hizalamasını kontrol etmenize olanak tanır.