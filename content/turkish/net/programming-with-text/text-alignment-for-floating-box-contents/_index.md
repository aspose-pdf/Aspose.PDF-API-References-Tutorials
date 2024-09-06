---
title: PDF Dosyasında Yüzen Kutu İçeriği İçin Metin Hizalaması
linktitle: PDF Dosyasında Yüzen Kutu İçeriği İçin Metin Hizalaması
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki yüzen kutulardaki metni nasıl hizalayacağınızı öğrenin.
type: docs
weight: 520
url: /tr/net/programming-with-text/text-alignment-for-floating-box-contents/
---
Bu eğitim, .NET için Aspose.PDF kullanarak PDF dosyasındaki yüzen kutulardaki metnin nasıl hizalanacağını açıklar. Sağlanan C# kaynak kodu, işlemi adım adım gösterir.

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
```

## Adım 3: Belge dizinine giden yolu ayarlayın

 Belge dizininize giden yolu kullanarak ayarlayın`dataDir` değişken:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

## Adım 4: Yeni bir Belge Oluşturun

 Yeni bir tane oluştur`Document` nesne:

```csharp
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

## Adım 5: Metin Parçalarıyla Yüzen Kutular Oluşturun

 Birden fazla oluştur`FloatingBox` farklı dikey ve yatay hizalamalara sahip nesneler:

```csharp
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);

Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);

Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
```

 Metni ve stilini değiştirin`TextFragment` İstenilen nesneler.

## Adım 6: PDF belgesini kaydedin

Değiştirilen PDF belgesini kaydedin:

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

 Değiştirdiğinizden emin olun`"FloatingBox_alignment_review_out.pdf"` İstenilen çıktı dosya adı ile.

### .NET için Aspose.PDF kullanarak Yüzen Kutu İçerikleri için Metin Hizalaması için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);
Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);
Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinde yüzen kutulardaki metni nasıl hizalayacağınızı başarıyla öğrendiniz. Bu eğitim, projeyi kurmaktan değiştirilmiş belgeyi kaydetmeye kadar adım adım bir kılavuz sağladı. Artık bu kodu kendi C# projelerinize dahil ederek PDF dosyalarındaki yüzen kutulardaki metnin hizalamasını özelleştirebilirsiniz.

### SSS

#### S: "PDF Dosyasında Kayan Kutu İçeriği İçin Metin Hizalaması" eğitiminin amacı nedir?

A: "PDF Dosyasında Yüzen Kutu İçerikleri İçin Metin Hizalaması" öğreticisinin amacı, kullanıcılara .NET için Aspose.PDF kullanarak bir PDF belgesindeki yüzen kutulardaki metni nasıl hizalayacakları konusunda rehberlik etmektir. Öğretici, işlemi göstermek için adım adım talimatlar ve C# kod örnekleri sağlar.

#### S: Bu eğitim, kayan kutulardaki metinlerin hizalanmasına nasıl yardımcı oluyor?

A: Bu eğitim, kullanıcıların bir PDF belgesindeki yüzen kutulardaki metni hizalamak için Aspose.PDF for .NET'i nasıl kullanacaklarını anlamalarına yardımcı olur. Sağlanan adımları ve kod örneklerini izleyerek, kullanıcılar yüzen kutulardaki metnin dikey ve yatay hizalamasını özelleştirebilir.

#### S: Bu eğitimi takip etmek için hangi ön koşullar gereklidir?

A: Eğitime başlamadan önce, C# programlama dili hakkında temel bir anlayışa sahip olmalısınız. Ek olarak, .NET için Aspose.PDF kütüphanesinin yüklü olması gerekir. Bunu Aspose web sitesinden edinebilir veya NuGet kullanarak projenize yükleyebilirsiniz.

#### S: Bu eğitimi takip edecek şekilde projemi nasıl kurarım?

A: Başlamak için, tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturun ve Aspose.PDF for .NET kitaplığına bir referans ekleyin. Bu, PDF belgeleriyle çalışmak ve yüzen kutular içindeki metni hizalamak için kitaplığın özelliklerinden yararlanmanızı sağlar.

#### S: Bu eğitimi herhangi bir tür yüzen kutu içindeki metni hizalamak için kullanabilir miyim?

C: Evet, bu eğitim, .NET için Aspose.PDF kullanarak bir PDF belgesindeki yüzen kutulardaki metnin nasıl hizalanacağına dair talimatlar sağlar. Yüzen kutulardaki metnin dikey ve yatay hizalamasını özelleştirmek için sağlanan kod örneklerini kullanabilirsiniz.

#### S: Yüzen bir kutu içindeki metnin hizalamasını nasıl belirlerim?

 A: Eğitimde nasıl oluşturulacağı gösterilmektedir`FloatingBox`nesneleri ve bunların ayarlarını ayarlayın`VerticalAlignment` Ve`HorizontalAlignment` İçerilen metnin hizalamasını kontrol etmek için özellikler. Bu özellikleri gereksinimlerinize göre ayarlayabilirsiniz.

#### S: Yüzen kutuların görünümünü nasıl özelleştirebilirim?

 A: Sınır, boyut ve metin içeriği gibi özellikleri değiştirerek yüzen kutuların görünümünü özelleştirebilirsiniz. Eğitim, yüzen kutuların nasıl oluşturulacağını ve biçimlendirileceğini gösteren kod örnekleri sağlar.`FloatingBox` nesneler.

#### S: Aynı PDF belgesine farklı hizalamalara sahip birden fazla yüzen kutu ekleyebilir miyim?

 A: Evet, eğitimde birden fazla öğenin nasıl oluşturulacağı gösterilmektedir.`FloatingBox` Farklı dikey ve yatay hizalamalara sahip nesneleri aynı PDF belgesine ekleyin. Bu, aynı belge içinde çeşitli hizalamaların etkilerini görmenizi sağlar.

#### S: Değiştirilen PDF belgesini nasıl kaydedebilirim?

 A: Değiştirilen PDF belgesini kaydetmek için şunu kullanabilirsiniz:`Save` yöntemi`Document` nesne. Eğitim, ortaya çıkan PDF belgesinin nasıl kaydedileceğini gösteren kod örnekleri sağlar.