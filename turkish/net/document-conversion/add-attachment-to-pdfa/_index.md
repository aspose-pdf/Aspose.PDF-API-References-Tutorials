---
title: PDFA'ya Ek Ekle
linktitle: PDFA'ya Ek Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'i kullanarak PDF/A dosyalarınıza kolayca ekler ekleyin.
type: docs
weight: 10
url: /tr/net/document-conversion/add-attachment-to-pdfa/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF/A dosyasına nasıl ek ekleyeceğiniz konusunda size adım adım rehberlik edeceğiz. C# kod örneklerini kullanarak her adımı açıklayacağız ve kolayca takip etmenize yardımcı olacak adım adım yönergeler sağlayacağız.

## giriiş

Ekler, ilgili resimler, belgeler veya medya gibi ek dosyalar eklemenize izin verdiği için PDF dosyalarına değerli eklemeler olabilir. Aspose.PDF for .NET ile PDF dosyalarınıza kolayca ekler ekleyebilir ve bunların nihai sonuca dahil edilmesini sağlayabilirsiniz.

## Ortam kurulumu

Uygulamaya başlamadan önce, geliştirme ortamımızı Aspose.PDF for .NET ile çalışacak şekilde yapılandıralım.

1. Visual Studio'yu veya C# geliştirmeye uygun başka bir IDE'yi kurun.
2. Yeni bir C# projesi oluşturun.
3. Gerekli bağımlılıkları eklemek için Aspose.PDF for .NET paketini NuGet aracılığıyla kurun.

## 1. Adım: Mevcut PDF dosyasını yükleyin

Ek eklemek için önce mevcut bir PDF dosyasını yüklememiz gerekiyor. Aspose.PDF for .NET kullanarak belgeyi yüklemek için şu adımları izleyin:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Mevcut dosyayı yüklemek için yeni bir Belge örneğinin örneğini oluşturun
Aspose.Pdf.Document doc = new Document(dataDir + "input.pdf");
```

 Yukarıdaki kodda değiştirin`"YOUR DOCUMENTS DIRECTORY"`giriş PDF belgenizin bulunduğu dizinin gerçek yolu ile. Bu kod, yeni bir örneğini başlatır.`Document` sınıflandırır ve mevcut PDF dosyasını yükler.

## 2. Adım: Ek için dosya belirtimi oluşturma

Bir ek eklemek için, ekin özelliklerini tanımlayan bir dosya özelliği oluşturmamız gerekir. Dosya belirtimini oluşturmak için şu adımları izleyin:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ek olarak eklenecek yeni dosyayı belirtin
FileSpecification fileSpecification = new FileSpecification(dataDir + "aspose-logo.jpg", "Large image file");
```

 Yukarıdaki kodda değiştirin`"YOUR DOCUMENTS DIRECTORY"` eklenecek resim dosyanızın bulunduğu dizinin gerçek yolu ile. Dosya belirtimi kullanılarak oluşturulur`FileSpecification` sınıf, dosya yolu ve bir açıklama belirterek.

## 3. Adım: Eki belgeye ekleme

Artık dosya özelliklerine sahip olduğumuza göre, onu belgenin ekler koleksiyonuna ekleyebiliriz. Eki eklemek için şu adımları izleyin:

