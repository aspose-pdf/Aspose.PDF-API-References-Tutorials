---
title: Görüntü Boyutunu Ayarla
linktitle: Görüntü Boyutunu Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesindeki görüntünün boyutunu ayarlamak için adım adım kılavuz.
type: docs
weight: 270
url: /tr/net/programming-with-images/set-image-size/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki görüntünün boyutunu nasıl ayarlayacağınız konusunda size yol göstereceğiz. Bu işlemi kolayca gerçekleştirmek için aşağıdaki adımları izleyin.

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

// Görüntü kaynak dosyasının yolu
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
//PDF dosyasının sayfa koleksiyonuna sayfa ekle
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