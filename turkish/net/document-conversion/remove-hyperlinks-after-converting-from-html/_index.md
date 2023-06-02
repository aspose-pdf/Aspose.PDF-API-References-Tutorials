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

### Aspose.Words for .NET kullanarak Html'den Dönüştürdükten Sonra Köprüleri Kaldır için örnek kaynak kodu

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