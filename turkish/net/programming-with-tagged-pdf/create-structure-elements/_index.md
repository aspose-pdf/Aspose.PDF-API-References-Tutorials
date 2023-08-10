---
title: Yapı Elemanları Oluştur
linktitle: Yapı Elemanları Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: Bu eğitimde, etiketli bir PDF belgesinde yapısal öğeler oluşturmak için Aspose.PDF for .NET'i nasıl kullanacağınızı öğreneceksiniz.
type: docs
weight: 60
url: /tr/net/programming-with-tagged-pdf/create-structure-elements/
---
Aşağıdaki C# kaynak kodu, yapı elemanları oluşturmak için Aspose.PDF for .NET'i kullanır. Kodun nasıl çalıştığını anlamak için aşağıdaki adımları izleyin.

## 1. Adım: Gerekli kitaplıkları içe aktarın

```csharp
using Aspose.Pdf;
```

## 2. Adım: Belgelerinizin dizinini tanımlayın

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Belgeler dizininizin doğru yolunu belirttiğinizden emin olun.

## 3. Adım: Bir PDF belgesi oluşturun

```csharp
Document document = new Document();
```

PDF belgesini temsil eden yeni bir Belge nesnesi yaratıyoruz.

## 4. Adım: İçeriğin TaggedPdf ile çalışmasını sağlayın

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

PDF belgesinin etiketli içeriğini alıyoruz. Bu, yapısal unsurları manipüle etmemize izin verecektir.

## 5. Adım: Belge başlığını ve dilini ayarlayın

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Etiketli PDF belgesinin başlığını ve dilini belirliyoruz. Bu, belgenin erişilebilirliğini artırır.

## 6. Adım: Gruplandırma öğeleri oluşturun

```csharp
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
```

PDF belgesindeki içeriği gruplandırmak için farklı yapısal öğeler oluşturuyoruz.

## 7. Adım: Paragraf yapısı öğeleri oluşturun

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

Paragraflar ve başlıklar için blok düzeyinde yapısal öğeler oluşturuyoruz. Yukarıdaki örnek, 1. düzey bir başlığın oluşturulmasını göstermektedir.

## 8. Adım: Satır içi düzey yapı öğeleri oluşturun

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

Metnin bir paragraf veya başlık içinde görünen bölümleri için satır içi düzey yapı öğeleri oluşturuyoruz.

## 9. Adım: Resim yapısı öğeleri oluşturun

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

Belgede bulunan çizimler ve matematiksel formüller için yapısal öğeler oluşturuyoruz.

## 10. Adım: Etiketli PDF belgesini kaydedin

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

Etiketli PDF belgesini oluşturulan yapı elemanları ile kaydediyoruz.

### Aspose.PDF for .NET kullanarak Yapı Elemanları Oluşturma için örnek kaynak kodu 

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
// Gruplandırma Öğeleri Oluşturma
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
// Metin Bloğu Düzeyinde Yapı Öğeleri Oluşturma
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// Metin Satır İçi Düzey Yapı Öğeleri Oluşturma
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// Resim Yapı Elemanları Oluşturma
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
// Yöntemler geliştirilme aşamasındadır
ListElement listElement = taggedContent.CreateListElement();
TableElement tableElement = taggedContent.CreateTableElement();
ReferenceElement referenceElement = taggedContent.CreateReferenceElement();
BibEntryElement bibEntryElement = taggedContent.CreateBibEntryElement();
CodeElement codeElement = taggedContent.CreateCodeElement();
LinkElement linkElement = taggedContent.CreateLinkElement();
AnnotElement annotElement = taggedContent.CreateAnnotElement();
RubyElement rubyElement = taggedContent.CreateRubyElement();
WarichuElement warichuElement = taggedContent.CreateWarichuElement();
FormElement formElement = taggedContent.CreateFormElement();
// Etiketli PDF Belgesini Kaydet
document.Save(dataDir + "StructureElements.pdf");

