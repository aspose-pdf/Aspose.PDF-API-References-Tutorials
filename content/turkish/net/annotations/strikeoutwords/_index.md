---
title: Kelimelerin Üstünü Çizin
linktitle: Kelimelerin Üstünü Çizin
second_title: .NET API Referansı için Aspose.PDF
description: Bu makale Aspose.PDF for .NET'in Sözcüklerin Üzerini Çiz özelliğinin kullanımıyla ilgili adım adım kılavuz ve açıklamalar sunmaktadır.
type: docs
weight: 150
url: /tr/net/annotations/strikeoutwords/
---
Aspose.PDF for .NET, PDF dosyalarını oluşturmak, değiştirmek ve dönüştürmek için çeşitli özellikler sağlayan bir PDF belge işleme ve işleme kitaplığıdır. Aspose.PDF'in sağladığı kullanışlı özelliklerden biri, C# kaynak kodunu kullanarak bir PDF belgesindeki sözcüklerin veya ifadelerin üzerini çizebilme yeteneğidir. Bu makalede, Aspose.PDF for .NET kullanarak kelimelerin üzerinin nasıl çizileceği konusunda adım adım bir kılavuz sunacağız.

## 1. Adım: PDF belgesini yükleme
İlk adım, değiştirmek istediğiniz PDF belgesini yüklemektir. Bu eğitimde "BELGE DİZİNİNİZ" klasöründen "input.pdf" adlı bir PDF belgesi yükleyeceğiz. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## 2. Adım: Metin parçalarını arama
PDF belgesindeki belirli kelimelerin veya kelime öbeklerinin üstünü çizmek için önce bunları aramanız gerekir. Aspose.PDF, PDF belgesinde belirli bir metin parçasını aramak için kullanılabilecek bir TextFragmentAbsorber sınıfı sağlar.

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

Yukarıdaki kodda PDF belgesinde "Estoque" metin parçasını arıyoruz. Üstünü çizmek istediğiniz başka bir kelimeyi veya ifadeyi aramak için bunu değiştirebilirsiniz.

## 3. Adım: Metin parçalarının üzerini çizme
Metin parçalarını bulduktan sonraki adım bunların üzerini çizmektir. Aspose.PDF, metin parçası için üstü çizili açıklama oluşturmak amacıyla kullanılabilecek bir StrikeOutAnnotation sınıfı sağlar. 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

Yukarıdaki kodda bulduğumuz her metin parçası için üstü çizili bir açıklama oluşturuyoruz. Üstü çizili açıklamanın opaklığını, kenarlığını ve rengini de ayarlıyoruz.

## Adım 4: Değiştirilen PDF belgesini kaydetme
Metin parçalarının üzerini çizdikten sonra değiştirilen belgeyi kaydedin.

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### Aspose.PDF for .NET kullanan Kelimelerin Üzerini Çizmek için örnek kaynak kodu


```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document document = new Document(dataDir + "input.pdf");

// Belirli bir metin parçasını aramak için TextFragment Absorber örneği oluşturun
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
// PDF belgesinin sayfalarını yineleyin
for (int i = 1; i <= document.Pages.Count; i++)
{
	// PDF belgesinin ilk sayfasını alın
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

// Emilmiş metinlerden oluşan bir koleksiyon oluşturun
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//Yukarıdaki koleksiyonu yineleyin
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	// TextFragment nesnesinin dikdörtgen boyutlarını alın
	Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
				(float)textFragment.Position.XIndent,
				(float)textFragment.Position.YIndent,
				(float)textFragment.Position.XIndent +
				(float)textFragment.Rectangle.Width,
				(float)textFragment.Position.YIndent +
				(float)textFragment.Rectangle.Height);

	// StrikeOut Ek Açıklama örneğini oluştur
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	// Ek açıklama için opaklığı ayarlayın
	strikeOut.Opacity = .80f;
	// Ek açıklama örneği için kenarlığı ayarlayın
	strikeOut.Border = new Border(strikeOut);
	// Ek açıklamanın rengini ayarlayın
	strikeOut.Color = Aspose.Pdf.Color.Red;
	// TextFragment'in ek açıklama koleksiyonuna ek açıklama ekleme
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

## Çözüm

Bu eğitimde, bir PDF belgesindeki belirli kelimelerin üzerini çizmek için Aspose.PDF for .NET'i nasıl kullanacağımızı öğrendik. Adım adım kılavuzu izleyerek ve sağlanan C# kaynak kodunu kullanarak, kolayca bir PDF belgesi yükleyebilir, belirli metin parçalarını arayabilir ve bu sözcükleri görsel olarak işaretlemek ve üstünü çizmek için üstü çizili ek açıklamalar oluşturabilirsiniz. Aspose.PDF for .NET, PDF belgelerini programlı olarak işlemek için basit ve etkili bir yol sağlayarak, onu .NET uygulamalarında PDF dosyalarıyla çalışan geliştiriciler için değerli bir araç haline getirir.

### SSS'ler

#### S: Aspose.PDF for .NET nedir?

C: Aspose.PDF for .NET, geliştiricilerin .NET uygulamalarında PDF belgelerini programlı olarak oluşturmasına, düzenlemesine ve işlemesine olanak tanıyan güçlü bir kitaplıktır. Metin çıkarma, açıklama ekleme, form doldurma ve çok daha fazlasını içeren PDF dosyalarıyla çalışmak için çok çeşitli özellikler sunar.

#### S: Bir PDF belgesindeki belirli kelimelerin üstünü çizmek için Aspose.PDF for .NET'i kullanabilir miyim?

C: Evet, Aspose.PDF for .NET, bir PDF belgesindeki belirli metin parçalarını aramak ve ardından bu sözcükleri görsel olarak işaretleyip çizmek için üstü çizili açıklamalar oluşturmak için işlevsellik sağlar.

#### S: PDF belgesinde üzerini çizmek istediğim metni nasıl belirlerim?

 C: Üzerini çizmek istediğiniz metni belirtmek için`TextFragmentAbsorber` sınıf Aspose.PDF for .NET tarafından sağlanmıştır. İstediğiniz kriterlere göre PDF belgesinde belirli bir metin parçasını aramanıza olanak tanır.

#### S: Üzeri çizili açıklamanın görünümünü özelleştirebilir miyim?

C: Evet, üstü çizili açıklamanın opaklık, kenarlık stili ve renk gibi çeşitli özelliklerini özelleştirebilirsiniz. Bu, üstü çizili açıklamanın görünümünü özel gereksinimlerinize göre uyarlamanıza olanak tanır.