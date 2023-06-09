---
title: Metin Yapısı Öğeleri
linktitle: Metin Yapısı Öğeleri
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesine metin yapısı öğeleri eklemeyi öğrenin. PDF'lerinizin yapısını ve erişilebilirliğini iyileştirin.
type: docs
weight: 230
url: /tr/net/programming-with-tagged-pdf/text-structure-elements/
---
Bu ayrıntılı öğreticide, Aspose.PDF for .NET kullanarak etiketli bir PDF belgesinde metin yapısı öğeleri oluşturmak için sağlanan C# kaynak kodunda adım adım yol göstereceğiz. Metin yapısı öğelerini PDF belgenize nasıl ekleyeceğinizi anlamak için aşağıdaki talimatları izleyin.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, geliştirme ortamınızı Aspose.PDF for .NET kullanacak şekilde yapılandırdığınızdan emin olun. Bu, Aspose.PDF kitaplığının kurulmasını ve projenizin buna referans verecek şekilde yapılandırılmasını içerir.

## 2. Adım: PDF belgesini oluşturma

Bu adımda Aspose.PDF ile yeni bir PDF belge nesnesi oluşturacağız.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// PDF belgesini oluşturun
Document document = new Document();
```

Aspose.PDF ile yeni bir PDF belgesi oluşturduk.

## 3. Adım: Etiketli içeriği alın ve başlığı ve dili ayarlayın

Şimdi PDF belgesinin etiketli içeriğini alalım ve belge başlığını ve dilini ayarlayalım.

```csharp
// Etiketli içerik alın
ITaggedContent taggedContent = document.TaggedContent;

// Belge başlığını ve dilini tanımlayın
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Etiketli PDF belgesinin başlığını ve dilini belirledik.

## Adım 4: Kök yapı elemanının elde edilmesi

Şimdi PDF belgesinin kök yapı elemanını alalım.

```csharp
// Kök yapı öğesini elde edin
StructureElement rootElement = taggedContent.RootElement;
```

PDF belgesinin kök yapı elemanını elde ettik.

## 5. Adım: Paragraf yapısı öğesinin eklenmesi

Şimdi PDF belgemize bir paragraf yapısı öğesi ekleyelim.

```csharp
// Paragraf yapısı öğesini oluşturma
ParagraphElement p = taggedContent.CreateParagraphElement();

// Paragraf yapısı öğesinin metninin tanımı
p.SetText("Paragraph.");

// Paragraf yapısı öğesini kök yapı öğesine ekleyin
rootElement.AppendChild(p);
```

PDF belgemize metin içeren bir paragraf yapısı öğesi ekledik.

## 6. Adım: PDF Belgesini Kaydetme

Artık PDF belgesini düzenlemeyi bitirdiğimize göre, onu bir dosyaya kaydedelim.

```csharp
// Etiketli PDF belgesini kaydedin
document.Save(dataDir + "ElementDeStructureDeTexte.pdf");
```

Metin yapısı öğesiyle etiketlenmiş PDF belgesini belirtilen dizine kaydettik.


### Aspose.PDF for .NET kullanan Text Structure Elements için örnek kaynak kodu 

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

//Kök Yapı Elemanlarını Alın
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p = taggedContent.CreateParagraphElement();

// Metni Metin Yapısı Öğesine Ayarla
p.SetText("Paragraph.");
rootElement.AppendChild(p);

// Etiketli PDF Belgesini Kaydet
document.Save(dataDir + "TextStructureElement.pdf");
```

## Çözüm

Bu eğitimde, bir PDF belgesine metin yapısı öğeleri eklemek için Aspose.PDF for .NET'i nasıl kullanacağımızı öğrendik. Artık bu özellikleri, PDF belgelerinizin yapısını ve erişilebilirliğini geliştirmek için kullanabilirsiniz.