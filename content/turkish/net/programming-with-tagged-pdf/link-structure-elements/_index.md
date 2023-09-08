---
title: Bağlantı Yapısı Elemanları
linktitle: Bağlantı Yapısı Elemanları
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile bağlantı yapısı öğelerini kullanma konusunda adım adım kılavuz. PDF belgelerinizde köprüler oluşturun.
type: docs
weight: 120
url: /tr/net/programming-with-tagged-pdf/link-structure-elements/
---
Bu adım adım kılavuzda, bağlantı yapısı öğelerini Aspose.PDF for .NET ile nasıl kullanacağınızı göstereceğiz. Aspose.PDF, PDF belgelerini programlı olarak oluşturmanıza ve değiştirmenize olanak tanıyan güçlü bir kütüphanedir. Bağlantı yapısı öğeleri, PDF belgenize köprüler eklemenizi sağlayarak kullanıcıların bağlantılara tıklamasına ve çevrimiçi kaynaklara gitmesine olanak tanır.

Haydi kodun derinliklerine inelim ve Aspose.PDF for .NET ile bağlantı yapısı öğelerinin nasıl kullanılacağını öğrenelim.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. .NET için Aspose.PDF kütüphanesi kuruldu.
2. C# programlama dili hakkında temel bilgi.

## 1. Adım: Ortamı ayarlama

Başlamak için C# geliştirme ortamınızı açın ve yeni bir proje oluşturun. Projenize .NET için Aspose.PDF kütüphanesine bir referans eklediğinizden emin olun.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
```

## Adım 2: Belgeyi oluşturma

 İlk adım, kullanarak yeni bir PDF belgesi oluşturmaktır.`Document` sınıf.

```csharp
// PDF belgesini oluşturun
Document document = new Document();
```

## 3. Adım: Etiketli içerikle çalışın

Daha sonra üzerinde çalışacağımız belgenin etiketli içeriğini alıyoruz.

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

## 5. Adım: Bağlantı yapısı öğelerini ekleyin

Şimdi belgemize link yapısı elemanlarını ekleyelim. Basit metin bağlantıları, resim bağlantıları ve çok satırlı bağlantılar dahil olmak üzere farklı türde bağlantılar oluşturacağız.
```csharp
// Kök yapı öğesini alın (belge yapısı öğesi)
StructureElement rootElement = taggedContent.RootElement;

// Köprü içeren bir paragraf ekleme
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Zengin metin içeren köprü içeren bir paragraf ekleme
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Kısmen biçimlendirilmiş metin içeren köprü içeren bir paragraf ekleme
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

// Çok satırlı köprü içeren bir paragraf ekleme
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// Resim içeren köprü içeren bir paragraf ekleme
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

Son olarak etiketlenen PDF belgesini kaydediyoruz.

```csharp
// Etiketli PDF belgesini kaydedin
document. Save(outFile);
```

## 7. Adım: PDF/UA uyumluluğunu kontrol edin

 Ayrıca belgeyi kullanarak PDF/UA uyumluluğunu da kontrol edebiliriz.`Validate` yöntemi`Document` sınıf.

