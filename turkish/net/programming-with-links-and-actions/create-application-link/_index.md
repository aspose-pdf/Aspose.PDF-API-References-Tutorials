---
title: Uygulama Bağlantısı Oluştur
linktitle: Uygulama Bağlantısı Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyalarınızda kolayca uygulama bağlantıları oluşturun.
type: docs
weight: 20
url: /tr/net/programming-with-links-and-actions/create-application-link/
---

Bir PDF belgesinde uygulama bağlantısı oluşturmak, yürütülebilir dosyalar veya URL'ler gibi harici uygulamalara bağlantılar oluşturmanıza olanak tanır. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu izleyerek kolayca uygulama bağlantıları oluşturabilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat yönergesi:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

Bu adımda, uygulama bağlantısı eklemek istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: PDF belgesini açın

Şimdi aşağıdaki kodu kullanarak uygulama bağlantısı eklemek istediğimiz PDF belgesini açacağız:

```csharp
Document document = new Document(dataDir + "CreateApplicationLink.pdf");
```

## 4. Adım: Uygulama Bağlantısını Oluşturun

 Bu adımda, kullanarak uygulama bağlantısını oluşturacağız.`LinkAnnotation` dipnot. Bağlantının koordinatlarını ve alanını ve ayrıca uygulama başlatma eylemini belirleyeceğiz. İşte ilgili kod:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
```

## 5. Adım: Güncellenen dosyayı kaydedin

Şimdi güncellenmiş PDF dosyasını kullanarak kaydedelim.`Save` yöntemi`document` nesne. İşte ilgili kod:

```csharp
dataDir = dataDir + "CreateApplicationLink_out.pdf";
document. Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Uygulama Bağlantısı Oluşturma için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document document = new Document( dataDir + "CreateApplicationLink.pdf");
// Bağlantı oluştur
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
dataDir = dataDir + "CreateApplicationLink_out.pdf";
// Güncellenen belgeyi kaydet
document.Save(dataDir);
Console.WriteLine("\nApplication link created successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET ile uygulama bağlantıları oluşturmak için adım adım bir kılavuza sahipsiniz. Bu kodu, PDF belgelerinizdeki harici uygulamalara bağlantılar eklemek için kullanabilirsiniz.

Etkileşimli bağlantıların gelişmiş özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.