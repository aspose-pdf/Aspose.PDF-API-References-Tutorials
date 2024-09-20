---
title: Mevcut PDF'deki Etiket Resmi
linktitle: Mevcut PDF'deki Etiket Resmi
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak mevcut PDF'lerdeki görselleri nasıl etiketleyeceğinizi öğrenin. PDF/UA uyumluluğu ile erişilebilirliği artırmak için adım adım kılavuz.
type: docs
weight: 210
url: /tr/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
## giriiş

Bu eğitimde, .NET için Aspose.PDF kullanarak mevcut bir PDF'deki bir resmi nasıl etiketleyeceğinizi göstereceğiz. Bu kılavuzun sonunda, resimler için alternatif metin ayarlayabilecek, düzen niteliklerini ayarlayabilecek ve PDF'nizin erişilebilirlik standartlarına uygun olduğundan emin olabileceksiniz.

## Ön koşullar

Başlamadan önce, başlamak için neye ihtiyacınız olduğunu gözden geçirelim:

-  Aspose.PDF for .NET: Aspose.PDF for .NET'in en son sürümünü indirip yüklediğinizden emin olun.[Buradan indirin](https://releases.aspose.com/pdf/net/).
- .NET Framework: Visual Studio gibi bir .NET geliştirme ortamının kurulu olduğundan emin olun.
- PDF Yapısının Temel Anlayışı: Paragraflar, bölümler, tablolar ve resimler gibi PDF yapı öğelerine aşinalık.
-  Geçerli Bir Lisans: Bir lisans satın alabilirsiniz[Burada](https://purchase.aspose.com/buy) veya geçici bir tane kullanın[Burada](https://purchase.aspose.com/temporary-license/).

## Paketleri İçe Aktar

Kodlamaya başlamak için, .NET için Aspose.PDF'den temel ad alanlarını içe aktarmanız gerekir. Bunlar, PDF belgesini düzenlemek için gerekli sınıflara ve yöntemlere erişmenizi sağlayacaktır.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Artık ortamı hazırladığımıza göre, bir görseli etiketleme sürecini birden fazla adıma bölelim.

## Adım 1: Mevcut PDF Belgesini Yükleyin

İlk adım, çalışmak istediğiniz PDF dosyasını yüklemektir. Bu, etiketlemek istediğiniz bir görsele sahip herhangi bir PDF dosyası olabilir.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Belgeyi aç
Document document = new Document(inFile);
```

-  Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` dosyanızın gerçek yolu ile.
-  The`Document` class, mevcut bir PDF'yi yüklemenize olanak tanır. Bu PDF'yi, resmi etiketlemek için değiştireceksiniz.

## Adım 2: Etiketli İçeriğe ve Kök Yapı Elemanına Erişim

PDF'yi açtıktan sonraki adım, etiketli içeriğe erişmek ve kök yapı öğesini belirlemektir. Bu, PDF'deki öğeler arasında gezinmenize ve değişiklikler yapmanıza olanak tanıdığı için önemlidir.

```csharp
// Etiketli içerik ve kök yapı öğesini alın
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

- `TaggedContent` PDF'deki yapılandırılmış öğelere erişim sağlar.
-  The`RootElement` en üstteki yapı elemanıdır, buradan paragraflar, tablolar ve resimler gibi diğer elemanlara geçebilirsiniz.

## Adım 3: Etiketli PDF Belgesi için Başlığı Ayarlayın

Etiketli PDF belgesine bir başlık eklemek, belgenizin düzgün bir şekilde etiketlenmesini sağlar; bu da erişilebilirlik ve PDF/UA uyumluluğu açısından faydalıdır.

```csharp
// Etiketli PDF belgesi için başlık belirleyin
taggedContent.SetTitle("Document with images");
```

- Etiketli PDF'niz için bir başlık belirlemek erişilebilirliği artırır ve ekran okuyucular ile yardımcı teknolojiler için belgenin netliğini iyileştirir.

## Adım 4: Görseli Bulun ve Etiketleyin

 Şimdi, resim öğesini (bir resim öğesi olarak adlandırılır) bulalım.`FigureElement` (Aspose.PDF'de) bunun için alternatif bir metin ayarlayın ve düzen niteliklerini yapılandırın.

```csharp
// Tüm Şekil öğelerinde (görüntülerde) döngü yapın ve alternatif metin ve düzen niteliklerini ayarlayın
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
    // Şekil için alternatif metin ayarlayın
    figureElement.AlternativeText = "Figure alternative text (technique 2)";
    
    // BBox niteliğini (sınırlayıcı kutu) oluşturun ve ayarlayın
    StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
    bboxAttribute.SetRectangleValue(new Aspose.Pdf.Rectangle(0.0, 0.0, 100.0, 100.0));
    
    // Şekil için düzen niteliklerini ayarlayın
    StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
    figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

-  Bu kod tüm döngüleri kapsar`FigureElement` Kök yapıdaki, görüntüleri temsil eden nesneler.
- Erişilebilirlik için alternatif metni ayarlar (ekran okuyucular bunu görüntüyü tanımlamak için kullanır).
- Sınırlayıcı kutu (`BBox`görüntünün düzeni için koordinatları belirtir ve belgede doğru şekilde görüntülenmesini sağlar.

## Adım 5: Tablodaki Span Elemanlarını Değiştirin

 Bazı durumlarda, bir tablo içindeki span öğelerini değiştirmeniz gerekebilir. Burada, bir span öğesinin nasıl bulunacağını göstereceğiz.`SpanElement` ve onu bir paragrafa taşıyın.

```csharp
// Tablo, aralık ve paragraf öğelerini bulun
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Span öğesini paragrafa taşı
spanElement.ChangeParentElement(paragraph);
```

-  Burada, şunu buluyoruz:`TableElement`, `SpanElement` , Ve`ParagraphElement` PDF'in içinde.
-  Kullanımı`ChangeParentElement` Bu yöntemde, uygun etiketleme ve yapıyı sağlamak için aralığı paragrafa taşıyoruz.

## Adım 6: Belgeyi Kaydedin ve PDF/UA Uyumluluğunu Doğrulayın

Tüm değişiklikler yapıldıktan sonra son adım güncellenen PDF'i kaydetmek ve PDF/UA standartlarına uygun olup olmadığını kontrol etmektir.

```csharp
// Güncellenen PDF belgesini kaydedin
document.Save(outFile);

// PDF/UA uyumluluğunu doğrulayın
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

-  The`Validate` yöntem PDF belgesini PDF/UA standartlarına göre kontrol eder ve sonuçları kaydeder.
- Uygunluğun sağlanması erişilebilirliği iyileştirmeye ve belge yayımlama konusunda düzenleyici gereklilikleri karşılamaya yardımcı olur.

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak mevcut bir PDF'deki görselleri nasıl etiketleyeceğinizi gösterdik. Alternatif metin ayarlayarak, düzen niteliklerini ayarlayarak ve belgeyi PDF/UA uyumluluğu için doğrulayarak, PDF'lerinizin erişilebilir olduğundan ve modern standartları karşıladığından emin olabilirsiniz. Aspose.PDF, yapılandırılmış öğelerle çalışmayı kolaylaştırır ve belgenizin düzeni ve erişilebilirliği üzerinde kontrol sahibi olmanızı sağlar.

## SSS

### Aspose.PDF for .NET ne için kullanılır?
Aspose.PDF for .NET, .NET ortamında PDF belgelerini programlı olarak oluşturmak, düzenlemek ve düzenlemek için kullanılan güçlü bir kütüphanedir.

### PDF/UA uyumluluğunu nasıl sağlayabilirim?
 Aspose.PDF'leri kullanabilirsiniz`Validate` Belgede değişiklik yapıldıktan sonra PDF/UA uyumluluğunu kontrol etme yöntemi.

### PDF'lerde alternatif metin nedir?
Alternatif metin, özellikle ekran okuyucu kullanan kullanıcılar için erişilebilirliği artırmak amacıyla PDF'lerdeki resimlere eklenen bir açıklamadır.

### Aspose.PDF ile PDF'deki tabloları ve alanları düzenleyebilir miyim?
Evet, Aspose.PDF bir PDF belgesindeki tabloları, aralıkları ve diğer yapılandırılmış öğeleri düzenlemenize olanak tanır.

### Aspose.PDF for .NET'i nereden indirebilirim?
 Aspose.PDF'in .NET için en son sürümünü indirebilirsiniz[Burada](https://releases.aspose.com/pdf/net/).