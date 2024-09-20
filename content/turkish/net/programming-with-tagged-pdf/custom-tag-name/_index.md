---
title: Özel Etiket Adı
linktitle: Özel Etiket Adı
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile özel etiket adı kullanma konusunda adım adım kılavuz. Özel etiketlerle PDF'lerinizin yapısını iyileştirin.
type: docs
weight: 90
url: /tr/net/programming-with-tagged-pdf/custom-tag-name/
---
## giriiş

Günümüzün dijital çağında, PDF'ler her yerdedir. Raporlardan kılavuzlara kadar, çeşitli sektörlerde çok sayıda amaca hizmet ederler. Ancak, bu belgelerin engelli bireyler de dahil olmak üzere herkes tarafından erişilebilir olmasını sağlamak çok önemlidir. Etiketli PDF'ler tam da burada devreye girer. Ekran okuyucuların ve diğer yardımcı teknolojilerin belge içeriğini etkili bir şekilde yorumlamasını kolaylaştırırlar.

## Ön koşullar

Kodlamaya geçmeden önce, her şeyin hazır olduğundan emin olmanız önemlidir. İhtiyacınız olanlar şunlardır:

1. Visual Studio - Herhangi bir güncel sürüm işinizi görecektir, ancak optimum işlevsellik için en son sürüme sahip olmak en iyisidir.
2.  Aspose.PDF for .NET - En son sürümü şu adresten kolayca indirebilirsiniz:[indirme bağlantısı](https://releases.aspose.com/pdf/net/).
3. C# Temel Bilgisi - Kodu uygularken C# programlama temellerine aşina olmanız faydalı olacaktır.

## Paketleri İçe Aktar

Ortamınızı kurduğunuzda, bir sonraki adım Aspose.PDF'yi kullanmak için gerekli paketleri içe aktarmaktır. Bunu Aspose.PDF kütüphanesini projenize ekleyerek yapabilirsiniz.

### Aspose.PDF'yi NuGet aracılığıyla yükleyin

1. Visual Studio Projenizi açın: Henüz bir proje oluşturmadıysanız, devam edip yeni bir proje oluşturun.
2. NuGet Paket Yöneticisine erişin: Çözüm Gezgini'nde projenize sağ tıklayın ve "NuGet Paketlerini Yönet" seçeneğini belirleyin.
3. Aspose.PDF'yi arayın: Arama çubuğuna “Aspose.PDF” girin.
4. Paketi Yükle: Paketi projenize eklemek için "Yükle"ye tıklayın. Yüklendikten sonra, hazırsınız!

### Yönergeyi Kullanarak Ekle

Kodunuzda Aspose işlevselliğinden faydalanabilmek için dosyanızın en üstüne gerekli using yönergesini eklemeniz gerekir:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Bu adımları tamamladığınızda, etiketli PDF'nizi oluşturmaya hazırsınız!

Artık her şeyi ayarladığınıza göre, asıl göreve geçelim: etiketli bir PDF belgesi oluşturma. İşte .NET için Aspose.PDF kullanarak bunu nasıl yapacağınıza dair adım adım bir kılavuz.

## Adım 1: Belge Dizinini Tanımlayın

Öncelikle, PDF'nizin kaydedileceği yolu belirtmeniz gerekecek. Veri dizininizi burada tanımlayacaksınız.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Açıklama: "YOUR DOCUMENT DIRECTORY" ifadesini PDF dosyasını kaydetmek istediğiniz gerçek yolla değiştirin. Herhangi bir çalışma zamanı istisnasından kaçınmak için bu dizinde yazma iznine sahip olmak çok önemlidir.

## Adım 2: Yeni bir PDF Belgesi Oluşturun

 Daha sonra, bir örnek oluşturacağız`Document` sınıf.

```csharp
Document document = new Document();
```

Açıklama: Bu satır yeni bir PDF belgesi başlatır. Bunu, PDF'nizin içeriğini boyayacağınız boş bir tuval oluşturmak olarak düşünün.

## Adım 3: Etiketli İçerik Oluşturun

Şimdi etiketlemenin özüne inme zamanı. Belgenin etiketli içeriğini alacağız.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

 Açıklama:`TaggedContent` nesnesi, içeriği hiyerarşik olarak düzenleyerek PDF'in mantıksal yapısını ve erişilebilirliğini değiştirmemize olanak tanır.

## Adım 4: Başlığı ve Dili Ayarlayın

Sonra, belgenin başlığını ve dil özniteliğini ayarlayabilirsiniz. Bu, ekran okuyucuların belgeyi doğru şekilde işlemesine yardımcı olur.

```csharp
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

Açıklama: Burada, bu PDF'i okuyan herkesi, özellikle erişilebilirlik araçları için kavramaya yardımcı olan başlığı ve dili hakkında bilgilendiriyoruz.

## Adım 5: Mantıksal Yapı Öğelerini Oluşturun

Şimdi PDF'nizin içinde yapılandırılmış öğeler oluşturmanın zamanı geldi.

```csharp
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
```

 Açıklama: Bu adım, içerik eklemeye başlayabileceğiniz bir bölüm öğesini tanıtır.`RootElement` sizin ana üssünüzdür.

## Adım 6: Paragraf Öğeleri Oluşturun

Şimdi çeşitli paragraf öğeleri oluşturalım ve bunların metin içeriklerini ayarlayalım.

```csharp
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1. ");
p2.SetText("P2. ");
p3.SetText("P3. ");
p4.SetText("P4. ");
```

Açıklama: Her paragraf bir hikâyedeki bir cümleye benzer, sahneyi hazırlar ve belgenize anlam katar.

## Adım 7: Paragraflara Etiketler Atamak

PDF'inizin erişilebilirliği için her paragrafı uygun şekilde etiketlemek çok önemlidir.

```csharp
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
```

Açıklama: Etiketlerle etiketleme yaparak, yardımcı teknolojilerin içeriğin yapısını anlamasını sağlıyoruz; bu, onlara alanda gezinmeleri için bir yol haritası vermek gibi bir şey.

## Adım 8: Bölüme Paragraflar Ekleyin

Şimdi bu paragrafları daha önce oluşturduğumuz bölüme ekleyeceğiz.

```csharp
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
```

Açıklama: Bu eylem, bölümdeki paragrafları düzenleyerek akışı mantıklı ve takip edilmesi kolay hale getirir.

## Adım 9: Span Elemanlarını Oluşturun

Paragraflar gibi, aralıklar da metin içeriğimize ayrıntılı bilgi ekler.

```csharp
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
```

Açıklama: Aralıklar, ayrıntıların ince ayarı gibidir; her paragrafta ilettiğiniz şeye özgüllük katarlar.

## Adım 10: Span Elemanlarına Etiketler Atamak

Paragraflarda yaptığımız gibi, anlaşılmasını kolaylaştırmak için span öğelerimizi etiketlememiz gerekir.

```csharp
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
```

Açıklama: Aralıkları doğru şekilde etiketlemek, tüm nüansların doğru bir şekilde temsil edilmesini sağlayarak, bununla karşılaşan herkes için zengin bir belge oluşturur.

## Adım 11: Paragraflara Aralıklar Ekleyin

Şimdi span elemanlarımızı ilgili paragraflara ekleyelim.

```csharp
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);
```

Açıklama: Bu entegrasyon, daha derin bir anlayış için bir kitaba dipnot eklemek gibi, ek bilgiler ekleyerek paragraflarınızı geliştirir.

## Adım 12: Etiketli PDF Belgesini Kaydedin

Sonunda şaheserinizi kurtarmanın zamanı geldi!

```csharp
document.Save(dataDir + "CustomTag.pdf");
```

Açıklama: Bu satır etiketli PDF'nizi belirtilen dizine kaydeder. Bununla, etiketli PDF belgenizin oluşturulmasını tamamlamış olursunuz!

## Çözüm

Aspose.PDF for .NET kullanarak etiketli PDF belgeleri oluşturmak yalnızca içerik eklemekle ilgili değildir; tüm kullanıcılar için erişilebilir bir deneyim oluşturmakla ilgilidir. Sadece birkaç adımla belgelerinizin herkesle iletişim kurmasını, engelleri kaldırmasını ve anlayışı geliştirmesini sağlayabilirsiniz. 

## SSS

### Etiketli PDF nedir?  
Etiketli PDF, belgenin içeriğinin yapısını ve erişilebilirliğini tanımlayan ek meta veriler içerir ve bu sayede yardımcı teknolojilerin yorumlaması kolaylaşır.

### .NET için Aspose.PDF'e neden ihtiyacım var?  
Aspose.PDF for .NET, geliştiricilerin kapsamlı özelliklerle PDF belgelerini programlı bir şekilde oluşturmalarına, değiştirmelerine ve düzenlemelerine olanak tanıyan güçlü bir kütüphanedir.

### Aspose.PDF'in deneme sürümünü nasıl edinebilirim?  
 Aspose.PDF'nin ücretsiz deneme sürümünü edinmek için şu adresi ziyaret edebilirsiniz:[bu bağlantı](https://releases.aspose.com/).

### Aspose.PDF için destek alabilir miyim?  
 Evet, destek için bize ulaşabilirsiniz[Aspose forumu](https://forum.aspose.com/c/pdf/10).

### Ayrıntılı Aspose.PDF dokümantasyonunu nerede bulabilirim?  
 Tam dokümantasyona buradan ulaşabilirsiniz[Burada](https://reference.aspose.com/pdf/net/).