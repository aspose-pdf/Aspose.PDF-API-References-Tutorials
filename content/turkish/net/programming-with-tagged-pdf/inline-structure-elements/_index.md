---
title: Satır İçi Yapı Elemanları
linktitle: Satır İçi Yapı Elemanları
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile çevrimiçi yapısal öğelerin kullanımına ilişkin adım adım kılavuz. PDF'lerinizi başlıklar ve paragraflarla düzenleyin.
type: docs
weight: 110
url: /tr/net/programming-with-tagged-pdf/inline-structure-elements/
---
## giriiş

Günümüzün dijital dünyasında erişilebilir ve iyi yapılandırılmış belgeler oluşturmak hayati önem taşır. Kendinizi bir PDF'de gezinirken bulduysanız ve metin denizinde kaybolduysanız, iyi bir organizasyonun önemini biliyorsunuzdur. PDF'nizdeki öğeleri etiketlemek erişilebilirliği artırabilir ve ekran okuyucuların içeriği yorumlamasını kolaylaştırabilir. Bu kılavuzda, çalışmanızın belge yapılandırmasında modern standartları karşılamasını sağlayarak etiketli PDF belgeleri oluşturmak için Aspose.PDF for .NET'i kullanmaya derinlemesine bakıyoruz.

## Ön koşullar

Aksiyona geçmeden önce, takip etmeniz gereken her şeye sahip olduğunuzdan emin olalım:

