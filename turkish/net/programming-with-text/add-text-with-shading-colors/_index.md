---
title: Gölgelendirme Renkleriyle Metin Ekleme
linktitle: Gölgelendirme Renkleriyle Metin Ekleme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesine gölgelendirme renkleriyle metin eklemeyi öğrenin.
type: docs
weight: 80
url: /tr/net/programming-with-text/add-text-with-shading-colors/
---

Bu eğitim, Aspose.PDF for .NET kullanarak gölgelendirme renkleriyle metin ekleme sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu, gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya makinenizde kurulu başka bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi kurun
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
Gölgelendirme renkleriyle metin eklemek istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki using yönergesini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## 3. Adım: Belge dizinini ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile.

## 4. Adım: PDF belgesini yükleyin
 kullanarak mevcut PDF belgesini yükleyin.`Document` yapıcı ve belge dosyasının yolunu sağlayın.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Kod buraya gelecek...
}
```

## 5. Adım: Değiştirilecek metni bulun
 Kullanmak`TextFragmentAbsorber` belge içinde istenen metni bulmak için. Sağlanan kodda "Lorem ipsum" metnini arar.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## 6. Adım: Metin için gölgelendirme rengini ayarlayın
 Yeni bir tane oluştur`Color`desen renk uzayına sahip nesneyi seçin ve degrade gölgeleme renklerini belirtin. Bu rengi şuraya atayın:`ForegroundColor` mülkiyeti`TextState` arasında`TextFragment` nesne.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## 7. Adım: Ek metin biçimlendirmesi uygulayın (isteğe bağlı)
 Özelliklerini değiştirerek metin parçasına altı çizili gibi ek biçimlendirme uygulayabilirsiniz.`TextState` nesne.

```csharp
textFragment.TextState.Underline = true;
```

## 8. Adım: Değiştirilen PDF belgesini kaydedin
 Değiştirilen PDF belgesini kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Aspose.PDF for .NET kullanarak Gölgelendirme Renkleriyle Metin Ekleme için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// Desen renk alanıyla yeni renk oluştur
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## Çözüm
Aspose.PDF for .NET'i kullanarak PDF belgenize gölgelendirme renkleriyle metni başarıyla eklediniz. Ortaya çıkan PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.