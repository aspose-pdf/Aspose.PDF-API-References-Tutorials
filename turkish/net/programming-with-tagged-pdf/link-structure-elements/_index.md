---
title: Bağlantı Yapısı Elemanları
linktitle: Bağlantı Yapısı Elemanları
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bağlantı yapısı öğelerini kullanmak için adım adım kılavuz. PDF belgelerinizde köprüler oluşturun.
type: docs
weight: 120
url: /tr/net/programming-with-tagged-pdf/link-structure-elements/
---
Bu adım adım kılavuzda, bağlantı yapısı öğelerini Aspose.PDF for .NET ile nasıl kullanacağınızı göstereceğiz. Aspose.PDF, PDF belgelerini programlı olarak oluşturmanıza ve yönetmenize izin veren güçlü bir kitaplıktır. Bağlantı yapısı öğeleri, kullanıcıların bağlantıları tıklatmasına ve çevrimiçi kaynaklara gitmesine olanak tanıyarak PDF belgenize köprüler eklemenize olanak tanır.

Şimdi koda inelim ve bağlantı yapısı öğelerinin Aspose.PDF for .NET ile nasıl kullanılacağını öğrenelim.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

1. Aspose.PDF kitaplığı for .NET kurulu.
2. C# programlama dili hakkında temel bilgi.

## 1. Adım: Ortamı ayarlama

Başlamak için C# geliştirme ortamınızı açın ve yeni bir proje oluşturun. Projenizde .NET için Aspose.PDF kitaplığına bir referans eklediğinizden emin olun.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
```

## 2. Adım: Belgeyi oluşturma

 İlk adım, kullanarak yeni bir PDF belgesi oluşturmaktır.`Document` sınıf.

```csharp
// PDF belgesini oluşturun
Document document = new Document();
```

## 3. Adım: Etiketli içerikle çalışın

Ardından, çalışmak için belgenin etiketli içeriğini alırız.

```csharp
// Belgenin etiketli içeriğini alın
ITaggedContent taggedContent = document.TaggedContent;
```

## 4. Adım: Belge başlığını ve dilini ayarlayın

Artık belge başlığını ve dilini ayarlayabiliriz.

```csharp
// Belge başlığını ve dilini tanımlayın
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## 5. Adım: Bağlantı yapısı öğeleri ekleyin

Şimdi link yapı elemanlarını belgemize ekleyelim. Basit metin bağlantıları, resim bağlantıları ve çok satırlı bağlantılar dahil olmak üzere farklı türde bağlantılar oluşturacağız.
```csharp
// Kök yapı öğesini alın (belge yapısı öğesi)
StructureElement rootElement = taggedContent.RootElement;

// Köprü içeren bir paragraf ekleyin
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Zengin metin içeren köprü içeren bir paragraf ekleyin
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Kısmen biçimlendirilmiş metin içeren köprü içeren bir paragraf ekleyin
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

// Çok satırlı köprü içeren bir paragraf ekleyin
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

//Resim içeren köprü içeren bir paragraf ekleyin
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";
```

## 6. Adım: Etiketli PDF belgesini kaydedin

Son olarak, etiketli PDF belgesini kaydediyoruz.

```csharp
// Etiketli PDF belgesini kaydedin
document. Save(outFile);
```

## 7. Adım: PDF/UA uyumluluğunu kontrol edin

 Belgeyi PDF/UA uyumluluğu için de kontrol edebiliriz.`Validate` yöntemi`Document` sınıf.

```csharp
// PDF/UA uyumluluğunu kontrol edin
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### Aspose.PDF for .NET kullanan Link Structure Elements için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

//Oluşturma belgesi ve Etiketli Pdf İçeriği alma
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Belge için Başlık ve Doğa Dilini Ayarlama
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Kök yapı öğesini alma (Belge yapı öğesi)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

// Etiketli PDF Belgesini Kaydet
document.Save(outFile);

// PDF/UA uyumluluğunu kontrol etme
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Çözüm

Tebrikler! Aspose.PDF for .NET ile bağlantı yapısı elemanlarını nasıl kullanacağınızı öğrendiniz. Artık PDF belgelerinizde kullanıcıların çevrimiçi kaynaklara gitmesine olanak tanıyan köprüler oluşturabilirsiniz. Etkileşimli ve zenginleştirilmiş PDF belgeleri oluşturmak için Aspose.PDF'nin diğer özelliklerini deneyin ve keşfedin.