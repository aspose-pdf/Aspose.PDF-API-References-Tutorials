---
title: Satır İçi Yapı Elemanları
linktitle: Satır İçi Yapı Elemanları
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile çevrimiçi yapısal öğelerin kullanımına ilişkin adım adım kılavuz. PDF'lerinizi başlıklar ve paragraflarla düzenleyin.
type: docs
weight: 110
url: /tr/net/programming-with-tagged-pdf/inline-structure-elements/
---
Bu adım adım kılavuzda, .NET için Aspose.PDF ile satır içi yapı öğelerini nasıl kullanacağınızı göstereceğiz. Aspose.PDF, PDF belgelerini programatik olarak düzenlemenizi sağlayan güçlü bir kütüphanedir. Satır içi yapı öğeleri, farklı düzeylerde ve paragraflarda başlıklar kullanarak PDF belgenizde hiyerarşik bir yapı oluşturmanıza olanak tanır.

Gelin koda bir göz atalım ve Aspose.PDF for .NET ile satır içi yapı öğelerinin nasıl kullanılacağını öğrenelim.

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. .NET için Aspose.PDF kütüphanesi kuruldu.
2. C# programlama dilinin temel bilgisi.

## Adım 1: Ortamı kurma

Başlamak için C# geliştirme ortamınızı açın ve yeni bir proje oluşturun. Projenize .NET için Aspose.PDF kütüphanesine bir başvuru eklediğinizden emin olun.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Belgenin oluşturulması

 İlk adım, yeni bir PDF belgesi oluşturmaktır`Document` sınıf.

```csharp
// PDF belgesini oluşturun
Document document = new Document();
```

## Adım 3: Etiketli içerikle çalışın

Daha sonra belgenin etiketli içeriğini alıp çalışmaya başlıyoruz.

```csharp
// Belgenin etiketli içeriğini alın
ITaggedContent taggedContent = document.TaggedContent;
```

## Adım 4: Belge başlığını ve dilini ayarlayın

Artık belge başlığını ve dilini ayarlayabiliriz.

```csharp
// Belge başlığını ve dilini tanımlayın
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Adım 5: Yapısal elemanları çevrimiçi ekleyin

Şimdi dokümanımıza farklı düzeylerde başlıklar ve paragraflar gibi satır içi yapı öğeleri ekleyeceğiz.

```csharp
// Kök yapı öğesini alın
StructureElement rootElement = taggedContent.RootElement;

// Farklı düzeylerde başlıklar ekleyin
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// Her başlığa içerik ekleyin
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

// Bir paragraf ekle
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

// Paragrafa içerik ekle
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

Burada farklı düzeylerde başlıklar ve bir paragraf gibi satır içi yapı öğeleri oluşturuyoruz ve bunlara içerik ekliyoruz.

## Adım 6: Etiketli PDF belgesini kaydedin

Son olarak etiketli PDF dokümanını kaydediyoruz.

```csharp
// Etiketli PDF belgesini kaydedin
document.Save(dataDir + "InlineStructureElements.pdf");
```

### .NET için Aspose.PDF'yi kullanarak Satır İçi Yapı Elemanları için örnek kaynak kodu 

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

// Kök Yapı Elemanını Al
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

// Etiketli PDF Belgesini Kaydet
document.Save(dataDir + "InlineStructureElements.pdf");

