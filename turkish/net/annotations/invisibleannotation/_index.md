---
title: Görünmez Açıklama
linktitle: Görünmez Açıklama
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile C# kaynak kodunu kullanarak PDF'lere nasıl görünmez bir şekilde açıklama ekleyeceğinizi öğrenin. Adım adım rehber.
type: docs
weight: 100
url: /tr/net/annotations/invisibleannotation/
---
## PDF Belgelerindeki Ek Açıklamaları Anlama

PDF belgelerindeki ek açıklamalar, gerçek içeriği değiştirmeden bir belgeye fazladan bilgi veya notlar eklemenizi sağlayan güçlü bir özelliktir. Metni vurgulamak, bir belgenin belirli alanlarına dikkat çekmek veya yorum veya geri bildirim eklemek için kullanılabilirler.

PDF belgelerinde kullanabileceğiniz pek çok farklı ek açıklama türü vardır, örneğin:

- Metin Açıklamaları
- Bağlantı Açıklamaları
- Damga Açıklamaları
- Ses Açıklamaları
- Dosya Ek Açıklamaları
- ve daha fazlası

## Aspose.PDF for .NET Kullanarak PDF Belgesinde Görünmez Ek Açıklama Oluşturma

 Aspose.PDF for .NET kullanarak bir PDF belgesinde görünmez bir ek açıklama oluşturmak için önce bir`FreeTextAnnotation` nesnesini seçin ve ek açıklamanın konumunu ve boyutunu belirtin.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

 Yukarıdaki kodda bir tane oluşturuyoruz.`FreeTextAnnotation`nesnesini seçin ve açıklamanın konumunu PDF belgesinin 2. sayfasında belirtin. Açıklamada görüntülenecek metnin yazı tipini, boyutunu ve rengini de belirliyoruz.

## Görünmez Ek Açıklamaya Özellikler Ekleme

Ardından, ek açıklamaya kenarlık rengi, arka plan rengi veya opaklık gibi bazı özellikler ekleyebiliriz.

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

Yukarıdaki kodda açıklamanın kenarlık rengini kırmızı olarak ayarladık.

## Ek Açıklama İşaretlerini Ayarlama

Ek açıklamayı oluşturup özelliklerini ayarladıktan sonra, açıklama bayraklarını belirtebiliriz. Bu öğreticide, ek açıklamanın yazdırılabilir olmasını ancak görüntülenemez olmasını istiyoruz.

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
```

## Değiştirilmiş PDF Belgesini Kaydetme

Son olarak, değiştirilen PDF belgesini yeni görünmez notla kaydedebiliriz.

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## Aspose.PDF for .NET kullanarak Nasıl Görünmez Ek Açıklama Yapılacağına İlişkin Örnek Kaynak Kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
annotation.Contents = "ABCDEFG";
annotation.Characteristics.Border = System.Drawing.Color.Red;
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1