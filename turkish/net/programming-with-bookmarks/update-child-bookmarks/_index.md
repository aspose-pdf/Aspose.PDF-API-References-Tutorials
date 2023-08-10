---
title: PDF Dosyasındaki Alt Yer İmlerini Güncelle
linktitle: PDF Dosyasındaki Alt Yer İmlerini Güncelle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasındaki alt yer imlerini kolayca güncelleyin.
type: docs
weight: 110
url: /tr/net/programming-with-bookmarks/update-child-bookmarks/
---
PDF dosyasındaki alt yer imlerini güncellemek, bir üst yer imindeki belirli yer imlerinin özelliklerini değiştirmenize olanak tanır. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu izleyerek alt yer imlerini kolayca güncelleyebilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat yönergesi:

```csharp
using Aspose.Pdf;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, güncellemek istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: PDF belgesini açın

Şimdi güncellemek istediğimiz PDF belgesini aşağıdaki kodu kullanarak açacağız:

```csharp
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
```

## 4. Adım: Üst yer imi nesnesini alın

Bu adımda, alt yer imlerini güncellemek istediğimiz belirli üst yer imi nesnesini alacağız. Aşağıdaki örnekte, dizin 1'deki (yer işaretleri koleksiyonundaki ikinci yer işareti) üst yer işaretini alıyoruz. Endeksi ihtiyaçlarınıza göre ayarlayabilirsiniz. İşte ilgili kod:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

## 5. Adım: Alt Yer İşareti Nesnesini Alın

Şimdi güncellemek istediğimiz belirli alt yer imi nesnesini alalım. Aşağıdaki örnekte, dizin 1'deki alt yer imini alıyoruz (üst yer iminin alt yer imleri koleksiyonundaki ikinci alt yer imi). Endeksi ihtiyaçlarınıza göre ayarlayabilirsiniz. İşte ilgili kod:

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

 Şimdi güncellenmiş PDF dosyasını kullanarak kaydedelim.`Save` yöntemi`pdfDocument` nesne. İşte ilgili kod:

```csharp
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Alt Yer İmlerini Güncellemek için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
// Bir yer imi nesnesi al
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

Tebrikler! Artık alt yer imlerini Aspose.PDF for .NET ile güncellemek için adım adım bir kılavuza sahipsiniz. Bu kodu, PDF belgelerinizdeki alt yer imlerinin özelliklerini değiştirmek için kullanabilirsiniz.

Gelişmiş yer imi düzenleme özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.

### PDF dosyasındaki alt yer imlerini güncellemeyle ilgili SSS

#### S: Bir PDF dosyasındaki alt yer işaretleri nelerdir?

C: Alt yer imleri, bir üst yer iminin içine yerleştirilmiş yer imleridir. Bir PDF belgesinin içeriğinde gezinmek için hiyerarşik bir yapı oluşturmanıza olanak tanırlar.

#### S: Alt yer imlerini neden güncellemem gerekiyor?

C: Alt yer imlerini güncellemek, bir üst yer imindeki belirli yer imlerinin özelliklerini, başlıklarını veya stillerini değiştirmek istediğinizde kullanışlıdır. Bu, belgenin gezinme yapısını özelleştirmeye yardımcı olur.

#### S: C# projem için gerekli kitaplıkları nasıl içeri aktarırım?

A: C# projeniz için gerekli kitaplıkları içe aktarmak için aşağıdaki içe aktarma yönergesini ekleyin:

```csharp
using Aspose.Pdf;
```

Bu yönerge, PDF belgeleri ve yer imleriyle çalışmak için gereken sınıflara ve yöntemlere erişmenizi sağlar.

#### S: Belgeler klasörünün yolunu nasıl belirtebilirim?

 C: Değiştir`"YOUR DOCUMENT DIRECTORY"` güncellemek istediğiniz PDF dosyasını içeren klasörün gerçek yolu ile sağlanan kaynak kodunda.

#### S: Alt yer imlerini güncellemek için bir PDF belgesini nasıl açarım?

C: Alt yer imlerini güncellemek üzere bir PDF belgesi açmak için aşağıdaki kodu kullanın:

```csharp
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
```

 Yer değiştirmek`"UpdateChildBookmarks.pdf"` gerçek dosya adı ile.

#### S: Alt yer imlerini güncellemek istediğim üst yer imi nesnesini nasıl alabilirim?

 A: Alt yer imlerini güncellemek üzere belirli bir üst yer imini almak için şuraya erişin:`Outlines` mülkiyeti`pdfDocument` nesne. Aşağıdaki örnekte, dizin 1'deki üst yer imini alıyoruz:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

#### S: Güncellemek istediğim alt yer imi nesnesini nasıl edinebilirim?

 A: Belirli bir alt yer imini güncellemek üzere almak için şuraya erişin:`OutlineItemCollection` üst yer iminin. Aşağıdaki örnekte, dizin 1'deki alt yer imini alıyoruz:

```csharp
OutlineItemCollection childOutline = pdfOutline[1];
```

#### S: Hangi alt yer imi özelliklerini güncelleyebilirim?

C: Alt yer iminin başlığı, italik stili ve kalın stili gibi çeşitli özelliklerini güncelleyebilirsiniz. Bu özellikleri ihtiyaçlarınıza göre özelleştirin:

```csharp
childOutline.Title = "Updated Outline";
childOutline.Italic = true;
childOutline.Bold = true;
```

#### S: Bu yöntemi kullanarak birden fazla alt yer işaretini güncelleyebilir miyim?

C: Evet, güncellemek istediğiniz her alt yer imi için 4 ila 7. adımları tekrarlayabilirsiniz. Üst dizini ve alt dizini gerektiği gibi değiştirin.

#### S: Güncellenmiş PDF dosyasını nasıl kaydedebilirim?

 A: Güncellenmiş PDF dosyasını kullanarak kaydedin.`Save` yöntemi`pdfDocument` nesne:

```csharp
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```