---
title: Yapı Elemanları Oluşturun
linktitle: Yapı Elemanları Oluşturun
second_title: .NET API Referansı için Aspose.PDF
description: Bu eğitimde, etiketli bir PDF belgesinde yapısal öğeler oluşturmak için Aspose.PDF for .NET'i nasıl kullanacağınızı öğreneceksiniz.
type: docs
weight: 60
url: /tr/net/programming-with-tagged-pdf/create-structure-elements/
---
Aşağıdaki C# kaynak kodu, yapı elemanları oluşturmak için Aspose.PDF for .NET'i kullanıyor. Kodun nasıl çalıştığını anlamak için aşağıdaki adımları izleyin.

## 1. Adım: Gerekli kitaplıkları içe aktarın

```csharp
using Aspose.Pdf;
```

## Adım 2: Belgelerinizin dizinini tanımlayın

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Belgeler dizininizin doğru yolunu belirttiğinizden emin olun.

## 3. Adım: Bir PDF belgesi oluşturun

```csharp
Document document = new Document();
```

PDF belgesini temsil eden yeni bir Belge nesnesi oluşturuyoruz.

## 4. Adım: TaggedPdf ile çalışacak içeriği edinin

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

PDF belgesinin etiketli içeriğini alıyoruz. Bu, yapısal elemanları manipüle etmemizi sağlayacaktır.

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

PDF belgesindeki içeriği gruplamak için farklı yapısal öğeler oluşturuyoruz.

## 7. Adım: Paragraf yapısı öğeleri oluşturun

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

Paragraflar ve başlıklar için blok düzeyinde yapısal öğeler oluşturuyoruz. Yukarıdaki örnekte 1. düzey başlığın oluşturulması gösterilmektedir.

## Adım 8: Satır içi düzey yapı öğeleri oluşturun

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

Bir paragrafın veya başlığın içinde görünen metin bölümleri için satır içi düzeyde yapı elemanları oluştururuz.

## 9. Adım: Resim yapısı öğeleri oluşturun

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

Belgede yer alan illüstrasyonlar ve matematiksel formüller için yapısal öğeler oluşturuyoruz.

## Adım 10: Etiketli PDF belgesini kaydedin

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

Etiketli PDF belgesini oluşturulan yapı elemanlarıyla birlikte kaydediyoruz.

### Aspose.PDF for .NET kullanarak Yapı Elemanları Oluşturma için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Pdf Belgesi Oluştur
Document document = new Document();
// TaggedPdf ile çalışmaya yönelik İçerik edinin
ITaggedContent taggedContent = document.TaggedContent;
// Documnet için Başlığı ve Dili Ayarlayın
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// Gruplandırma Öğeleri Oluşturun
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
// Metin Satır İçi Düzeyde Yapı Öğeleri Oluşturma
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// İllüstrasyon Yapı Elemanları Oluşturun
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
// Yöntemler geliştiriliyor
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
// Etiketli Pdf Belgesini Kaydet
document.Save(dataDir + "StructureElements.pdf");

