---
title: Alt Öğelere Erişim
linktitle: Alt Öğelere Erişim
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesinin alt öğelerine erişmek ve bunları düzenlemek için adım adım kılavuz. PDF içeriğinizi kişiselleştirin.
type: docs
weight: 10
url: /tr/net/programming-with-tagged-pdf/access-children-elements/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesinin alt öğelerine erişme konusunda adım adım bir kılavuz sağlayacağız. Aspose.PDF, PDF belgelerini program aracılığıyla oluşturmanıza, değiştirmenize ve dönüştürmenize izin veren güçlü bir kitaplıktır. Aspose.PDF'nin işaretli içerik yapısı özelliklerini kullanarak, bir PDF belgesindeki yapılandırılmış öğelerin özelliklerine erişebilir ve özelliklerini değiştirebilirsiniz.

## Önkoşullar

Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

1. .NET çerçevesiyle yüklenen Visual Studio.
2. .NET için Aspose.PDF kitaplığı.

## Adım 1: Proje Kurulumu

Başlamak için Visual Studio'da yeni bir proje oluşturun ve Aspose.PDF for .NET kitaplığına bir referans ekleyin. Kütüphaneyi Aspose resmi sitesinden indirebilir ve makinenize kurabilirsiniz.

## 2. Adım: Gerekli ad alanlarını içe aktarın

Aspose.PDF tarafından sağlanan sınıflara ve yöntemlere erişmek için gereken ad alanlarını C# kod dosyanıza aktarın:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## 3. Adım: PDF Belgesini Yükleme ve Alt Öğelere Erişim

PDF belgesini yüklemek ve alt öğelere erişmek için aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document(dataDir + "StructureElementsTree.pdf");
ITaggedContent taggedContent = document.TaggedContent;
ElementList elementList = taggedContent.StructTreeRootElement.ChildElements;

foreach(Element element in elementList)
{
if (element is StructureElement)
{
StructureElement structureElement = element as StructureElement;
// Öğenin özelliklerine erişin
string title = structureElement.Title;
string language = structureElement.Language;
string actualText = structureElement.ActualText;
string expansionText = structureElement.ExpansionText;
string alternativeText = structureElement.AlternativeText;
}
}
```

Bu kod, PDF belge yapısının kökünün alt öğelerine erişmenizi ve her bir öğenin özelliklerini almanızı sağlar.

## Adım 4: Kök Öğe Alt Öğelerine Erişim ve Özellikleri Değiştirme

Kök öğenin alt öğelerine erişmek ve özellikleri değiştirmek için aşağıdaki kodu kullanın:

```csharp
elementList = taggedContent.RootElement.ChildElements[1].ChildElements;

foreach(Element element in elementList)
{
if (element is StructureElement)
{
StructureElement structureElement = element as StructureElement;
// Öğenin özelliklerini değiştirin
structureElement.Title = "title";
structureElement.Language = "fr-FR";
structureElement.ActualText = "actual text";
structureElement.ExpansionText = "exp";
structureElement.AlternativeText = "alt";
}
}
```

Bu kod, kök öğenin ilk öğesinin çocuklarına erişmenizi ve her öğenin özelliklerini değiştirmenizi sağlar.


### Aspose.PDF for .NET kullanan Access Child Elements için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Pdf Belgesini Aç
Document document = new Document(dataDir + "StructureElementsTree.pdf");
// TaggedPdf ile çalışmak için İçerik Alın
ITaggedContent taggedContent = document.TaggedContent;
// Kök öğe(ler)e erişim
ElementList elementList = taggedContent.StructTreeRootElement.ChildElements;
foreach (Element element in elementList)
{
	if (element is StructureElement)
	{
		StructureElement structureElement = element as StructureElement;
		// özellikleri al
		string title = structureElement.Title;
		string language = structureElement.Language;
		string actualText = structureElement.ActualText;
		string expansionText = structureElement.ExpansionText;
		string alternativeText = structureElement.AlternativeText;
	}
}
// Kök öğedeki ilk öğenin alt öğelerine erişim
elementList = taggedContent.RootElement.ChildElements[1].ChildElements;
foreach (Element element in elementList)
{
	if (element is StructureElement)
	{
		StructureElement structureElement = element as StructureElement;
		// Özellikleri ayarla
		structureElement.Title = "title";
		structureElement.Language = "fr-FR";
		structureElement.ActualText = "actual text";
		structureElement.ExpansionText = "exp";
		structureElement.AlternativeText = "alt";
	}
}
// Etiketli PDF Belgesini Kaydet
document.Save(dataDir + "AccessChildrenElements.pdf");
```

## Çözüm

Bu öğreticide, bir PDF belgesinin alt öğelerine nasıl erişeceğinizi ve Aspose.PDF for .NET kullanarak öğe özelliklerini nasıl değiştireceğinizi öğrendiniz. Bu, bir PDF belgesindeki yapılandırılmış öğeleri ihtiyaçlarınıza göre özelleştirmenize ve değiştirmenize olanak tanır.