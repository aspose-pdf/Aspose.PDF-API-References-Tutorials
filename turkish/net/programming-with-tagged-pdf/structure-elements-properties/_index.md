---
title: Yapı Elemanları Özellikleri
linktitle: Yapı Elemanları Özellikleri
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF belgesinde yapısal eleman özellikleriyle çalışmak için adım adım kılavuz. Bilgi açısından zengin yapısal öğeler oluşturun.
type: docs
weight: 150
url: /tr/net/programming-with-tagged-pdf/structure-elements-properties/
---
Bu kılavuzda, Aspose.PDF kitaplığını .NET kullanarak bir PDF belgesinde yapısal eleman özellikleriyle nasıl çalışacağınızı göstereceğiz. Aspose.PDF, PDF dosyalarını programlı olarak oluşturmanıza, değiştirmenize ve dönüştürmenize izin veren güçlü bir kitaplıktır.

Şimdi koda inelim ve Aspose.PDF for .NET kullanarak bir PDF belgesinde yapı elemanı özellikleriyle nasıl çalışılacağını öğrenelim.

## Önkoşullar

Başlamadan önce, Aspose.PDF for .NET'i kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun.

## 1. Adım: Belgeyi oluşturma

 İlk adım, kullanarak yeni bir PDF belgesi oluşturmaktır.`Document` sınıf.

```csharp
// PDF belgesini oluşturun
Document document = new Document();
```

## 2. Adım: Etiketli içeriğe erişin

 Ardından, kullanarak belgenin etiketli içeriğine erişiyoruz.`ITaggedContent` nesne.

```csharp
//Etiketli içeriğe erişin
Tagged.ITaggedContent taggedContent = document.TaggedContent;
```

## 3. Adım: Başlığı ve dili ayarlayın

 Artık belge başlığını ve dilini kullanarak ayarlayabiliriz.`SetTitle` Ve`SetLanguage` yöntemleri`ITaggedContent` nesne.

```csharp
// Belgenin başlığını tanımlayın
taggedContent.SetTitle("Tagged PDF document");

// Belge dilini ayarla
taggedContent.SetLanguage("fr-FR");
```

## Adım 4: Yapısal elemanların oluşturulması

Daha sonra PDF belgesinde yapısal elemanları oluşturuyoruz. Bu örnekte, bir bölüm öğesi oluşturacağız (`SectElement`) ve bir başlık öğesi (`HeaderElement`).

```csharp
//Bölüm öğesi oluşturma
StructureElement rootElement = taggedContent.RootElement;
SectElement sect = taggedContent.CreateSectElement();
rootElement.AppendChild(sect);

// Bir başlık öğesi oluşturun
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
sect.AppendChild(h1);
h1.SetText("Header");
h1.Title = "Title";
h1.Language = "fr-FR";
h1.AlternativeText = "Alternative Text";
h1.ExpansionText = "Expansion Text";
h1.ActualText = "Actual Text";
```

## 5. Adım: Etiketli PDF belgesini kaydedin

Son olarak, etiketli PDF belgesini kaydediyoruz.

```csharp
// Etiketli PDF belgesini kaydedin
document.Save(dataDir + "StructureElementsProperties.pdf");
```

### Aspose.PDF for .NET kullanan Yapı Elemanları Özellikleri için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF Belgesi Oluştur
Document document = new Document();

// TaggedPdf ile çalışmak için İçerik Alın
ITaggedContent taggedContent = document.TaggedContent;

// Documnet için Başlığı ve Dili Ayarlayın
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Yapı Elemanları Oluştur
StructureElement rootElement = taggedContent.RootElement;
SectElement sect = taggedContent.CreateSectElement();
rootElement.AppendChild(sect);
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
sect.AppendChild(h1);
h1.SetText("The Header");
h1.Title = "Title";
h1.Language = "en-US";
h1.AlternativeText = "Alternative Text";
h1.ExpansionText = "Expansion Text";
h1.ActualText = "Actual Text";

// Etiketli PDF Belgesini Kaydet
document.Save(dataDir + "StructureElementsProperties.pdf");

```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF belgesinde yapısal eleman özellikleriyle nasıl çalışacağınızı biliyorsunuz. Bilgi açısından zengin yapı öğeleriyle kişiselleştirilmiş PDF belgeleri oluşturmak için Aspose.PDF'nin özelliklerini daha fazla keşfedebilirsiniz.
