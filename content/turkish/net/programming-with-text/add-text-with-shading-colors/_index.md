---
title: PDF Dosyasına Gölgelendirme Renkleriyle Metin Ekleme
linktitle: PDF Dosyasına Gölgelendirme Renkleriyle Metin Ekleme
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak PDF dosyasına gölgelendirme renkleriyle metin eklemeyi öğrenin.
type: docs
weight: 80
url: /tr/net/programming-with-text/add-text-with-shading-colors/
---
Bu eğitim, Aspose.PDF for .NET kullanarak PDF dosyasına gölgelendirme renkleriyle metin ekleme sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Makinenizde kurulu Visual Studio veya başka herhangi bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi ayarlayın
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
Gölgelendirme renklerine sahip metin eklemek istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki kullanma yönergesini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## 3. Adım: Belge dizinini ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile birlikte.

## 4. Adım: PDF belgesini yükleyin
 Mevcut PDF belgesini kullanarak yükleyin.`Document` yapıcıya gidin ve belge dosyasının yolunu sağlayın.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Kod buraya gelecek...
}
```

## 5. Adım: Değiştirilecek metni bulun
 Kullanmak`TextFragmentAbsorber` Belgede istenen metni bulmak için. Sağlanan kodda "Lorem ipsum" metnini arar.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## 6. Adım: Metin için gölgeleme rengini ayarlayın
 Yeni bir tane oluştur`Color` Desen renk uzayına sahip nesneyi seçin ve degrade gölgeleme renklerini belirtin. Bu rengi şuna atayın:`ForegroundColor` mülkiyeti`TextState` arasında`TextFragment` nesne.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## 7. Adım: Ek metin biçimlendirmesi uygulayın (isteğe bağlı)
 Metin parçasının özelliklerini değiştirerek, metin parçasına alt çizgi gibi ek biçimlendirmeler uygulayabilirsiniz.`TextState` nesne.

```csharp
textFragment.TextState.Underline = true;
```

## 8. Adım: Değiştirilen PDF belgesini kaydedin
 Değiştirilen PDF belgesini kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Aspose.PDF for .NET kullanarak Gölgeleme Renkleriyle Metin Ekleme için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// Desen renk alanıyla yeni renk oluşturma
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## Çözüm
Aspose.PDF for .NET'i kullanarak PDF belgenize gölgelendirme renklerine sahip metni başarıyla eklediniz. Ortaya çıkan PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.

### SSS'ler

#### S: Bu eğitimin ana odağı nedir?

C: Bu eğitim, Aspose.PDF for .NET kütüphanesini kullanarak bir PDF dosyasına gölgelendirme renkleri içeren metin ekleme sürecinde size yol gösterir. Sağlanan C# kaynak kodu, bunu başarmak için gerekli adımları gösterir.

#### S: Bu eğitim için hangi ad alanlarını içe aktarmam gerekiyor?

C: Gölgelendirme renklerine sahip metin eklemek istediğiniz kod dosyasında, dosyanın başına aşağıdaki ad alanlarını içe aktarın:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### S: Belge dizinini nasıl belirlerim?

 A: Kodda satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

#### S: Mevcut bir PDF belgesini nasıl yüklerim?

 C: 4. Adımda, mevcut bir PDF belgesini`Document` yapıcı ve belge dosyasının yolunu sağlama:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Kod buraya gelecek...
}
```

#### S: PDF belgesindeki belirli metni nasıl bulurum ve değiştiririm?

 C: 5. Adımda şunları kullanacaksınız:`TextFragmentAbsorber`Belgede istenen metni bulmak için. Daha sonra özelliklerini değiştirebilirsiniz:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### S: Metnin gölgeleme renklerini nasıl ayarlayabilirim?

 C: 6. Adımda yeni bir`Color` Desen renk uzayına sahip nesneyi seçin ve degrade gölgeleme renklerini belirtin. Bu rengi şuna atayın:`ForegroundColor` mülkiyeti`TextState` arasında`TextFragment` nesne:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### S: Değiştirilen metne ek metin biçimlendirmesi uygulayabilir miyim?

 C: Evet, 7. Adımda, metnin özelliklerini değiştirerek altını çizme gibi ek metin biçimlendirmeleri uygulayabilirsiniz.`TextState` nesne:

```csharp
textFragment.TextState.Underline = true;
```

#### S: Değiştirilen PDF belgesini nasıl kaydederim?

 C: 8. Adımda, değiştirilen PDF belgesini aşağıdaki komutu kullanarak kaydedeceksiniz:`Save` yöntemi`Document` nesne:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### S: Bu eğitimden çıkan ana sonuç nedir?

C: Bu eğitimi takip ederek, Aspose.PDF for .NET'i kullanarak gölgeli renklerle metin ekleyerek PDF belgenizi nasıl geliştireceğinizi başarıyla öğrendiniz. Bu, özellikle PDF dosyalarınızdaki belirli metin içeriğini vurgulamak ve vurgulamak için yararlı olabilir.