---
title: PDF Dosyasında Görüntü Boyutunu Ayarla
linktitle: PDF Dosyasında Görüntü Boyutunu Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki bir görüntünün boyutunu ayarlamak için adım adım kılavuz.
type: docs
weight: 270
url: /tr/net/programming-with-images/set-image-size/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak PDF dosyasındaki bir görüntünün boyutunu nasıl ayarlayacağınız konusunda size yol göstereceğiz. Bu işlemi kolayca gerçekleştirmek için aşağıdaki adımları izleyin.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya kurulu ve yapılandırılmış başka bir geliştirme ortamı.
- C# programlama dili hakkında temel bilgi.
- Aspose.PDF kitaplığı for .NET kurulu. Aspose resmi sitesinden indirebilirsiniz.

## 1. Adım: PDF belgesinin oluşturulması

Başlamak için, yeni bir PDF belgesi oluşturmak üzere aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Belge nesnesi örneği oluşturma
Document doc = new Document();

// PDF dosyasının sayfa koleksiyonuna bir sayfa ekleyin
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 2. Adım: Resim eklendi

Ardından, PDF belgesinin sayfasına bir resim ekleyeceğiz. Aşağıdaki kodu kullanın:

```csharp
// Bir görüntü örneği oluşturun
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Görüntünün genişliğini ve yüksekliğini nokta olarak ayarlayın
img. FixWidth = 100;
img. FixHeight = 100;

// Resim türünü bilinmiyor olarak ayarla (Bilinmiyor)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

//Görüntü kaynak dosyasının yolu
img.File = dataDir + "aspose-logo.jpg";

// Görüntüyü sayfanın paragraf koleksiyonuna ekleyin
page.Paragraphs.Add(img);
```

Görüntü kaynak dosyasına doğru yolu sağladığınızdan emin olun.

## 3. Adım: Sayfa özelliklerini ayarlama

Son olarak, genişliği ve yüksekliği dahil olmak üzere sayfanın özelliklerini ayarlayacağız. Aşağıdaki kodu kullanın:

```csharp
// Sayfa özelliklerini ayarla
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Aspose.PDF for .NET kullanarak Set Image Size için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge nesnesini örneklendir
Document doc = new Document();
// PDF dosyasının sayfa koleksiyonuna sayfa ekle
Aspose.Pdf.Page page = doc.Pages.Add();
// Bir görüntü örneği oluşturun
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Görüntü Genişliğini ve Yüksekliğini Nokta Olarak Ayarlayın
img.FixWidth = 100;
img.FixHeight = 100;
// Görüntü türünü SVG olarak ayarla
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// Kaynak dosya yolu
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//Sayfa özelliklerini ayarla
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// ortaya çıkan PDF dosyasını kaydet
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesindeki görüntünün boyutunu başarıyla ayarladınız. Artık PDF dosyalarındaki görüntülerin boyutunu ayarlamak için bu yöntemi kendi projelerinize uygulayabilirsiniz.

### PDF dosyasında görüntü boyutunu ayarlamak için SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesindeki görüntünün boyutunu ayarlamanın amacı nedir?

C: Bir PDF belgesinde görüntünün boyutunu ayarlamanın amacı, PDF'ye eklendiğinde görüntünün boyutlarını kontrol etmektir. Bu, PDF dosyalarınızdaki görüntülerin görünümünü ve düzenini ayarlamanıza olanak tanır.

#### S: Bir görüntünün boyutunu ayarlama işlemi bir PDF belgesinde nasıl çalışır?

 C: Süreç, bir`Aspose.Pdf.Image` örneğini kullanarak genişliğini ve yüksekliğini belirterek`FixWidth` Ve`FixHeight` özellikleri ve ardından görüntüyü PDF belgesine ekleme. Ek olarak, görüntüyü yerleştirmek için sayfanın boyutlarını ayarlayabilirsiniz.

#### S: Bir resmin boyutunu sayfa boyutlarının belirli bir yüzdesine ayarlayabilir miyim?

A: Sağlanan kod, görüntünün mutlak genişliğini ve yüksekliğini noktalar olarak ayarlar. Bir görüntünün boyutunu sayfa boyutlarının yüzdesine göre ayarlamak istiyorsanız, boyutları buna göre hesaplamanız ve kodu buna göre ayarlamanız gerekir.

####  S: Önemi nedir?`FileType` property when adding an image to the PDF document?

 C:`FileType`özelliği, PDF belgesine eklenen görüntünün türünü belirtir. Sağlanan kodda, değer`Unknown` görüntü türünün bilinmediğini belirtir ve Aspose.PDF dosya uzantısına göre görüntü türünü belirlemeye çalışır.

#### S: Bu yöntemi kullanarak tek bir sayfaya birden fazla resim ekleyebilir miyim?

 C: Evet, birden çok görüntü oluşturarak tek bir sayfaya birden çok görüntü ekleyebilirsiniz.`Aspose.Pdf.Image` örnekleri ve bunları sayfanın paragraf koleksiyonuna ekleme. Görüntülerin konumunu ve düzenini gerektiği gibi ayarladığınızdan emin olun.

#### S: Eklenen görselin sayfada yerleşimini ve hizalamasını nasıl kontrol edebilirim?

 C: Eklenen görüntünün yerleşimi ve hizalaması, aşağıdaki gibi özellikler kullanılarak görüntünün koordinatları ve düzeni ayarlanarak kontrol edilebilir:`img.Left`, `img.Top`ve paragraf biçimlendirme özellikleri.

####  S: kullanarak sayfa özelliklerini ayarlamanın amacı nedir?`page.PageInfo.Width` and `page.PageInfo.Height`?

A: Sayfa özelliklerini ayarlamak, sayfanın boyutlarını tanımlamanıza olanak tanır. Bu, sayfa boyutlarının eklenen görseli ve sayfada sahip olabileceğiniz diğer içeriği barındırmasını sağlar.

#### S: Aynı PDF belgesinde farklı görüntüler için farklı boyutlar ayarlayabilir miyim?

 C: Evet, ayrı görüntüler oluşturarak farklı görüntüler için farklı boyutlar ayarlayabilirsiniz.`Aspose.Pdf.Image` örnekler ve ayarlama`FixWidth`, `FixHeight`ve her görüntü için yerleşim özellikleri.

#### S: PDF dosyalarında görüntü boyutlarını ayarlamak için bu yöntemi kendi projelerime nasıl entegre edebilirim?

Y: Bu yöntemi projelerinize entegre etmek için belirtilen adımları izleyin ve kodu gerektiği gibi değiştirin. Bu yöntemi, uygulamanızın gereksinimlerine göre belirli boyutlardaki görüntüleri PDF belgelerinize eklemek için kullanabilirsiniz.