---
title: Bağlantı Metin Rengini Güncelle
linktitle: Bağlantı Metin Rengini Güncelle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF dosyasındaki bağlantıların metin rengini nasıl güncelleyeceğinizi öğrenin.
type: docs
weight: 130
url: /tr/net/programming-with-links-and-actions/update-link-text-color/
---

Bu adım adım kılavuz ile Aspose.PDF for .NET kullanarak bir PDF dosyasındaki bağlantıların metin rengini nasıl güncelleyeceğinizi öğrenin.

## 1. Adım: Ortamı ayarlama

Geliştirme ortamınızı bir C# projesi ve uygun Aspose.PDF referansları ile kurduğunuzdan emin olun.

## 2. Adım: PDF dosyasını yükleme

Belgelerinizin dizin yolunu ayarlayın ve aşağıdaki kodu kullanarak PDF dosyasını yükleyin:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// PDF dosyasını yükleyin
Document doc = new Document(dataDir + "UpdateLinks.pdf");
```

## 3. Adım: Bağlantı Ek Açıklamalarında Gezinme

Aşağıdaki kodu kullanarak belgenin ikinci sayfasındaki tüm bağlantı ek açıklamaları arasında geçiş yapın:

```csharp
foreach(Annotation annotation in doc.Pages[1].Annotations)
{
     if (annotation is LinkAnnotation)
     {
         // Ek açıklamanın altındaki metni bulun
         TextFragmentAbsorber ta = new TextFragmentAbsorber();
         Rectangle rect = annotation.Rect;
         rect.LLX -= 10;
         rect.LLY -= 10;
         rect.URX += 10;
         rect.URY += 10;
         ta.TextSearchOptions = new TextSearchOptions(rect);
         your.Visit(doc.Pages[1]);
         // Metin rengini değiştirin.
         foreach(TextFragment tf in ta.TextFragments)
         {
             tf.TextState.ForegroundColor = Color.Red;
         }
     }
}
```

## 4. Adım: Belgeyi güncellenmiş bağlantı metniyle kaydedin

 kullanarak belgeyi güncellenmiş bağlantı metniyle kaydedin.`Save` yöntem:

```csharp
dataDir = dataDir + "UpdateLinkTextColor_out.pdf";
doc.Save(dataDir);
```

## 5. Adım: Sonucun görüntülenmesi

Bağlantı açıklaması metin renginin başarıyla güncellendiğini belirten bir mesaj görüntüleyin ve kaydedilen dosyanın konumunu belirtin:

```csharp
Console.WriteLine("\nText color of link annotations updated successfully.\nFile saved to location: " + dataDir);
```

### Aspose.PDF for .NET kullanarak Bağlantı Metin Rengini Güncelleme için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// PDF dosyasını yükleyin
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	foreach (Annotation annotation in doc.Pages[1].Annotations)
	{
		if (annotation is LinkAnnotation)
		{
			// Ek açıklama altındaki metni arayın
			TextFragmentAbsorber ta = new TextFragmentAbsorber();
			Rectangle rect = annotation.Rect;
			rect.LLX -= 10;
			rect.LLY -= 10;
			rect.URX += 10;
			rect.URY += 10;
			ta.TextSearchOptions = new TextSearchOptions(rect);
			ta.Visit(doc.Pages[1]);
			// Metnin rengini değiştirin.
			foreach (TextFragment tf in ta.TextFragments)
			{
				tf.TextState.ForegroundColor = Color.Red;
			}
		}
	}
	dataDir = dataDir + "UpdateLinkTextColor_out.pdf";
	// Belgeyi güncellenmiş bağlantıyla kaydedin
	doc.Save(dataDir);
	Console.WriteLine("\nLinkAnnotation text color updated successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm

Tebrikler! Artık bir PDF dosyasındaki bağlantıların metin rengini Aspose.PDF for .NET kullanarak nasıl güncelleyeceğinizi biliyorsunuz. PDF belgelerindeki bağlantılarınızın görünümünü özelleştirmek için bu bilgiyi kullanın.

Artık bu kılavuzu tamamladığınıza göre, bu kavramları kendi projelerinize uygulayabilir ve Aspose.PDF for .NET tarafından sunulan özellikleri daha fazla keşfedebilirsiniz.