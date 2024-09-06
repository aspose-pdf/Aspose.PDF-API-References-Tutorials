---
title: PDF Dosyasında Metin Ve Resim Paragraf Olarak
linktitle: PDF Dosyasında Metin Ve Resim Paragraf Olarak
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasına satır içi paragraflar olarak metin ve resim eklemeyi öğrenin.
type: docs
weight: 530
url: /tr/net/programming-with-text/text-and-image-as-paragraph/
---
Bu eğitim, .NET için Aspose.PDF kullanarak PDF dosyasına satır içi paragraflar olarak metin ve resim eklemeyi açıklar. Sağlanan C# kaynak kodu, işlemi adım adım gösterir.

## Ön koşullar

Eğitime başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dilinin temel bilgisi.
- .NET kütüphanesi için Aspose.PDF yüklendi. Bunu Aspose web sitesinden edinebilir veya projenize yüklemek için NuGet'i kullanabilirsiniz.

## Adım 1: Projeyi kurun

Tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturarak başlayın ve .NET için Aspose.PDF kitaplığına bir başvuru ekleyin.

## Adım 2: Gerekli ad alanlarını içe aktarın

Gerekli ad alanlarını içe aktarmak için C# dosyanızın başına aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## Adım 3: Belge dizinine giden yolu ayarlayın

 Belge dizininize giden yolu kullanarak ayarlayın`dataDir` değişken:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

## Adım 4: Yeni bir Belge ve Sayfa Oluşturun

 Yeni bir tane oluştur`Document` nesneyi seçin ve bir sayfayı sayfalar koleksiyonuna ekleyin:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Adım 5: Bir TextFragment oluşturun ve bunu bir paragraf olarak ekleyin

 Bir tane oluştur`TextFragment` nesneyi seçin ve sayfanın paragraf koleksiyonuna ekleyin:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Adım 6: Satır içi paragraf olarak bir resim ekleyin

 Bir tane oluştur`Aspose.Pdf.Image` nesneyi yazın ve onu bir önceki paragraftan hemen sonra görünecek şekilde satır içi paragraf olarak ayarlayın:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // İsteğe bağlı: Görüntü yüksekliğini ayarlayın
