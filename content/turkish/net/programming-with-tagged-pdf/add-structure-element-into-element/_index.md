---
title: Elemana Yapı Elemanı Ekle
linktitle: Elemana Yapı Elemanı Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Bu kapsamlı adım adım eğitimde, Aspose.PDF for .NET kullanarak PDF'lere erişilebilirlik yapı öğelerinin nasıl ekleneceğini öğrenin.
type: docs
weight: 20
url: /tr/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
## giriiş

Günümüzün dijital dünyasında erişilebilirlik anahtardır. Herkesin bilgiye eşit erişimi olmalı ve bunu herkesin kolayca gezinebileceği bir biçimde sağlamak hayati önem taşır. Bu eğitimde, .NET için Aspose.PDF kullanarak yapı öğeleri ekleyerek PDF erişilebilirliğini nasıl artıracağımızı ele alacağız. Bu güçlü kitaplık, geliştiricilerin PDF belgeleriyle sorunsuz bir şekilde çalışmasını sağlayarak erişilebilirlik standartlarına uygun etiketli PDF'ler oluşturmalarını sağlar.

## Ön koşullar

PDF yapı öğelerinin dünyasına yolculuğumuza başlamadan önce, ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1.  Görsel Stüdyo: Bu, C# kodunuzu yazacağınız ve çalıştıracağınız IDE'nizdir. Buradan indirebilirsiniz[Visual Studio](https://visualstudio.microsoft.com/) Eğer henüz yapmadıysanız.
2.  .NET için Aspose.PDF Kütüphanesi: PDF'leri düzenlemek için kütüphaneye ihtiyacınız olacak. En son sürümü şu adresten indirin:[Aspose web sitesi](https://releases.aspose.com/pdf/net/)Bu kütüphane projemiz için çok önemli.
3. Temel C# Bilgisi: C# sözdizimi ve nesne yönelimli programlamaya aşinalık faydalı olacaktır. Birkaç satır C# yazabiliyorsanız, hazırsınız demektir!
4. PDF Belge Dizini: Bu eğitim için giriş ve çıkış PDF dosyalarını saklayacağınız sisteminizde bir dizin oluşturun.

Artık araçlarımızı ve bilgilerimizi hazırladığımıza göre, işe koyulmak için gerekli paketleri hazırlayalım!

## Paketleri İçe Aktar

İlk önce gerekli ad alanlarını içe aktaralım. C# dosyanızın en üstünde aşağıdakilerin olduğundan emin olun:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
```

Bu ad alanları, PDF belgelerinizle çalışmak ve etiketli içerik oluşturmak için gereken sınıflara ve yöntemlere erişmenizi sağlar. Şimdi, konunun özüne inelim ve kodlamaya başlayalım!

## Adım 1: Belge Dizininizi Ayarlayın

Herhangi bir kodlama gerçekleşmeden önce, dosyalarımızı nereye kaydedeceğimizi belirlememiz gerekir. Bu, betiğimizin sorunsuz çalışması için çok önemlidir.

```csharp
// Belgeler dizinine giden yolu tanımlayın.
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF dosyalarınızı saklamak istediğiniz gerçek yol ile. Bu, aşağıdaki gibi bir şey olabilir`C:\\PDFs\\`.

## Adım 2: Yeni bir PDF Belgesi Oluşturun

Artık dizinimiz hazır olduğuna göre, yapı elemanlarımızı ekleyeceğimiz bir PDF belgesi oluşturalım.

```csharp
Document document = new Document();
```

 Bu satır, yeni bir örneğini başlatır`Document` Sınıf, PDF içeriğimizle çalışmaya başlamamızı sağlıyor.

## Adım 3: Etiketli İçeriğe Erişim ve Kurulum

Belgeniz hazır olduğunda, erişilebilirlik için olmazsa olmaz olan etiketli içerikleri ayarlamanın zamanı geldi.

### Etiketli İçeriği Başlat

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

Bu satır PDF'nizin etiketli içeriğine erişim sağlar. Etiketli içerik, ekran okuyucuların belgenizi doğru bir şekilde yorumlayabilmesi için gereklidir.

### Belge Meta Verilerini Ayarla

