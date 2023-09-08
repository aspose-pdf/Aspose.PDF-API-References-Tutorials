---
title: PDF Dosyasında Görüntü Boyutunu Ayarlayın
linktitle: PDF Dosyasında Görüntü Boyutunu Ayarlayın
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki bir görüntünün boyutunu ayarlamak için adım adım kılavuz.
type: docs
weight: 270
url: /tr/net/programming-with-images/set-image-size/
---
Bu eğitimde, Aspose.PDF for .NET'i kullanarak PDF dosyasındaki bir görüntünün boyutunu nasıl ayarlayacağınız konusunda size yol göstereceğiz. Bu işlemi kolayca gerçekleştirmek için aşağıdaki adımları izleyin.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya kurulu ve yapılandırılmış başka bir geliştirme ortamı.
- C# programlama dili hakkında temel bilgi.
- .NET için Aspose.PDF kütüphanesi kuruldu. Aspose'un resmi web sitesinden indirebilirsiniz.

## Adım 1: PDF belgesinin oluşturulması

Başlamak için yeni bir PDF belgesi oluşturmak üzere aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Bir Belge nesnesinin örneğini oluşturma
Document doc = new Document();

// PDF dosyasının sayfa koleksiyonuna bir sayfa ekleyin
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Adım 2: Resim eklendi

Daha sonra PDF belgesinin sayfasına bir resim ekleyeceğiz. Aşağıdaki kodu kullanın:

```csharp
// Bir görüntü örneği oluşturun
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Görüntünün genişliğini ve yüksekliğini nokta olarak ayarlayın
img. FixWidth = 100;
img. FixHeight = 100;

// Resim türünü bilinmeyen (Bilinmeyen) olarak ayarla
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

//Görüntü kaynak dosyasının yolu
img.File = dataDir + "aspose-logo.jpg";

// Resmi sayfanın paragraf koleksiyonuna ekleyin
page.Paragraphs.Add(img);
```

Görüntü kaynak dosyasına doğru yolu sağladığınızdan emin olun.

## 3. Adım: Sayfa özelliklerini ayarlama

Son olarak sayfanın genişliği ve yüksekliği de dahil olmak üzere özelliklerini ayarlayacağız. Aşağıdaki kodu kullanın:

```csharp
// Sayfa özelliklerini ayarlama
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Aspose.PDF for .NET kullanarak Görüntü Boyutunu Ayarlama için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge nesnesini somutlaştır
Document doc = new Document();
// PDF dosyasının sayfa koleksiyonuna sayfa ekle
Aspose.Pdf.Page page = doc.Pages.Add();
// Bir görüntü örneği oluşturun
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Görüntü Genişliğini ve Yüksekliğini Nokta Olarak Ayarlayın
img.FixWidth = 100;
img.FixHeight = 100;
// Resim türünü SVG olarak ayarla
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// Kaynak dosyanın yolu
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//Sayfa özelliklerini ayarlama
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// ortaya çıkan PDF dosyasını kaydet
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF belgesindeki görüntünün boyutunu başarıyla ayarladınız. Artık PDF dosyalarındaki görsellerin boyutunu ayarlamak için bu yöntemi kendi projelerinize uygulayabilirsiniz.

### PDF dosyasında resim boyutunu ayarlamak için SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesindeki görüntünün boyutunu ayarlamanın amacı nedir?

C: PDF belgesindeki bir görüntünün boyutunu ayarlamanın amacı, PDF'ye eklendiğinde görüntünün boyutlarını kontrol etmektir. Bu, PDF dosyalarınızdaki görüntülerin görünümünü ve düzenini ayarlamanıza olanak tanır.

#### S: Bir PDF belgesinde görüntünün boyutunu ayarlama işlemi nasıl çalışır?

 C: Süreç, bir`Aspose.Pdf.Image` örneğin, genişliğini ve yüksekliğini belirterek`FixWidth` Ve`FixHeight` özellikleri ve ardından görüntüyü PDF belgesine ekleme. Ek olarak, sayfanın boyutlarını görsele uyum sağlayacak şekilde ayarlayabilirsiniz.

#### S: Bir görselin boyutunu, sayfa boyutlarının belirli bir yüzdesine ayarlayabilir miyim?

C: Sağlanan kod, görüntünün mutlak genişliğini ve yüksekliğini nokta cinsinden belirler. Bir görselin boyutunu sayfa boyutlarının yüzdesine göre ayarlamak istiyorsanız boyutları buna göre hesaplamanız ve kodu buna göre ayarlamanız gerekir.

####  Soru: Bunun önemi nedir?`FileType` property when adding an image to the PDF document?

 C:`FileType`özelliği, PDF belgesine eklenen görüntünün türünü belirtir. Sağlanan koddaki değer`Unknown` görselin türünün bilinmediğini belirtir ve Aspose.PDF, dosya uzantısına göre görselin türünü belirlemeye çalışır.

#### S: Bu yöntemi kullanarak tek bir sayfaya birden fazla resim ekleyebilir miyim?

 C: Evet, birden fazla resim oluşturarak tek bir sayfaya birden fazla resim ekleyebilirsiniz.`Aspose.Pdf.Image` örnekleri ve bunları sayfanın paragraf koleksiyonuna ekleme. Resimlerin konumunu ve düzenini gerektiği gibi ayarladığınızdan emin olun.

#### S: Eklenen görselin sayfaya yerleşimini ve hizalamasını nasıl kontrol edebilirim?

 C: Eklenen görüntünün yerleşimi ve hizalaması, aşağıdaki özellikler kullanılarak görüntünün koordinatları ve düzeni ayarlanarak kontrol edilebilir:`img.Left`, `img.Top`ve paragraf biçimlendirme özellikleri.

####  S: Sayfa özelliklerini kullanarak ayarlamanın amacı nedir?`page.PageInfo.Width` and `page.PageInfo.Height`?

C: Sayfa özelliklerini ayarlamak, sayfanın boyutlarını tanımlamanıza olanak tanır. Bu, sayfa boyutlarının eklenen görsele ve sayfada bulunabilecek diğer içeriğe uygun olmasını sağlar.

#### S: Aynı PDF belgesindeki farklı görseller için farklı boyutlar ayarlayabilir miyim?

 C: Evet, ayrı görseller oluşturarak farklı görseller için farklı boyutlar ayarlayabilirsiniz.`Aspose.Pdf.Image` örnekler ve ayarlamalar`FixWidth`, `FixHeight`ve her görselin yerleşim özellikleri.

#### S: PDF dosyalarındaki görüntü boyutlarını ayarlamak için bu yöntemi kendi projelerime nasıl entegre edebilirim?

C: Bu yöntemi projelerinize entegre etmek için özetlenen adımları izleyin ve kodu gerektiği gibi değiştirin. Uygulamanızın gereksinimlerine göre PDF belgelerinize belirli boyutlarda görseller eklemek için bu yöntemi kullanabilirsiniz.