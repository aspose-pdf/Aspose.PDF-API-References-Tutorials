---
title: Etiketli Resimle PDF Oluştur
linktitle: Etiketli Resimle PDF Oluştur
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak etiketli görüntüyle PDF oluşturmak için adım adım kılavuz.
type: docs
weight: 40
url: /tr/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
Bu eğitimde size Aspose.PDF for .NET kullanarak etiketli görsel içeren bir PDF belgesinin nasıl oluşturulacağı konusunda adım adım bir kılavuz sunacağız. Aspose.PDF, PDF belgelerini programlı olarak oluşturmanıza, değiştirmenize ve dönüştürmenize olanak tanıyan güçlü bir kütüphanedir. Aspose.PDF'in etiketli içerik yapısı özelliklerini kullanarak etiketli görüntüleri PDF belgenize ekleyebilirsiniz.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1. .NET framework ile yüklenen Visual Studio.
2. .NET için Aspose.PDF kütüphanesi.

## Adım 1: Proje Kurulumu

Başlamak için Visual Studio'da yeni bir proje oluşturun ve Aspose.PDF for .NET kitaplığına bir referans ekleyin. Kütüphaneyi Aspose resmi web sitesinden indirebilir ve makinenize kurabilirsiniz.

## 2. Adım: Gerekli ad alanlarını içe aktarın

Aspose.PDF tarafından sağlanan sınıflara ve yöntemlere erişmek için gereken ad alanlarını C# kod dosyanıza aktarın:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## 3. Adım: Etiketli görselle PDF belgesi oluşturma

Etiketli bir görsele sahip bir PDF belgesi oluşturmak için aşağıdaki kodu kullanın:

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

Bu kod boş bir PDF belgesi oluşturur ve Aspose.PDF tarafından sağlanan yöntemleri kullanarak etiketli bir görüntü ekler. Resim alternatif metin, başlık ve etiketle belirtilir.

## Adım 4: PDF Belgesini Kaydetme

PDF belgesini kaydetmek için aşağıdaki kodu kullanın:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Bu kod, etiketli görüntünün bulunduğu PDF belgesini belirtilen bir dosyaya kaydeder.

### Aspose.PDF for .NET kullanarak Etiketli Görüntüyle PDF Oluşturmak için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
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
// 300 DPI çözünürlüğe sahip resim ekleyin (varsayılan olarak)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// PDF Belgesini Kaydet
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak etiketli bir görüntüye sahip bir PDF belgesinin nasıl oluşturulacağını öğrendiniz. Etiketli görseller PDF belgenize ek, yapılandırılmış bilgiler ekler.

### SSS'ler

#### S: Aspose.PDF for .NET kullanarak etiketli bir görüntü içeren bir PDF belgesi oluşturmanın amacı nedir?

C: Aspose.PDF for .NET kullanarak etiketli bir görüntü içeren bir PDF belgesi oluşturmak, belgenin içeriğine etiketli görüntüler eklemenizi sağlar. Etiketli görseller, alternatif metin ve başlıklar gibi yapılandırılmış bilgiler sağlayarak erişilebilirliği ve organizasyonu geliştirir.

#### S: Aspose.PDF kütüphanesi etiketli görsel içeren bir PDF belgesi oluşturmaya nasıl yardımcı olur?

C: Aspose.PDF for .NET, PDF belgelerini programlı olarak oluşturmaya, işlemeye ve dönüştürmeye yönelik işlevler sağlayan güçlü bir kitaplıktır. Bu eğitimde, kitaplığın etiketli içerik yapısı özellikleri, PDF belgesine etiketli bir görüntü eklemek için kullanılır.

#### S: Aspose.PDF for .NET kullanarak etiketli bir görüntüye sahip bir PDF belgesi oluşturmanın önkoşulları nelerdir?

C: Başlamadan önce, Visual Studio'nun .NET framework ile kurulu olduğundan ve projenizde .NET için Aspose.PDF kütüphanesinin referans alındığından emin olun.

#### S: Sağlanan C# kodu, etiketli bir görüntüye sahip bir PDF belgesini nasıl oluşturur?

C: Kod, bir PDF belgesinin nasıl oluşturulacağını, etiketli bir görüntü öğesinin nasıl tanımlanacağını ve bunun belgenin içeriğine nasıl ekleneceğini gösterir. Etiketlenen görüntü, Aspose.PDF tarafından sağlanan yöntemleri kullanan alternatif metin, başlık ve etiket içerir.

#### S: Etiketli görsel için farklı görsel formatlarını kullanabilir miyim?

C: Evet, etiketli görsel için JPEG, PNG, GIF vb. gibi farklı görsel formatları kullanabilirsiniz. Eğitimde sağlanan kod örneği bir JPEG görseli kullanıyor ancak bunu, içindeki bir görsel dosyasının yoluyla değiştirebilirsiniz. tercih ettiğiniz format.

#### S: Etiketli görsellerde alternatif metin (alt metin) nasıl kullanılır?

 C: Alternatif metin, görselin, görme engelli kullanıcılar için ekran okuyucular tarafından yüksek sesle okunan metinsel bir açıklamasını sağlar. Sağlanan kodda, alternatif metin şu şekilde ayarlanır:`AlternativeText` mülkiyeti`IllustrationElement` etiketlenen görüntüyü temsil eder.

####  S: Nasıl`SetTitle` method contribute to the PDF document's tagged image?

 C:`SetTitle` yöntemi, etiketli görüntü için ek bağlam sağlayarak PDF belgesinin etiketli içeriğinin başlığını belirler. Bu başlık, etiketlenen içeriğin amacını veya konusunu belirlemenize yardımcı olabilir.

#### S: Etiketlenen görselin etiketini ve başlığını özelleştirebilir miyim?

 C: Evet, etiketli görselin etiketini ve başlığını kullanarak özelleştirebilirsiniz.`SetTag` Ve`Title` yöntemleri`IllustrationElement`. Kod örneği, etiketin "Şekil" ve başlığın "Resim 1" olarak nasıl ayarlanacağını gösterir.

#### S: Etiketlenen görselin erişilebilir olduğundan ve erişilebilirlik standartlarıyla uyumlu olduğundan nasıl emin olabilirim?

C: Aspose.PDF'in etiketli içerik yapısı özelliklerini kullanarak ve alternatif metin ile diğer ilgili bilgileri sağlayarak, etiketlenen görselin erişilebilirliğine katkıda bulunursunuz. Erişilebilirlik standartlarına uygunluğun sağlanması, alternatif metin ve belge yapısına ilişkin en iyi uygulamaların izlenmesini içerir.

#### S: Benzer teknikler kullanılarak aynı PDF belgesine birden fazla etiketli görüntü eklemek mümkün müdür?

 C: Evet, benzer teknikleri kullanarak aynı PDF belgesine birden fazla etiketli görüntü ekleyebilirsiniz. Ek oluşturacaksınız`IllustrationElement` Her etiketli görüntü için örnekler oluşturun ve özelliklerini gerektiği gibi özelleştirin.