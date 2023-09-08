---
title: Satır İçi Yapı Elemanları
linktitle: Satır İçi Yapı Elemanları
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile çevrimiçi yapısal elemanların kullanımına ilişkin adım adım kılavuz. PDF'lerinizi başlıklar ve paragraflarla düzenleyin.
type: docs
weight: 110
url: /tr/net/programming-with-tagged-pdf/inline-structure-elements/
---
Bu adım adım kılavuzda, satır içi yapı elemanlarını Aspose.PDF for .NET ile nasıl kullanacağınızı göstereceğiz. Aspose.PDF, PDF belgelerini programlı olarak değiştirmenizi sağlayan güçlü bir kütüphanedir. Satır içi yapı öğeleri, farklı düzeydeki başlıklar ve paragraflar kullanarak PDF belgenizde hiyerarşik bir yapı oluşturmanıza olanak tanır.

Kodun derinliklerine inelim ve Aspose.PDF for .NET ile satır içi yapı elemanlarının nasıl kullanılacağını öğrenelim.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. .NET için Aspose.PDF kütüphanesi kuruldu.
2. C# programlama dili hakkında temel bilgi.

## 1. Adım: Ortamı ayarlama

Başlamak için C# geliştirme ortamınızı açın ve yeni bir proje oluşturun. Projenize .NET için Aspose.PDF kütüphanesine bir referans eklediğinizden emin olun.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Belgeyi oluşturma

 İlk adım, kullanarak yeni bir PDF belgesi oluşturmaktır.`Document` sınıf.

```csharp
// PDF belgesini oluşturun
Document document = new Document();
```

## 3. Adım: Etiketli içerikle çalışın

Daha sonra üzerinde çalışacağımız belgenin etiketli içeriğini alıyoruz.

```csharp
// Belgenin etiketli içeriğini alın
ITaggedContent taggedContent = document.TaggedContent;
```

## 4. Adım: Belge başlığını ve dilini ayarlayın

Artık belge başlığını ve dilini ayarlayabiliriz.

```csharp
// Belge başlığını ve dilini tanımlayın
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## 5. Adım: Yapısal öğeleri çevrimiçi olarak ekleyin

Şimdi belgemize farklı düzeylerde başlıklar ve paragraflar gibi satır içi yapı öğeleri ekleyeceğiz.

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

// Paragraf ekle
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

// Paragrafa içerik ekleme
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

Burada farklı düzeylerde başlıklar ve paragraf gibi satır içi yapı öğeleri oluşturup bunlara içerik ekliyoruz.

## 6. Adım: Etiketli PDF belgesini kaydedin

Son olarak etiketlenen PDF belgesini kaydediyoruz.

```csharp
// Etiketli PDF belgesini kaydedin
document.Save(dataDir + "InlineStructureElements.pdf");
```

### Aspose.PDF for .NET kullanan Satır İçi Yapı Elemanları için örnek kaynak kodu 

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

// Kök Yapı Elemanını Alın
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

// Etiketli Pdf Belgesini Kaydet
document.Save(dataDir + "InlineStructureElements.pdf");

```

## Çözüm

Tebrikler! Aspose.PDF for .NET ile satır içi yapı elemanlarının nasıl kullanılacağını öğrendiniz. Artık farklı düzeylerde başlıklar ve paragraflar kullanarak PDF belgenizde hiyerarşik bir yapı oluşturabilirsiniz. Aspose.PDF'in tüm potansiyelini keşfetmek için diğer özelliklerini keşfedin.

### SSS'ler

#### S: Bir PDF belgesindeki satır içi yapı öğeleri nelerdir ve bunlar hiyerarşik bir yapı oluşturmaya nasıl katkıda bulunur?

C: Bir PDF belgesindeki farklı düzeylerdeki başlıklar ve paragraflar gibi satır içi yapı öğeleri, içeriği yapılandırılmış bir şekilde düzenleyen ve sunan hiyerarşik bir yapı oluşturmak için kullanılır. Bu öğeler, belge içinde net bir hiyerarşi ve bilgi akışı oluşturmanıza olanak tanır.

#### S: Satır içi yapı öğeleri bir PDF belgesinin okunabilirliğini ve düzenini nasıl geliştirebilir?

