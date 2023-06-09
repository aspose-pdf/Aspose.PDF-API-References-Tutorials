---
title: Swf Dosyasını Açıklama Olarak Ekle
linktitle: Swf Dosyasını Açıklama Olarak Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuz ile Aspose.PDF for .NET'te SWF dosyalarını açıklama olarak nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 30
url: /tr/net/annotations/addswffileasannotation/
---
Aspose.PDF for .NET kullanarak PDF belgenize ek açıklama olarak bir SWF multimedya dosyası eklemek isteyen bir .NET geliştiricisiyseniz, bu adım adım kılavuz tam size göre. Bu yazıda, C# programlama dilini kullanarak SWF dosyalarını PDF belgelerinize açıklama olarak nasıl ekleyeceğinizi açıklayacağız. 

Aspose.PDF for .NET kullanarak PDF belgenize ek açıklama olarak bir SWF dosyası eklemek için aşağıdaki adımları izleyin:

## 1. Adım: Dizin yolunu ayarlayın

Öncelikle, PDF dosyasının ve SWF dosyasının saklandığı dizin yolunu belirlememiz gerekiyor. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

"BELGE DİZİNİNİZİ", belge dizininizin yolu ile değiştirin.

## 2. Adım: PDF belgesini yükleyin

Ardından, aşağıdaki kodu kullanarak PDF belgesini yüklememiz gerekiyor:

```csharp
Document doc = new Document(dataDir + "AddSwfFileAsAnnotation.pdf");
```

Bu kod, "AddSwfFileAsAnnotation.pdf" dosyasını belge dizininden yükleyecektir.

## 3. Adım: Ek açıklama eklemek için sayfayı alın

Şimdi ek açıklama eklemek istediğimiz sayfanın referansını almamız gerekiyor. Bu öğreticide, açıklamayı belgenin ilk sayfasına ekleyeceğiz.

```csharp
Page page = doc.Pages[1];
```

## 4. Adım: Bir ScreenAnnotation nesnesi oluşturun

 şimdi bir tane oluşturabiliriz`ScreenAnnotation` bağımsız değişken olarak SWF dosyasıyla nesne.

```csharp
ScreenAnnotation annotation = new ScreenAnnotation(page, new Aspose.Pdf.Rectangle(0, 400, 600, 700), dataDir + "input.swf");
```

 bu`ScreenAnnotation` yapıcı üç bağımsız değişken alır:

- `page`: Ek açıklamanın ekleneceği sayfa.
- `rectangle`: SWF dosyasının sayfada görüntüleneceği dikdörtgen.
- `dataDir + "input.swf"`: SWF dosyasının yolu.

## 5. Adım: Ek açıklamayı sayfaya ekleyin

Artık notu sayfanın not koleksiyonuna ekleyebiliriz.

```csharp
page.Annotations.Add(annotation);
```

## 6. Adım: Güncellenmiş PDF belgesini kaydedin

Son olarak, güncellenmiş PDF belgesini aşağıdaki kodu kullanarak ek açıklamayla kaydetmemiz gerekiyor:

```csharp
dataDir = dataDir + "AddSwfFileAsAnnotation_out.pdf";
doc.Save(dataDir);
```

Bu kod, güncellenmiş PDF belgesini açıklamayla birlikte belge dizinine "AddSwfFileAsAnnotation_out.pdf" olarak kaydedecektir.

### Aspose.PDF for .NET kullanarak SWF dosyasını ek açıklama olarak eklemek için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF belgesini aç
Document doc = new Document(dataDir + "AddSwfFileAsAnnotation.pdf");

// Ek açıklamayı eklemeniz gereken sayfanın referansını alın
Page page = doc.Pages[1];

// Bağımsız değişken olarak .swf multimedya dosyasıyla ScreenAnnotation nesnesi oluşturun
ScreenAnnotation annotation = new ScreenAnnotation(page, new Aspose.Pdf.Rectangle(0, 400, 600, 700), dataDir + "input.swf");

// Ek açıklamayı sayfanın ek açıklamalar koleksiyonuna ekleyin
page.Annotations.Add(annotation);

dataDir = dataDir + "AddSwfFileAsAnnotation_out.pdf";
// Güncelleme PDF belgesini ek açıklama ile kaydedin
doc.Save(dataDir);
```        