```csharp
// PDF/UA uyumluluğunu kontrol edin
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### Aspose.PDF for .NET kullanan Bağlantı Yapısı Elemanları için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Belge oluşturma ve Etiketli Pdf İçeriği alma
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Belgenin Başlığını ve Doğa Dilini Ayarlama
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Kök yapı öğesini alma (Belge yapısı öğesi)
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

// Etiketli Pdf Belgesini Kaydet
document.Save(outFile);

// PDF/UA uyumluluğunu kontrol etme
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Çözüm

Tebrikler! Aspose.PDF for .NET ile bağlantı yapısı öğelerini nasıl kullanacağınızı öğrendiniz. Artık PDF belgelerinizde kullanıcıların çevrimiçi kaynaklara gitmesine olanak tanıyan köprüler oluşturabilirsiniz. Etkileşimli ve zenginleştirilmiş PDF belgeleri oluşturmak için Aspose.PDF'in daha fazla özelliğini deneyin ve keşfedin.

### SSS'ler

#### S: Bir PDF belgesindeki bağlantı yapısı öğeleri nelerdir ve belge etkileşimini nasıl geliştirirler?

C: Bir PDF belgesindeki bağlantı yapısı öğeleri, kullanıcıların çevrimiçi kaynaklara veya belge içindeki belirli konumlara gitmesine olanak tanıyan köprüler oluşturmak için kullanılır. Bu öğeler, kullanıcıların ilgili içeriğe veya harici web sitelerine erişmesine olanak tanıyan tıklanabilir bağlantılar sağlayarak etkileşimi artırır.

#### S: Bağlantı yapısı öğeleri bir PDF belgesinde nasıl faydalı olabilir?

C: Bağlantı yapısı öğeleri, PDF belgesini etkileşimli hale getirerek kullanıcı deneyimini geliştirir. Ek bilgilere, ilgili içeriğe, harici web sitelerine veya belge içindeki belirli bölümlere hızlı erişim sağlayarak gezinmeyi geliştirir ve bilgi almayı kolaylaştırır.

#### S: Aspose.PDF for .NET'teki bağlantı yapısı öğelerini kullanarak farklı türde köprüler oluşturabilir miyim?

C: Evet, bağlantı yapısı öğelerini kullanarak çeşitli türlerde köprüler oluşturabilirsiniz. Aspose.PDF for .NET, düz metin, zengin metin, resimler ve çok satırlı açıklamalarla köprüler oluşturmanıza olanak tanıyarak, belge içindeki harici içeriğe veya konumlara bağlantı verme şeklinizde çok yönlülük sunar.

#### S: Aspose.PDF for .NET'i kullanarak bir PDF belgesindeki bağlantı yapısı öğelerini nasıl kurabilirim ve başlatabilirim?

 C: Bağlantı yapısı öğelerini kullanmak için öncelikle aşağıdakileri kullanarak yeni bir PDF belgesi oluşturmanız gerekir:`Document` sınıf. Daha sonra, etiketli içeriği aşağıdakileri kullanarak edinin:`TaggedContent`belgenin özelliği. Buradan bağlantı yapısı öğelerini oluşturup özelleştirebilir ve bunları kök yapı öğesine ekleyebilirsiniz.

#### S: Bağlantı yapısı öğelerini kullanarak nasıl basit bir metin köprüsü oluşturabilirim?
 C: Basit bir metin köprüsü oluşturarak basit bir metin köprüsü oluşturabilirsiniz.`LinkElement` ve onun ayarlanması`Hyperlink` bir mülk`WebHyperlink` Bağlanmak istediğiniz URL ile. Ayrıca bağlantının görüntü metnini aşağıdaki düğmeyi kullanarak da ayarlayabilirsiniz:`SetText` yöntem.

#### S: Bağlantı yapısı öğelerini kullanarak resimlerle köprüler oluşturmak mümkün müdür?

 C: Evet, bağlantı yapısı öğelerini kullanarak resimlerle köprüler oluşturabilirsiniz. Bir tane yaratırdın`LinkElement` ve ardından bir tane ekleyin`FigureElement` bir görüntüyle birlikte. Bu, görüntü tabanlı bir köprü oluşturmanıza olanak tanır.

#### S: Köprü içeren PDF belgemin erişilebilirlik açısından PDF/UA standardıyla uyumlu olduğundan nasıl emin olabilirim?

 C: Aspose.PDF for .NET, PDF belgenizin PDF/UA standardına uygunluğunu aşağıdakileri kullanarak doğrulama olanağı sağlar:`Validate` yöntemi`Document`sınıf. Bu, belgedeki köprülerin engelli kullanıcılar tarafından erişilebilir olmasını sağlar.

#### S: Bağlantı yapısı öğeleri için alternatif açıklamalar nelerdir ve bunlar neden önemlidir?

C: Bağlantı yapısı öğelerine ilişkin alternatif açıklamalar (alternatif metin), köprülerin metinsel açıklamalarını sağlar. Bu açıklamalar erişilebilirlik açısından önemlidir ve görme bozukluğu olan kullanıcıların bağlantının amacını ve hedefini anlamalarına olanak tanır.

#### S: Bağlantı yapısı öğeleri kullanılarak oluşturulan köprülerin görünümünü ve davranışını özelleştirebilir miyim?

C: Bağlantı yapısı öğeleri öncelikle köprü oluşturmaya odaklanırken, Aspose.PDF for .NET tarafından sunulan diğer özellikleri kullanarak köprülerin görünümünü ve davranışını daha da özelleştirebilirsiniz. Bu, renkleri, stilleri ve bağlantı eylemlerini belirtmeyi içerir.

#### S: Bağlantı yapısı öğeleri, PDF belgelerinin daha etkileşimli ve kullanıcı dostu olmasına nasıl katkıda bulunur?

C: Bağlantı yapısı öğeleri, tıklanabilir köprüler ekleyerek statik PDF belgelerini etkileşimli deneyimlere dönüştürür. Bu etkileşim, kullanıcı katılımını artırır, ilgili içerik arasında kesintisiz gezinmeyi sağlar ve belgenin genel kullanılabilirliğini artırır.