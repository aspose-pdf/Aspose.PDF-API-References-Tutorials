---
title: Kurulum Dili ve Başlığı
linktitle: Kurulum Dili ve Başlığı
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF belgesinin dilini ve başlığını yapılandırmak için adım adım kılavuz. Kişiselleştirilmiş çok dilli belgeler oluşturun.
type: docs
weight: 140
url: /tr/net/programming-with-tagged-pdf/setup-language-and-title/
---
Bu kılavuzda, Aspose.PDF library for .NET'i kullanarak bir PDF belgesinin dilini ve başlığını nasıl yapılandıracağınızı anlatacağız. Aspose.PDF, PDF dosyalarını programlı olarak oluşturmanıza, değiştirmenize ve dönüştürmenize izin veren güçlü bir kitaplıktır.

Şimdi koda inelim ve Aspose.PDF for .NET kullanarak bir PDF belgesinin dilini ve başlığını nasıl yapılandıracağınızı öğrenelim.

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
taggedContent.SetTitle("Example of tagged document");

// Belge dilini ayarla
taggedContent.SetLanguage("fr-FR");
```

## 4. Adım: Çok dilli içerik ekleyin

Ardından, her dil için paragraf öğelerini kullanarak belgeye çok dilli içerik ekliyoruz.

```csharp
// İngilizce bir paragraf ekleyin
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// Almanca bir paragraf ekleyin
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hello Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

// Fransızca bir paragraf ekleyin
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Hello world!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// İspanyolca bir paragraf ekleyin
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);
```

## 5. Adım: Etiketli PDF belgesini kaydedin

Son olarak, etiketli PDF belgesini kaydediyoruz.

```csharp
// Etiketli PDF belgesini kaydedin
document.Save(dataDir + "SetupLanguageAndTitle.pdf");
```

### Aspose.PDF for .NET kullanan Setup Language And Title için örnek kaynak kodu 
```csharp

Document document = new Document();

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// İçeriği Etiketle
Tagged.ITaggedContent taggedContent = document.TaggedContent;

// Başlığı ve Dili Ayarla
taggedContent.SetTitle("Example Tagged Document");
taggedContent.SetLanguage("en-US");

// Başlık (en-US, belgeden devralınmıştır)
LogicalStructure.HeaderElement h1 = taggedContent.CreateHeaderElement(1);
h1.SetText("Phrase on different languages");
taggedContent.RootElement.AppendChild(h1);

// Paragraf (İngilizce)
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// Paragraf (Almanca)
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hallo Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

// Paragraf (Fransızca)
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Bonjour le monde!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// Paragraf (İspanyolca)
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);

// Etiketli PDF Belgesini Kaydet
document.Save(dataDir + "SetupLanguageAndTitle.pdf");

```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF belgesinin dilini ve başlığını nasıl yapılandıracağınızı biliyorsunuz. Kişiselleştirilmiş ve çok dilli PDF belgeleri oluşturmak için Aspose.PDF'nin özelliklerini daha fazla keşfedebilirsiniz.