image.FixWidth = 100; // İsteğe bağlı: Görüntü genişliğini ayarlayın
page.Paragraphs.Add(image);
```

 Yer değiştirmek`"aspose-logo.jpg"` Gerçek resim dosya adı ile birlikte, isteğe bağlı resim yüksekliğini ve genişliğini istediğiniz gibi ayarlayabilirsiniz.

## Adım 7: Satır içi paragraf olarak başka bir TextFragment ekleyin

 Yeniden başlat`TextFragment` Farklı içerikli nesneyi satır içi paragraf olarak ekleyin:

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

 Değiştirdiğinizden emin olun`"TextAndImageAsParagraph_out.pdf"` İstenilen çıktı dosya adı ile.

### .NET için Aspose.PDF kullanarak Metin ve Resim Olarak Paragraf için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge örneğini örneklendir
Document doc = new Document();
// Belge örneğinin sayfalar koleksiyonuna sayfa ekle
Page page = doc.Pages.Add();
// TextFragmnet Oluştur
TextFragment text = new TextFragment("Hello World.. ");
// Sayfa nesnesinin paragraf koleksiyonuna metin parçası ekle
page.Paragraphs.Add(text);
// Bir görüntü örneği oluşturun
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Resmi satır içi paragraf olarak ayarlayın, böylece hemen sonra görünür
// Önceki paragraf nesnesi (TextFragment)
image.IsInLineParagraph = true;
// Görüntü dosya yolunu belirtin
image.File = dataDir + "aspose-logo.jpg";
// Resim Yüksekliğini Ayarla (isteğe bağlı)
image.FixHeight = 30;
// Resim Genişliğini Ayarla (isteğe bağlı)
image.FixWidth = 100;
// Sayfa nesnesinin paragraf koleksiyonuna resim ekle
page.Paragraphs.Add(image);
// TextFragment nesnesini farklı içeriklerle yeniden başlatın
text = new TextFragment(" Hello Again..");
// TextFragment'ı satır içi paragraf olarak ayarla
text.IsInLineParagraph = true;
// Yeni oluşturulan TextFragment'ı sayfanın paragraf koleksiyonuna ekle
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesine satır içi paragraflar olarak metin ve resim eklemeyi başarıyla öğrendiniz. Bu eğitim, projeyi kurmaktan değiştirilmiş belgeyi kaydetmeye kadar adım adım bir kılavuz sağladı. Artık bu kodu kendi C# projelerinize dahil ederek PDF dosyalarındaki metin ve resimlerin düzenini özelleştirebilirsiniz.

### SSS

#### S: "PDF Dosyası İçinde Metin ve Resim Paragraf Olarak" eğitiminin amacı nedir?

A: "PDF Dosyasında Paragraf Olarak Metin ve Görüntü" öğreticisinin amacı, kullanıcılara .NET için Aspose.PDF kullanarak bir PDF belgesine hem metin hem de görüntüleri satır içi paragraflar olarak nasıl ekleyebilecekleri konusunda rehberlik etmektir. Öğretici, işlemi göstermek için adım adım talimatlar ve C# kod örnekleri sağlar.

#### S: Bu eğitim, satır içi paragraflara metin ve resim eklemede nasıl yardımcı oluyor?

A: Bu eğitim, kullanıcıların hem metni hem de görselleri bir PDF belgesi içinde satır içi paragraflar olarak dahil etmek için Aspose.PDF for .NET'i nasıl kullanacaklarını anlamalarına yardımcı olur. Sağlanan adımları ve kod örneklerini izleyerek kullanıcılar, metin ve görselleri birleştiren özel düzenlere sahip PDF dosyaları oluşturabilir.

#### S: Bu eğitimi takip etmek için hangi ön koşullar gereklidir?

A: Eğitime başlamadan önce, C# programlama dili hakkında temel bir anlayışa sahip olmalısınız. Ek olarak, .NET için Aspose.PDF kütüphanesinin yüklü olması gerekir. Bunu Aspose web sitesinden edinebilir veya NuGet kullanarak projenize yükleyebilirsiniz.

#### S: Bu eğitimi takip edecek şekilde projemi nasıl kurarım?

A: Başlamak için, tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturun ve Aspose.PDF for .NET kitaplığına bir referans ekleyin. Bu, PDF belgeleri, metin parçaları ve resimlerle çalışmak için kitaplığın özelliklerini kullanmanıza olanak tanır.

#### S: Bu eğitimi kullanarak bir PDF'e birden fazla metin ve resim paragrafı ekleyebilir miyim?

C: Evet, aynı PDF belgesine hem metin hem de resim paragraflarının birden fazla örneğini eklemek için sağlanan kod örneklerini kullanabilirsiniz. Bu eğitim, satır içi paragrafların nasıl oluşturulacağını gösterir ve farklı metin ve resim kombinasyonlarını eklemeyi kolaylaştırır.

#### S: Metin paragraflarının ve görsellerin içeriğini ve görünümünü nasıl belirleyebilirim?

 A: Eğitimde nasıl oluşturulacağı gösterilmektedir`TextFragment`metin paragraflarını ve nesneleri temsil eden nesneler`Aspose.Pdf.Image` Görüntüleri temsil eden nesneler. Sağlanan kod örneklerini kullanarak hem metnin hem de görüntülerin içeriğini, boyutlarını ve görünümünü özelleştirebilirsiniz.

#### S: Satır içi paragrafların düzenini ayarlayabilir miyim?

 A: Evet, satır içi paragrafların düzenini sayfadaki konumlarını, boyutlarını ve sıralarını kontrol ederek ayarlayabilirsiniz. Eğitim, satır içi özniteliklerin nasıl ayarlanacağını gösterir, örneğin:`IsInLineParagraph`, metin ve resim paragraflarının düzenini kontrol etmek için.

#### S: Değiştirilen PDF belgesini nasıl kaydedebilirim?

 A: Değiştirilen PDF belgesini kaydetmek için şunu kullanabilirsiniz:`Save` yöntemi`Document` nesne. Eğitim, ortaya çıkan PDF belgesinin nasıl kaydedileceğini gösteren kod örnekleri sağlar.