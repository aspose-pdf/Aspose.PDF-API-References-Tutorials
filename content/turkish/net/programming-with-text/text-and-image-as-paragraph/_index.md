---
title: PDF Dosyasında Paragraf Olarak Metin ve Resim
linktitle: PDF Dosyasında Paragraf Olarak Metin ve Resim
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak PDF dosyasına metin ve görüntüyü satır içi paragraflar olarak nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 530
url: /tr/net/programming-with-text/text-and-image-as-paragraph/
---
Bu eğitimde Aspose.PDF for .NET kullanılarak PDF dosyasına metin ve görüntünün satır içi paragraflar olarak nasıl ekleneceği açıklanmaktadır. Sağlanan C# kaynak kodu süreci adım adım gösterir.

## Önkoşullar

Eğiticiye devam etmeden önce aşağıdakilere sahip olduğunuzdan emin olun:

- Temel C# programlama dili bilgisi.
- Aspose.PDF for .NET kütüphanesi kuruldu. Bunu Aspose web sitesinden edinebilir veya projenize kurmak için NuGet'i kullanabilirsiniz.

## 1. Adım: Projeyi ayarlayın

Tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturarak başlayın ve Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın

Gerekli ad alanlarını içe aktarmak için C# dosyanızın başına aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## 3. Adım: Belge dizininin yolunu ayarlayın

 kullanarak belge dizininizin yolunu ayarlayın.`dataDir` değişken:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

## 4. Adım: Yeni bir Belge ve Sayfa Oluşturun

 Yeni bir tane oluştur`Document` nesnesini açın ve sayfa koleksiyonuna bir sayfa ekleyin:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Adım 5: Bir TextFragment oluşturun ve onu paragraf olarak ekleyin

 Oluşturmak`TextFragment` nesnesini seçin ve sayfanın paragraf koleksiyonuna ekleyin:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## 6. Adım: Satır içi paragraf olarak bir resim ekleyin

 Oluşturduğunuz bir`Aspose.Pdf.Image` nesnesini seçin ve önceki paragraftan hemen sonra görünecek şekilde satır içi paragraf olarak ayarlayın:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // İsteğe bağlı: Görüntü yüksekliğini ayarlayın
