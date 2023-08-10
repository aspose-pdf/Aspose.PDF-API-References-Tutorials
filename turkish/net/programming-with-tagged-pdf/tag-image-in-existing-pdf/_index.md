---
title: Mevcut PDF'de Resmi Etiketle
linktitle: Mevcut PDF'de Resmi Etiketle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile mevcut bir PDF'de bir görüntüyü nasıl işaretleyeceğinizi öğrenin. Görüntülere Etiket Eklemek İçin Adım Adım Kılavuz.
type: docs
weight: 210
url: /tr/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
Bu ayrıntılı öğreticide, Aspose.PDF for .NET kullanarak mevcut bir PDF'de bir görüntüyü işaretlemek için size sağlanan C# kaynak kodunda adım adım yol göstereceğiz. PDF'deki bir görüntüye nasıl etiket ekleneceğini anlamak için aşağıdaki talimatları izleyin.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, geliştirme ortamınızı Aspose.PDF for .NET kullanacak şekilde yapılandırdığınızdan emin olun. Bu, Aspose.PDF kitaplığının kurulmasını ve projenizin buna referans verecek şekilde yapılandırılmasını içerir.

## 2. Adım: Mevcut PDF belgesini açın

Bu adımda Aspose.PDF kullanarak mevcut bir PDF belgesini açacağız.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Giriş ve çıkış dosya yolları
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// belgeyi aç
Document document = new Document(inFile);
```

Mevcut PDF belgesini Aspose.PDF kullanarak açtık.

## 3. Adım: Etiketli İçerik ve Kök Yapı Öğesi Elde Edin

Şimdi PDF belgesinin etiketli içeriğini ve karşılık gelen kök yapı öğesini alacağız.

```csharp
// Etiketli içerik ve kök yapı öğesini alın
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

PDF belgesinin etiketli içeriğini ve karşılık gelen kök yapı öğesini aldık.

## 4. Adım: Etiketli PDF belgesi için başlığın ayarlanması

Şimdi etiketli PDF belgesi için başlığı ayarlayalım.

```csharp
// Etiketli PDF belgesi için başlığı tanımlayın
taggedContent.SetTitle("Document with images");
```

Etiketli PDF belgesi için başlığı belirledik.

## 5. Adım: Resme alternatif metinler ve sınırlayıcı kutu atayın

Şimdi, her resim öğesi için alternatif metin ve bir sınırlayıcı kutu atayacağız.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Resme alternatif metin atayın
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // Sınırlayıcı kutu (bbox) oluşturma ve atama
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

PDF belgesindeki her resim öğesine alternatif metin ve bir sınırlayıcı kutu atadık.

## 6. Adım: Span öğesini paragrafın içine taşıma

Şimdi Span öğesini paragrafın içine taşıyalım.

```csharp
// Span öğesini paragrafa taşı (ilk TD'de yanlış yayılma ve paragrafı bul)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Yayılma öğesini paragrafta taşıma
spanElement.ChangeParentElement(paragraph);
```

Span öğesini belirtilen paragrafa taşıdık.

## 7. Adım: Değiştirilen PDF belgesini kaydetme

Artık gerekli değişiklikleri yaptığımıza göre, değiştirilen PDF belgesini kaydedeceğiz.

```csharp
// PDF belgesini kaydedin
document. Save(outFile);
```

Değiştirilen PDF belgesini belirtilen dizine kaydettik.

### Aspose.PDF for .NET kullanılarak Mevcut PDF'de Görüntüyü Etiketlemek için örnek kaynak kodu 

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

