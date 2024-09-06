---
title: Bağlantı Yapısı Elemanları
linktitle: Bağlantı Yapısı Elemanları
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bağlantı yapısı öğelerini kullanmaya yönelik adım adım kılavuz. PDF belgelerinizde köprüler oluşturun.
type: docs
weight: 120
url: /tr/net/programming-with-tagged-pdf/link-structure-elements/
---
Bu adım adım kılavuzda, .NET için Aspose.PDF ile bağlantı yapısı öğelerini nasıl kullanacağınızı göstereceğiz. Aspose.PDF, PDF belgelerini programatik olarak oluşturmanıza ve düzenlemenize olanak tanıyan güçlü bir kütüphanedir. Bağlantı yapısı öğeleri, PDF belgenize köprüler eklemenize olanak tanır ve kullanıcıların bağlantıları tıklamasına ve çevrimiçi kaynaklara gitmesine olanak tanır.

Gelin koda bir göz atalım ve Aspose.PDF for .NET ile bağlantı yapısı öğelerinin nasıl kullanılacağını öğrenelim.

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. .NET için Aspose.PDF kütüphanesi kuruldu.
2. C# programlama dilinin temel bilgisi.

## Adım 1: Ortamı kurma

Başlamak için C# geliştirme ortamınızı açın ve yeni bir proje oluşturun. Projenize .NET için Aspose.PDF kütüphanesine bir başvuru eklediğinizden emin olun.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
```

## Adım 2: Belgenin oluşturulması

 İlk adım, yeni bir PDF belgesi oluşturmaktır`Document` sınıf.

```csharp
// PDF belgesini oluşturun
Document document = new Document();
```

## Adım 3: Etiketli içerikle çalışın

Daha sonra belgenin etiketli içeriğini alıp çalışmaya başlıyoruz.

```csharp
// Belgenin etiketli içeriğini alın
ITaggedContent taggedContent = document.TaggedContent;
```

## Adım 4: Belge başlığını ve dilini ayarlayın

Artık belge başlığını ve dilini ayarlayabiliriz.

```csharp
// Belge başlığını ve dilini tanımlayın
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## Adım 5: Bağlantı yapısı öğelerini ekleyin

