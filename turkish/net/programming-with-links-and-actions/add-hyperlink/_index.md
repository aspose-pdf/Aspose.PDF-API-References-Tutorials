---
title: Köprü Ekle
linktitle: Köprü Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyalarınıza kolayca etkileşimli köprüler ekleyin.
type: docs
weight: 10
url: /tr/net/programming-with-links-and-actions/add-hyperlink/
---

Bir PDF belgesine köprüler eklemek, belgedeki diğer sayfalara, web sitelerine veya hedeflere etkileşimli köprüler oluşturmanıza olanak tanır. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu takip ederek köprüleri kolayca ekleyebilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat yönergesi:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, köprü eklemek istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: PDF belgesini açın

Şimdi aşağıdaki kodu kullanarak köprü eklemek istediğimiz PDF belgesini açacağız:

```csharp
Document document = new Document(dataDir + "AddHyperlink.pdf");
```

## 4. Adım: Bir bağlantı oluşturun

 Bu adımda, kullanarak bir köprü oluşturacağız.`LinkAnnotation` dipnot. Bağlantının iletişim bilgilerini ve alanını, bağlantının türünü ve bağlantının içeriğini belirteceğiz. İşte ilgili kod:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
Border border = new Border(link);
border. Width = 0;
link. Border = border;
link. Action = new GoToURIAction("www.aspose.com");
page.Annotations.Add(link);
```

## 5. Adım: Ek metin ekleyin

 Köprüye ek olarak, kullanarak ek metin de ekleyebiliriz.`FreeTextAnnotation` dipnot. Koordinatları, metin görünümünü ve metin içeriğini belirleyeceğiz. İşte ilgili kod:

```csharp
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System .Drawing.Color.Blue));
textAnnotation.Contents = "Link to Aspose website";
textAnnotation. Border = border;
document.Pages[1].Annotations.Add(textAnnotation);
```

## 6. Adım: Güncellenen dosyayı kaydedin

Şimdi güncellenmiş PDF dosyasını kullanarak kaydedelim.`Save` yöntemi`document` nesne. İşte ilgili kod:

```csharp
dataDir = dataDir + "AddHyperlink_out.pdf";
document. Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Köprü Ekleme için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document document = new Document(dataDir + "AddHyperlink.pdf");
// Bağlantı oluştur
Page page = document.Pages[1];
//Bağlantı açıklama nesnesi oluştur
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
// LinkAnnotation için sınır nesnesi oluşturun
Border border = new Border(link);
// Kenarlık genişliği değerini 0 olarak ayarlayın
border.Width = 0;
// LinkAnnotation için sınırı ayarlayın
link.Border = border;
// Bağlantı türünü uzak URI olarak belirtin
link.Action = new GoToURIAction("www.aspose.com");
// PDF dosyasının ilk sayfasının açıklama koleksiyonuna bağlantı ek açıklaması ekleyin
page.Annotations.Add(link);
// Serbest Metin notu oluştur
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System.Drawing.Color.Blue));
// Serbest metin olarak eklenecek dize
textAnnotation.Contents = "Link to Aspose website";
// Serbest Metin Açıklaması için sınırı ayarlayın
textAnnotation.Border = border;
// Belgenin ilk sayfasının açıklama koleksiyonuna FreeText ek açıklaması ekleyin
document.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddHyperlink_out.pdf";
// Güncellenen belgeyi kaydet
document.Save(dataDir);
Console.WriteLine("\nHyperlink added successfully.\nFile saved at " + dataDir);            
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET ile hiper bağlantı eklemek için adım adım bir kılavuza sahipsiniz. PDF belgelerinizde etkileşimli bağlantılar oluşturmak için bu kodu kullanabilirsiniz.