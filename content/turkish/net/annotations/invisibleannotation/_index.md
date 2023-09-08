---
title: PDF Dosyasında Görünmez Açıklama
linktitle: PDF Dosyasında Görünmez Açıklama
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile C# kaynak kodunu kullanarak PDF dosyasında açıklamaların nasıl görünmez hale getirileceğini öğrenin. Adım adım rehber.
type: docs
weight: 100
url: /tr/net/annotations/invisibleannotation/
---
PDF dosyasındaki ek açıklamalar, gerçek içeriği değiştirmeden bir belgeye ekstra bilgi veya notlar eklemenizi sağlayan güçlü bir özelliktir. Metni vurgulamak, belgenin belirli alanlarına dikkat çekmek veya yorum veya geri bildirim eklemek için kullanılabilirler.

PDF belgelerinde kullanabileceğiniz birçok farklı türde ek açıklama vardır:

- Metin Açıklamaları
- Bağlantı Açıklamaları
- Damga Açıklamaları
- Ses Açıklamaları
- Dosya Eki Ek Açıklamaları
- ve daha fazlası

## Adım 1: Aspose.PDF for .NET Kullanarak PDF Belgesinde Görünmez Açıklama Oluşturma

 Aspose.PDF for .NET kullanarak bir PDF belgesinde görünmez bir açıklama oluşturmak için öncelikle bir`FreeTextAnnotation` nesneyi seçin ve ek açıklamanın konumunu ve boyutunu belirtin.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

 Yukarıdaki kodda bir tane oluşturuyoruz.`FreeTextAnnotation`nesneyi seçin ve PDF belgesinin 2. sayfasındaki açıklamanın konumunu belirtin. Ek açıklamada görüntülenecek metnin yazı tipini, boyutunu ve rengini de belirtiyoruz.

## Adım 2: Görünmez Açıklamaya Özellikler Ekleme

Daha sonra ek açıklamaya kenarlık rengi, arka plan rengi veya opaklık gibi bazı özellikler ekleyebiliriz.

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

Yukarıdaki kodda ek açıklamanın kenar rengini kırmızı olarak ayarladık.

## 3. Adım: Ek Açıklama Bayraklarını Ayarlama

Açıklamayı oluşturup özelliklerini ayarladıktan sonra açıklama bayraklarını belirleyebiliriz. Bu öğreticide, ek açıklamanın yazdırılabilir olmasını ancak görüntülenememesini istiyoruz.

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);
```

## Adım 4: Değiştirilen PDF Belgesini Kaydetme

Son olarak, değiştirilen PDF belgesini yeni görünmez ek açıklamayla kaydedebiliriz.

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## Aspose.PDF for .NET kullanarak Görünmez Açıklamaların Nasıl Yapılacağına İlişkin Örnek Kaynak Kodu

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
// Çıkış dosyasını kaydet
doc.Save(dataDir);
// ExEnd:Görünmez Ek Açıklama
Console.WriteLine("\nAnnotation nvisible successfully.\nFile saved at " + dataDir);
```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF belgesinde görünmez bir açıklamanın nasıl oluşturulacağını öğrendik. Görünmez ek açıklamalar, bir belgeye okuyucuya gösterilmeden ek bilgi veya notlar eklemek istediğinizde kullanışlı bir özelliktir. Geliştiriciler, adım adım kılavuzu izleyerek ve sağlanan C# kaynak kodunu kullanarak, PDF belgelerinde görünmez ek açıklamaları kolayca oluşturabilir ve özelleştirebilir. Aspose.PDF for .NET, açıklamalarla çalışmak için kapsamlı bir araç seti sağlayarak PDF dosyalarınızın etkileşimini ve kullanılabilirliğini geliştirmenize olanak tanır.

### SSS'ler

#### S: PDF belgesindeki görünmez ek açıklama nedir?

C: PDF belgesindeki görünmez ek açıklama, sayfada görünmeyen ancak ek bilgi veya notlar içeren ek açıklamadır. Okuyucuya göstermeden yorum veya geri bildirim eklemenizi sağlar.

#### S: Görünmez bir ek açıklamaya ne tür özellikler eklenebilir?

C: Görünmez bir açıklamaya, görüntülenecek metnin kenarlık rengi, arka plan rengi, opaklık, yazı tipi türü, boyutu ve rengi gibi çeşitli özellikler eklenebilir.

#### S: Görünmez bir açıklama için farklı açıklama bayrakları ayarlayabilir miyim?

C: Evet, gereksinimlerinize bağlı olarak görünmez bir açıklama için farklı açıklama bayrakları ayarlayabilirsiniz. Örneğin, ek açıklamayı yazdırılabilir ancak görüntülenemez hale getirebilirsiniz.

#### S: PDF belgesinin belirli bir sayfasına nasıl görünmez bir açıklama ekleyebilirim?

 C: PDF belgesinin belirli bir sayfasına görünmez bir açıklama eklemek için bir`FreeTextAnnotation` nesneyi seçin ve o sayfadaki ek açıklamanın konumunu ve boyutunu belirtin.

#### S: Bir PDF dosyasındaki mevcut görünmez ek açıklamanın özelliklerini değiştirebilir miyim?

C: Evet, Aspose.PDF for .NET'i kullanarak bir PDF dosyasındaki mevcut görünmez açıklamanın özelliklerini değiştirebilirsiniz. Ek açıklamanın yazı tipi türünü, boyutunu, rengini, kenarlık rengini, arka plan rengini, opaklığını ve diğer özelliklerini değiştirebilirsiniz.