1. Temel C# Bilgisi: C# programlama ve .NET framework temellerine aşinalık şarttır.
2. Visual Studio Kurulu: Kodunuzu yazıp çalıştırmak için Visual Studio gibi bir IDE'ye ihtiyacınız olacak.
3.  Aspose.PDF for .NET: Aspose.PDF for .NET'i indirip kurduğunuzdan emin olun. Bunu şuradan alabilirsiniz:[indirme bağlantısı](https://releases.aspose.com/pdf/net/).
4. Geçici Lisans: Bu isteğe bağlıdır, ancak tüm özellikleri sınırlama olmaksızın değerlendirmek istiyorsanız, bir tane edinmeyi düşünün.[geçici lisans](https://purchase.aspose.com/temporary-license/).

Bu ön koşulları sağladığınızda, ilk etiketli PDF belgenizi oluşturmaya hazırsınız!

## Paketleri İçe Aktar

Başlamak için gerekli paketleri içe aktaralım. Bu, projenizin Aspose.PDF kütüphanesinin yeteneklerinden yararlanmasını sağlar.

1. Visual Studio projenizi açın.
2. Aspose.PDF kütüphanesine bir referans ekleyin. Henüz eklemediyseniz, yüklemek için NuGet Paket Yöneticisi'ni kullanabilirsiniz.
3. C# dosyanızın en üstüne aşağıdaki ad alanlarını ekleyin:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Bu ithalatları yaptığınızda başarıya hazırsınız demektir.

## Kod Ayrıntısı: Etiketli PDF Oluşturmak İçin Adım Adım Kılavuz

Artık her şey hazır olduğuna göre, kodu adım adım parçalayalım. Başlıklar ve paragraflar gibi yapılandırılmış öğelerle etiketli bir PDF oluşturacağız ve daha iyi erişilebilirlik sağlayacağız.

### Adım 1: Belge Dizinini Ayarlayın

Öncelikle belgenizin kaydedileceği yolu ayarlayın. Düzenli bir dosya yapısı korumak iyi bir fikirdir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Gerçek yolunuzla değiştirin
```

### Adım 2: Bir PDF Belgesi Örneği Oluşturun

 Sonra, şunun bir örneğini oluşturun:`Document` PDF içeriklerinizin konteyneri olarak hizmet edecek sınıf.

```csharp
Document document = new Document();
```

### Adım 3: Etiketli İçeriğe Erişim

Şimdi, belgenin etiketli içeriğine erişin. Sihir burada gerçekleşir—içeriği etiketleyerek erişilebilirliğini artırırız.

```csharp
ITaggedContent taggedContent = document.TaggedContent;    
```

### Adım 4: Başlığı ve Dili Ayarlayın

PDF belgeniz için bir başlık ve dil belirlemek hem kullanıcılar hem de ekran okuyucular için önemlidir. Bu, belgenizi daha bilgilendirici ve erişilebilir hale getirir.

```csharp
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

### Adım 5: Kök Yapı Elemanını Alın

Belgenize öğeler eklemeye başlayalım. İlk olarak, belgenizin yapısını oluşturmak için temel görevi gören etiketli içeriğin kök yapı öğesini edinin.

```csharp
StructureElement rootElement = taggedContent.RootElement;
```

### Adım 6: Başlık Öğeleri Oluşturun

Şimdi başlık öğeleri oluşturma zamanı. Bu, içeriği bir hiyerarşiye göre düzenlemeye yardımcı olacaktır. Altı düzeyde başlık oluşturacağız.

```csharp
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
```

### Adım 7: Kök Elemana Başlıklar Ekleyin

Başlık öğelerini oluşturduktan sonra, bunları kök öğeye ekleyin. Bu, belgenin yapısal hiyerarşisini oluşturur.

```csharp
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
```

### Adım 8: Her Başlığa Metin Ekleyin

Şimdi, her başlığa biraz metin ekleyelim. Bu basit bir işlemdir ancak belgenizi kullanışlı hale getirmek için hayati önem taşır. 

```csharp
// H1
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);

// Yukarıda gösterildiği gibi H2 - H6 için tekrarlayın
```

### Adım 9: Bir Paragraf Elemanı Oluşturun

Sonra, bir paragraf öğesi ekleyelim. Bu, PDF'nizin ana içerik alanı olarak hizmet edecektir. 

```csharp
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
```

### Adım 10: Paragrafa Metin Ekleyin

Artık paragraf öğemiz olduğuna göre, onu metinle doldurmanın zamanı geldi. İçeriğinizi oluşturmak için birden fazla aralık ekleyebilirsiniz.

```csharp
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
// Gerektiğinde ek aralıklar eklemeye devam edin
```

### Adım 11: Etiketli PDF Belgesini Kaydedin

Son olarak, tüm içeriğinizi ekledikten sonra belgenizi kaydetmeniz gerekiyor. Hadi bitirelim!

```csharp
document.Save(dataDir + "InlineStructureElements.pdf");
```

Ve işte! Artık yapılandırılmış ve erişilebilir etiketli bir PDF belgeniz var.

## Çözüm

Etiketli PDF belgeleri oluşturmak göz korkutucu görünebilir, ancak .NET için Aspose.PDF ile bu çok kolay! Bu adım adım kılavuzu izleyerek, belge yapılandırmanın temellerinde ustalaştınız. Unutmayın, PDF'nizi düzgün bir şekilde etiketlemek erişilebilirliğini artırır ve değerli içeriğinizin daha geniş bir kitleye ulaşmasını sağlar. Öyleyse, devam edin ve PDF'lerinizi yalnızca güzel değil, aynı zamanda kullanıcı dostu yapın!

## SSS

### Etiketli PDF nedir?
Etiketli PDF, belgenin yapısı hakkında bilgi içeren ve bu sayede engelli kullanıcıların erişimini kolaylaştıran bir PDF'dir.

### PDF'lerde etiketleme neden önemlidir?
Etiketleme erişilebilirliği artırarak ekran okuyucuların belgeyi net bir şekilde yorumlamasına olanak tanır ve böylece engelli kullanıcılar için daha iyi bir deneyim sunar.

### Aspose.PDF'yi ücretsiz kullanabilir miyim?
 Evet, Aspose.PDF for .NET'i şu şekilde değerlendirebilirsiniz:[ücretsiz deneme](https://releases.aspose.com/).

### Aspose.PDF için desteği nereden alabilirim?
 Desteğe şuradan erişilebilir:[Aspose destek forumu](https://forum.aspose.com/c/pdf/10).

### Aspose.PDF for .NET lisansını nasıl satın alabilirim?
 Lisansı doğrudan şu adresten satın alabilirsiniz:[satın alma sayfası](https://purchase.aspose.com/buy).