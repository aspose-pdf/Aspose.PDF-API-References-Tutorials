---
title: Açıklama Kaynağını Alın
linktitle: Açıklama Kaynağını Alın
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuz ile Aspose.PDF for .NET kullanarak bir ek açıklamanın kaynağını nasıl alacağınızı öğrenin.
type: docs
weight: 90
url: /tr/net/annotations/getresourceofannotation/
---
Örnek, Aspose.PDF for .NET ile açıklama kaynağının nasıl alınacağını gösterir. Aspose.PDF for .NET kullanarak bir ek açıklamanın kaynağını almak için şu adımları izleyin:

## Adım 1: Belgenin bulunduğu dizinin yolunu ayarlayın.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Kaynağını almak istediğiniz ek açıklamayı içeren PDF belgesini açın.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## 3. Adım: Bir ek açıklama oluşturun.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## Adım 4: Ek açıklamayı belgedeki bir sayfaya ekleyin.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## Adım 5: Belgeyi kaydedin.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Adım 6: Değiştirilen belgeyi açın.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Adım 7: Ek açıklamanın eylemini alın.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## Adım 7: Eylemin yorumunu alın.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## Adım 8: Medya klibini alın.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## Adım 9: Dosya belirtimini alın.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## Adım 10: Ortamın verilerini okuyun.

```csharp
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
   ms.Write(buffer, 0, read);
}
```

## Adım 11: Yorumlamanın ve yorumlama işleminin adını yazdırın.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

Bu adımları izleyerek, Aspose.PDF for .NET kullanarak bir PDF belgesindeki notun kaynağını kolayca alabilirsiniz.

### Aspose.PDF for .NET kullanarak Get Resource Of Annotation için örnek kaynak kodu:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//Ek açıklama oluştur
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
// Dokümanı Kaydet
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
// Belgeyi aç
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
//Ek açıklamanın eylemini alın
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
//yorumlama eyleminin yorumlamasını alın
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
// Medya Klibi
MediaClip clip = (rendition as MediaRendition).MediaClip;
FileSpecification data = (clip as MediaClipData).Data;
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
//Ortam verilerine FileSpecification.Contents'tan erişilebilir
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
ms.Write(buffer, 0, read);
}
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesinden belirli bir ek açıklamanın kaynağının nasıl alınacağını araştırdık. Geliştiriciler, adım adım kılavuzu izleyerek ve sağlanan C# kaynak kodunu kullanarak, PDF belgelerindeki yorumlama ek açıklamaları da dahil olmak üzere ek açıklamalara kolayca erişebilir ve bunları yönetebilir.

### SSS

#### S: PDF açıklamaları bağlamında yorumlama nedir?

C: PDF ek açıklamaları bağlamında yorumlama, bir multimedya içerik sunumudur. Ses veya video gibi multimedyaların PDF belgesine gömülmesine izin verir. Yorumlama ek açıklaması, sunulacak medyayı ve nasıl oynatılması gerektiğini belirtir.

#### S: Bir yorumlama ek açıklamasıyla ilişkili medya dosyasının adını alabilir miyim?

 C: Evet, Aspose.PDF for .NET'i kullanarak bir yorumlama ek açıklamasıyla ilişkili medya dosyasının adını alabilirsiniz. Ortam dosyası adına şu adresten erişilebilir:`FileSpecification` arasında`MediaClip` nesne.

#### S: Aspose.PDF for .NET, medya dosyalarını bir yorumlama ek açıklamasından çıkarabilir mi?

C: Evet, Aspose.PDF for .NET, ses veya video içeriği içeren bir yorumlama notundan medya verilerini çıkarabilir ve ayrı bir dosya olarak kaydedebilir.

#### S: Bir yorum notunun medya verilerine nasıl erişebilirim?

 Y: Bir yorumlama ek açıklamasının medya verilerine şu adresten erişilebilir:`FileSpecification.Contents` mülkiyeti`MediaClipData` nesne.

#### S: Aspose.PDF for .NET kullanarak bir yorum açıklama notuyla ilişkili medyayı değiştirebilir miyim?

Y: Aspose.PDF for .NET, bir yorumlama ek açıklamasıyla ilişkili ortam verilerine erişmek ve bunları değiştirmek için yöntemler sağlar. Bir yorumlama notu tarafından kullanılan medya dosyasını güncelleyebilir veya değiştirebilirsiniz.