---
title: Vurgulanan Metni Çıkar
linktitle: Vurgulanan Metni Çıkar
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuz ile Aspose.PDF for .NET kullanarak vurgulanan metni nasıl çıkaracağınızı öğrenin.
type: docs
weight: 60
url: /tr/net/annotations/extracthighlightedtext/
---
Bir PDF belgesinden vurgulanan metni çıkarmak için Aspose.PDF for .NET API'sini kullanabilirsiniz. Bu API, bir belgede vurgulanan tüm metni almanın basit bir yolunu sağlar.

## 1. Adım: PDF belgesini yükleyin

 Bir PDF belgesinden vurgulanan metni çıkarmanın ilk adımı, belgeyi Aspose.PDF for .NET API kullanarak yüklemektir. Bunu, yeni bir örnek oluşturarak yapabilirsiniz.`Document` sınıfı ve yolu bir parametre olarak PDF belgesine geçirme. 

```csharp
// Belgeler dizininin yolu.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## 2. Adım: Tüm ek açıklamalar arasında geçiş yapın

 Bir sonraki adım, PDF belgesindeki tüm notlar arasında geçiş yapmaktır. Bunu kullanarak yapabilirsiniz`foreach` döngü, şöyle:

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	// Kod buraya gelecek
}
```

## 3. Adım: Metin biçimlendirme ek açıklamalarını filtreleyin

 İçinde`foreach` döngü, metin biçimlendirme ek açıklamaları olmayan tüm ek açıklamaları filtrelemeniz gerekir. Ek açıklamanın bir örneği olup olmadığını kontrol ederek bunu yapabilirsiniz.`TextMarkupAnnotation` sınıf.

```csharp
if (annotation is TextMarkupAnnotation)
{
	// Kod buraya gelecek
}
```

## 4. Adım: Vurgulanan metin parçalarını alın

 Tüm metin biçimlendirme ek açıklamalarını filtreledikten sonra, her ek açıklama için vurgulanan metin parçalarını alabilirsiniz. numaralı telefonu arayarak bunu yapabilirsiniz.`GetMarkedTextFragments()` yöntemi`TextMarkupAnnotation` nesne.

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## 5. Adım: Vurgulanan metni görüntüleyin

 Son olarak, vurgulanan metni kullanıcıya gösterebilirsiniz. Bunu, her biri arasında döngü yaparak yapabilirsiniz.`TextFragment` içindeki nesne`TextFragmentCollection` ve çağrı`Text` mülk.

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### Aspose.PDF for .NET kullanarak Vurgulanmış Metni Çıkarma için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir ="YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");

	foreach (Annotation annotation in doc.Pages[1].Annotations)
	{
		if (annotation is TextMarkupAnnotation)
		{
			TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
			TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
			foreach (TextFragment tf in collection)
			{
				Console.WriteLine(tf.Text);
			}
		}
	}
```