```

## Çözüm

Bu eğitimde, etiketli bir PDF belgesinde yapı elemanları oluşturmak için Aspose.PDF for .NET'i nasıl kullanacağımızı öğrendik. Yapısal öğeler, belge erişilebilirliğini artırmaya ve içeriği anlamlı bir şekilde düzenlemeye yardımcı olur. Artık bu bilgiyi yapılandırılmış, gezinmesi kolay PDF belgeleri oluşturmak için kullanabilirsiniz.

### SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinde yapı elemanları oluşturmanın amacı nedir?

C: Aspose.PDF for .NET kullanarak bir PDF belgesinde yapı öğeleri oluşturmak, belge içeriğinin erişilebilirliğini ve organizasyonunu geliştirir. Yapı öğeleri, gezinmeyi, anlambilimi ve yardımcı teknolojilerle uyumluluğu geliştiren hiyerarşik bir yapı sağlar.

#### S: Sağlanan C# kodu, bir PDF belgesinde yapı öğelerini nasıl oluşturur?

A: Kod örneği, gruplandırma öğeleri (parçalar, bölümler ve div'ler gibi), blok düzeyi öğeler (paragraflar ve başlıklar gibi), satır içi düzey öğeler (açıklık, alıntı, not) dahil olmak üzere çeşitli yapı öğeleri türlerinin nasıl oluşturulacağını gösterir. ) ve çizim öğeleri (şekiller ve formüller gibi). Bu yapı öğeleri, içeriğin düzenlenmesine yardımcı olur.

####  S: kullanarak belgenin başlığını ve dilini ayarlamak neden önemlidir?`SetTitle` and `SetLanguage` methods?

 A: kullanarak belgenin başlığını ve dilini ayarlama`SetTitle` Ve`SetLanguage`yöntemler, belge erişilebilirliğini ve anlamını geliştirir. Başlık, belgenin amacının kısa bir açıklamasını sağlarken, dil özelliği dile özgü işlemeyi ve erişilebilirliği geliştirir.

####  S: gibi öğeleri gruplama nasıl yapılır?`PartElement` and `SectElement`, contribute to the structure of the PDF document?

Y: Gruplandırma öğeleri, PDF belgesi içinde hiyerarşik bir yapı oluşturarak ilgili içeriği mantıksal olarak düzenlemenize ve gruplandırmanıza olanak tanır. Bu, gezinmeyi geliştirir ve kullanıcılar için net bir yapı sağlar.

#### S: Blok düzeyinde ve satır içi düzeyde yapı öğeleri nelerdir ve nasıl farklılık gösterirler?

C: Blok düzeyindeki yapı öğeleri, paragraflar ve başlıklar gibi daha büyük içerik bloklarını temsil ederken, satır içi düzeydeki öğeler, bir paragraf veya başlık içindeki açıklıklar, alıntılar ve notlar gibi metin bölümlerini temsil eder. İçeriğin hiyerarşisini ve ilişkilerini tanımlamaya yardımcı olurlar.

####  S: Sanat eseri yapı öğeleri nasıl`FigureElement` and `FormulaElement`, contribute to the document?

C: Sanat eseri yapı öğeleri, belgeye çizimler, şekiller ve matematiksel formüller eklemenizi sağlar. Görsel ve matematiksel içeriği dahil etmek için yapılandırılmış bir yol sağlarlar.

#### S: Listeler, tablolar veya ek açıklamalar gibi diğer yapı öğesi türlerini oluşturmak için benzer teknikleri kullanabilir miyim?

C: Evet, listeler, tablolar, ek açıklamalar, referanslar ve daha fazlası gibi diğer yapı öğesi türlerini oluşturmak için benzer teknikleri kullanabilirsiniz. Aspose.PDF, çok çeşitli yapı öğesi oluşturma yöntemleri sunar.

####  S: etiketli PDF belgesini kullanarak nasıl kaydedilir?`Save` method ensure the preservation of structure elements?

 C:`Save` yöntem, PDF belgesini oluşturulan yapı öğeleriyle birlikte kaydederek, belgenin hiyerarşik ve anlamsal yapısının erişilebilirlik ve gezinme için korunmasını sağlar.

#### S: Yapı öğeleri, erişilebilirlik ve yardımcı teknolojilerle uyumluluk açısından PDF belgelerine ne gibi faydalar sağlar?

Y: Yapı öğeleri, belgeye anlamlı bir yapı ve anlambilim sağlayarak erişilebilirliği artırır. Bu, ekran okuyucular gibi yardımcı teknolojilerin belge içeriğini engelli kullanıcılara daha etkili bir şekilde yorumlamasını ve iletmesini sağlar.

#### S: PDF belgelerimde farklı türde yapı öğelerini nasıl daha fazla özelleştirip birleştirebilirim?

Y: Aspose.PDF tarafından sağlanan uygun oluşturma yöntemlerini kullanarak yapı öğelerini birleştirebilir ve özelleştirebilirsiniz. İyi yapılandırılmış ve düzenli bir PDF belgesi oluşturmak için farklı öğeler ve özellikleriyle denemeler yapın.