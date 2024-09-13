---
title: Elemana Yapı Elemanı Ekle
linktitle: Elemana Yapı Elemanı Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF belgesine yapı öğesi eklemeye yönelik adım adım kılavuz.
type: docs
weight: 20
url: /tr/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesindeki bir öğeye bir yapı öğesinin nasıl ekleneceği konusunda adım adım bir kılavuz sağlayacağız. Aspose.PDF, PDF belgelerini programatik olarak oluşturmanıza, düzenlemenize ve dönüştürmenize olanak tanıyan güçlü bir kütüphanedir. Aspose.PDF'nin işaretli içerik yapısı özelliklerini kullanarak PDF belgenizde hiyerarşik bir yapı oluşturabilirsiniz.

## Ön koşullar

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

1. .NET framework ile Visual Studio kuruldu.
2. .NET için Aspose.PDF kütüphanesi.

## Adım 1: Proje Kurulumu

Başlamak için, Visual Studio'da yeni bir proje oluşturun ve Aspose.PDF for .NET kütüphanesine bir referans ekleyin. Kütüphaneyi Aspose resmi web sitesinden indirebilir ve makinenize kurabilirsiniz.

## Adım 2: Gerekli ad alanlarını içe aktarın

C# kod dosyanıza, Aspose.PDF tarafından sağlanan sınıflara ve yöntemlere erişmek için gereken ad alanlarını içe aktarın:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Adım 3: PDF belgesini oluşturma ve yapılandırılmış öğeleri tanımlama

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

Bu kod boş bir PDF belgesi oluşturur ve paragraflar ve aralıklar gibi yapılandırılmış öğeler ekler. Her yapı öğesi Aspose.PDF tarafından sağlanan yöntemler kullanılarak oluşturulur.

## Adım 4: PDF Belgesini Kaydetme

PDF belgesini kaydetmek için aşağıdaki kodu kullanın:

```csharp
document. Save(outFile);
```

Bu kod, yapılandırılmış öğeler içeren PDF belgesini belirtilen bir dosyaya kaydeder.

### .NET için Aspose.PDF kullanarak Elemana Yapı Elemanı Ekleme için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
//Belge oluşturma ve Etiketli Pdf İçeriği alma
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// Belge için Başlık ve Doğa Dilinin Ayarlanması
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// Kök yapı elemanını alma (Belge yapı elemanı)
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
// PDF/UA uyumluluğunun kontrol edilmesi
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesindeki bir öğeye bir yapı öğesinin nasıl ekleneceğini öğrendiniz. Aspose.PDF'nin işaretli içerik yapısı özelliklerini kullanarak, PDF belgenizde hiyerarşik bir yapı oluşturabilir, bu da içeriği yönetmeyi ve gezinmeyi kolaylaştırır.

### SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesindeki bir öğeye yapı öğesi eklemenin amacı nedir?

A: Aspose.PDF for .NET kullanarak bir PDF belgesindeki bir öğeye bir yapı öğesi eklemek, belgenin içeriğinde hiyerarşik bir yapı oluşturmanıza olanak tanır. Bu hiyerarşik yapı, içeriğin organizasyonunu ve gezinmesini geliştirerek belirli öğeleri yönetmeyi ve erişmeyi kolaylaştırır.

#### S: Aspose.PDF kütüphanesi bir PDF belgesine yapı öğeleri eklemeye nasıl yardımcı olur?

A: Aspose.PDF for .NET, PDF belgelerini programatik olarak oluşturma, düzenleme ve dönüştürme yetenekleri sağlayan güçlü bir kütüphanedir. Bu eğitimde, kütüphanenin işaretli içerik yapısı özellikleri, PDF belgesinin içeriğine yapı öğeleri oluşturmak ve eklemek için kullanılır.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesine yapı öğeleri eklemenin ön koşulları nelerdir?

C: Başlamadan önce, Visual Studio'nun .NET Framework ile birlikte yüklü olduğundan ve projenizde .NET için Aspose.PDF kütüphanesine başvurulduğundan emin olun.

#### S: Sağlanan C# kodu PDF belgesinin içeriğine yapı öğelerini nasıl oluşturur ve ekler?

A: Kod, bir PDF belgesinin nasıl oluşturulacağını, bir kök yapı öğesinin nasıl tanımlanacağını ve paragraflar ve açıklıklar gibi çeşitli yapılandırılmış öğelerin nasıl ekleneceğini gösterir. Her yapılandırılmış öğe, Aspose.PDF tarafından sağlanan yöntemler kullanılarak oluşturulur ve hiyerarşik bir yapı oluşturmanıza olanak tanır.

#### S: PDF belgesine eklediğim yapı elemanlarının türlerini özelleştirebilir miyim?

C: Evet, Aspose.PDF kütüphanesi tarafından sağlanan farklı yöntemleri keşfederek yapı öğelerinin türlerini özelleştirebilirsiniz. Kod, örnek olarak paragrafları ve aralıkları gösterir, ancak ihtiyaç duyduğunuzda diğer türde yapılandırılmış öğeler oluşturabilir ve ekleyebilirsiniz.

#### S: Eklenen yapı elemanları arasındaki hiyerarşik ilişkiyi nasıl tanımlarım?

 A: Yapı elemanları arasındaki hiyerarşik ilişki, bunları üst elemanlarına eklediğiniz sıraya göre tanımlanır. Kodda, üst-alt ilişkileri,`AppendChild` Yöntem.

#### S: PDF belgesinde hiyerarşik bir yapı oluşturmanın faydaları nelerdir?

A: PDF belgesinde hiyerarşik bir yapı oluşturmak erişilebilirliğini, gezinmesini ve organizasyonunu geliştirir. Yardımcı teknolojilerin belgenin içeriğini daha iyi yorumlamasına ve iletmesine olanak tanır ve engelli bireyler için daha kullanıcı dostu hale getirir.

#### S: Yapı elemanlarını ekledikten sonra PDF/UA uyumluluğunu nasıl doğrulayabilirim?

A: Eğitimde sağlanan kod, PDF/UA uyumluluğunun nasıl doğrulanacağını göstermektedir.`Validate` yöntem. Belgeyi PDF/UA standardına göre doğrulayarak, eklenen yapı öğelerinin erişilebilirlik yönergelerine uygun olduğundan emin olabilirsiniz.

#### S: Bu yaklaşımı mevcut bir PDF belgesine yapı öğeleri eklemek için kullanabilir miyim?

A: Evet, mevcut bir PDF belgesine yapı öğeleri eklemek için sağlanan yaklaşımı değiştirebilirsiniz. Yeni bir belge oluşturmak yerine, Aspose.PDF kullanarak mevcut belgeyi yükler ve ardından yapı öğelerini eklemek için benzer adımları izlersiniz.