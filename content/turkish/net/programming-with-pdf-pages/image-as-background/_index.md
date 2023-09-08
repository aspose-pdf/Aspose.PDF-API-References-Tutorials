---
title: Görüntüyü PDF Dosyasında Sayfa Arka Planı Olarak Ayarla
linktitle: Görüntüyü PDF Dosyasında Sayfa Arka Planı Olarak Ayarla
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak bir görüntüyü PDF dosyasında sayfa arka planı olarak ayarlamak için adım adım kılavuz.
type: docs
weight: 110
url: /tr/net/programming-with-pdf-pages/image-as-background/
---
Bu eğitimde, Aspose.PDF for .NET'i kullanarak bir görüntüyü sayfa arka planı olarak ayarlamak için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sunacağız. Bu eğitimin sonunda Aspose.PDF for .NET kullanarak bir PDF belgesine sayfa arka planı olarak nasıl resim ekleyeceğinizi öğreneceksiniz.

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Aspose.PDF for .NET, geliştirme ortamınızda yüklü

## 1. Adım: Belge dizinini tanımlayın
Öncelikle belgeler dizininizin yolunu ayarlamanız gerekir. Bu, düzenlenmiş PDF belgenizi kaydetmek istediğiniz konumdur. "BELGELERİNİZ DİZİNİ"ni uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Yeni bir belge oluşturun
 Daha sonra şunu kullanarak yeni bir Belge nesnesi oluşturabilirsiniz:`Document` sınıf.

```csharp
Document doc = new Document();
```

## 3. Adım: Belgeye yeni bir sayfa ekleyin
 Artık Belge nesnesine yeni bir sayfa ekleyebilirsiniz.`Add()` yöntemi`Pages` sınıf.

```csharp
Page page = doc.Pages.Add();
```

## 4. Adım: Arka Plan Yapısı nesnesi oluşturun
Daha sonra arka plan resmini ayarlamak için yeni bir TextureArtifact nesnesi oluşturabilirsiniz.

```csharp
BackgroundArtifact background = new BackgroundArtifact();
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
```

## 5. Adım: Arka planı sayfaya ekleyin
Ardından, Arka PlanArtifact nesnesini kullanarak sayfanın yapıt koleksiyonuna ekleyebilirsiniz.`Artifacts` mülkiyeti`Page` sınıf.

```csharp
page. Artifacts. Add(background);
```

## Adım 6: PDF belgesini kaydedin
 Son olarak, PDF belgesini kullanarak bir dosyaya kaydedebilirsiniz.`Save()` yöntemi`Document`sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

```csharp
doc.Save(dataDir + "ImageAsBackground_out.pdf");
```

### Aspose.PDF for .NET kullanan Arka Plan Olarak Görüntü için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Yeni bir Belge nesnesi oluşturun
Document doc = new Document();
// Belge nesnesine yeni bir sayfa ekleyin
Page page = doc.Pages.Add();
// Arka Plan Yapısı nesnesi oluştur
BackgroundArtifact background = new BackgroundArtifact();
// Arka plan yapı nesnesi için görüntüyü belirtin
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
// Sayfanın yapıt koleksiyonuna arka plan yapıtını ekleyin
page.Artifacts.Add(background);
dataDir = dataDir + "ImageAsBackground_out.pdf";
// Belgeyi kaydet
doc.Save(dataDir);
System.Console.WriteLine("\nImage as page background added successfully.\nFile saved at " + dataDir);

```

## Çözüm
Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF belgesinde bir görüntüyü sayfa arka planı olarak nasıl ayarlayacağımızı öğrendik. Bu adım adım kılavuzu izleyerek PDF belgelerinize kolayca arka plan resmi ekleyebilirsiniz. Aspose.PDF, PDF dosyalarıyla çalışmak için sayfa arka planı özelleştirmesi de dahil olmak üzere güçlü ve esnek bir API sunar. Özel arka plan görsellerine sahip PDF belgeleri oluşturmak için artık bu özelliği kendi projelerinize uygulayabilirsiniz.

### PDF dosyasında resmi sayfa arka planı olarak ayarlamak için SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinde bir görüntüyü sayfa arka planı olarak nasıl ayarlayabilirim?

C: Aspose.PDF for .NET kullanarak bir görüntüyü PDF belgesinde sayfa arka planı olarak ayarlamak için şu adımları takip edebilirsiniz:

1. Düzenlenen PDF belgenizi kaydetmek istediğiniz yolu belirterek belge dizinini ayarlayın.
2.  kullanarak yeni bir Belge nesnesi oluşturun.`Document` sınıf.
3.  kullanarak Belge nesnesine yeni bir sayfa ekleyin.`Add()` yöntemi`Pages` sınıf.
4.  Arka plan resmini ayarlamak için yeni bir ArkaplanArtifact nesnesi oluşturun. Görüntü dosyasını kullanarak belirtebilirsiniz.`File.OpenRead()` yöntem.
5.  ArkaplanArtifact nesnesini kullanarak sayfanın yapıt koleksiyonuna ekleyin.`Artifacts` mülkiyeti`Page` sınıf.
6.  PDF belgesini kullanarak bir dosyaya kaydedin.`Save()` yöntemi`Document` sınıfını seçin ve çıktı için doğru yolu ve dosya adını belirtin.

#### S: PDF belgesinin farklı sayfalarına birden fazla arka plan resmi ekleyebilir miyim?

C: Evet, öğreticide açıklanan işlemi her sayfa için tekrarlayarak PDF belgesinin farklı sayfalarına birden fazla arka plan resmi ekleyebilirsiniz. Her sayfa için istediğiniz görseli içeren yeni bir Arka PlanArtifact nesnesi oluşturun ve bunu ilgili sayfanın yapıt koleksiyonuna ekleyin.

#### S: Sayfadaki arka plan resmine resim ölçekleme veya konumlandırma uygulayabilir miyim?

 C: Evet, sayfadaki arka plan görüntüsüne görüntü ölçekleme veya konumlandırma uygulayabilirsiniz.`background.BackgroundImage` ArkaplanArtifact nesnesinin özelliği. Arka Plan Artifact'ini sayfaya eklemeden önce görüntünün arka plan olarak nasıl görüneceğini özelleştirmek için genişlik, yükseklik ve konum gibi görüntü özelliklerini değiştirebilirsiniz.

#### S: Aspose.PDF for .NET, içerikli mevcut PDF belgelerine arka plan resimleri eklemeyi destekliyor mu?

C: Evet, Aspose.PDF for .NET, içerikli mevcut PDF belgelerine arka plan resimleri eklemenizi sağlar. Mevcut bir PDF belgesini yükleyebilir, arka plan resmini istediğiniz sayfaya ekleyebilir ve ardından güncellenen belgeyi yeni bir dosyaya kaydedebilir veya orijinal dosyanın üzerine yazabilirsiniz.

#### S: PNG veya BMP gibi farklı formatlardaki görselleri sayfa arka planı olarak kullanabilir miyim?

C: Evet, öğreticide kullanılan JPEG formatına ek olarak PNG veya BMP gibi farklı formatlardaki görselleri sayfa arka planı olarak kullanabilirsiniz. Aspose.PDF for .NET çok çeşitli görüntü formatlarını destekler ve desteklenen herhangi bir görüntü formatını PDF sayfalarının arka planı olarak kullanabilirsiniz.