```

## Çözüm

Tebrikler! .NET için Aspose.PDF ile satır içi yapı öğelerini nasıl kullanacağınızı öğrendiniz. Artık farklı düzeylerde ve paragraflarda başlıklar kullanarak PDF belgenizde hiyerarşik bir yapı oluşturabilirsiniz. Aspose.PDF'nin tüm potansiyelini keşfetmek için diğer özelliklerini keşfedin.

### SSS

#### S: Bir PDF belgesinde satır içi yapı öğeleri nelerdir ve hiyerarşik bir yapı oluşturmaya nasıl katkıda bulunurlar?

A: Farklı düzeylerdeki başlıklar ve paragraflar gibi PDF belgesindeki satır içi yapı öğeleri, içeriği yapılandırılmış bir şekilde düzenleyen ve sunan hiyerarşik bir yapı oluşturmak için kullanılır. Bu öğeler, belge içinde net bir hiyerarşi ve bilgi akışı oluşturmanıza olanak tanır.

#### S: Satır içi yapı öğeleri bir PDF belgesinin okunabilirliğini ve organizasyonunu nasıl artırabilir?

A: Satır içi yapı öğeleri, özellikle başlıklar ve paragraflar, mantıksal bir yapı sağlayarak bir PDF belgesinin okunabilirliğini ve organizasyonunu iyileştirmeye yardımcı olur. Başlıklar farklı önem düzeylerini belirtir ve okuyucuların içerikte gezinmesine yardımcı olurken, paragraflar ilgili bilgileri bir araya getirir.

#### S: Aspose.PDF for .NET, satır içi yapı öğelerinin kullanımını nasıl kolaylaştırır?

A: .NET için Aspose.PDF, başlıklar ve paragraflar gibi satır içi yapı öğelerini oluşturmak ve düzenlemek için sınıflar ve yöntemler sunar. Bu öğeler özelleştirilebilir, hiyerarşik olarak düzenlenebilir ve belgenin görsel sunumunu ve erişilebilirliğini iyileştirmek için içerikle zenginleştirilebilir.

####  S: Amacı nedir?`taggedContent` object in relation to inline structure elements?

 A:`taggedContent` nesne, elde edilen`TaggedContent` birinin mülkü`Document`, satır içi yapı öğeleri de dahil olmak üzere yapılandırılmış öğelerle çalışmanıza olanak tanır. Belge içinde başlıklar ve paragraflar oluşturmanıza, özelleştirmenize ve düzenlemenize olanak tanır.

#### S: Satır içi yapı öğeleri net bir belge hiyerarşisi oluşturmaya nasıl yardımcı olur?

A: Çeşitli düzeylerdeki başlıklar gibi satır içi yapı öğeleri, belgede net ve iyi tanımlanmış bir hiyerarşi oluşturmaya katkıda bulunur. Okuyucular ana konuları, alt konuları ve ilgili içerikleri hızla belirleyebilir, bu da belgenin gezinmesini ve anlaşılmasını kolaylaştırır.

#### S: Aspose.PDF for .NET'i kullanarak satır içi yapı öğelerinin görünümünü ve biçimlendirmesini özelleştirebilir miyim?

A: Evet, satır içi yapı öğelerinin görünümünü ve biçimlendirmesini özelleştirebilirsiniz. Başlıklar ve paragraflar için istediğiniz görsel sunumu elde etmek için yazı tipi stilleri, boyutlar, renkler, hizalama, girinti ve aralık gibi özellikleri ayarlayabilirsiniz.

#### S: Aspose.PDF for .NET'te satır içi yapı öğelerini kullanarak bir PDF belgesine farklı düzeylerde başlıklar nasıl oluşturabilir ve ekleyebilirim?

 A: Farklı düzeylerde başlıklar oluşturmak için şunları kullanabilirsiniz:`CreateHeaderElement` yöntemini kullanın ve ardından bunları kök yapı öğesine ekleyin. Daha sonra, her başlık öğesine içerik ekleyebilirsiniz.`CreateSpanElement` metin aralıkları oluşturma yöntemi.

#### S: PDF belgesinde listeler, madde işaretleri veya diğer içerik düzenleme türlerini oluşturmak için satır içi yapı öğelerini kullanabilir miyim?

A: Satır içi yapı öğeleri öncelikli olarak başlıklar ve paragraflar için kullanılsa da, kapsamlı bir belge yapısı için listeler, madde işaretleri, tablolar ve diğer içerik düzenleme türlerini oluşturmak amacıyla bunları Aspose.PDF for .NET tarafından sunulan diğer özellikler ile birlikte kullanabilirsiniz.

#### S: Satır içi yapı öğeleri belge erişilebilirliğine nasıl katkıda bulunur?

A: Satır içi yapı öğeleri, belge erişilebilirliğini geliştirmede önemli bir rol oynar. Uygun şekilde yapılandırılmış başlıklar ve paragraflar, ekran okuyucuların ve diğer yardımcı teknolojilerin içeriği engelli kullanıcılara doğru şekilde yorumlamasına ve iletmesine yardımcı olan net bir belge hiyerarşisi sağlar.

#### S: Etkileşimli öğeler oluşturma veya multimedya yerleştirme gibi satır içi yapı öğelerinin daha gelişmiş kullanımlarını keşfedebilir miyim?

A: Kesinlikle! Bu eğitim başlıklar ve paragraflar oluşturmaya odaklanırken, Aspose.PDF for .NET etkileşimli öğeler oluşturmak, multimedya yerleştirmek, köprü metinleri eklemek ve daha fazlası için gelişmiş özellikler sunar. Bu gelişmiş yetenekleri derinlemesine incelemek için kütüphanenin belgelerine ve örneklerine bakın.