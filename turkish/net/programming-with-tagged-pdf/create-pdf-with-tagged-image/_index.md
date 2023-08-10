---
title: Etiketli Görüntü ile PDF Oluşturun
linktitle: Etiketli Görüntü ile PDF Oluşturun
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak etiketli görüntü ile PDF oluşturmak için adım adım kılavuz.
type: docs
weight: 40
url: /tr/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak etiketli bir görüntü ile bir PDF belgesinin nasıl oluşturulacağına dair adım adım bir kılavuz sağlayacağız. Aspose.PDF, PDF belgelerini program aracılığıyla oluşturmanıza, değiştirmenize ve dönüştürmenize izin veren güçlü bir kitaplıktır. Aspose.PDF'nin etiketli içerik yapısı özelliklerini kullanarak, etiketli görselleri PDF belgenize ekleyebilirsiniz.

## Önkoşullar

Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

1. .NET çerçevesiyle yüklenen Visual Studio.
2. .NET için Aspose.PDF kitaplığı.

## Adım 1: Proje Kurulumu

Başlamak için Visual Studio'da yeni bir proje oluşturun ve Aspose.PDF for .NET kitaplığına bir referans ekleyin. Kütüphaneyi Aspose resmi sitesinden indirebilir ve makinenize kurabilirsiniz.

## 2. Adım: Gerekli ad alanlarını içe aktarın

Aspose.PDF tarafından sağlanan sınıflara ve yöntemlere erişmek için gereken ad alanlarını C# kod dosyanıza aktarın:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## 3. Adım: Etiketli bir görselle PDF belgesi oluşturma

Etiketli bir görüntü ile bir PDF belgesi oluşturmak için aşağıdaki kodu kullanın:

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

Bu kod, boş bir PDF belgesi oluşturur ve Aspose.PDF tarafından sağlanan yöntemleri kullanarak etiketlenmiş bir görüntü ekler. Resim alternatif metin, başlık ve etiket ile belirtilir.

## 4. Adım: PDF Belgesini Kaydetme

PDF belgesini kaydetmek için aşağıdaki kodu kullanın:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Bu kod, etiketli görüntü içeren PDF belgesini belirtilen bir dosyaya kaydeder.

### Aspose.PDF for .NET kullanarak Etiketli Görüntü ile PDF Oluşturma için örnek kaynak kodu 
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
// 300 DPI çözünürlüklü görüntü ekleyin (varsayılan olarak)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// PDF Belgesini Kaydet
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kullanarak etiketli bir görüntü ile PDF belgesi oluşturmayı öğrendiniz. Etiketli görüntüler, PDF belgenize ek, yapılandırılmış bilgiler ekler.

### SSS

#### S: Aspose.PDF for .NET kullanarak etiketli bir görüntü ile bir PDF belgesi oluşturmanın amacı nedir?

C: Aspose.PDF for .NET kullanarak etiketli görüntü içeren bir PDF belgesi oluşturmak, belgenin içeriğine etiketli görüntüler eklemenizi sağlar. Etiketli resimler, alternatif metin ve başlıklar gibi yapılandırılmış bilgiler sağlayarak erişilebilirliği ve düzeni geliştirir.

#### S: Aspose.PDF kitaplığı, etiketli bir görüntü ile bir PDF belgesi oluşturmaya nasıl yardımcı olur?

Y: Aspose.PDF for .NET, PDF belgelerini program aracılığıyla oluşturmak, değiştirmek ve dönüştürmek için işlevsellikler sağlayan güçlü bir kitaplıktır. Bu öğreticide, kitaplığın etiketli içerik yapısı özellikleri, PDF belgesine etiketli bir görüntü eklemek için kullanılır.

#### S: Aspose.PDF for .NET kullanarak etiketli görsel içeren bir PDF belgesi oluşturmak için ön koşullar nelerdir?

C: Başlamadan önce, Visual Studio'nun .NET çerçevesiyle kurulu olduğundan ve projenizde Aspose.PDF for .NET kitaplığına referans verildiğinden emin olun.

#### S: Sağlanan C# kodu, etiketli görüntü içeren bir PDF belgesini nasıl oluşturur?

C: Kod, bir PDF belgesinin nasıl oluşturulacağını, etiketli bir görüntü öğesinin nasıl tanımlanacağını ve bunun belgenin içeriğine nasıl ekleneceğini gösterir. Etiketlenen görüntü, Aspose.PDF tarafından sağlanan yöntemleri kullanan alternatif metin, başlık ve etiket içerir.

#### S: Etiketli görsel için farklı görsel formatları kullanabilir miyim?

C: Evet, etiketli görüntü için JPEG, PNG, GIF vb. tercih ettiğiniz biçim.

#### S: Etiketli görsellerde alternatif metin (alt metin) nasıl kullanılır?

 C: Alternatif metin, görselin görme engelli kullanıcılar için ekran okuyucular tarafından yüksek sesle okunan metinsel bir açıklamasını sağlar. Sağlanan kodda, alternatif metin kullanılarak ayarlanır`AlternativeText` mülkiyeti`IllustrationElement` etiketli görseli temsil eder.

####  S: nasıl`SetTitle` method contribute to the PDF document's tagged image?

 C:`SetTitle` yöntemi, PDF belgesinin etiketli içeriğinin başlığını ayarlar ve etiketli görüntü için ek bağlam sağlar. Bu başlık, etiketlenen içeriğin amacını veya konusunu belirlemeye yardımcı olabilir.

#### S: Etiketlenen görüntünün etiketini ve başlığını özelleştirebilir miyim?

 C: Evet, etiketli görüntünün etiketini ve başlığını kullanarak özelleştirebilirsiniz.`SetTag` Ve`Title` yöntemleri`IllustrationElement`. Kod örneği, etiketin "Şek" ve başlığın "Resim 1" olarak nasıl ayarlanacağını gösterir.

#### S: Etiketlenen görüntünün erişilebilir ve erişilebilirlik standartlarına uygun olduğundan nasıl emin olabilirim?

C: Aspose.PDF'nin etiketli içerik yapısı özelliklerini kullanarak ve alternatif metin ve diğer ilgili bilgileri sağlayarak, etiketli görselin erişilebilirliğine katkıda bulunuyorsunuz. Erişilebilirlik standartlarına uygunluğun sağlanması, alternatif metin ve belge yapısı için en iyi uygulamaların izlenmesini içerir.

#### S: Benzer teknikler kullanılarak aynı PDF belgesine birden çok etiketli görüntü eklemek mümkün müdür?

 C: Evet, benzer teknikleri kullanarak aynı PDF belgesine birden çok etiketli görüntü ekleyebilirsiniz. Ek oluşturursunuz`IllustrationElement` her etiketli görüntü için örnekler ve bunların özelliklerini gerektiği gibi özelleştirin.