---
title: Serbest Metin Açıklaması Biçimlendirmesini Ayarlama
linktitle: Serbest Metin Açıklaması Biçimlendirmesini Ayarlama
second_title: .NET API Referansı için Aspose.PDF
description: Bu makale, Aspose.PDF for .NET kullanılarak serbest metin açıklamasının nasıl oluşturulacağı ve içeriğinin nasıl belirleneceği konusunda adım adım bir kılavuz sunmaktadır.
type: docs
weight: 140
url: /tr/net/annotations/setfreetextannotationformatting/
---
Aspose.PDF for .NET, .NET uygulamalarınızda PDF dosyalarıyla programlı olarak çalışmanıza olanak tanıyan güçlü ve kullanımı kolay bir PDF belge işleme API'sidir. Aspose.PDF for .NET'in sağladığı özelliklerden biri, PDF belgelerinde serbest metin açıklama formatını ayarlama yeteneğidir. Bu makalede, Aspose.PDF for .NET'i kullanarak serbest metin açıklaması formatını ayarlama konusunda size adım adım yol göstereceğiz.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- Microsoft Visual Studio 2010 veya üzeri
- .NET için Aspose.PDF
- Temel C# bilgisi



## 1. Adım: Yeni bir C# konsol uygulaması oluşturun

Öncelikle Microsoft Visual Studio'da yeni bir C# konsol uygulaması oluşturun. Yeni bir konsol uygulaması oluşturmak için ana menüden "Dosya" > "Yeni" > "Proje" > "Visual C#" > "Konsol Uygulaması"nı seçin.

## Adım 2: Aspose.PDF for .NET'e referans ekleyin

Daha sonra projenize Aspose.PDF for .NET'e bir referans ekleyin. Bunu yapmak için, "Çözüm Gezgini" bölmesinde projenize sağ tıklayın, "Ekle" > "Referans"ı seçin ve ardından Aspose.PDF for .NET DLL dosyasını kaydettiğiniz konuma göz atın. Referansı projenize eklemek için DLL dosyasını seçin ve "Tamam"a tıklayın.

## 3. Adım: Ortamı ayarlayın

Referansı Aspose.PDF for .NET'e ekledikten sonra ortamı ayarlamanız gerekir. Bunu yapmak için "dataDir" adında yeni bir dize değişkeni oluşturun ve bunu PDF belgenizin bulunduğu dizinin yoluna ayarlayın. Aşağıdaki koddaki "BELGE DİZİNİNİZ" ifadesini belge dizininizin gerçek yolu ile değiştirin:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 4. Adım: PDF belgesini açın

Ortamı ayarladıktan sonra aşağıdaki kodu kullanarak PDF belgesini açabilirsiniz:

```csharp
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");
```

"SetFreeTextAnnotationFormatting.pdf" ifadesini PDF belgenizin gerçek adıyla değiştirin.

## 5. Adım: Varsayılan görünümü ayarlayın

Serbest metin açıklamasının varsayılan görünümünü ayarlamak için, DefaultAppearance nesnesini istenen yazı tipi, yazı tipi boyutu ve renkle başlatmanız gerekir. Bu dersimizde yazı tipini "Arial", yazı tipi boyutunu 28 ve rengini kırmızı olarak ayarlıyoruz.

```csharp
// DefaultAppearance nesnesini örnekle
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
```

## 6. Adım: Serbest metin ek açıklaması oluşturun

Artık varsayılan görünümü ayarladığınıza göre, aşağıdaki kodu kullanarak serbest metin açıklaması oluşturabilirsiniz:

```csharp
// Ek açıklama oluştur
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
```

Yukarıdaki kod, PDF belgesinin ikinci sayfasında yeni bir serbest metin açıklaması oluşturur. Ek açıklama (200, 400) konumuna yerleştirilecek ve 400 genişliğinde ve 600 yüksekliğinde olacaktır.

## 7. Adım: Ek açıklamanın içeriğini belirtin

Serbest metin açıklamasını oluşturduktan sonra aşağıdaki kodu kullanarak açıklamanın içeriğini belirleyebilirsiniz:

```csharp
// Ek açıklamanın içeriğini belirtin
freetext.Contents = "Free Text
```

### Aspose.PDF for .NET kullanarak Serbest Metin Açıklaması Formatını Ayarlama için örnek kaynak kodu
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");

// DefaultAppearance nesnesini örnekle
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
// Ek açıklama oluştur
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
// Ek açıklamanın içeriğini belirtin
freetext.Contents = "Free Text";
// Sayfanın ek açıklamalar koleksiyonuna ek açıklama ekleyin
pdfDocument.Pages[1].Annotations.Add(freetext);
dataDir = dataDir + "SetFreeTextAnnotationFormatting_out.pdf";
// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir);            
```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF belgesinde serbest metin açıklaması formatının nasıl ayarlanacağını öğrendik. Kitaplık, PDF belgeleriyle programlı olarak çalışmanın basit ve etkili bir yolunu sunarak geliştiricilerin serbest metin açıklamaları da dahil olmak üzere çeşitli türde açıklamaları oluşturmasına ve özelleştirmesine olanak tanır. Adım adım kılavuzu izleyerek ve sağlanan C# kaynak kodunu kullanarak ortamı kolayca kurabilir, bir PDF belgesi açabilir ve özel biçimlendirmeyle serbest metin açıklaması oluşturabilirsiniz. Aspose.PDF for .NET, PDF belgesi düzenleme görevlerini basitleştiren, onu PDF dosyalarıyla çalışan .NET geliştiricileri için değerli bir araç haline getiren sağlam ve güvenilir bir API'dir.

### SSS'ler

#### S: PDF belgesindeki serbest metin açıklaması nedir?

C: PDF belgesindeki serbest metin açıklaması, belirli bir konuma veya yapıya bağlı kalmadan belgeye metin eklemenizi sağlayan bir açıklama türüdür. Genellikle belgede yorum, not veya diğer ek bilgileri sağlamak için kullanılır.

#### S: Aspose.PDF for .NET'i kullanarak serbest metin açıklamasının görünümünü özelleştirebilir miyim?

C: Evet, serbest metin açıklamasının yazı tipi, yazı tipi boyutu, rengi, konumu ve daha fazlası gibi çeşitli özelliklerini özelleştirebilirsiniz.

#### S: Serbest metin açıklamasının içeriğini nasıl belirleyebilirim?

 C: Serbest metin açıklamasının içeriğini belirtmek için`Contents` mülkiyeti`FreeTextAnnotation` İstenilen metne itiraz edin.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesine birden fazla serbest metin açıklaması ekleyebilir miyim?

 C: Evet, bir PDF belgesinde birden çok serbest metin açıklaması oluşturabilirsiniz.`FreeTextAnnotation`nesneyi kullanma ve bunları belgedeki farklı sayfalara veya konumlara ekleme.