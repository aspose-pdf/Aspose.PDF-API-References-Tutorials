---
title: PDF Dosyasındaki Kayan Kutu İçerikleri İçin Metin Hizalaması
linktitle: PDF Dosyasındaki Kayan Kutu İçerikleri İçin Metin Hizalaması
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak PDF dosyasındaki kayan kutular içindeki metni nasıl hizalayacağınızı öğrenin.
type: docs
weight: 520
url: /tr/net/programming-with-text/text-alignment-for-floating-box-contents/
---
Bu eğitimde Aspose.PDF for .NET kullanılarak PDF dosyasındaki kayan kutular içindeki metnin nasıl hizalanacağı açıklanmaktadır. Sağlanan C# kaynak kodu süreci adım adım gösterir.

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
```

## 3. Adım: Belge dizininin yolunu ayarlayın

 kullanarak belge dizininizin yolunu ayarlayın.`dataDir` değişken:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

## 4. Adım: Yeni bir Belge oluşturun

 Yeni bir tane oluştur`Document` nesne:

```csharp
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

## Adım 5: Metin Parçalarıyla Kayan Kutular Oluşturun

 Birden fazla oluştur`FloatingBox` farklı dikey hizalamalara ve yatay hizalamalara sahip nesneler:

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

 Metnini ve stilini değiştirin`TextFragment` nesneleri istediğiniz gibi seçin.

## Adım 6: PDF belgesini kaydedin

Değiştirilen PDF belgesini kaydedin:

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

 Değiştirdiğinizden emin olun`"FloatingBox_alignment_review_out.pdf"` İstenilen çıktı dosyası adı ile.

### Aspose.PDF for .NET kullanarak Kayan Kutu İçeriği İçin Metin Hizalama için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
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

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF belgesindeki kayan kutular içindeki metni nasıl hizalayacağınızı başarıyla öğrendiniz. Bu eğitimde, projenin kurulumundan değiştirilen belgenin kaydedilmesine kadar adım adım bir kılavuz sağlanmıştır. PDF dosyalarındaki kayan kutular içindeki metnin hizalamasını özelleştirmek için artık bu kodu kendi C# projelerinize dahil edebilirsiniz.

### SSS'ler

#### S: "PDF Dosyasındaki Kayan Kutu İçerikleri İçin Metin Hizalama" eğitiminin amacı nedir?

C: "PDF Dosyasındaki Kayan Kutu İçeriği İçin Metin Hizalama" eğitimi, kullanıcılara Aspose.PDF for .NET kullanarak bir PDF belgesindeki kayan kutular içindeki metni nasıl hizalayacakları konusunda rehberlik etmeyi amaçlamaktadır. Öğretici, süreci göstermek için adım adım talimatlar ve C# kod örnekleri sağlar.

#### S: Bu eğitim, kayan kutulardaki metnin hizalanmasına nasıl yardımcı olur?

C: Bu eğitim, kullanıcıların bir PDF belgesindeki kayan kutular içindeki metni hizalamak için Aspose.PDF for .NET'i nasıl kullanacaklarını anlamalarına yardımcı olur. Sağlanan adımları ve kod örneklerini takip ederek kullanıcılar, kayan kutular içindeki metnin dikey ve yatay hizalamasını özelleştirebilir.

#### S: Bu öğreticiyi takip etmek için hangi ön koşullar gereklidir?

C: Eğitime başlamadan önce C# programlama dili hakkında temel bilgiye sahip olmanız gerekir. Ayrıca Aspose.PDF for .NET kütüphanesinin de kurulu olması gerekir. Bunu Aspose web sitesinden edinebilir veya NuGet'i kullanarak projenize yükleyebilirsiniz.

#### S: Projemi bu öğreticiyi takip edecek şekilde nasıl ayarlayabilirim?

C: Başlamak için tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturun ve Aspose.PDF for .NET kütüphanesine bir referans ekleyin. Bu, kitaplığın PDF belgeleriyle çalışma ve kayan kutular içindeki metni hizalama özelliklerinden yararlanmanıza olanak tanır.

#### S: Bu öğreticiyi herhangi bir kayan kutu türündeki metni hizalamak için kullanabilir miyim?

C: Evet, bu eğitimde Aspose.PDF for .NET kullanılarak bir PDF belgesindeki kayan kutular içindeki metnin nasıl hizalanacağına ilişkin talimatlar verilmektedir. Kayan kutular içindeki metnin dikey ve yatay hizalamasını özelleştirmek için sağlanan kod örneklerini kullanabilirsiniz.

#### S: Kayan bir kutu içindeki metnin hizalamasını nasıl belirlerim?

 C: Eğitimde nasıl oluşturulacağı gösteriliyor`FloatingBox`nesneleri ve bunların ayarlarını yapın`VerticalAlignment` Ve`HorizontalAlignment` içerilen metnin hizalamasını kontrol eden özellikler. Bu özellikleri ihtiyaçlarınıza göre ayarlayabilirsiniz.

#### S: Yüzen kutuların görünümünü nasıl özelleştirebilirim?

 C: Kenarlık, boyut ve metin içeriği gibi özellikleri değiştirerek kayan kutuların görünümünü özelleştirebilirsiniz. Öğreticide, öğenin nasıl oluşturulacağını ve stillendirileceğini gösteren kod örnekleri sağlanır.`FloatingBox` nesneler.

#### S: Aynı PDF belgesine farklı hizalamalara sahip birden fazla kayan kutu ekleyebilir miyim?

 C: Evet, eğitimde birden fazla öğenin nasıl oluşturulacağı gösterilmektedir`FloatingBox` farklı dikey ve yatay hizalamalara sahip nesneleri seçin ve bunları aynı PDF belgesine ekleyin. Bu, aynı belgedeki çeşitli hizalamaların etkilerini görmenize olanak tanır.

#### S: Değiştirilen PDF belgesini nasıl kaydederim?

 C: Değiştirilen PDF belgesini kaydetmek için`Save` yöntemi`Document` nesne. Eğitimde, ortaya çıkan PDF belgesinin nasıl kaydedileceğini gösteren kod örnekleri sağlanır.