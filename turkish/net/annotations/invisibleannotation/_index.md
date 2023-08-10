---
title: PDF Dosyasında Görünmez Açıklama
linktitle: PDF Dosyasında Görünmez Açıklama
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile C# kaynak kodunu kullanarak PDF dosyasında nasıl görünmez açıklama ekleyeceğinizi öğrenin. Adım adım rehber.
type: docs
weight: 100
url: /tr/net/annotations/invisibleannotation/
---
PDF dosyasındaki açıklamalar, gerçek içeriği değiştirmeden bir belgeye fazladan bilgi veya notlar eklemenizi sağlayan güçlü bir özelliktir. Metni vurgulamak, bir belgenin belirli alanlarına dikkat çekmek veya yorum veya geri bildirim eklemek için kullanılabilirler.

PDF belgelerinde kullanabileceğiniz pek çok farklı ek açıklama türü vardır, örneğin:

- Metin Açıklamaları
- Bağlantı Açıklamaları
- Damga Açıklamaları
- Ses Açıklamaları
- Dosya Ek Açıklamaları
- ve daha fazlası

## 1. Adım: Aspose.PDF for .NET Kullanarak PDF Belgesinde Görünmez Ek Açıklama Oluşturma

 Aspose.PDF for .NET kullanarak bir PDF belgesinde görünmez bir ek açıklama oluşturmak için önce bir`FreeTextAnnotation` nesnesini seçin ve ek açıklamanın konumunu ve boyutunu belirtin.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

 Yukarıdaki kodda bir tane oluşturuyoruz.`FreeTextAnnotation` nesnesini seçin ve açıklamanın konumunu PDF belgesinin 2. sayfasında belirtin. Açıklamada görüntülenecek metnin yazı tipini, boyutunu ve rengini de belirliyoruz.

## 2. Adım: Görünmez Ek Açıklamaya Özellikler Ekleme

Ardından, ek açıklamaya kenarlık rengi, arka plan rengi veya opaklık gibi bazı özellikler ekleyebiliriz.

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

Yukarıdaki kodda açıklamanın kenarlık rengini kırmızı olarak ayarladık.

## 3. Adım: Ek Açıklama İşaretlerini Ayarlama

Ek açıklamayı oluşturup özelliklerini ayarladıktan sonra, açıklama bayraklarını belirtebiliriz. Bu öğreticide, ek açıklamanın yazdırılabilir olmasını ancak görüntülenemez olmasını istiyoruz.

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);
```

## 4. Adım: Değiştirilmiş PDF Belgesini Kaydetme

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
doc.Pages[1].Annotations.Add(annotation);

dataDir = dataDir + "InvisibleAnnotation_out.pdf";
// Çıktı dosyasını kaydet
doc.Save(dataDir);
// ExEnd:GörünmezAçıklama
Console.WriteLine("\nAnnotation nvisible successfully.\nFile saved at " + dataDir);
```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesinde nasıl görünmez bir ek açıklama oluşturacağımızı öğrendik. Görünmez açıklamalar, okuyucuya göstermeden bir belgeye fazladan bilgi veya notlar eklemek istediğinizde yararlı bir özelliktir. Geliştiriciler, adım adım kılavuzu izleyerek ve sağlanan C# kaynak kodunu kullanarak PDF belgelerinde kolayca görünmez açıklamalar oluşturabilir ve özelleştirebilirler. Aspose.PDF for .NET, ek açıklamalarla çalışmak için kapsamlı bir araç seti sağlar ve PDF dosyalarınızın etkileşimini ve kullanılabilirliğini geliştirmenize olanak tanır.

### SSS

#### S: Bir PDF belgesindeki görünmez açıklama nedir?

Y: Bir PDF belgesindeki görünmez açıklama, sayfada görünmeyen ancak ek bilgiler veya notlar içeren bir açıklamadır. Okuyucuya göstermeden yorum veya geri bildirim eklemenizi sağlar.

#### S: Görünmez bir açıklamaya ne tür özellikler eklenebilir?

C: Görünmez bir ek açıklamaya, görüntülenecek metnin kenarlık rengi, arka plan rengi, opaklık, yazı tipi türü, boyutu ve rengi gibi çeşitli özellikler eklenebilir.

#### S: Görünmez bir açıklama için farklı açıklama bayrakları ayarlayabilir miyim?

C: Evet, gereksinimlerinize bağlı olarak görünmez bir açıklama için farklı açıklama bayrakları ayarlayabilirsiniz. Örneğin, ek açıklamayı yazdırılabilir ancak görüntülenemez hale getirebilirsiniz.

#### S: PDF belgesinin belirli bir sayfasına nasıl görünmez bir not ekleyebilirim?

 Y: PDF belgesinin belirli bir sayfasına görünmez bir ek açıklama eklemek için, bir`FreeTextAnnotation` nesnesini seçin ve o sayfadaki ek açıklamanın konumunu ve boyutunu belirtin.

#### S: Bir PDF dosyasında var olan görünmez notun özelliklerini değiştirebilir miyim?

C: Evet, Aspose.PDF for .NET'i kullanarak bir PDF dosyasındaki mevcut bir görünmez notun özelliklerini değiştirebilirsiniz. Ek açıklamanın yazı tipini, boyutunu, rengini, kenarlık rengini, arka plan rengini, opaklığını ve diğer özelliklerini değiştirebilirsiniz.