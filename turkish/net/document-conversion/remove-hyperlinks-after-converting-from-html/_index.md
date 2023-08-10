---
title: Html'den Dönüştürdükten Sonra Köprüleri Kaldırma
linktitle: Html'den Dönüştürdükten Sonra Köprüleri Kaldırma
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak HTML'yi PDF'e dönüştürdükten sonra köprüleri kaldırmak için adım adım kılavuz.
type: docs
weight: 250
url: /tr/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
Bu eğitimde, Aspose.PDF for .NET kullanılarak bir HTML dosyasından oluşturulan bir PDF dosyasından köprüleri kaldırma sürecinde size yol göstereceğiz. Köprüler, diğer sayfalara veya web sitelerine yönlendirebilen tıklanabilir bağlantılardır. Aşağıdaki adımları izleyerek, ortaya çıkan PDF dosyasından köprüleri kaldırabileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgi.
- Sisteminizde kurulu .NET için Aspose.PDF kitaplığı.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: HTML dosyasını yükleme ve köprüleri kaldırma
Bu adımda, HTML dosyasını yükleyeceğiz ve ortaya çıkan PDF belgesinden köprüleri kaldıracağız. Aşağıdaki kodu kullanın:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// HTML yükleme seçeneklerini kullanarak HTML dosyasını yükleyin
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// Belgenin ilk sayfasının açıklamalarına göz atın
foreach(Annotation a in doc.Pages[1].Annotations)
{
     // Ek açıklamanın bir bağlantı olup olmadığını kontrol edin
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         // Eylemin GoToURIAction türünde olup olmadığını kontrol edin
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             // Eşleşen metin parçalarını bulmak için bir metin parçası emici kullanın
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             // Eşleşen metin parçaları arasında dolaşın ve köprülerden nitelikleri kaldırın
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         // Ek açıklamayı sayfadan kaldır
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` HTML dosyanızın bulunduğu gerçek dizinle.

## 2. Adım: Ortaya çıkan PDF dosyasını kaydetme
Son olarak, ortaya çıkan PDF dosyasını köprüler olmadan kaydedeceğiz. Aşağıdaki kodu kullanın:

```csharp
// Ortaya çıkan PDF dosyasını kaydedin
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Yukarıdaki kod, ortaya çıkan PDF dosyasını dosya adıyla kaydeder.`"RemoveHyperlinksFromText_out.pdf"`.

### Aspose.PDF for .NET kullanarak Html'den Dönüştürdükten Sonra Köprüleri Kaldır için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
doc.Save(new MemoryStream());
foreach (Annotation a in doc.Pages[1].Annotations)
{
	if (a.AnnotationType == AnnotationType.Link)
	{
		LinkAnnotation la = (LinkAnnotation)a;
		if (la.Action is GoToURIAction)
		{
			GoToURIAction gta = (GoToURIAction)la.Action;
			gta.URI = "";
			TextFragmentAbsorber tfa = new TextFragmentAbsorber();
			tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
			doc.Pages[a.PageIndex].Accept(tfa);
			foreach (TextFragment tf in tfa.TextFragments)
			{
				tf.TextState.Underline = false;
				tf.TextState.ForegroundColor = Color.Black;
			}
		}
		doc.Pages[a.PageIndex].Annotations.Delete(a);
	}
}
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

## Çözüm
Bu öğreticide, Aspose.PDF for .NET kullanılarak bir HTML dosyasından oluşturulan bir PDF dosyasından köprüleri kaldırma sürecini adım adım ele aldık. Yukarıda açıklanan talimatları izleyerek, ortaya çıkan PDF dosyasından köprüleri başarıyla kaldırabileceksiniz.

### SSS

#### S: Aspose.PDF for .NET nedir?

Y: Aspose.PDF for .NET, geliştiricilerin C# uygulamalarında PDF belgeleriyle çalışmasını sağlayan güçlü bir kitaplıktır. HTML dosyalarını PDF'ye dönüştürme ve PDF içeriğini değiştirme yeteneği de dahil olmak üzere çok çeşitli işlevler sunar.

#### S: Neden bir PDF dosyasından köprüleri kaldırmak isteyeyim?

Y: Bir PDF dosyasından köprüleri kaldırmanın çeşitli nedenleri vardır. Örneğin, yazdırma veya arşivleme amacıyla harici bağlantıları ortadan kaldırmak veya PDF içeriğinin köprüler aracılığıyla gezinilebilir olmamasını sağlamak isteyebilirsiniz.

#### S: Aspose.PDF for .NET kullanarak bir HTML dosyasını nasıl yükleyebilirim ve köprüleri nasıl kaldırabilirim?

 C: Bir HTML dosyası yüklemek ve köprüleri kaldırmak için Aspose.PDF for .NET's kullanabilirsiniz.`HtmlLoadOptions` sınıf. Bağlantı ek açıklamalarını bulmak ve niteliklerini değiştirmek için PDF sayfalarının ek açıklamalarını yineleyin.

#### S: Ortaya çıkan PDF için çıktı dosya adını özelleştirebilir miyim?

C: Evet, PDF belgesini kaydeden kodu değiştirerek ortaya çıkan PDF dosyası için çıktı dosya adını özelleştirebilirsiniz. İstenen dosya adını değiştirmeniz yeterlidir.`doc.Save()` yöntem.

#### S: Köprüleri belirli kriterlere göre seçerek kaldırmak mümkün müdür?

C: Evet, köprüleri belirli kriterlere göre seçerek kaldırabilirsiniz. Örneğin, yalnızca harici bağlantıları veya belirli URL'lere işaret eden bağlantıları kaldırmayı seçebilirsiniz.