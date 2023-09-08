---
title: Vurgulanan Metni PDF Dosyasından Çıkart
linktitle: Vurgulanan Metni PDF Dosyasından Çıkart
second_title: .NET API Referansı için Aspose.PDF
description: Bu adım adım kılavuzla Aspose.PDF for .NET kullanarak PDF dosyasındaki vurgulanan metni nasıl çıkaracağınızı öğrenin.
type: docs
weight: 60
url: /tr/net/annotations/extracthighlightedtext/
---
Vurgulanan metni PDF dosyasından çıkarmak için Aspose.PDF for .NET API'sini kullanabilirsiniz. Bu API, bir belgede vurgulanan tüm metni almanın basit bir yolunu sağlar.

## 1. Adım: PDF belgesini yükleyin

 PDF dosyasında vurgulanan metni çıkarmanın ilk adımı, belgeyi Aspose.PDF for .NET API'sini kullanarak yüklemektir. Bunu, yeni bir örneğini oluşturarak yapabilirsiniz.`Document` sınıf ve PDF belgesinin yolunu parametre olarak geçirmek. 

```csharp
// Belgeler dizininin yolu.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## 2. Adım: Tüm ek açıklamalar arasında geçiş yapın

 Bir sonraki adım, PDF belgesindeki tüm ek açıklamalar arasında geçiş yapmaktır. Bunu bir kullanarak yapabilirsiniz`foreach` döngü, şöyle:

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	// Kod buraya gelecek
}
```

## 3. Adım: Metin işaretleme ek açıklamalarını filtreleyin

 İçinde`foreach` döngüsünde, metin işaretleme ek açıklamaları olmayan tüm ek açıklamaları filtrelemeniz gerekecektir. Ek açıklamanın bir örneği olup olmadığını kontrol ederek bunu yapabilirsiniz.`TextMarkupAnnotation` sınıf.

```csharp
if (annotation is TextMarkupAnnotation)
{
	// Kod buraya gelecek
}
```

## 4. Adım: Vurgulanan metin parçalarını alın

 Tüm metin işaretleme ek açıklamalarını filtreledikten sonra, her ek açıklama için vurgulanan metin parçalarını alabilirsiniz. Bunu arayarak yapabilirsiniz.`GetMarkedTextFragments()` konusundaki yöntem`TextMarkupAnnotation` nesne.

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## 5. Adım: Vurgulanan metni görüntüleyin

 Son olarak, vurgulanan metni kullanıcıya görüntüleyebilirsiniz. Bunu her biri arasında döngü yaparak yapabilirsiniz.`TextFragment` içindeki nesne`TextFragmentCollection` ve arayarak`Text` mülk.

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### Aspose.PDF for .NET kullanarak Vurgulanan Metni Çıkarma için örnek kaynak kodu

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

Bu eğitimde, Aspose.PDF for .NET kullanarak vurgulanan metni bir PDF belgesinden nasıl çıkaracağımızı araştırdık. Geliştiriciler, adım adım kılavuzu izleyerek ve sağlanan C# kaynak kodunu kullanarak, PDF belgelerindeki vurgulanan metni kolayca çıkarabilir ve yönetebilir.

### PDF dosyasında vurgulanan metni ayıklamak için SSS

#### S: PDF belgesindeki metin işaretleme açıklamaları nedir?

C: Metin işaretleme ek açıklamaları, bir PDF belgesindeki belirli metni vurgulayan veya işaretleyen ek açıklamalardır. Metin işaretleme ek açıklamalarına örnek olarak vurgulamalar, alt çizgiler ve üstü çizili çizgiler verilebilir.

#### S: Aspose.PDF for .NET'i kullanarak diğer açıklama türlerinden metin çıkarabilir miyim?

C: Evet, Aspose.PDF for .NET, metin işaretleme ek açıklamaları, serbest metin ek açıklamaları ve daha fazlası dahil olmak üzere farklı türdeki ek açıklamalardan metin çıkarmak için çeşitli yöntemler sunar.

#### S: Aspose.PDF for .NET, parola korumalı PDF dosyalarından metin çıkarmayı destekliyor mu?

 C: Evet, Aspose.PDF for .NET, parola korumalı PDF dosyalarından metin çıkarmayı destekler. PDF belgesini kullanarak yüklerken doğru şifreyi girmeniz gerekir.`Document` sınıf.

#### S: Vurgulanan metni renk veya yazar gibi diğer ölçütlere göre filtreleyebilir miyim?

C: Evet, vurgulanan metni renk, yazar veya oluşturulma tarihi gibi diğer kriterlere göre filtreleyebilirsiniz. Aspose.PDF for .NET, özelliklerine göre açıklamalara erişmek ve bunları filtrelemek için yöntemler sağlar.

#### S: Çıkarılan vurgulanan metni ayrı bir dosyaya kaydetmek mümkün mü?

C: Evet, çıkarılan vurgulanan metni ayrı bir dosyaya kaydedebilir veya daha ileri işlemler veya analizler için bir veri yapısında saklayabilirsiniz.