// Etiketli pdf belgesi için başlık ayarla
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// Şekil için Alternatif Metin Ayarla
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// BBox Niteliği Oluşturma ve Ayarlama
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Span Öğesini Paragrafa Taşı (ilk TD'de yanlış yayılma ve paragrafı bul)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Span Öğesini Paragrafa Taşı
spanElement.ChangeParentElement(paragraph);

// Belgeyi kaydet
document.Save(outFile);

//Çıkan belge için PDF/UA Uyumluluğunu kontrol etme
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak mevcut bir PDF'de bir görüntüyü nasıl işaretleyeceğimizi öğrendik. Artık Aspose.PDF'yi PDF belgelerinize etiket eklemek ve resimlerde düzenlemeler yapmak için kullanabilirsiniz.

### SSS

#### S: Aspose.PDF for .NET kullanarak mevcut bir PDF'deki görüntüleri etiketlemeye ilişkin bu eğitimin temel amacı nedir?

Y: Bu eğitimin temel amacı, Aspose.PDF for .NET kullanarak mevcut bir PDF belgesindeki bir görüntüyü işaretleme sürecinde size rehberlik etmektir. Öğretici, görüntülere nasıl alternatif metin ve sınırlayıcı kutular atayacağınızı, belge içindeki öğeleri nasıl taşıyacağınızı ve görüntülere etiketler ekleyeceğinizi anlamanıza yardımcı olacak adım adım yönergeler ve C# kaynak kodu örnekleri sağlar.

#### S: Aspose.PDF for .NET kullanarak bir PDF'de görüntüleri etiketlemeye ilişkin bu öğreticiyi takip etmek için ön koşullar nelerdir?

C: Başlamadan önce, geliştirme ortamınızı Aspose.PDF for .NET'i kullanacak şekilde kurduğunuzdan emin olun. Bu, Aspose.PDF kitaplığının kurulmasını ve projenizin buna referans verecek şekilde yapılandırılmasını içerir.

#### S: Aspose.PDF for .NET kullanarak mevcut bir PDF belgesini nasıl açabilirim ve etiketlenmiş içeriğine nasıl erişebilirim?

C: Eğitim, Aspose.PDF for .NET kullanılarak mevcut bir PDF belgesinin nasıl açılacağını ve daha fazla değişiklik için etiketli içeriğine nasıl erişileceğini gösteren C# kaynak kodu örnekleri sağlar.

#### S: Bir PDF belgesindeki resimlere alternatif metin ve sınırlayıcı kutular atamanın amacı nedir?

Y: Görüntülere alternatif metin ve sınırlayıcı kutular atamak, görüntüler için açıklayıcı metin sağlayarak ve bunların düzenini ve belge içindeki konumunu tanımlayarak erişilebilirliği artırır. Bu bilgiler, ekran okuyucular ve diğer yardımcı teknolojiler için çok önemlidir.

#### S: Aspose.PDF for .NET kullanarak etiketli bir PDF belgesi için başlığı nasıl ayarlayabilirim?

C: Eğitim, Aspose.PDF for .NET kullanılarak etiketli bir PDF belgesi için başlığın nasıl ayarlanacağını gösteren C# kaynak kodu örnekleri içerir.

#### S: Bir PDF belgesindeki öğeleri taşıma işlemi neleri içerir?

C: Bir PDF belgesindeki öğelerin taşınması, belirli bir öğenin ana öğesinin değiştirilmesini içerir. Bu öğreticide, bir Span öğesini tablodaki belirli bir Paragraph öğesine nasıl taşıyacağınızı öğreneceksiniz.

#### S: Etiketleri ekledikten ve resimlerde düzenlemeler yaptıktan sonra değiştirilen PDF belgesini nasıl kaydedebilirim?

 C: Etiketleri ekledikten, alternatif metin atadıktan, sınırlayıcı kutuları ayarladıktan ve PDF belgesinde düzenlemeler yaptıktan sonra, değiştirilen PDF belgesini kaydetmek için sağlanan C# kaynak kodu örneklerini kullanabilirsiniz.`Save()` yöntem.

#### S: Eğitimde sağlanan örnek kaynak kodunun amacı nedir?

C: Örnek kaynak kodu, Aspose.PDF for .NET kullanılarak görüntü etiketleme ve manipülasyonu gerçekleştirmek için pratik bir referans görevi görür. Bu kodu bir başlangıç noktası olarak kullanabilir ve özel gereksinimlerinize uyacak şekilde değiştirebilirsiniz.

#### S: Bu teknikleri bir PDF belgesindeki yalnızca resimlere değil, diğer öğe türlerine de uygulayabilir miyim?

C: Evet, bu eğitimde gösterilen teknikler, bir PDF belgesindeki çeşitli öğe türleriyle çalışacak şekilde uyarlanabilir. Metin, tablolar ve daha fazlası gibi diğer öğeleri etiketlemek ve değiştirmek için benzer ilkeleri uygulayabilirsiniz.

#### S: Değiştirilen PDF belgesinin PDF/UA uyumluluğunu nasıl doğrulayabilirim?

 C: Öğretici, değiştirilen PDF belgesinin PDF/UA uyumluluğunun`Validate()` yöntemi ve bir XML raporu oluşturma.

#### S: Aspose.PDF for .NET, PDF belgeleriyle çalışmak için başka hangi özellikleri sunuyor?

Y: Aspose.PDF for .NET, PDF belgeleriyle çalışmak için metin işleme, resim ekleme, tablo oluşturma, form alanı yönetimi, dijital imzalar, ek açıklamalar ve daha fazlasını içeren çok çeşitli özellikler sunar. Daha fazla araştırma için resmi belgelere ve kaynaklara başvurun.