---
title: Mevcut PDF'de Görüntüyü Etiketle
linktitle: Mevcut PDF'de Görüntüyü Etiketle
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile mevcut bir PDF'deki bir görüntüyü nasıl işaretleyeceğinizi öğrenin. Resimlere Etiket Eklemek İçin Adım Adım Kılavuz.
type: docs
weight: 210
url: /tr/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
Bu ayrıntılı eğitimde, Aspose.PDF for .NET kullanarak mevcut bir PDF'deki bir görüntüyü işaretlemek için sağlanan C# kaynak kodunu size adım adım anlatacağız. PDF'deki bir görsele nasıl etiket ekleneceğini anlamak için aşağıdaki talimatları izleyin.

## 1. Adım: Ortamı ayarlama

Başlamadan önce geliştirme ortamınızı Aspose.PDF for .NET'i kullanacak şekilde yapılandırdığınızdan emin olun. Buna Aspose.PDF kütüphanesinin kurulması ve projenizin buna referans verecek şekilde yapılandırılması da dahildir.

## 2. Adım: Mevcut PDF belgesini açın

Bu adımda Aspose.PDF kullanarak mevcut bir PDF belgesini açacağız.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Giriş ve çıkış dosyası yolları
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Belgeyi aç
Document document = new Document(inFile);
```

Mevcut PDF belgesini Aspose.PDF kullanarak açtık.

## 3. Adım: Etiketli İçeriği ve Kök Yapı Öğesini Elde Edin

Şimdi PDF belgesinin etiketli içeriğini ve karşılık gelen kök yapı öğesini alacağız.

```csharp
// Etiketli içeriği ve kök yapı öğesini alın
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

PDF belgesinin etiketli içeriğini ve karşılık gelen kök yapı öğesini aldık.

## 4. Adım: Etiketli PDF belgesinin başlığını ayarlama

Şimdi etiketli PDF belgesinin başlığını ayarlayalım.

```csharp
// Etiketli PDF belgesinin başlığını tanımlayın
taggedContent.SetTitle("Document with images");
```

Etiketli PDF belgesinin başlığını belirledik.

## 5. Adım: Resme alternatif metinler ve sınırlayıcı kutu atayın

Şimdi her resim öğesine alternatif metin ve bir sınırlayıcı kutu atayacağız.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Resme alternatif metin atayın
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // Sınırlayıcı kutuyu (bbox) oluşturma ve atama
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

PDF belgesindeki her görüntü öğesine alternatif metin ve bir sınırlayıcı kutu atadık.

## Adım 6: Span öğesini paragrafa taşıma

Şimdi Span öğesini paragrafın içine taşıyalım.

```csharp
// Span öğesini paragrafa taşıyın (ilk TD'de hatalı yayılma ve paragrafı bulun)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Span öğesini paragrafta taşıma
spanElement.ChangeParentElement(paragraph);
```

Span öğesini belirtilen paragrafa taşıdık.

## Adım 7: Değiştirilen PDF belgesini kaydetme

Artık gerekli değişiklikleri yaptığımıza göre değiştirilen PDF belgesini kaydedeceğiz.

```csharp
// PDF belgesini kaydedin
document. Save(outFile);
```

Değiştirilen PDF belgesini belirtilen dizine kaydettik.

### Aspose.PDF for .NET kullanarak Mevcut PDF'deki Etiket Görüntüsü için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Belgeyi aç
Document document = new Document(inFile);

