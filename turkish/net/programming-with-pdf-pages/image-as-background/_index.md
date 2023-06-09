---
title: Görüntüyü Arka Plan Olarak Ayarla
linktitle: Görüntüyü Arka Plan Olarak Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesinde bir görüntüyü sayfa arka planı olarak ayarlamak için adım adım kılavuz.
type: docs
weight: 110
url: /tr/net/programming-with-pdf-pages/image-as-background/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak bir görüntüyü sayfa arka planı olarak ayarlamak için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, Aspose.PDF for .NET kullanarak bir PDF belgesine sayfa arka planı olarak nasıl resim ekleyeceğinizi öğreneceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Aspose.PDF for .NET geliştirme ortamınızda yüklü

## 1. Adım: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Bu, düzenlenmiş PDF belgenizi kaydetmek istediğiniz konumdur. "BELGELER DİZİNİNİZİ" uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Yeni bir belge oluşturun
 Ardından, kullanarak yeni bir Belge nesnesi oluşturabilirsiniz.`Document` sınıf.

```csharp
Document doc = new Document();
```

## 3. Adım: Belgeye yeni bir sayfa ekleyin
 Artık Belge nesnesine yeni bir sayfa ekleyebilirsiniz.`Add()` yöntemi`Pages` sınıf.

```csharp
Page page = doc.Pages.Add();
```

## 4. Adım: Arka Plan Yapısı nesnesi oluşturun
Ardından, arka plan görüntüsünü ayarlamak için yeni bir BackgroundArtifact nesnesi oluşturabilirsiniz.

```csharp
BackgroundArtifact background = new BackgroundArtifact();
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
```

## 5. Adım: Sayfaya arka plan ekleyin
 Ardından, BackgroundArtifact nesnesini kullanarak sayfanın yapı koleksiyonuna ekleyebilirsiniz.`Artifacts` mülkiyeti`Page` sınıf.

```csharp
page. Artifacts. Add(background);
```

## 6. Adım: PDF belgesini kaydedin
 Son olarak, PDF belgesini kullanarak bir dosyaya kaydedebilirsiniz.`Save()` yöntemi`Document`sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

```csharp
doc.Save(dataDir + "ImageAsBackground_out.pdf");
```

### Aspose.PDF for .NET kullanan Image As Background için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Yeni bir Belge nesnesi oluşturun
Document doc = new Document();
// Belge nesnesine yeni bir sayfa ekle
Page page = doc.Pages.Add();
// Arka Plan Yapısı nesnesi oluştur
BackgroundArtifact background = new BackgroundArtifact();
// backgroundartifact nesnesi için görüntüyü belirtin
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
// Sayfanın eserler koleksiyonuna arka plan artifacti ekleyin
page.Artifacts.Add(background);
dataDir = dataDir + "ImageAsBackground_out.pdf";
// belgeyi kaydet
doc.Save(dataDir);
System.Console.WriteLine("\nImage as page background added successfully.\nFile saved at " + dataDir);

```

## Çözüm
Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesinde bir görüntünün sayfa arka planı olarak nasıl ayarlanacağını öğrendik. Bu adım adım kılavuzu izleyerek, PDF belgelerinize kolayca bir arka plan resmi ekleyebilirsiniz. Aspose.PDF, sayfa arka planı özelleştirme dahil olmak üzere PDF dosyalarıyla çalışmak için güçlü ve esnek bir API sunar. Özel arka plan resimleriyle PDF belgeleri oluşturmak için artık bu özelliği kendi projelerinize uygulayabilirsiniz.
