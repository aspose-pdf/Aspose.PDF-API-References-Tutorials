---
title: Elemana Yapı Elemanı Ekleme
linktitle: Elemana Yapı Elemanı Ekleme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF belgesindeki öğeye yapı öğesi eklemek için adım adım kılavuz.
type: docs
weight: 20
url: /tr/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesindeki bir öğeye nasıl yapı öğesi ekleyeceğiniz konusunda adım adım bir kılavuz sağlayacağız. Aspose.PDF, PDF belgelerini program aracılığıyla oluşturmanıza, değiştirmenize ve dönüştürmenize izin veren güçlü bir kitaplıktır. Aspose.PDF'in işaretli içerik yapısı özelliklerini kullanarak, PDF belgenizde hiyerarşik bir yapı oluşturabilirsiniz.

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

## 3. Adım: PDF belgesini oluşturma ve yapılandırılmış öğeleri tanımlama

Bir PDF belgesi oluşturmak ve yapılandırılmış öğeleri tanımlamak için aşağıdaki kodu kullanın:

```csharp

string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Text Items");
taggedContent.SetLanguage("fr-FR");

StructureElement rootElement = taggedContent.RootElement;

ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);

ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);

ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");

ParagraphElement p4 = taggedContent.CreateParagraphElement();
root

Element.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
```

Bu kod, boş bir PDF belgesi oluşturur ve paragraflar ve açıklıklar gibi yapılandırılmış öğeler ekler. Her bir yapı elemanı, Aspose.PDF tarafından sağlanan yöntemler kullanılarak oluşturulur.

## 4. Adım: PDF Belgesini Kaydetme

PDF belgesini kaydetmek için aşağıdaki kodu kullanın:

```csharp
document. Save(outFile);
```

Bu kod, yapılandırılmış öğelerle birlikte PDF belgesini belirtilen bir dosyaya kaydeder.

### Aspose.PDF for .NET kullanarak Add Structure Element Into Element için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// Oluşturma belgesi ve Etiketli Pdf İçeriği alma
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// Belge için Başlık ve Doğa Dilini Ayarlama
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// Kök yapı öğesini alma (Belge yapı öğesi)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
// Etiketli PDF Belgesini Kaydet
document.Save(outFile);
// PDF/UA uyumluluğunu kontrol etme
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesindeki bir öğeye bir yapı öğesi eklemeyi öğrendiniz. Aspose.PDF'nin işaretli içerik yapısı özelliklerini kullanarak, PDF belgenizde hiyerarşik bir yapı oluşturabilirsiniz, bu da içeriği yönetmeyi ve içerikte gezinmeyi kolaylaştırır.

### SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesindeki bir öğeye yapı öğesi eklemenin amacı nedir?

C: Aspose.PDF for .NET kullanarak bir PDF belgesindeki bir öğeye bir yapı öğesi eklemek, belgenin içeriğinde hiyerarşik bir yapı oluşturmanıza olanak tanır. Bu hiyerarşik yapı, içeriğin organizasyonunu ve gezinmesini geliştirerek belirli öğelere erişimi ve yönetimi kolaylaştırır.

#### S: Aspose.PDF kitaplığı, bir PDF belgesine yapı öğeleri eklenmesine nasıl yardımcı olur?

Y: Aspose.PDF for .NET, PDF belgelerini program aracılığıyla oluşturma, işleme ve dönüştürme yetenekleri sağlayan güçlü bir kitaplıktır. Bu öğreticide, kitaplığın işaretli içerik yapısı özellikleri, yapı öğeleri oluşturmak ve PDF belgesinin içeriğine eklemek için kullanılır.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesine yapı elemanları eklemek için ön koşullar nelerdir?

C: Başlamadan önce, Visual Studio'nun .NET çerçevesiyle kurulu olduğundan ve projenizde Aspose.PDF for .NET kitaplığına referans verildiğinden emin olun.

#### S: Sağlanan C# kodu, yapı öğelerini nasıl oluşturur ve PDF belgesinin içeriğine ekler?

Y: Kod, bir PDF belgesinin nasıl oluşturulacağını, bir kök yapı öğesinin nasıl tanımlanacağını ve buna paragraflar ve aralıklar gibi çeşitli yapısal öğelerin nasıl ekleneceğini gösterir. Her yapılandırılmış öğe, Aspose.PDF tarafından sağlanan ve hiyerarşik bir yapı oluşturmanıza olanak sağlayan yöntemler kullanılarak oluşturulur.

#### S: PDF belgesine eklediğim yapı öğesi türlerini özelleştirebilir miyim?

C: Evet, Aspose.PDF kitaplığı tarafından sağlanan farklı yöntemleri keşfederek yapı öğelerinin türlerini özelleştirebilirsiniz. Kod, paragrafları ve açıklıkları örnek olarak gösterir, ancak gerektiğinde başka türde yapılandırılmış öğeler oluşturabilir ve ekleyebilirsiniz.

#### S: Eklenen yapı elemanları arasındaki hiyerarşik ilişkiyi nasıl tanımlarım?

 Y: Yapı öğeleri arasındaki hiyerarşik ilişki, onları üst öğelerine eklediğiniz sırayla tanımlanır. Kodda, ebeveyn-çocuk ilişkileri kullanılarak kurulur.`AppendChild` yöntem.

#### S: Bir PDF belgesinde hiyerarşik bir yapı oluşturmanın faydaları nelerdir?

Y: Bir PDF belgesinde hiyerarşik bir yapı oluşturmak, belgenin erişilebilirliğini, gezinmesini ve düzenini geliştirir. Yardımcı teknolojilerin belge içeriğini daha iyi yorumlamasını ve iletmesini sağlayarak belgeyi engelli bireyler için daha kullanıcı dostu hale getirir.

#### S: Yapı öğeleri ekledikten sonra PDF/UA uyumluluğunu nasıl doğrulayabilirim?

 Y: Öğreticide sağlanan kod, PDF/UA uyumluluğunun nasıl doğrulanacağını gösterir.`Validate` yöntem. Belgeyi PDF/UA standardına göre doğrulayarak, eklenen yapı öğelerinin erişilebilirlik yönergelerine uygun olmasını sağlayabilirsiniz.

#### S: Mevcut bir PDF belgesine yapı öğeleri eklemek için bu yaklaşımı kullanabilir miyim?

C: Evet, mevcut bir PDF belgesine yapı öğeleri eklemek için sağlanan yaklaşımı değiştirebilirsiniz. Yeni bir belge oluşturmak yerine, mevcut belgeyi Aspose.PDF kullanarak yükler ve ardından yapı elemanlarını eklemek için benzer adımları izlersiniz.