// Etiketli içeriği ve kök yapı öğesini alır
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Etiketli pdf belgesinin başlığını ayarla
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// Şekil için Alternatif Metin Ayarla
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// BBox Özniteliğini Oluşturun ve Ayarlayın
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Yayılma Öğesini Paragrafa Taşı (ilk TD'de yanlış yayılma ve paragrafı bulun)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Yayılma Öğesini Paragrafa Taşı
spanElement.ChangeParentElement(paragraph);

// Belgeyi kaydet
document.Save(outFile);

//Belgemiz için PDF/UA Uyumluluğunun kontrol edilmesi
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Çözüm

Bu eğitimde Aspose.PDF for .NET'i kullanarak mevcut bir PDF'deki bir görüntüyü nasıl işaretleyeceğimizi öğrendik. Artık Aspose.PDF'i kullanarak PDF belgelerinize etiket ekleyebilir ve görüntülerde düzenlemeler yapabilirsiniz.

### SSS'ler

#### S: Mevcut bir PDF'deki görüntüleri Aspose.PDF for .NET kullanarak etiketlemeye yönelik bu eğitimin ana amacı nedir?

C: Bu eğitimin temel amacı, Aspose.PDF for .NET kullanarak mevcut bir PDF belgesindeki bir görüntüyü işaretleme sürecinde size rehberlik etmektir. Öğretici, görüntülere alternatif metin ve sınırlayıcı kutular atamayı, belge içindeki öğeleri nasıl taşıyacağınızı ve görüntülere etiket eklemeyi anlamanıza yardımcı olacak adım adım talimatlar ve C# kaynak kodu örnekleri sağlar.

#### S: Aspose.PDF for .NET kullanarak PDF'deki görüntüleri etiketlemeye ilişkin bu eğitimi takip etmenin önkoşulları nelerdir?

C: Başlamadan önce, geliştirme ortamınızı Aspose.PDF for .NET'i kullanacak şekilde ayarladığınızdan emin olun. Bu, Aspose.PDF kütüphanesinin kurulmasını ve projenizin buna referans verecek şekilde yapılandırılmasını içerir.

#### S: Mevcut bir PDF belgesini Aspose.PDF for .NET kullanarak nasıl açabilirim ve etiketli içeriğine nasıl erişebilirim?

C: Eğitimde Aspose.PDF for .NET kullanılarak mevcut bir PDF belgesinin nasıl açılacağını ve daha fazla düzenleme için etiketli içeriğine nasıl erişileceğini gösteren C# kaynak kodu örnekleri sunulmaktadır.

#### S: Bir PDF belgesindeki görsellere alternatif metin ve sınırlayıcı kutular atamanın amacı nedir?

C: Resimlere alternatif metin ve sınırlayıcı kutular atamak, resimler için açıklayıcı metin sağlayarak ve bunların belgedeki düzenini ve konumunu tanımlayarak erişilebilirliği artırır. Bu bilgiler ekran okuyucular ve diğer yardımcı teknolojiler için çok önemlidir.

#### S: Etiketli bir PDF belgesinin başlığını Aspose.PDF for .NET kullanarak nasıl ayarlayabilirim?

C: Eğitim, Aspose.PDF for .NET kullanılarak etiketli bir PDF belgesinin başlığının nasıl ayarlanacağını gösteren C# kaynak kodu örneklerini içerir.

#### S: Bir PDF belgesindeki öğeleri taşıma süreci neleri içerir?

C: Bir PDF belgesindeki öğelerin taşınması, belirli bir öğenin ana öğesinin değiştirilmesini içerir. Bu öğreticide, Span öğesini tablo içindeki belirli bir Paragraf öğesine nasıl taşıyacağınızı öğreneceksiniz.

#### S: Etiketler ekledikten ve görüntülerde düzenlemeler yaptıktan sonra değiştirilen PDF belgesini nasıl kaydedebilirim?

 C: Etiketler ekledikten, alternatif metin atadıktan, sınırlayıcı kutuları ayarladıktan ve PDF belgesinde düzenlemeler yaptıktan sonra, değiştirilen PDF belgesini kaydetmek için sağlanan C# kaynak kodu örneklerini kullanabilirsiniz.`Save()` yöntem.

#### S: Eğitimde sağlanan örnek kaynak kodunun amacı nedir?

C: Örnek kaynak kodu, Aspose.PDF for .NET kullanılarak görüntü etiketleme ve manipülasyon uygulamak için pratik bir referans görevi görür. Bu kodu bir başlangıç noktası olarak kullanabilir ve özel gereksinimlerinize uyacak şekilde değiştirebilirsiniz.

#### S: Bu teknikleri bir PDF belgesindeki yalnızca resimlere değil diğer türdeki öğelere de uygulayabilir miyim?

C: Evet, bu eğitimde gösterilen teknikler, bir PDF belgesindeki çeşitli öğe türleriyle çalışacak şekilde uyarlanabilir. Metin, tablolar ve daha fazlası gibi diğer öğeleri etiketlemek ve değiştirmek için benzer ilkeleri uygulayabilirsiniz.

#### S: Değiştirilen PDF belgesinin PDF/UA uyumluluğunu nasıl doğrulayabilirim?

 C: Eğitimde, değiştirilmiş PDF belgesinin PDF/UA uyumluluğunun aşağıdakileri kullanarak nasıl doğrulanacağını gösteren C# kaynak kodu örnekleri sağlanmaktadır:`Validate()` yöntemi ve bir XML raporu oluşturma.

#### S: Aspose.PDF for .NET, PDF belgeleriyle çalışmak için başka hangi özellikleri sunuyor?

C: Aspose.PDF for .NET, PDF belgeleriyle çalışmak için metin işleme, görüntü ekleme, tablo oluşturma, form alanı yönetimi, dijital imzalar, açıklamalar ve daha fazlasını içeren çok çeşitli özellikler sunar. Daha fazla araştırma için resmi belgelere ve kaynaklara bakın.