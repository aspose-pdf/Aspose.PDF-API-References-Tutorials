---
title: Bağlantıları Ayıkla
linktitle: Bağlantıları Ayıkla
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesinden kolayca bağlantı çıkarın.
type: docs
weight: 50
url: /tr/net/programming-with-links-and-actions/extract-links/
---

Bağlantıları bir PDF belgesinden çıkarmak, belgede bulunan tüm köprü metni bağlantılarını kurtarmanıza olanak tanır. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu takip ederek bu bağlantıları kolaylıkla çıkarabilirsiniz:

## 1. Adım: Gerekli Kitaplıkları İçe Aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat yönergesi:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, bağlantıları ayıklamak istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: PDF belgesini açın

 PDF belgesini kullanarak açacağız.`Document` sınıf. İşte ilgili kod:

```csharp
Document document = new Document(dataDir + "ExtractLinks.pdf");
```

## 4. Adım: Bağlantıları çıkarın

 Bu adımda, PDF belgesinde bulunan bağlantıları kullanarak ayıklayacağız.`AnnotationSelector` sınıf. İşte ilgili kod:

```csharp
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page. Accept(selector);
IList<Annotation> list = selector. Selected;
Annotation annotation = (Annotation)list[0];
```

## 5. Adım: Güncellenen belgeyi kaydedin

Şimdi güncellenmiş PDF dosyasını kullanarak kaydedelim.`Save` yöntemi`document` nesne. İşte ilgili kod:

```csharp
dataDir = dataDir + "ExtractLinks_out.pdf";
document. Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Bağlantıları Çıkarma için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document document = new Document(dataDir+ "ExtractLinks.pdf");
// Ayıkla eylemleri
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page.Accept(selector);
IList<Annotation> list = selector.Selected;
Annotation annotation = (Annotation)list[0];
dataDir = dataDir + "ExtractLinks_out.pdf";
// Güncellenen belgeyi kaydet
document.Save(dataDir);
Console.WriteLine("\nLinks extracted successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF belgesinden bağlantı ayıklamak için adım adım bir kılavuza sahipsiniz. Belgede bulunan tüm köprüleri almak için bu kodu kullanabilirsiniz.

Gelişmiş bağlantı ayıklama özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.