Belgenize uygun bir başlık vermeli ve dili tanımlamalısınız.

```csharp
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
```

Bu, belgenin meta verilerini geliştirir ve erişilebilirliğini artırır.

## Adım 4: Yapı Öğelerini Oluşturun ve Ekleyin

Biraz yapı ekleyelim! Bu, düzgün biçimlendirilmiş ve etiketlenmiş bir belge oluşturmak için paragraflar ve span öğeleri oluşturmayı içerir.

### Kök Yapı Elemanı Oluştur

```csharp
StructureElement rootElement = taggedContent.RootElement;
```

Şimdi ilk paragraf ve span elemanlarımızı oluşturacağız.

### İlk Paragraf Öğesini Oluştur

```csharp
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```

Burada yeni bir paragraf öğesi başlatıyoruz ve onu kök yapı öğesine ekliyoruz. Bu, içeriğinizin başlangıç noktasıdır!

### Paragrafa Span Elemanları Ekle

```csharp
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
```

 The`span` öğeler, daha büyük paragrafımızın içindeki mini paragraflar gibidir. Metin biçimlendirmesi üzerinde daha ince kontrol sağlarlar.

### Hepsini Birleştir

Şimdi tüm unsurları bir araya getirerek tam paragrafı oluşturalım:

```csharp
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
```

### Ek Paragraflar için tekrarlayın

Bu işlemi diğer paragraflar için tekrarlayacaksınız:

```csharp
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
```

 Sadece yaratmaya devam et`ParagraphElement` kum`SpanElement` s, bunları ekleyerek`rootElement` yukarıda gösterildiği gibi aynı şekilde`p1`.

## Adım 5: Belgenizi Kaydedin

Tüm yapı öğeleriniz yerli yerindeyken, PDF belgenizi kaydetme zamanı geldi.

### Çıktı Dosyası Yolunu Belirleyin

```csharp
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
```

### Belgeyi Kaydet

```csharp
document.Save(outFile);
```

İşte sihir burada gerçekleşiyor! Belgeniz belirtilen çıktı dosyası yoluna kaydedilir.

## Adım 6: PDF/UA Uyumluluğunu Doğrulayın

Son adım, belgenizin erişilebilirlik açısından PDF/UA standartlarına uygun olup olmadığını kontrol etmektir.

Uygunluğu kontrol etmek için aşağıdaki kodu kullanın:

```csharp
document = new Document(outFile);
string logFile = dataDir + "46144_log.xml";
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

Bu, erişilebilirlik açısından önemli olan belgenizin PDF/UA standartlarına uygun olup olmadığını gösterecektir.

## Çözüm

İşte karşınızda! Aspose.PDF for .NET kullanarak bir PDF belgesine yapı öğelerinin nasıl ekleneceğini öğrendiniz. Bu adımları izleyerek, herhangi bir PDF'yi standartlara uyan erişilebilir bir biçime dönüştürebilir ve herkesin bilgiye eşit erişimden yararlanmasını sağlayabilirsiniz. 

## SSS

### Aspose.PDF for .NET nedir?
Aspose.PDF for .NET, geliştiricilerin PDF belgelerini programlı bir şekilde oluşturmalarına, düzenlemelerine ve dönüştürmelerine olanak tanıyan bir kütüphanedir.

### PDF dosyamın erişilebilir olup olmadığını nasıl kontrol edebilirim?
Erişilebilirlik yönergelerine uyduğundan emin olmak için Aspose.PDF kütüphanesini kullanarak PDF'nizi PDF/UA standartlarına göre doğrulayabilirsiniz.

### Aspose.PDF'yi ücretsiz kullanabilir miyim?
 Evet, Aspose ücretsiz deneme sürümü sunuyor ve bu sayede özelliklerini hiçbir maliyet olmadan keşfedebilirsiniz. İndirebilirsiniz[Burada](https://releases.aspose.com/).

### Aspose.PDF'in dokümanlarını nerede bulabilirim?
Aspose.PDF için kapsamlı dokümanları bulabilirsiniz[Burada](https://reference.aspose.com/pdf/net/).

### Aspose.PDF için lisans nasıl satın alabilirim?
 Lisansı doğrudan Aspose web sitesinden satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).