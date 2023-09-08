---
title: PDF Dosyasındaki Alt Yer İşaretlerini Güncelle
linktitle: PDF Dosyasındaki Alt Yer İşaretlerini Güncelle
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF dosyasındaki alt yer imlerini kolayca güncelleyin.
type: docs
weight: 110
url: /tr/net/programming-with-bookmarks/update-child-bookmarks/
---
PDF dosyasındaki alt yer imlerini güncellemek, ana yer imindeki belirli yer imlerinin özelliklerini değiştirmenize olanak tanır. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu takip ederek alt yer imlerini kolayca güncelleyebilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce C# projeniz için gerekli kütüphaneleri içe aktarmanız gerekir. Gerekli ithalat direktifi aşağıdadır:

```csharp
using Aspose.Pdf;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda güncellemek istediğiniz PDF dosyasının bulunduğu klasörün yolunu belirtmeniz gerekmektedir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`belgeler klasörünüzün gerçek yolunu içeren aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: PDF belgesini açın

Şimdi aşağıdaki kodu kullanarak güncellemek istediğimiz PDF belgesini açacağız:

```csharp
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
```

## 4. Adım: Ana yer imi nesnesini alın

Bu adımda, alt yer imlerini güncellemek istediğimiz belirli ana yer imi nesnesini alacağız. Aşağıdaki örnekte, dizin 1'deki ana yer imini alıyoruz (yer imleri koleksiyonundaki ikinci yer imi). Endeksi ihtiyaçlarınıza göre ayarlayabilirsiniz. İşte ilgili kod:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

## Adım 5: Çocuk Yer İşareti Nesnesini Alın

Şimdi güncellemek istediğimiz belirli alt yer imi nesnesini alalım. Aşağıdaki örnekte, dizin 1'deki alt yer imini alıyoruz (ana yer iminin alt yer imleri koleksiyonundaki ikinci alt yer imi). Endeksi ihtiyaçlarınıza göre ayarlayabilirsiniz. İşte ilgili kod:

```csharp
OutlineItemCollection childOutline = pdfOutline[1];
```

## 6. Adım: Alt yer imi özelliklerini güncelleyin

Şimdi başlık, italik stil ve kalın stil gibi alt yer imi özelliklerini güncelleyelim. Bu özellikleri ihtiyaçlarınıza göre ayarlayabilirsiniz. İşte ilgili kod:

```csharp
childOutline.Title = "Updated Outline";
childOutline. Italic = true;
childOutline. Bold = true;
```

## 7. Adım: Güncellenen dosyayı kaydedin

 Şimdi güncellenen PDF dosyasını kullanarak kaydedelim.`Save` yöntemi`pdfDocument` nesne. İşte ilgili kod:

```csharp
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Alt Yer İşaretlerini Güncelleme için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
// Bir yer imi nesnesi alın
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
//Alt yer imi nesnesini al
OutlineItemCollection childOutline = pdfOutline[1];
childOutline.Title = "Updated Outline";
childOutline.Italic = true;
childOutline.Bold = true;
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";            
// Çıktıyı kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmarks updated successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Artık alt yer imlerini Aspose.PDF for .NET ile güncellemek için adım adım bir kılavuza sahipsiniz. PDF belgelerinizdeki alt yer imlerinin özelliklerini değiştirmek için bu kodu kullanabilirsiniz.

Gelişmiş yer imi düzenleme özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine göz atmayı unutmayın.

### PDF dosyasındaki alt yer işaretlerini güncellemeye ilişkin SSS

#### S: PDF dosyasındaki alt yer imleri nedir?

C: Alt yer imleri, bir üst yer iminin içine yerleştirilmiş yer imleridir. Bir PDF belgesinin içeriğinde gezinmek için hiyerarşik bir yapı oluşturmanıza olanak tanır.

#### S: Alt yer işaretlerini neden güncellemem gerekiyor?

C: Alt yer imlerini güncellemek, bir ana yer imindeki belirli yer imlerinin özelliklerini, başlıklarını veya stillerini değiştirmek istediğinizde kullanışlıdır. Bu, belgenin gezinme yapısını özelleştirmeye yardımcı olur.

#### S: C# projem için gerekli kitaplıkları nasıl içeri aktarabilirim?

C: C# projeniz için gerekli kitaplıkları içe aktarmak için aşağıdaki içe aktarma yönergesini ekleyin:

```csharp
using Aspose.Pdf;
```

Bu yönerge, PDF belgeleri ve yer imleriyle çalışmak için gereken sınıflara ve yöntemlere erişmenizi sağlar.

#### S: Belgeler klasörünün yolunu nasıl belirlerim?

 C: Değiştir`"YOUR DOCUMENT DIRECTORY"` sağlanan kaynak kodunda, güncellemek istediğiniz PDF dosyasını içeren klasörün gerçek yolunu belirtin.

#### S: Alt yer imlerini güncellemek için bir PDF belgesini nasıl açarım?

C: Alt yer imlerini güncellemek amacıyla bir PDF belgesi açmak için aşağıdaki kodu kullanın:

```csharp
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
```

 Yer değiştirmek`"UpdateChildBookmarks.pdf"` gerçek dosya adı ile.

#### S: Alt yer imlerini güncellemek istediğim ana yer imi nesnesini nasıl edinebilirim?

 C: Alt yer imlerini güncellemek amacıyla belirli bir ana yer imini almak için`Outlines` mülkiyeti`pdfDocument` nesne. Aşağıdaki örnekte, dizin 1'deki ana yer imini alıyoruz:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

#### S: Güncellemek istediğim alt yer imi nesnesini nasıl edinebilirim?

 C: Güncelleme amacıyla belirli bir alt yer imini almak için`OutlineItemCollection` ana yer iminin. Aşağıdaki örnekte, dizin 1'deki alt yer imini alıyoruz:

```csharp
OutlineItemCollection childOutline = pdfOutline[1];
```

#### S: Hangi alt yer imi özelliklerini güncelleyebilirim?

C: Bir alt yer iminin başlığı, italik stili ve kalın stili gibi çeşitli özelliklerini güncelleyebilirsiniz. Bu özellikleri ihtiyaçlarınıza göre özelleştirin:

```csharp
childOutline.Title = "Updated Outline";
childOutline.Italic = true;
childOutline.Bold = true;
```

#### S: Bu yöntemi kullanarak birden fazla alt yer imini güncelleyebilir miyim?

C: Evet, güncellemek istediğiniz her alt yer imi için 4'ten 7'ye kadar olan adımları tekrarlayabilirsiniz. Gerektiğinde üst dizini ve alt dizini değiştirin.

#### S: Güncellenen PDF dosyasını nasıl kaydederim?

 C: Güncellenen PDF dosyasını kullanarak kaydedin.`Save` yöntemi`pdfDocument` nesne:

```csharp
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```