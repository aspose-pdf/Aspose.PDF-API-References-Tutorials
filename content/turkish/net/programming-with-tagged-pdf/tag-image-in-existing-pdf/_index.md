---
title: Mevcut PDF'deki Etiket Resmi
linktitle: Mevcut PDF'deki Etiket Resmi
second_title: Aspose.PDF for .NET API Referansı
description: Mevcut bir PDF'deki bir görüntüyü Aspose.PDF for .NET ile nasıl işaretleyeceğinizi öğrenin. Görüntülere Etiket Eklemek İçin Adım Adım Kılavuz.
type: docs
weight: 210
url: /tr/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
Bu detaylı eğitimde, .NET için Aspose.PDF kullanarak mevcut bir PDF'deki bir resmi işaretlemek için sağlanan C# kaynak kodunu adım adım inceleyeceğiz. Bir PDF'deki bir resme etiketlerin nasıl ekleneceğini anlamak için aşağıdaki talimatları izleyin.

## Adım 1: Ortamı kurma

Başlamadan önce, geliştirme ortamınızı .NET için Aspose.PDF kullanacak şekilde yapılandırdığınızdan emin olun. Bu, Aspose.PDF kitaplığını yüklemeyi ve projenizi buna başvuracak şekilde yapılandırmayı içerir.

## Adım 2: Mevcut PDF belgesini açın

Bu adımda Aspose.PDF kullanarak mevcut bir PDF belgesini açacağız.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Giriş ve çıkış dosya yolları
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Belgeyi aç
Document document = new Document(inFile);
```

Mevcut PDF dokümanını Aspose.PDF kullanarak açtık.

## Adım 3: Etiketli İçeriği ve Kök Yapı Elemanını Edinin

Şimdi PDF belgesinin etiketli içeriğini ve karşılık gelen kök yapı öğesini alacağız.

```csharp
// Etiketli içerik ve kök yapı öğesini alın
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

PDF belgesinin etiketli içeriğini ve buna karşılık gelen kök yapı öğesini aldık.

## Adım 4: Etiketli PDF belgesi için başlığı ayarlama

Şimdi etiketli PDF belgesinin başlığını belirleyelim.

```csharp
// Etiketli PDF belgesi için başlığı tanımlayın
taggedContent.SetTitle("Document with images");
```

Etiketli PDF belgesi için başlığı belirledik.

## Adım 5: Resme alternatif metinler ve sınırlayıcı kutu atayın

Şimdi her resim öğesi için alternatif metin ve sınırlayıcı kutu atayacağız.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Resme alternatif metin atayın
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // Sınırlayıcı kutuyu (bbox) oluşturun ve atayın
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

PDF belgesindeki her resim öğesine alternatif metin ve sınırlayıcı kutu atadık.

## Adım 6: Span öğesini paragrafa taşıma

Şimdi Span öğesini paragrafın içine taşıyalım.

```csharp
// Span öğesini paragrafa taşı (ilk TD'de yanlış span ve paragrafı bul)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Span öğesini paragrafta taşı
spanElement.ChangeParentElement(paragraph);
```

Span öğesini belirtilen paragrafa taşıdık.

## Adım 7: Değiştirilen PDF belgesinin kaydedilmesi

Gerekli değişiklikleri yaptıktan sonra şimdi değiştirilmiş PDF dokümanını kaydedebiliriz.

```csharp
// PDF belgesini kaydedin
document. Save(outFile);
```

Değiştirilen PDF dokümanını belirtilen dizine kaydettik.

### .NET için Aspose.PDF kullanarak Mevcut PDF'deki Etiket Resmi için örnek kaynak kodu 