C: Satır içi yapı öğeleri, özellikle başlıklar ve paragraflar, mantıksal bir yapı sağlayarak PDF belgesinin okunabilirliğini ve düzenini iyileştirmeye yardımcı olur. Başlıklar farklı önem düzeylerini belirtir ve okuyucuların içerikte gezinmesine yardımcı olur; paragraflar ise ilgili bilgileri bir arada gruplandırır.

#### S: Aspose.PDF for .NET satır içi yapı elemanlarının kullanımını nasıl kolaylaştırıyor?

C: Aspose.PDF for .NET, başlıklar ve paragraflar gibi satır içi yapı öğelerini oluşturmak ve değiştirmek için sınıflar ve yöntemler sunar. Bu öğeler, belgenin görsel sunumunu ve erişilebilirliğini geliştirmek için özelleştirilebilir, hiyerarşik olarak düzenlenebilir ve içerikle zenginleştirilebilir.

####  Soru: Programın amacı nedir?`taggedContent` object in relation to inline structure elements?

 C:`taggedContent` elde edilen nesne`TaggedContent` bir mülk`Document`, satır içi yapı öğeleri de dahil olmak üzere yapılandırılmış öğelerle çalışmanıza olanak tanır. Belge içinde başlıklar ve paragraflar oluşturmanıza, özelleştirmenize ve düzenlemenize olanak tanır.

#### S: Satır içi yapı öğeleri net bir belge hiyerarşisi oluşturmaya nasıl yardımcı olur?

C: Farklı düzeylerdeki başlıklar gibi satır içi yapı öğeleri, belgede açık ve iyi tanımlanmış bir hiyerarşi oluşturulmasına katkıda bulunur. Okuyucular ana konuları, alt konuları ve ilgili içeriği hızlı bir şekilde tanımlayabilir, böylece belgede gezinmek ve anlamak daha kolay hale gelir.

#### S: Satır içi yapı elemanlarının görünümünü ve formatını Aspose.PDF for .NET kullanarak özelleştirebilir miyim?

C: Evet, satır içi yapı öğelerinin görünümünü ve biçimlendirmesini özelleştirebilirsiniz. Başlıklar ve paragraflar için istenen görsel sunumu elde etmek amacıyla yazı tipi stilleri, boyutları, renkleri, hizalaması, girintisi ve aralığı gibi özellikleri ayarlayabilirsiniz.

#### S: Aspose.PDF for .NET'teki satır içi yapı öğelerini kullanarak bir PDF belgesine farklı düzeylerde başlıkları nasıl oluşturabilirim ve eklerim?

 C: Düğmeyi kullanarak farklı düzeylerde başlıklar oluşturabilirsiniz.`CreateHeaderElement` yöntemini kullanın ve ardından bunları kök yapı öğesine ekleyin. Daha sonra, her bir başlık öğesine içerik ekleyebilirsiniz.`CreateSpanElement` metin aralıkları oluşturma yöntemi.

#### S: Bir PDF belgesinde listeler, madde işaretleri veya diğer içerik organizasyonu türlerini oluşturmak için satır içi yapı öğelerini kullanabilir miyim?

C: Satır içi yapı elemanları öncelikle başlıklar ve paragraflar için kullanılsa da bunları Aspose.PDF for .NET'in sunduğu diğer özelliklerle birlikte kullanarak kapsamlı bir içerik organizasyonu için listeler, madde işaretleri, tablolar ve diğer içerik organizasyonu türlerini oluşturabilirsiniz. belge yapısı.

#### S: Satır içi yapı öğeleri belge erişilebilirliğine nasıl katkıda bulunur?

C: Satır içi yapı öğeleri belge erişilebilirliğini artırmada çok önemli bir rol oynar. Düzgün yapılandırılmış başlıklar ve paragraflar, içeriğin engelli kullanıcılara doğru şekilde yorumlanması ve iletilmesinde ekran okuyuculara ve diğer yardımcı teknolojilere yardımcı olan net bir belge hiyerarşisi sağlar.

#### S: Satır içi yapı öğelerinin etkileşimli öğeler oluşturma veya multimedya yerleştirme gibi daha gelişmiş kullanımlarını keşfedebilir miyim?

C: Kesinlikle! Bu eğitim başlıklar ve paragraflar oluşturmaya odaklanırken, Aspose.PDF for .NET etkileşimli öğeler oluşturmak, multimedya yerleştirmek, köprüler eklemek ve daha fazlası için gelişmiş özellikler sunar. Bu gelişmiş yetenekleri ayrıntılı olarak incelemek için kitaplığın belgelerine ve örneklerine bakın.