image.FixWidth = 100; // İsteğe bağlı: Görüntü genişliğini ayarlayın
page.Paragraphs.Add(image);
```

 Yer değiştirmek`"aspose-logo.jpg"` gerçek görüntü dosyası adını girin ve isteğe bağlı görüntü yüksekliğini ve genişliğini istediğiniz gibi ayarlayın.

## 7. Adım: Satır içi paragraf olarak başka bir TextFragment ekleyin

 Yeniden başlat`TextFragment` farklı içeriğe sahip bir nesne oluşturun ve onu satır içi paragraf olarak ekleyin:

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## Adım 8: PDF belgesini kaydedin

Değiştirilen PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

 Değiştirdiğinizden emin olun`"TextAndImageAsParagraph_out.pdf"` İstenilen çıktı dosyası adı ile.

### Aspose.PDF for .NET kullanılarak Paragraf Olarak Metin ve Resim için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge örneğini oluştur
Document doc = new Document();
// Belge örneğinin sayfa koleksiyonuna sayfa ekle
Page page = doc.Pages.Add();
// TextFragmnet'i oluştur
TextFragment text = new TextFragment("Hello World.. ");
// Sayfa nesnesinin paragraf koleksiyonuna metin parçası ekleme
page.Paragraphs.Add(text);
// Bir görüntü örneği oluşturun
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Resmi paragraftan hemen sonra görünecek şekilde satır içi paragraf olarak ayarlayın
// Önceki paragraf nesnesi (TextFragment)
image.IsInLineParagraph = true;
// Görüntü dosyası yolunu belirtin
image.File = dataDir + "aspose-logo.jpg";
// Görüntü Yüksekliğini Ayarla (isteğe bağlı)
image.FixHeight = 30;
// Resim Genişliğini Ayarla (isteğe bağlı)
image.FixWidth = 100;
// Sayfa nesnesinin paragraf koleksiyonuna resim ekleme
page.Paragraphs.Add(image);
// TextFragment nesnesini farklı içeriklerle yeniden başlatın
text = new TextFragment(" Hello Again..");
// TextFragment'i satır içi paragraf olarak ayarla
text.IsInLineParagraph = true;
// Yeni oluşturulan TextFragment'i sayfanın paragraf koleksiyonuna ekleyin
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF belgesine metin ve görüntüyü satır içi paragraflar olarak nasıl ekleyeceğinizi başarıyla öğrendiniz. Bu eğitimde, projenin kurulumundan değiştirilen belgenin kaydedilmesine kadar adım adım bir kılavuz sağlanmıştır. Artık PDF dosyalarındaki metin ve görüntülerin düzenini özelleştirmek için bu kodu kendi C# projelerinize dahil edebilirsiniz.

### SSS'ler

#### S: "PDF Dosyasında Paragraf Olarak Metin ve Görüntü" eğitiminin amacı nedir?

C: "PDF Dosyasında Paragraf Olarak Metin ve Görüntü" eğitimi, kullanıcılara Aspose.PDF for .NET kullanarak bir PDF belgesine hem metin hem de görüntüleri satır içi paragraflar olarak nasıl ekleyecekleri konusunda rehberlik etmeyi amaçlamaktadır. Öğretici, süreci göstermek için adım adım talimatlar ve C# kod örnekleri sağlar.

#### S: Bu eğitim, metin ve resimlerin satır içi paragraf olarak eklenmesine nasıl yardımcı olur?

C: Bu eğitim, kullanıcıların Aspose.PDF for .NET'i kullanarak hem metni hem de görüntüleri bir PDF belgesine satır içi paragraflar olarak nasıl dahil edeceklerini anlamalarına yardımcı olur. Sağlanan adımları ve kod örneklerini takip ederek kullanıcılar, metin ve görüntüleri birleştiren özel düzenlere sahip PDF dosyaları oluşturabilir.

#### S: Bu öğreticiyi takip etmek için hangi ön koşullar gereklidir?

C: Eğitime başlamadan önce C# programlama dili hakkında temel bilgiye sahip olmanız gerekir. Ayrıca Aspose.PDF for .NET kütüphanesinin de kurulu olması gerekir. Bunu Aspose web sitesinden edinebilir veya NuGet'i kullanarak projenize yükleyebilirsiniz.

#### S: Projemi bu öğreticiyi takip edecek şekilde nasıl ayarlayabilirim?

C: Başlamak için tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturun ve Aspose.PDF for .NET kütüphanesine bir referans ekleyin. Bu, kitaplığın PDF belgeleri, metin parçaları ve resimlerle çalışma özelliklerini kullanmanızı sağlar.

#### S: Bu eğitimi bir PDF'ye birden fazla metin ve resim paragrafı eklemek için kullanabilir miyim?

C: Evet, aynı PDF belgesine hem metin hem de resim paragraflarının birden çok örneğini eklemek için sağlanan kod örneklerini kullanabilirsiniz. Bu eğitimde satır içi paragrafların nasıl oluşturulacağı gösterilerek farklı metin ve resim kombinasyonlarının eklenmesi kolaylaşır.

#### S: Metin paragraflarının ve resimlerin içeriğini ve görünümünü nasıl belirlerim?

 C: Eğitimde nasıl oluşturulacağı gösteriliyor`TextFragment`metin paragraflarını temsil eden nesneler ve`Aspose.Pdf.Image` görüntüleri temsil eden nesneler. Sağlanan kod örneklerini kullanarak hem metnin hem de görsellerin içeriğini, boyutlarını ve görünümünü özelleştirebilirsiniz.

#### S: Satır içi paragrafların düzenini ayarlayabilir miyim?

 C: Evet, satır içi paragrafların sayfa içindeki konumlarını, boyutlarını ve sıralarını kontrol ederek düzenini ayarlayabilirsiniz. Öğretici, aşağıdaki gibi satır içi niteliklerin nasıl ayarlanacağını gösterir:`IsInLineParagraph`, metin ve resim paragraflarının düzenini kontrol etmek için.

#### S: Değiştirilen PDF belgesini nasıl kaydederim?

 C: Değiştirilen PDF belgesini kaydetmek için`Save` yöntemi`Document` nesne. Eğitimde, ortaya çıkan PDF belgesinin nasıl kaydedileceğini gösteren kod örnekleri sağlanır.