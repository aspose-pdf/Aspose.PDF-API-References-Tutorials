---
title: Belge Bağlantısı Oluştur
linktitle: Belge Bağlantısı Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile diğer PDF belgelerine kolayca bağlantılar oluşturun.
type: docs
weight: 30
url: /tr/net/programming-with-links-and-actions/create-document-link/
---

Bir PDF dosyasındaki başka bir belgeye bağlantı vermek, kullanıcıları diğer PDF belgelerine yönlendiren tıklanabilir bağlantılar oluşturmanıza olanak tanır. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu izleyerek bu tür bağlantıları kolayca oluşturabilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat yönergesi:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, başka bir belgeye bağlantı eklemek istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: PDF belgesini açın

Şimdi başka bir belgeye link eklemek istediğimiz PDF belgesini aşağıdaki kodu kullanarak açacağız:

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## 4. Adım: Başka bir belgeye bağlantı oluşturun

 Bu adımda, kullanarak başka bir belgeye bağlantı oluşturacağız.`LinkAnnotation` dipnot. Bağlantının koordinatlarını ve alanını ve gezinme eylemini harici bir belgeye belirteceğiz. İşte ilgili kod:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## 5. Adım: Güncellenen dosyayı kaydedin

Şimdi güncellenmiş PDF dosyasını kullanarak kaydedelim.`Save` yöntemi`document` nesne. İşte ilgili kod:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Belge Bağlantısı Oluşturma için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
// Bağlantı oluştur
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
// Güncellenen belgeyi kaydet
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET ile diğer belgelere bağlantı oluşturmak için adım adım bir kılavuza sahipsiniz. Bu kodu, PDF dosyalarınızda kullanıcıları diğer belgelere yönlendiren tıklanabilir bağlantılar oluşturmak için kullanabilirsiniz.

Etkileşimli bağlantıların gelişmiş özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.