Şimdi belgemize bağlantı yapısı öğeleri ekleyelim. Basit metin bağlantıları, resim bağlantıları ve çok satırlı bağlantılar dahil olmak üzere farklı türde bağlantılar oluşturacağız.
```csharp
// Kök yapı öğesini (belge yapı öğesini) alın
StructureElement rootElement = taggedContent.RootElement;

// Köprü metni içeren bir paragraf ekleyin
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Zengin metin içeren bir köprü metni içeren bir paragraf ekleyin
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Kısmen biçimlendirilmiş metin içeren bir köprü metni içeren bir paragraf ekleyin
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

// Çok satırlı köprü metni içeren bir paragraf ekleyin
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// Resim içeren bir köprü metni içeren bir paragraf ekleyin
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

## Adım 6: Etiketli PDF belgesini kaydedin

Son olarak etiketli PDF dokümanını kaydediyoruz.

```csharp
// Etiketli PDF belgesini kaydedin
document. Save(outFile);
```

## Adım 7: PDF/UA uyumluluğunu kontrol edin

 Ayrıca PDF/UA uyumluluğunu da kullanarak belgeyi kontrol edebiliriz.`Validate` yöntemi`Document` sınıf.

```csharp
// PDF/UA uyumluluğunu kontrol edin
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### .NET için Aspose.PDF'yi kullanarak Bağlantı Yapısı Elemanları için örnek kaynak kodu 
```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Belge oluşturma ve Etiketli Pdf İçeriği alma
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Belge için Başlık ve Doğa Dilinin Ayarlanması
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Kök yapı elemanını alma (Belge yapı elemanı)
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

// PDF/UA uyumluluğunun kontrol edilmesi
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Çözüm

Tebrikler! Aspose.PDF for .NET ile bağlantı yapısı öğelerini nasıl kullanacağınızı öğrendiniz. Artık PDF belgelerinizde köprüler oluşturabilir ve kullanıcıların çevrimiçi kaynaklara gitmesini sağlayabilirsiniz. Etkileşimli ve zenginleştirilmiş PDF belgeleri oluşturmak için Aspose.PDF'nin daha fazla özelliğini deneyin ve keşfedin.

### SSS

#### S: Bir PDF belgesinde bağlantı yapısı öğeleri nelerdir ve belge etkileşimini nasıl artırırlar?

A: PDF belgesindeki bağlantı yapısı öğeleri, kullanıcıların çevrimiçi kaynaklara veya belge içindeki belirli konumlara gitmesini sağlayan köprüler oluşturmak için kullanılır. Bu öğeler, kullanıcıların ilgili içeriklere veya harici web sitelerine erişmesini sağlayan tıklanabilir bağlantılar sağlayarak etkileşimi artırır.

#### S: PDF belgesinde bağlantı yapı elemanlarının faydası ne olabilir?

A: Bağlantı yapısı öğeleri, PDF belgesini etkileşimli hale getirerek kullanıcı deneyimini geliştirir. Ek bilgilere, ilgili içeriklere, harici web sitelerine veya belge içindeki belirli bölümlere hızlı erişim sağlayarak gezinmeyi iyileştirir ve bilgi almayı kolaylaştırır.

#### S: Aspose.PDF for .NET'te bağlantı yapısı öğelerini kullanarak farklı türde köprü metinleri oluşturabilir miyim?

A: Evet, bağlantı yapısı öğelerini kullanarak çeşitli türde köprü metinleri oluşturabilirsiniz. .NET için Aspose.PDF, düz metin, zengin metin, resimler ve çok satırlı açıklamalarla köprü metinleri oluşturmanıza olanak tanır ve belge içindeki harici içeriklere veya konumlara nasıl bağlantı kuracağınız konusunda çok yönlülük sunar.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinde bağlantı yapısı öğelerini nasıl kurar ve başlatırım?

 A: Bağlantı yapısı öğelerini kullanmak için öncelikle yeni bir PDF belgesi oluşturmanız gerekir.`Document` sınıf. Ardından, etiketli içeriği kullanarak elde edin`TaggedContent`Belgenin özelliği. Buradan, bağlantı yapısı öğelerini oluşturabilir ve özelleştirebilir ve bunları kök yapı öğesine ekleyebilirsiniz.

#### S: Bağlantı yapısı öğelerini kullanarak basit bir metin köprüsü nasıl oluşturabilirim?
 A: Basit bir metin köprüsü oluşturmak için bir`LinkElement` ve ayarını yapmak`Hyperlink` bir mülke`WebHyperlink` Bağlantı kurmak istediğiniz URL ile. Ayrıca bağlantının görüntü metnini kullanarak ayarlayabilirsiniz`SetText` Yöntem.

#### S: Bağlantı yapı elemanlarını kullanarak görsellerle hiperlink oluşturmak mümkün müdür?

 A: Evet, bağlantı yapısı öğelerini kullanarak görsellerle köprüler oluşturabilirsiniz. Bir`LinkElement` ve sonra bir tane ekle`FigureElement` bir resimle birlikte. Bu, resim tabanlı bir köprü metni oluşturmanıza olanak tanır.

#### S: Köprü metni içeren PDF belgemin erişilebilirlik açısından PDF/UA standardıyla uyumlu olduğundan nasıl emin olabilirim?

 A: Aspose.PDF for .NET, PDF belgenizin PDF/UA standardıyla uyumluluğunu doğrulama olanağı sağlar.`Validate` yöntemi`Document`sınıf. Bu, belgenin köprü metinlerinin engelli kullanıcılar tarafından erişilebilir olmasını sağlar.

#### S: Bağlantı yapısı öğeleri için alternatif açıklamalar nelerdir ve neden önemlidirler?

A: Bağlantı yapısı öğeleri için alternatif açıklamalar (alt metin), köprü metinlerinin metinsel açıklamalarını sağlar. Bu açıklamalar erişilebilirlik için önemlidir ve görme engelli kullanıcıların bağlantının amacını ve hedefini anlamalarını sağlar.

#### S: Bağlantı yapı öğelerini kullanarak oluşturulan köprü metinlerinin görünümünü ve davranışını özelleştirebilir miyim?

A: Bağlantı yapısı öğeleri öncelikle köprü metinleri oluşturmaya odaklanırken, Aspose.PDF for .NET tarafından sunulan diğer özellikleri kullanarak köprü metinlerinin görünümünü ve davranışını daha da özelleştirebilirsiniz. Bu, renkleri, stilleri ve bağlantı eylemlerini belirtmeyi içerir.

#### S: Bağlantı yapısı öğeleri PDF belgelerinin daha etkileşimli ve kullanıcı dostu olmasına nasıl katkıda bulunur?

A: Bağlantı yapısı öğeleri, tıklanabilir köprüler ekleyerek statik PDF belgelerini etkileşimli deneyimlere dönüştürür. Bu etkileşim, kullanıcı katılımını iyileştirir, ilgili içerikler arasında sorunsuz gezinmeyi sağlar ve belgenin genel kullanılabilirliğini artırır.