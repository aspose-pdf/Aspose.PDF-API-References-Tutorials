---
title: Html'den Dönüştürdükten Sonra Köprüleri Kaldır
linktitle: Html'den Dönüştürdükten Sonra Köprüleri Kaldır
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak HTML'yi PDF'ye dönüştürdükten sonra köprüleri kaldırmak için adım adım kılavuz.
type: docs
weight: 250
url: /tr/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
Bu eğitimde, Aspose.PDF for .NET kullanılarak bir HTML dosyasından oluşturulan PDF dosyasındaki köprüleri kaldırma sürecinde size yol göstereceğiz. Köprüler, diğer sayfalara veya web sitelerine yönlendirme yapabilen tıklanabilir bağlantılardır. Aşağıdaki adımları izleyerek, ortaya çıkan PDF dosyasından köprüleri kaldırabileceksiniz.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgiler.
- Sisteminizde yüklü olan .NET için Aspose.PDF kütüphanesi.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: HTML dosyasını yükleme ve köprüleri kaldırma
Bu adımda HTML dosyasını yükleyeceğiz ve ortaya çıkan PDF belgesindeki köprüleri kaldıracağız. Aşağıdaki kodu kullanın:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// HTML yükleme seçeneklerini kullanarak HTML dosyasını yükleyin
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// Belgenin ilk sayfasındaki ek açıklamalara göz atın
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
        
         // Ek açıklamayı sayfadan kaldırın
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` HTML dosyanızın bulunduğu gerçek dizinle.

## Adım 2: Ortaya çıkan PDF dosyasını kaydetme
Son olarak, ortaya çıkan PDF dosyasını köprüler olmadan kaydedeceğiz. Aşağıdaki kodu kullanın:

```csharp
// Ortaya çıkan PDF dosyasını kaydedin
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Yukarıdaki kod, ortaya çıkan PDF dosyasını dosya adıyla kaydeder.`"RemoveHyperlinksFromText_out.pdf"`.

### Aspose.PDF for .NET kullanarak Html'den Dönüştürdükten Sonra Köprüleri Kaldırmak için örnek kaynak kodu

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
Bu eğitimde, Aspose.PDF for .NET kullanılarak bir HTML dosyasından oluşturulan bir PDF dosyasındaki köprüleri adım adım kaldırma işlemini ele aldık. Yukarıda açıklanan talimatları izleyerek, ortaya çıkan PDF dosyasından köprüleri başarıyla kaldırabileceksiniz.

### SSS'ler

#### S: Aspose.PDF for .NET nedir?

C: Aspose.PDF for .NET, geliştiricilerin C# uygulamalarında PDF belgeleriyle çalışmasına olanak tanıyan güçlü bir kitaplıktır. HTML dosyalarını PDF'ye dönüştürme ve PDF içeriğini değiştirme yeteneği de dahil olmak üzere çok çeşitli işlevler sunar.

#### S: Bir PDF dosyasındaki köprüleri neden kaldırmak isteyeyim?

C: Bir PDF dosyasından köprüleri kaldırmanın çeşitli nedenleri vardır. Örneğin, yazdırma veya arşivleme amacıyla harici bağlantıları ortadan kaldırmak veya PDF içeriğinin köprüler aracılığıyla gezinilemez olmasını sağlamak isteyebilirsiniz.

#### S: Aspose.PDF for .NET'i kullanarak bir HTML dosyasını nasıl yükleyebilirim ve köprüleri nasıl kaldırabilirim?

 C: Bir HTML dosyası yüklemek ve köprüleri kaldırmak için Aspose.PDF for .NET'i kullanabilirsiniz.`HtmlLoadOptions` sınıf. Bağlantı ek açıklamalarını bulmak ve niteliklerini değiştirmek için PDF sayfalarındaki ek açıklamaları yineleyin.

#### S: Ortaya çıkan PDF için çıktı dosya adını özelleştirebilir miyim?

C: Evet, PDF belgesini kaydeden kodu değiştirerek, ortaya çıkan PDF dosyasının çıktı dosya adını özelleştirebilirsiniz. İstediğiniz dosya adını değiştirmeniz yeterlidir.`doc.Save()` yöntem.

#### S: Köprüleri belirli kriterlere göre seçerek kaldırmak mümkün müdür?

C: Evet, belirli ölçütlere göre köprüleri seçerek kaldırabilirsiniz. Örneğin, yalnızca harici bağlantıları veya belirli URL'lere işaret eden bağlantıları kaldırmayı seçebilirsiniz.