---
title: Elemana Yapı Elemanı Ekleme
linktitle: Elemana Yapı Elemanı Ekleme
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF belgesindeki öğeye yapı öğesi eklemek için adım adım kılavuz.
type: docs
weight: 20
url: /tr/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
Bu eğitimde size Aspose.PDF for .NET kullanarak bir PDF belgesindeki bir öğeye yapı öğesinin nasıl ekleneceği konusunda adım adım bir kılavuz sunacağız. Aspose.PDF, PDF belgelerini programlı olarak oluşturmanıza, değiştirmenize ve dönüştürmenize olanak tanıyan güçlü bir kütüphanedir. Aspose.PDF'in işaretlenmiş içerik yapısı özelliklerini kullanarak PDF belgenizde hiyerarşik bir yapı oluşturabilirsiniz.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1. .NET framework ile yüklenen Visual Studio.
2. .NET için Aspose.PDF kütüphanesi.

## Adım 1: Proje Kurulumu

Başlamak için Visual Studio'da yeni bir proje oluşturun ve Aspose.PDF for .NET kitaplığına bir referans ekleyin. Kütüphaneyi Aspose resmi web sitesinden indirebilir ve makinenize kurabilirsiniz.

## 2. Adım: Gerekli ad alanlarını içe aktarın

Aspose.PDF tarafından sağlanan sınıflara ve yöntemlere erişmek için gereken ad alanlarını C# kod dosyanıza aktarın:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Adım 3: PDF belgesinin oluşturulması ve yapılandırılmış öğelerin tanımlanması

PDF belgesi oluşturmak ve yapılandırılmış öğeleri tanımlamak için aşağıdaki kodu kullanın:

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

Bu kod boş bir PDF belgesi oluşturur ve paragraflar ve açıklıklar gibi yapılandırılmış öğeler ekler. Her yapı elemanı Aspose.PDF tarafından sağlanan yöntemler kullanılarak oluşturulur.

## Adım 4: PDF Belgesini Kaydetme

PDF belgesini kaydetmek için aşağıdaki kodu kullanın:

```csharp
document. Save(outFile);
```

Bu kod, yapılandırılmış öğeleri içeren PDF belgesini belirtilen bir dosyaya kaydeder.

### Aspose.PDF for .NET kullanarak Yapı Elemanını Elemana Eklemek için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// Belge oluşturma ve Etiketli Pdf İçeriği alma
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// Belgenin Başlığını ve Doğa Dilini Ayarlama
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// Kök yapı öğesini alma (Belge yapısı öğesi)
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
// Etiketli Pdf Belgesini Kaydet
document.Save(outFile);
// PDF/UA uyumluluğunu kontrol etme
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF belgesindeki bir öğeye nasıl yapı öğesi ekleyeceğinizi öğrendiniz. Aspose.PDF'in işaretlenmiş içerik yapısı özelliklerini kullanarak PDF belgenizde hiyerarşik bir yapı oluşturabilirsiniz, bu da içeriği yönetmenizi ve içeriğin içinde gezinmenizi kolaylaştırır.

### SSS'ler

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesindeki bir öğeye yapı öğesi eklemenin amacı nedir?

C: Aspose.PDF for .NET kullanarak bir PDF belgesindeki bir öğeye yapı öğesi eklemek, belgenin içeriğinde hiyerarşik bir yapı oluşturmanıza olanak tanır. Bu hiyerarşik yapı, içeriğin organizasyonunu ve gezinmesini geliştirerek belirli öğelerin yönetilmesini ve bunlara erişilmesini kolaylaştırır.

#### S: Aspose.PDF kütüphanesi bir PDF belgesine yapı elemanları eklemeye nasıl yardımcı olur?

C: Aspose.PDF for .NET, PDF belgelerini programlı olarak oluşturma, değiştirme ve dönüştürme yetenekleri sağlayan güçlü bir kitaplıktır. Bu öğreticide, yapı öğelerini oluşturmak ve PDF belgesinin içeriğine eklemek için kitaplığın işaretli içerik yapısı özelliklerinden yararlanılır.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesine yapı elemanları eklemenin önkoşulları nelerdir?

C: Başlamadan önce, Visual Studio'nun .NET framework ile kurulu olduğundan ve projenizde .NET için Aspose.PDF kütüphanesinin referans alındığından emin olun.

#### S: Sağlanan C# kodu yapı öğelerini nasıl oluşturur ve PDF belgesinin içeriğine ekler?

C: Kod, bir PDF belgesinin nasıl oluşturulacağını, bir kök yapı öğesinin nasıl tanımlanacağını ve buna paragraflar ve açıklıklar gibi çeşitli yapılandırılmış öğelerin nasıl ekleneceğini gösterir. Her yapılandırılmış öğe, Aspose.PDF tarafından sağlanan yöntemler kullanılarak oluşturulur ve hiyerarşik bir yapı oluşturmanıza olanak tanır.

#### S: PDF belgesine eklediğim yapı öğelerinin türlerini özelleştirebilir miyim?

C: Evet, Aspose.PDF kütüphanesinin sağladığı farklı yöntemleri keşfederek yapı elemanlarının türlerini özelleştirebilirsiniz. Kod, örnek olarak paragrafları ve kapsamları gösterir, ancak gerektiğinde başka türde yapılandırılmış öğeler oluşturabilir ve ekleyebilirsiniz.

#### S: Eklenen yapı öğeleri arasındaki hiyerarşik ilişkiyi nasıl tanımlarım?

 C: Yapı öğeleri arasındaki hiyerarşik ilişki, onları üst öğelerine ekleme sıranıza göre tanımlanır. Kodda ebeveyn-çocuk ilişkileri şu şekilde kurulur:`AppendChild` yöntem.

#### S: PDF belgesinde hiyerarşik bir yapı oluşturmanın faydaları nelerdir?

C: Bir PDF belgesinde hiyerarşik bir yapı oluşturmak, belgenin erişilebilirliğini, gezinmesini ve organizasyonunu geliştirir. Yardımcı teknolojilerin belgenin içeriğini daha iyi yorumlayıp iletmesine olanak tanıyarak belgeyi engelli bireyler için daha kullanıcı dostu hale getirir.

#### S: Yapı öğelerini ekledikten sonra PDF/UA uyumluluğunu nasıl doğrulayabilirim?

 C: Eğitimde sağlanan kod, PDF/UA uyumluluğunun nasıl doğrulanacağını gösterir.`Validate` yöntem. Belgeyi PDF/UA standardına göre doğrulayarak eklenen yapı öğelerinin erişilebilirlik yönergelerine uygun olduğundan emin olabilirsiniz.

#### S: Bu yaklaşımı mevcut bir PDF belgesine yapı öğeleri eklemek için kullanabilir miyim?

C: Evet, mevcut bir PDF belgesine yapı öğeleri eklemek için sağlanan yaklaşımı değiştirebilirsiniz. Yeni bir belge oluşturmak yerine mevcut belgeyi Aspose.PDF kullanarak yükleyebilir ve ardından yapı elemanlarını eklemek için benzer adımları takip edebilirsiniz.