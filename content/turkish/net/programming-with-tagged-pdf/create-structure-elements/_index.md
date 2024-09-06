---
title: Yapı Elemanları Oluştur
linktitle: Yapı Elemanları Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: Bu eğitimde, etiketli bir PDF belgesinde yapısal öğeler oluşturmak için Aspose.PDF for .NET'in nasıl kullanılacağını öğreneceksiniz.
type: docs
weight: 60
url: /tr/net/programming-with-tagged-pdf/create-structure-elements/
---
Aşağıdaki C# kaynak kodu, yapı öğeleri oluşturmak için Aspose.PDF for .NET'i kullanır. Kodun nasıl çalıştığını anlamak için aşağıdaki adımları izleyin.

## Adım 1: Gerekli kütüphaneleri içe aktarın

```csharp
using Aspose.Pdf;
```

## Adım 2: Belgelerinizin dizinini tanımlayın

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Belgelerinizin bulunduğu dizine doğru yolu belirttiğinizden emin olun.

## Adım 3: Bir PDF belgesi oluşturun

```csharp
Document document = new Document();
```

PDF belgesini temsil eden yeni bir Belge nesnesi oluşturuyoruz.

## Adım 4: İçeriğin TaggedPdf ile çalışmasını sağlayın

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

PDF belgesinin etiketli içeriğini alıyoruz. Bu, yapısal öğeleri düzenlememize olanak tanıyacak.

## Adım 5: Belge başlığını ve dilini ayarlayın

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Etiketli PDF belgesinin başlığını ve dilini ayarlıyoruz. Bu, belgenin erişilebilirliğini artırır.

## Adım 6: Gruplama öğelerini oluşturun

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

PDF dokümanındaki içerikleri gruplandırmak için farklı yapısal öğeler oluşturuyoruz.

## Adım 7: Paragraf yapı öğelerini oluşturun

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

Paragraflar ve başlıklar için blok düzeyinde yapısal öğeler oluşturuyoruz. Yukarıdaki örnek, 1. düzey bir başlığın oluşturulmasını göstermektedir.

## Adım 8: Satır içi düzeyde yapı öğeleri oluşturun

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

Bir paragrafın veya başlığın içinde görünen metin bölümleri için satır içi düzeyde yapı öğeleri oluşturuyoruz.

## Adım 9: Sanat eserinin yapı elemanlarını oluşturun

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

Belgede yer alan görseller ve matematiksel formüller için yapısal elemanlar oluşturuyoruz.

## Adım 10: Etiketli PDF belgesini kaydedin

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

Oluşturulan yapı elemanları ile etiketli PDF dokümanını kaydediyoruz.

### .NET için Aspose.PDF kullanarak Yapı Elemanları Oluşturma için örnek kaynak kodu 

