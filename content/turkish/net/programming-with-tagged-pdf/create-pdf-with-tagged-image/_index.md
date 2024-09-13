---
title: Etiketli Resimle PDF Oluştur
linktitle: Etiketli Resimle PDF Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak etiketli görsellerle PDF oluşturmaya yönelik adım adım kılavuz.
type: docs
weight: 40
url: /tr/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak etiketli bir resimle PDF belgesi oluşturma konusunda adım adım bir kılavuz sunacağız. Aspose.PDF, PDF belgelerini programatik olarak oluşturmanıza, düzenlemenize ve dönüştürmenize olanak tanıyan güçlü bir kütüphanedir. Aspose.PDF'nin etiketli içerik yapısı özelliklerini kullanarak, PDF belgenize etiketli resimler ekleyebilirsiniz.

## Ön koşullar

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

1. .NET framework ile Visual Studio kuruldu.
2. .NET için Aspose.PDF kütüphanesi.

## Adım 1: Proje Kurulumu

Başlamak için, Visual Studio'da yeni bir proje oluşturun ve Aspose.PDF for .NET kütüphanesine bir referans ekleyin. Kütüphaneyi Aspose resmi web sitesinden indirebilir ve makinenize kurabilirsiniz.

## Adım 2: Gerekli ad alanlarını içe aktarın

C# kod dosyanıza, Aspose.PDF tarafından sağlanan sınıflara ve yöntemlere erişmek için gereken ad alanlarını içe aktarın:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Adım 3: Etiketli bir resimle PDF belgesi oluşturma

Etiketli bir resim içeren bir PDF belgesi oluşturmak için aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

Bu kod boş bir PDF belgesi oluşturur ve Aspose.PDF tarafından sağlanan yöntemleri kullanarak etiketli bir resim ekler. Resim, alt metin, başlık ve etiketle belirtilir.

## Adım 4: PDF Belgesini Kaydetme

PDF belgesini kaydetmek için aşağıdaki kodu kullanın:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Bu kod, etiketli görseli içeren PDF belgesini belirtilen dosyaya kaydeder.

### .NET için Aspose.PDF kullanarak Etiketli Resimli PDF Oluşturma için örnek kaynak kodu 
```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
// Çözünürlüğü 300 DPI olan resim ekle (varsayılan olarak)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// PDF Belgesini Kaydet
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak etiketli bir resimle PDF belgesi oluşturmayı öğrendiniz. Etiketli resimler PDF belgenize ek, yapılandırılmış bilgiler ekler.

### SSS

#### S: Aspose.PDF for .NET kullanarak etiketli bir resim içeren bir PDF belgesi oluşturmanın amacı nedir?

A: Aspose.PDF for .NET kullanarak etiketli bir resimle PDF belgesi oluşturmak, belgenin içeriğine etiketli resimler eklemenize olanak tanır. Etiketli resimler, erişilebilirliği ve organizasyonu geliştiren alt metin ve başlıklar gibi yapılandırılmış bilgiler sağlar.

#### S: Aspose.PDF kütüphanesi etiketli bir görsel içeren PDF belgesi oluşturmaya nasıl yardımcı olur?

A: Aspose.PDF for .NET, PDF belgelerini programatik olarak oluşturma, düzenleme ve dönüştürme işlevleri sağlayan sağlam bir kütüphanedir. Bu eğitimde, kütüphanenin etiketli içerik yapısı özellikleri PDF belgesine etiketli bir resim eklemek için kullanılır.

#### S: Aspose.PDF for .NET kullanarak etiketli bir resim içeren bir PDF belgesi oluşturmanın ön koşulları nelerdir?

C: Başlamadan önce, Visual Studio'nun .NET Framework ile birlikte yüklü olduğundan ve projenizde .NET için Aspose.PDF kütüphanesine başvurulduğundan emin olun.

#### S: Sağlanan C# kodu etiketli bir resim içeren bir PDF belgesini nasıl oluşturur?

A: Kod, bir PDF belgesinin nasıl oluşturulacağını, etiketli bir resim öğesinin nasıl tanımlanacağını ve belgenin içeriğine nasıl ekleneceğini gösterir. Etiketli resim, Aspose.PDF tarafından sağlanan yöntemleri kullanarak alternatif metin, bir başlık ve bir etiket içerir.

#### S: Etiketli resim için farklı resim formatları kullanabilir miyim?

C: Evet, etiketli resim için JPEG, PNG, GIF vb. gibi farklı resim formatlarını kullanabilirsiniz. Eğitimde verilen kod örneği bir JPEG resmi kullanır, ancak bunu tercih ettiğiniz formattaki bir resim dosyasının yoluyla değiştirebilirsiniz.

#### S: Etiketli görsellerde alternatif metin (alt text) nasıl kullanılır?

 A: Alt text, görme engelli kullanıcılar için ekran okuyucular tarafından yüksek sesle okunan görüntünün metinsel bir açıklamasını sağlar. Sağlanan kodda, alt text,`AlternativeText` mülkiyeti`IllustrationElement` Etiketli görseli temsil ediyor.

#### S: Nasıl?`SetTitle` method contribute to the PDF document's tagged image?

 A:`SetTitle` method, PDF belgesinin etiketli içeriğinin başlığını ayarlar ve etiketli görüntü için ek bağlam sağlar. Bu başlık, etiketli içeriğin amacını veya konusunu tanımlamaya yardımcı olabilir.

#### S: Etiketli görselin etiketini ve başlığını özelleştirebilir miyim?

 A: Evet, etiketli resmin etiketini ve başlığını kullanarak özelleştirebilirsiniz.`SetTag` Ve`Title` yöntemleri`IllustrationElement`Kod örneği, etiketin "Şekil" ve başlığın "Resim 1" olarak nasıl ayarlanacağını göstermektedir.

#### S: Etiketli görselin erişilebilir ve erişilebilirlik standartlarına uygun olduğundan nasıl emin olabilirim?

A: Aspose.PDF'nin etiketli içerik yapısı özelliklerini kullanarak ve alt metin ve diğer ilgili bilgileri sağlayarak, etiketli görüntünün erişilebilirliğine katkıda bulunursunuz. Erişilebilirlik standartlarına uyumun sağlanması, alt metin ve belge yapısı için en iyi uygulamaları takip etmeyi içerir.

#### S: Benzer teknikleri kullanarak aynı PDF belgesine birden fazla etiketli resim eklemek mümkün müdür?

A: Evet, benzer teknikleri kullanarak aynı PDF belgesine birden fazla etiketli resim ekleyebilirsiniz. Ek olarak`IllustrationElement` Her etiketli görüntü için örnekler oluşturun ve bunların özelliklerini gerektiği gibi özelleştirin.