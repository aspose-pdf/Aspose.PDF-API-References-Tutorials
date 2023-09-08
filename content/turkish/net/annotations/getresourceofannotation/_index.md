---
title: Ek Açıklamanın Kaynağını Alın
linktitle: Ek Açıklamanın Kaynağını Alın
second_title: .NET API Referansı için Aspose.PDF
description: Bu adım adım kılavuzla Aspose.PDF for .NET kullanarak bir açıklamanın kaynağını nasıl alacağınızı öğrenin.
type: docs
weight: 90
url: /tr/net/annotations/getresourceofannotation/
---
Örnek, Aspose.PDF for .NET ile açıklama kaynağının nasıl alınacağını gösterir. Aspose.PDF for .NET kullanarak bir açıklamanın kaynağını almak için şu adımları izleyin:

## Adım 1: Belgenin bulunduğu dizinin yolunu ayarlayın.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Kaynağını almak istediğiniz ek açıklamayı içeren PDF belgesini açın.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## Adım 3: Bir ek açıklama oluşturun.

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

## Adım 9: Dosya özelliklerini alın.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## Adım 10: Medyanın verilerini okuyun.

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

## Adım 11: Yorumlamanın adını ve yorumlama işlemini yazdırın.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

Bu adımları izleyerek Aspose.PDF for .NET'i kullanarak bir PDF belgesindeki bir açıklamanın kaynağını kolayca alabilirsiniz.

### Aspose.PDF for .NET kullanarak Get Resource Of Annotation için örnek kaynak kodu:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//Ek açıklama oluştur
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
// Belgeyi Kaydet
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
// Belgeyi aç
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
//Ek açıklamanın eylemini alın
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
//Yorumlama eyleminin yorumunu alın
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
// Medya Klibi
MediaClip clip = (rendition as MediaRendition).MediaClip;
FileSpecification data = (clip as MediaClipData).Data;
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
//Medya verilerine FileSpecification.Contents adresinden erişilebilir.
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
ms.Write(buffer, 0, read);
}
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinden belirli bir açıklamanın kaynağının nasıl alınacağını araştırdık. Geliştiriciler, adım adım kılavuzu izleyerek ve sağlanan C# kaynak kodunu kullanarak, PDF belgelerindeki yorumlama ek açıklamaları da dahil olmak üzere ek açıklamalara kolayca erişebilir ve bunları yönetebilir.

### SSS'ler

#### S: PDF ek açıklamaları bağlamında yorumlama nedir?

C: PDF ek açıklamaları bağlamında yorumlama, multimedya içerik sunumudur. PDF belgesine ses veya video gibi multimedyaların yerleştirilmesine olanak tanır. Yorumlama açıklaması, sunulacak medyayı ve nasıl oynatılması gerektiğini belirtir.

#### S: Bir yorumlama açıklamasıyla ilişkili medya dosyasının adını alabilir miyim?

C: Evet, Aspose.PDF for .NET'i kullanarak bir yorumlama açıklamasıyla ilişkili medya dosyasının adını alabilirsiniz. Medya dosyası adına şu adresten erişilebilir:`FileSpecification` arasında`MediaClip` nesne.

#### S: Aspose.PDF for .NET bir yorumlama açıklamasından medya dosyalarını çıkarabilir mi?

C: Evet, Aspose.PDF for .NET, ses veya video içeriği içeren bir yorumlama notundan medya verilerini çıkarabilir ve ayrı bir dosya olarak kaydedebilir.

#### S: Bir yorumlama ek açıklamasının medya verilerine nasıl erişebilirim?

 C: Bir yorumlama ek açıklamasının medya verilerine şu adresten erişilebilir:`FileSpecification.Contents` mülkiyeti`MediaClipData` nesne.

#### S: Bir yorumlama açıklamasıyla ilişkili medyayı Aspose.PDF for .NET kullanarak değiştirebilir miyim?

C: Aspose.PDF for .NET, bir yorumlama açıklamasıyla ilişkili medya verilerine erişmeye ve bunları değiştirmeye yönelik yöntemler sağlar. Bir yorumlama ek açıklaması tarafından kullanılan medya dosyasını güncelleyebilir veya değiştirebilirsiniz.