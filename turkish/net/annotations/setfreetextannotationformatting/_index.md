---
title: Serbest Metin Açıklama Biçimlendirmesini Ayarla
linktitle: Serbest Metin Açıklama Biçimlendirmesini Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Bu makale, Aspose.PDF for .NET kullanarak serbest metin ek açıklamasının nasıl oluşturulacağı ve içeriğinin nasıl belirleneceği konusunda adım adım bir kılavuz sunmaktadır.
type: docs
weight: 140
url: /tr/net/annotations/setfreetextannotationformatting/
---

Aspose.PDF for .NET, .NET uygulamalarınızda PDF dosyalarıyla programatik olarak çalışmanıza olanak tanıyan, güçlü ve kullanımı kolay bir PDF belge işleme API'sidir. Aspose.PDF for .NET tarafından sağlanan özelliklerden biri, PDF belgelerinde serbest metin açıklama biçimlendirmesi ayarlama yeteneğidir. Bu makalede, Aspose.PDF for .NET kullanarak serbest metin açıklama biçimlendirmesini ayarlama sürecini adım adım anlatacağız.

## Önkoşullar

Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- Microsoft Visual Studio 2010 veya sonrası
- .NET için Aspose.PDF
- Temel C# bilgisi



## 1. Yeni bir C# konsol uygulaması oluşturun

İlk olarak, Microsoft Visual Studio'da yeni bir C# konsol uygulaması oluşturun. Yeni bir konsol uygulaması oluşturmak için ana menüden "Dosya" > "Yeni" > "Proje" > "Visual C#" > "Konsol Uygulaması"nı seçin.

## 2. Aspose.PDF for .NET'e referans ekleyin

Ardından, projenize Aspose.PDF for .NET'e bir referans ekleyin. Bunu yapmak için "Çözüm Gezgini" bölmesinde projenize sağ tıklayın, "Ekle" > "Referans" öğesini seçin ve ardından Aspose.PDF for .NET DLL dosyasını kaydettiğiniz konuma göz atın. DLL dosyasını seçin ve referansı projenize eklemek için "Tamam"a tıklayın.

## 3. Ortamı kurun

Aspose.PDF for .NET'e referansı ekledikten sonra, ortamı ayarlamanız gerekir. Bunu yapmak için "dataDir" adlı yeni bir dize değişkeni oluşturun ve bunu PDF belgenizin bulunduğu dizinin yoluna ayarlayın. Aşağıdaki kodda "BELGE DİZİNİNİZİ", belge dizininizin gerçek yolu ile değiştirin:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 4. PDF belgesini açın

Ortamı kurduktan sonra, aşağıdaki kodu kullanarak PDF belgesini açabilirsiniz:

```csharp
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");
```

"SetFreeTextAnnotationFormatting.pdf" ifadesini PDF belgenizin gerçek adıyla değiştirin.

## 5. Varsayılan görünümü ayarlayın

Serbest metin açıklamasının varsayılan görünümünü ayarlamak için, istenen yazı tipi, yazı tipi boyutu ve rengiyle DefaultAppearance nesnesini başlatmanız gerekir. Bu eğitimde yazı tipini "Arial", yazı tipi boyutunu 28 ve rengi kırmızı olarak ayarlıyoruz.

```csharp
// DefaultAppearance nesnesinin örneğini oluşturun
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
```

## 6. Ücretsiz bir metin ek açıklaması oluşturun

Artık varsayılan görünümü ayarladığınıza göre, aşağıdaki kodu kullanarak bir serbest metin notu oluşturabilirsiniz:

```csharp
// Ek açıklama oluştur
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
```

Yukarıdaki kod, PDF belgesinin ikinci sayfasında yeni bir serbest metin açıklaması oluşturur. Ek açıklama (200, 400) konumunda olacak ve 400 genişliğe ve 600 yüksekliğe sahip olacaktır.

## 7. Ek açıklamanın içeriğini belirtin

Serbest metin açıklamasını oluşturduktan sonra, açıklamanın içeriğini aşağıdaki kodu kullanarak belirleyebilirsiniz:

```csharp
// Ek açıklamanın içeriğini belirtin
freetext.Contents = "Free Text
```

### Aspose.PDF for .NET kullanarak Serbest Metin Açıklama Biçimlendirmesini Ayarlamak için örnek kaynak kodu
```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	// Belgeyi aç
	Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");

	// DefaultAppearance nesnesinin örneğini oluşturun
	DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
	// Ek açıklama oluştur
	FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
	// Ek açıklamanın içeriğini belirtin
	freetext.Contents = "Free Text";
	// Sayfanın ek açıklamalar koleksiyonuna açıklama ekleme
	pdfDocument.Pages[1].Annotations.Add(freetext);
	dataDir = dataDir + "SetFreeTextAnnotationFormatting_out.pdf";
	//Güncellenen belgeyi kaydedin
	pdfDocument.Save(dataDir);            
 
```