```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PDF Belgesi Oluştur
Document document = new Document();
// TaggedPdf ile çalışmak için İçerik Alın
ITaggedContent taggedContent = document.TaggedContent;
// Belge için Başlık ve Dil Ayarla
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// Gruplama Öğeleri Oluştur
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
// Metin Bloğu Düzeyinde Yapı Elemanları Oluşturun
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// Metin Satır İçi Düzey Yapı Elemanları Oluştur
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// İllüstrasyon Yapı Elemanları Oluştur
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

Bu eğitimde, etiketli bir PDF belgesinde yapı öğeleri oluşturmak için Aspose.PDF for .NET'i nasıl kullanacağımızı öğrendik. Yapısal öğeler, belge erişilebilirliğini iyileştirmeye ve içeriği anlamlı bir şekilde düzenlemeye yardımcı olur. Artık bu bilgiyi yapılandırılmış, gezinmesi kolay PDF belgeleri oluşturmak için kullanabilirsiniz.

### SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinde yapı elemanları oluşturmanın amacı nedir?

A: Aspose.PDF for .NET kullanarak bir PDF belgesinde yapı öğeleri oluşturmak, belgenin içeriğinin erişilebilirliğini ve organizasyonunu artırır. Yapı öğeleri, gezinmeyi, semantiği ve yardımcı teknolojilerle uyumluluğu iyileştiren hiyerarşik bir yapı sağlar.

#### S: Sağlanan C# kodu bir PDF belgesinde yapı elemanlarını nasıl oluşturur?

A: Kod örneği, gruplama öğeleri (parçalar, bölümler ve div'ler gibi), blok düzeyindeki öğeler (paragraflar ve başlıklar gibi), satır içi düzeydeki öğeler (span, quote, note) ve sanat eseri öğeleri (şekiller ve formüller gibi) dahil olmak üzere çeşitli yapı öğesi türlerinin nasıl oluşturulacağını gösterir. Bu yapı öğeleri içeriğin düzenlenmesine yardımcı olur.

####  S: Belgenin başlığını ve dilini kullanarak ayarlamak neden önemlidir?`SetTitle` and `SetLanguage` methods?

 A: Belgenin başlığını ve dilini ayarlamak`SetTitle` Ve`SetLanguage`yöntemler belge erişilebilirliğini ve semantiğini geliştirir. Başlık, belgenin amacının kısa bir açıklamasını sağlarken, dil niteliği dil özgül işlemeyi ve erişilebilirliği geliştirir.

####  S: Öğeleri gruplandırmak nasıl yapılır?`PartElement` and `SectElement`, contribute to the structure of the PDF document?

A: Gruplama öğeleri, PDF belgesi içinde hiyerarşik bir yapı oluşturarak ilgili içerikleri mantıksal olarak düzenlemenize ve gruplamanıza olanak tanır. Bu, gezinmeyi geliştirir ve kullanıcılar için net bir yapı sağlar.

#### S: Blok düzeyinde ve satır içi düzeyde yapı öğeleri nelerdir ve bunlar arasındaki farklar nelerdir?

A: Blok düzeyindeki yapı öğeleri, paragraflar ve başlıklar gibi daha büyük içerik bloklarını temsil ederken, satır içi düzeydeki öğeler, açıklıklar, alıntılar ve notlar gibi bir paragraf veya başlık içindeki metin bölümlerini temsil eder. İçeriğin hiyerarşisini ve ilişkilerini tanımlamaya yardımcı olurlar.

####  S: Sanat eseri öğeleri nasıl yapılandırılır?`FigureElement` and `FormulaElement`, contribute to the document?

A: Sanat eseri yapı öğeleri, belgeye çizimler, şekiller ve matematiksel formüller eklemenize olanak tanır. Görsel ve matematiksel içerik eklemenin yapılandırılmış bir yolunu sağlarlar.

#### S: Listeler, tablolar veya açıklamalar gibi diğer yapı öğelerini oluşturmak için benzer teknikleri kullanabilir miyim?

A: Evet, listeler, tablolar, açıklamalar, referanslar ve daha fazlası gibi diğer yapı öğesi türlerini oluşturmak için benzer teknikleri kullanabilirsiniz. Aspose.PDF, çok çeşitli yapı öğesi oluşturma yöntemleri sunar.

####  S: Etiketli PDF belgesini kullanarak kaydetmek nasıl olur?`Save` method ensure the preservation of structure elements?

 A:`Save` yöntemi, oluşturulan yapı öğeleriyle birlikte PDF belgesini kaydeder ve erişilebilirlik ve gezinme için belgenin hiyerarşik ve anlamsal yapısının korunmasını sağlar.

#### S: Yapı öğeleri, erişilebilirlik ve yardımcı teknolojilerle uyumluluk açısından PDF belgelerine ne gibi avantajlar sağlar?

A: Yapı öğeleri, belgeye anlamlı bir yapı ve anlamsallık sağlayarak erişilebilirliği artırır. Bu, ekran okuyucular gibi yardımcı teknolojilerin belgenin içeriğini engelli kullanıcılara daha etkili bir şekilde yorumlamasına ve iletmesine olanak tanır.

#### S: PDF belgelerimde farklı yapı elemanlarını nasıl daha fazla özelleştirebilir ve birleştirebilirim?

A: Aspose.PDF tarafından sağlanan uygun oluşturma yöntemlerini kullanarak yapı öğelerini birleştirebilir ve özelleştirebilirsiniz. İyi yapılandırılmış ve organize edilmiş bir PDF belgesi oluşturmak için farklı öğeler ve özellikleriyle denemeler yapın.