```csharp
// Eki koleksiyonuna ekle

  document attachments
doc.EmbeddedFiles.Add(fileSpecification);
```

 Yukarıdaki kodda,`Add` belge yöntemi`s `Dosya belirtimini ek olarak eklemek için EmbeddedFiles` koleksiyonu.

## 4. Adım: PDF/A_3a'ya dönüştürün

Ekin ortaya çıkan dosyaya dahil olması için PDF/A_3a formatına dönüştürmemiz gerekiyor. Dönüştürmeyi gerçekleştirmek için şu adımları izleyin:

```csharp
// PDF/A_3a biçimine dönüştürmeyi gerçekleştirin
doc.Convert(dataDir + "log.txt", Aspose.Pdf.PdfFormat.PDF_A_3A, ConvertErrorAction.Delete);
```

 Yukarıdaki kodda,`Convert` kullanarak belgeyi dönüştürmek için yöntem`"log.txt"` log dosyası. Çıktı biçimini kullanarak belirtiriz.`PdfFormat.PDF_A_3A` enum ve dönüştürme hatasıyla ilgili yapılacak eylemi belirtin`ConvertErrorAction.Delete`.

## 5. Adım: Ortaya çıkan dosyayı kaydedin

Son olarak, değiştirilmiş PDF belgesini eklenen ek ile kaydediyoruz. Ortaya çıkan dosyayı kaydetmek için şu adımları izleyin:

```csharp
// Ortaya çıkan dosyayı kaydedin
doc.Save(dataDir + "AddAttachmentToPDFA_out.pdf");
```

 Yukarıdaki kodda,`Save` belgeyi dosya adıyla kaydetme yöntemi`"AddAttachmentToPDFA_out.pdf"`. Ortaya çıkan dosyayı kaydetmek istediğiniz uygun yolu belirttiğinizden emin olun.

### Aspose.PDF for .NET kullanarak PDFA'ya ek eklemek için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mevcut dosyayı yüklemek için Belge örneğini oluşturun
Aspose.Pdf.Document doc = new Document(dataDir + "input.pdf");
// Ek olarak eklenecek yeni dosyayı ayarlayın
FileSpecification fileSpecification = new FileSpecification(dataDir + "aspose-logo.jpg", "Large Image file");
//Belgenin ek koleksiyonuna ek ekleyin
doc.EmbeddedFiles.Add(fileSpecification);
// Ekin sonuç dosyasına dahil edilmesi için PDF/A_3a'ya dönüştürme gerçekleştirin
doc.Convert(dataDir + "log.txt", Aspose.Pdf.PdfFormat.PDF_A_3A, ConvertErrorAction.Delete);
// Ortaya çıkan dosyayı kaydet
doc.Save(dataDir + "AddAttachmentToPDFA_out.pdf");

Console.WriteLine("\nAttachment added successfully to PDF/A file.\nFile saved at " + dataDir);
```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF/A dosyasına nasıl ek ekleyeceğinizi öğrendiniz. Mevcut belgeyi yüklemekten sonuçtaki dosyayı dönüştürmeye ve kaydetmeye kadar sürecin her adımını ele aldık. Sağlanan kod örneklerini kullanarak bu işlevi kendi projelerinize kolayca entegre edebilirsiniz. Aspose.PDF for .NET ile deneyler yapın ve PDF dosyalarının gelişmiş şekilde işlenmesi için sunduğu olanakları keşfedin.

### SSS

#### S: Aspose.PDF for .NET nedir?

Y: Aspose.PDF for .NET, .NET uygulamaları için güçlü bir PDF düzenleme ve işleme kitaplığıdır. Geliştiricilerin PDF dosyalarını programlı olarak oluşturmasına, düzenlemesine, dönüştürmesine ve değiştirmesine olanak tanır.

#### S: PDF dosyalarına ek eklemenin amacı nedir?

Y: PDF dosyalarına ekler eklemek, PDF belgesine resimler, belgeler veya medya gibi ek dosyalar eklemenize olanak tanır. Bu, ek bilgiler veya ilgili kaynaklar sağlamak için yararlı olabilir.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesine birden çok ek ekleyebilir miyim?

 C: Evet, Aspose.PDF for .NET'i kullanarak bir PDF belgesine birden çok ek ekleyebilirsiniz. Basitçe çoklu oluşturun`FileSpecification` her biri farklı bir eki temsil eden nesneler ve bunları`EmbeddedFiles` belgenin toplanması.

#### S: PDF/A_3a biçimine dönüştürme eki nasıl etkiler?

A: PDF/A_3a biçimine dönüştürme, ekin ortaya çıkan PDF/A belgesine dahil edilmesini sağlar. PDF/A_3a, elektronik belgelerin uzun süreli arşivlenmesi için bir standarttır ve bu formata dönüştürüldüğünde ek, PDF belgesinin kalıcı bir parçası haline gelir.