```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Belgeyi aç
Document document = new Document(inFile);

// Etiketli içerik ve kök yapı öğesini alır
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Etiketli pdf belgesi için başlık ayarlayın
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// Şekil için Alternatif Metin Ayarla
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// BBox Niteliğini Oluştur ve Ayarla
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Span Elemanını Paragrafa Taşı (ilk TD'de yanlış span ve paragrafı bulun)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Span Elemanını Paragrafa Taşı
spanElement.ChangeParentElement(paragraph);

// Belgeyi kaydet
document.Save(outFile);

//Belgemiz için PDF/UA Uyumluluğunun Kontrol Edilmesi
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak mevcut bir PDF'deki bir resmi nasıl işaretleyeceğinizi öğrendik. Artık PDF belgelerinizdeki resimlere etiket eklemek ve düzenlemeler yapmak için Aspose.PDF'yi kullanabilirsiniz.

### SSS

#### S: Aspose.PDF for .NET kullanarak mevcut bir PDF'deki resimleri etiketlemeye ilişkin bu eğitimin temel amacı nedir?

A: Bu eğitimin temel amacı, .NET için Aspose.PDF kullanarak mevcut bir PDF belgesindeki bir resmi işaretleme sürecinde size rehberlik etmektir. Eğitim, resimlere alternatif metin ve sınırlayıcı kutular atamayı, belge içindeki öğeleri taşımayı ve resimlere etiket eklemeyi anlamanıza yardımcı olmak için adım adım talimatlar ve C# kaynak kodu örnekleri sağlar.

#### S: Aspose.PDF for .NET kullanarak bir PDF'deki resimleri etiketlemeyle ilgili bu öğreticiyi takip etmek için ön koşullar nelerdir?

A: Başlamadan önce, geliştirme ortamınızı Aspose.PDF for .NET kullanacak şekilde ayarladığınızdan emin olun. Bu, Aspose.PDF kitaplığını yüklemeyi ve projenizi buna başvuracak şekilde yapılandırmayı içerir.

#### S: Aspose.PDF for .NET kullanarak mevcut bir PDF belgesini nasıl açabilir ve etiketli içeriğine nasıl erişebilirim?

C: Bu eğitimde, Aspose.PDF for .NET kullanılarak mevcut bir PDF belgesinin nasıl açılacağı ve daha fazla düzenleme için etiketli içeriğe nasıl erişileceği gösterilmektedir.

#### S: PDF belgesindeki görsellere alternatif metin ve sınırlayıcı kutular atamanın amacı nedir?

A: Görüntülere alternatif metin ve sınırlayıcı kutular atamak, görüntüler için açıklayıcı metin sağlayarak ve belgedeki düzenlerini ve konumlarını tanımlayarak erişilebilirliği artırır. Bu bilgi, ekran okuyucular ve diğer yardımcı teknolojiler için çok önemlidir.

#### S: Aspose.PDF for .NET kullanarak etiketli bir PDF belgesinin başlığını nasıl ayarlayabilirim?

C: Eğitimde, Aspose.PDF for .NET kullanılarak etiketli bir PDF belgesinin başlığının nasıl ayarlanacağını gösteren C# kaynak kodu örnekleri yer almaktadır.

#### S: PDF belgesi içindeki öğeleri taşıma süreci nasıldır?

A: Bir PDF belgesindeki öğeleri taşımak, belirli bir öğenin üst öğesini değiştirmeyi içerir. Bu eğitimde, bir Span öğesini bir tablodaki belirtilen bir Paragraph öğesine nasıl taşıyacağınızı öğreneceksiniz.

#### S: Resimlere etiket ekledikten ve düzenlemeler yaptıktan sonra değiştirilen PDF belgesini nasıl kaydederim?

 A: Etiketleri ekledikten, alternatif metin atadıktan, sınırlayıcı kutuları ayarladıktan ve PDF belgesinde düzenlemeler yaptıktan sonra, değiştirilen PDF belgesini kaydetmek için sağlanan C# kaynak kodu örneklerini kullanabilirsiniz.`Save()` Yöntem.

#### S: Eğitimde verilen örnek kaynak kodunun amacı nedir?

A: Örnek kaynak kodu, .NET için Aspose.PDF kullanarak resim etiketleme ve düzenlemeyi uygulamak için pratik bir referans görevi görür. Bu kodu bir başlangıç noktası olarak kullanabilir ve özel gereksinimlerinize uyacak şekilde değiştirebilirsiniz.

#### S: Bu teknikleri yalnızca görsellere değil, PDF belgesindeki diğer öğe türlerine de uygulayabilir miyim?

C: Evet, bu eğitimde gösterilen teknikler bir PDF belgesindeki çeşitli türdeki öğelerle çalışmak için uyarlanabilir. Benzer prensipleri metin, tablolar ve daha fazlası gibi diğer öğeleri etiketlemek ve düzenlemek için uygulayabilirsiniz.

#### S: Değiştirilen PDF belgesinin PDF/UA uyumluluğunu nasıl doğrulayabilirim?

 A: Eğitimde, değiştirilmiş PDF belgesinin PDF/UA uyumluluğunun nasıl doğrulanacağını gösteren C# kaynak kodu örnekleri sağlanmaktadır.`Validate()` Yöntem ve XML raporunun oluşturulması.

#### S: Aspose.PDF for .NET, PDF belgeleriyle çalışmak için başka hangi özellikleri sunuyor?

A: Aspose.PDF for .NET, metin düzenleme, resim ekleme, tablo oluşturma, form alanı yönetimi, dijital imzalar, açıklamalar ve daha fazlası dahil olmak üzere PDF belgeleriyle çalışmak için çok çeşitli özellikler sunar. Daha fazla araştırma için resmi belgelere ve kaynaklara başvurun.