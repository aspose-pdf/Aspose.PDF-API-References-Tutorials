---
title: Belirli Ek Açıklamayı Sil
linktitle: Belirli Ek Açıklamayı Sil
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuz ile Aspose.PDF for .NET kullanarak bir PDF belgesinden belirli bir açıklamayı nasıl sileceğinizi öğrenin.
type: docs
weight: 50
url: /tr/net/annotations/deleteparticularannotation/
---
Bu eğitimde, C# kullanarak bir PDF dosyasından belirli bir açıklamayı silmek için Aspose.PDF for .NET'i nasıl kullanacağınızı göstereceğiz.

Aspose.PDF for .NET ile belirli notların nasıl silineceğini göstermek için aşağıdaki adımları izleyin.

## 1. Adım: Dizin yolunu ayarlayın

Silinecek ek açıklamayı içeren PDF dosyasının yolunu tutmak için bir değişken bildirin. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: PDF belgesini açın

 kullanarak PDF dosyasını açın.`Document` Aspose.PDF for .NET'te sınıf.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteParticularAnnotation.pdf");
```

## 3. Adım: Belirli notu silmek için sayfayı alın

Dizini ve ait olduğu sayfanın dizinini belirterek söz konusu ek açıklamayı silin. Bu eğitimde, PDF dosyasının ikinci sayfasındaki 1. indekste bulunan ek açıklamayı siliyoruz.

```csharp
pdfDocument.Pages[1].Annotations.Delete(1);
```
## 4. Adım: Güncellenmiş PDF belgesini kaydedin

Güncellenmiş PDF dosyasını farklı bir adla yeni bir dosyaya kaydedin.

```csharp
dataDir = dataDir + "DeleteParticularAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```

## 5. Adım: Belirli Açıklamayı Sil için bir mesaj gösterin

Belirli açıklamanın silindiğini ve güncellenmiş PDF dosyasının kaydedildiğini belirten bir mesaj yazdırın.

```csharp
Console.WriteLine("\nParticular annotation deleted successfully.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanarak Belirli Bir Açıklamayı Silmek için Örnek Kaynak Kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Belgeyi aç
	Document pdfDocument = new Document(dataDir + "DeleteParticularAnnotation.pdf");

	// Belirli notu sil
	pdfDocument.Pages[1].Annotations.Delete(1);

	dataDir = dataDir + "DeleteParticularAnnotation_out.pdf";
	// Güncellenen belgeyi kaydet
	pdfDocument.Save(dataDir);

	Console.WriteLine("\nParticular annotation deleted successfully.\nFile saved at " + dataDir);

```
