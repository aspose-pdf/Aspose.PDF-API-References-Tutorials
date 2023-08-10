---
title: PDF Dosyasında Vurgulanan Metni Çıkarın
linktitle: PDF Dosyasında Vurgulanan Metni Çıkarın
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuz ile Aspose.PDF for .NET kullanarak PDF dosyasındaki vurgulanmış metni nasıl çıkaracağınızı öğrenin.
type: docs
weight: 60
url: /tr/net/annotations/extracthighlightedtext/
---
Vurgulanan metni PDF dosyasına çıkarmak için Aspose.PDF for .NET API'sini kullanabilirsiniz. Bu API, bir belgede vurgulanan tüm metni almanın basit bir yolunu sağlar.

## 1. Adım: PDF belgesini yükleyin

 PDF dosyasında vurgulanan metni çıkarmanın ilk adımı, belgeyi Aspose.PDF for .NET API kullanarak yüklemektir. Bunu, yeni bir örnek oluşturarak yapabilirsiniz.`Document` sınıfı ve yolu bir parametre olarak PDF belgesine geçirme. 

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

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinden vurgulanmış metnin nasıl çıkarılacağını araştırdık. Geliştiriciler, adım adım kılavuzu izleyerek ve sağlanan C# kaynak kodunu kullanarak PDF belgelerindeki vurgulanan metni kolayca çıkarabilir ve yönetebilir.

### PDF dosyasında vurgulanan metni çıkarmak için SSS

#### S: Bir PDF belgesindeki metin biçimlendirme ek açıklamaları nelerdir?

A: Metin işaretleme ek açıklamaları, bir PDF belgesindeki belirli metni vurgulayan veya işaretleyen ek açıklamalardır. Metin biçimlendirme ek açıklamalarına örnek olarak vurgular, alt çizgiler ve üstleri çizilir.

#### S: Aspose.PDF for .NET kullanarak diğer açıklama türlerinden metin çıkarabilir miyim?

C: Evet, Aspose.PDF for .NET, metin biçimlendirme açıklamaları, serbest metin açıklamaları ve daha fazlası dahil olmak üzere farklı açıklama türlerinden metin çıkarmak için çeşitli yöntemler sunar.

#### S: Aspose.PDF for .NET, parola korumalı PDF dosyalarından metin çıkarmayı destekliyor mu?

C: Evet, Aspose.PDF for .NET, parola korumalı PDF dosyalarından metin çıkarmayı destekler. kullanarak PDF belgesini yüklerken doğru parolayı girmeniz gerekir.`Document` sınıf.

#### S: Vurgulanan metni renk veya yazar gibi diğer ölçütlere göre filtreleyebilir miyim?

C: Evet, vurgulanan metni renk, yazar veya oluşturma tarihi gibi diğer ölçütlere göre filtreleyebilirsiniz. Aspose.PDF for .NET, ek açıklamalara özelliklerine göre erişmek ve bunları filtrelemek için yöntemler sağlar.

#### S: Ayıklanan vurgulanmış metni ayrı bir dosyaya kaydetmek mümkün müdür?

C: Evet, ayıklanan vurgulanmış metni ayrı bir dosyaya kaydedebilir veya daha fazla işleme veya analiz için bir veri yapısında saklayabilirsiniz.
