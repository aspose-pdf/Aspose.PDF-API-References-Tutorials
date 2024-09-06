---
title: PDF Dosyasında Görüntü Boyutunu Ayarla
linktitle: PDF Dosyasında Görüntü Boyutunu Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki bir görüntünün boyutunu ayarlamaya yönelik adım adım kılavuz.
type: docs
weight: 270
url: /tr/net/programming-with-images/set-image-size/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak PDF dosyasındaki bir görüntünün boyutunu nasıl ayarlayacağınızı göstereceğiz. Bu işlemi kolayca gerçekleştirmek için şu adımları izleyin.

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya herhangi bir geliştirme ortamının kurulu ve yapılandırılmış olması.
- C# programlama dilinin temel bilgisi.
- .NET için Aspose.PDF kütüphanesi yüklü. Aspose resmi web sitesinden indirebilirsiniz.

## Adım 1: PDF belgesinin oluşturulması

Başlamak için, yeni bir PDF belgesi oluşturmak üzere aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Bir Belge nesnesi örneği oluşturun
Document doc = new Document();

// PDF dosyasının sayfa koleksiyonuna bir sayfa ekleyin
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Adım 2: Resim eklendi

Sonra, PDF belgesinin sayfasına bir resim ekleyeceğiz. Aşağıdaki kodu kullanın:

```csharp
// Bir görüntü örneği oluşturun
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Resmin genişliğini ve yüksekliğini noktalar halinde ayarlayın
img. FixWidth = 100;
img. FixHeight = 100;

//Görüntü türünü bilinmeyen (Bilinmeyen) olarak ayarla
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

// Görüntü kaynak dosyasının yolu
img.File = dataDir + "aspose-logo.jpg";

// Resmi sayfanın paragraf koleksiyonuna ekleyin
page.Paragraphs.Add(img);
```

Resim kaynak dosyasına doğru yolu sağladığınızdan emin olun.

## Adım 3: Sayfa özelliklerini ayarlama

Son olarak, sayfanın genişliği ve yüksekliği de dahil olmak üzere özelliklerini ayarlayacağız. Aşağıdaki kodu kullanın:

```csharp
// Sayfa özelliklerini ayarla
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### .NET için Aspose.PDF kullanarak Görüntü Boyutunu Ayarlamak için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge nesnesini örnekle
Document doc = new Document();
// PDF dosyası koleksiyonuna sayfa sayfa ekle
Aspose.Pdf.Page page = doc.Pages.Add();
// Bir görüntü örneği oluşturun
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Görüntü Genişliğini ve Yüksekliğini Noktalar Cinsinden Ayarla
img.FixWidth = 100;
img.FixHeight = 100;
// Resim türünü SVG olarak ayarla
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// Kaynak dosya yolu
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//Sayfa özelliklerini ayarla
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// sonuç PDF dosyasını kaydet
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesindeki bir görüntünün boyutunu başarıyla ayarladınız. Artık bu yöntemi kendi projelerinize uygulayarak PDF dosyalarındaki görüntülerin boyutunu ayarlayabilirsiniz.

### PDF dosyasında resim boyutunu ayarlamaya ilişkin SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesindeki bir görüntünün boyutunu ayarlamanın amacı nedir?

A: Bir PDF belgesinde bir görüntünün boyutunu ayarlamanın amacı, görüntünün PDF'ye eklendiğinde boyutlarını kontrol etmektir. Bu, PDF dosyalarınızdaki görüntülerin görünümünü ve düzenini ayarlamanıza olanak tanır.

#### S: PDF belgesinde bir görselin boyutunu ayarlama işlemi nasıl işliyor?

 A: Süreç, bir`Aspose.Pdf.Image` örneğin, genişliğini ve yüksekliğini belirterek`FixWidth` Ve`FixHeight` özellikleri ve ardından görüntüyü PDF belgesine ekleme. Ayrıca, sayfanın boyutlarını görüntüyü barındıracak şekilde ayarlayabilirsiniz.

#### S: Bir resmin boyutunu sayfa boyutlarının belirli bir yüzdesine ayarlayabilir miyim?

A: Sağlanan kod, görüntünün mutlak genişliğini ve yüksekliğini noktalar halinde ayarlar. Bir görüntünün boyutunu sayfa boyutlarının bir yüzdesine göre ayarlamak istiyorsanız, boyutları buna göre hesaplamanız ve kodu buna göre ayarlamanız gerekir.

####  S: Bunun önemi nedir?`FileType` property when adding an image to the PDF document?

 A:`FileType`özellik, PDF belgesine eklenen görüntünün türünü belirtir. Sağlanan kodda, değer`Unknown` Görüntünün türünün bilinmediğini belirtir ve Aspose.PDF dosya uzantısına göre görüntü türünü belirlemeye çalışır.

#### S: Bu yöntemi kullanarak tek bir sayfaya birden fazla resim ekleyebilir miyim?

 A: Evet, birden fazla resim oluşturarak tek bir sayfaya birden fazla resim ekleyebilirsiniz.`Aspose.Pdf.Image` örnekleri ve bunları sayfanın paragraf koleksiyonuna ekleme. Görüntülerin konumunu ve düzenini gerektiği gibi ayarladığınızdan emin olun.

#### S: Sayfaya eklenen görselin yerleşimini ve hizalamasını nasıl kontrol edebilirim?

 A: Eklenen görüntünün yerleşimi ve hizalaması, görüntünün koordinatları ve düzeni gibi özellikler kullanılarak ayarlanarak kontrol edilebilir.`img.Left`, `img.Top`ve paragraf biçimlendirme özellikleri.

####  S: Sayfa özelliklerini kullanarak ayarlamanın amacı nedir?`page.PageInfo.Width` and `page.PageInfo.Height`?

A: Sayfa özelliklerini ayarlamak, sayfanın boyutlarını tanımlamanıza olanak tanır. Bu, sayfa boyutlarının eklenen görüntüye ve sayfada olabilecek diğer içeriklere uyum sağlamasını sağlar.

#### S: Aynı PDF belgesindeki farklı resimler için farklı boyutlar belirleyebilir miyim?

 A: Evet, ayrı boyutlar oluşturarak farklı resimler için farklı boyutlar ayarlayabilirsiniz.`Aspose.Pdf.Image` örnekler ve ayarlama`FixWidth`, `FixHeight`ve her bir görsel için yerleşim özellikleri.

#### S: Bu yöntemi kendi projelerime nasıl entegre ederek PDF dosyalarındaki resim boyutlarını ayarlayabilirim?

A: Bu yöntemi projelerinize entegre etmek için, belirtilen adımları izleyin ve kodu gerektiği gibi değiştirin. Bu yöntemi, uygulamanızın gereksinimlerine göre PDF belgelerinize belirli boyutlarda resimler eklemek için kullanabilirsiniz.