```

## Çözüm

Bu eğitimde, etiketli bir PDF belgesinde yapı öğeleri oluşturmak için Aspose.PDF for .NET'in nasıl kullanılacağını öğrendik. Yapısal öğeler belge erişilebilirliğini artırmaya ve içeriği anlamlı bir şekilde düzenlemeye yardımcı olur. Artık bu bilgiyi yapılandırılmış, gezinmesi kolay PDF belgeleri oluşturmak için kullanabilirsiniz.

### SSS'ler

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinde yapı elemanları oluşturmanın amacı nedir?

C: Aspose.PDF for .NET kullanarak bir PDF belgesinde yapı öğeleri oluşturmak, belge içeriğinin erişilebilirliğini ve organizasyonunu geliştirir. Yapı öğeleri gezinmeyi, anlambilimi ve yardımcı teknolojilerle uyumluluğu geliştiren hiyerarşik bir yapı sağlar.

#### S: Sağlanan C# kodu bir PDF belgesinde yapı öğelerini nasıl oluşturur?

C: Kod örneği, gruplandırma öğeleri (parçalar, bölümler ve div'ler gibi), blok düzeyi öğeler (paragraflar ve başlıklar gibi), satır içi düzey öğeler (yayılma, alıntı, not) dahil olmak üzere çeşitli türde yapı öğelerinin nasıl oluşturulacağını gösterir. ) ve resim öğeleri (şekiller ve formüller gibi). Bu yapı öğeleri içeriğin düzenlenmesine yardımcı olur.

####  S: Belgenin başlığını ve dilini ayarlamak neden önemlidir?`SetTitle` and `SetLanguage` methods?

 C: Belgenin başlığını ve dilini kullanarak ayarlama`SetTitle` Ve`SetLanguage`yöntemleri belge erişilebilirliğini ve anlambilimini geliştirir. Başlık, belgenin amacının kısa bir açıklamasını sağlarken, dil özelliği dile özgü oluşturmayı ve erişilebilirliği geliştirir.

####  S: gibi öğeler nasıl gruplandırılır?`PartElement` and `SectElement`, contribute to the structure of the PDF document?

C: Gruplandırma öğeleri, PDF belgesinde hiyerarşik bir yapı oluşturarak ilgili içeriği mantıksal olarak düzenlemenize ve gruplandırmanıza olanak tanır. Bu, gezinmeyi geliştirir ve kullanıcılar için net bir yapı sağlar.

#### S: Blok düzeyi ve satır içi düzey yapı öğeleri nelerdir ve bunlar arasındaki farklar nelerdir?

C: Blok düzeyindeki yapı öğeleri, paragraflar ve başlıklar gibi daha büyük içerik bloklarını temsil ederken satır içi düzeydeki öğeler, bir paragraf veya başlık içindeki açıklıklar, alıntılar ve notlar gibi metnin bölümlerini temsil eder. İçeriğin hiyerarşisini ve ilişkilerini tanımlamaya yardımcı olurlar.

####  S: Sanat eseri öğeleri nasıl yapılandırılır?`FigureElement` and `FormulaElement`, contribute to the document?

C: Sanat eseri yapısı öğeleri, belgeye resimler, şekiller ve matematiksel formüller eklemenizi sağlar. Görsel ve matematiksel içeriği dahil etmek için yapılandırılmış bir yol sağlarlar.

#### S: Listeler, tablolar veya ek açıklamalar gibi diğer türdeki yapı öğelerini oluşturmak için benzer teknikleri kullanabilir miyim?

C: Evet, listeler, tablolar, ek açıklamalar, referanslar ve daha fazlası gibi diğer türdeki yapı öğelerini oluşturmak için benzer teknikleri kullanabilirsiniz. Aspose.PDF çok çeşitli yapı elemanı oluşturma yöntemleri sunar.

####  S: Etiketli PDF belgesini kullanarak nasıl kaydedilir?`Save` method ensure the preservation of structure elements?

 C:`Save` yöntemi, PDF belgesini oluşturulan yapı öğeleriyle birlikte kaydederek belgenin hiyerarşik ve anlamsal yapısının erişilebilirlik ve gezinme açısından korunmasını sağlar.

#### S: Yapı öğeleri, erişilebilirlik ve yardımcı teknolojilerle uyumluluk açısından PDF belgelerine ne gibi faydalar sağlar?

C: Yapı öğeleri, belgeye anlamlı bir yapı ve anlam bilgisi sağlayarak erişilebilirliği artırır. Bu, ekran okuyucular gibi yardımcı teknolojilerin belge içeriğini engelli kullanıcılara daha etkili bir şekilde yorumlamasına ve aktarmasına olanak tanır.

#### S: PDF belgelerimde farklı türdeki yapı öğelerini nasıl daha fazla kişiselleştirebilir ve birleştirebilirim?

C: Aspose.PDF tarafından sağlanan uygun oluşturma yöntemlerini kullanarak yapı elemanlarını birleştirebilir ve özelleştirebilirsiniz. İyi yapılandırılmış ve organize bir PDF belgesi oluşturmak için farklı öğeler ve özellikleriyle denemeler yapın.