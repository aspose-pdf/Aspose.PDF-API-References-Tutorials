---
title: PDF Dosyasında Son Kullanma Tarihini Ayarla
linktitle: PDF Dosyasında Son Kullanma Tarihini Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzla Aspose.PDF for .NET kullanarak PDF dosyasına son kullanma tarihinin nasıl ayarlanacağını öğrenin.
type: docs
weight: 300
url: /tr/net/programming-with-document/setexpirydate/
---
Aspose.PDF for .NET, PDF dosyalarıyla çalışmak için çeşitli özellikler sağlayan güçlü bir kütüphanedir. Bu özelliklerden biri de PDF belgesi için son kullanma tarihi belirleme yeteneğidir. Bu eğitimde, Aspose.PDF for .NET kullanarak PDF belgesi için son kullanma tarihi belirleme sürecini adım adım anlatacağız. 

## Adım 1: Belge dizinine giden yolu ayarlayın

Başlamadan önce, PDF belgemizin bulunduğu dizine giden yolu ayarlamamız gerekiyor. Bu yolu "dataDir" adlı bir değişkende saklayacağız.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Yeni bir PDF belgesi oluşturma

 Yeni bir PDF belgesi oluşturmak için yeni bir örnek oluşturmamız gerekir`Aspose.Pdf.Document` nesne. Bunu aşağıdaki kodu kullanarak yapabiliriz:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Adım 3: PDF belgesine yeni bir sayfa ekleme

PDF belgesini oluşturduğumuzda, ona yeni bir sayfa ekleyebiliriz. Bunu aşağıdaki kodu kullanarak yapabiliriz:

```csharp
doc.Pages.Add();
```

## Adım 4: PDF Belgesine Metin Ekleme

 PDF belgesine bir sayfa ekledikten sonra, şunu kullanarak ona metin ekleyebiliriz:`Paragraphs` koleksiyon. Bunu aşağıdaki kodu kullanarak yapabiliriz:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## Adım 5: JavaScript kullanarak PDF son kullanma tarihini ayarlama

PDF son kullanma tarihini ayarlamak için bir JavaScript nesnesi oluşturmamız gerekir. Bunu aşağıdaki kodu kullanarak yapabiliriz:

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// JavaScript'i PDF olarak ayarla açık eylem
doc.OpenAction = javaScript;
```

Bu kodda son kullanma tarihini Mayıs 2017 olarak ayarlıyoruz.

## Adım 6: PDF Dosyasını Kaydedin

 Son kullanma tarihini ayarladıktan sonra PDF dosyasını kaydetmeniz gerekir. Bunu yapmak için şunu kullanabilirsiniz:`Save` yöntemi`Document` nesnesini seçin ve güncellenmiş PDF dosyasını kaydetmek istediğiniz yolu girin.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// PDF Belgesini Kaydet
doc.Save(dataDir);
```

### .NET için Aspose.PDF kullanarak Son Kullanma Tarihini Ayarlamak için örnek kaynak kodu

İşte .NET için Aspose.PDF kullanarak son kullanma tarihini ayarlamaya yönelik tam örnek kaynak kodu:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge nesnesini örnekle
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// PDF dosyasının sayfa sayfa koleksiyonunu ekle
doc.Pages.Add();
// Sayfa nesnesinin paragraf koleksiyonuna metin parçası ekle
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// PDF son kullanma tarihini ayarlamak için JavaScript nesnesi oluşturun
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// JavaScript'i PDF olarak ayarla açık eylem
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// PDF Belgesini Kaydet
doc.Save(dataDir);
```

## Çözüm

Aspose.PDF for .NET kullanarak bir PDF belgesi için son kullanma tarihi belirlemek, belgenin yalnızca belirli bir süre için geçerli olduğundan emin olmak için kullanışlı bir özelliktir. Adım adım kılavuzu izleyerek ve sağlanan C# kaynak kodunu kullanarak, geliştiriciler son kullanma tarihini kolayca ayarlayabilir ve zaman sınırlı geçerliliğe sahip PDF'ler oluşturabilir. Bu özellik, sınırlı bir süre için erişilmesi veya dağıtılması gereken belgeler için özellikle yararlı olabilir.

### PDF dosyasında son kullanma tarihi belirlemeye ilişkin SSS

#### S: PDF belgesi için farklı bir son kullanma tarihi belirleyebilir miyim?

 A: Evet, Adım 5'teki JavaScript kodunu değiştirerek PDF belgesi için farklı bir son kullanma tarihi belirleyebilirsiniz. Sağlanan örnekte son kullanma tarihi Mayıs 2017 olarak ayarlanmıştır. Farklı bir son kullanma tarihi belirlemek için,`year` Ve`month` JavaScript kodundaki değişkenleri istenilen yıl ve aya ayarlayın.

#### S: PDF belgesinin süresi dolduğunda ne olur?

A: JavaScript kodunda belirtildiği gibi PDF belgesinin süresi dolduğunda, görüntüleyici dosyanın süresinin dolduğunu ve kullanıcının yenisine ihtiyacı olduğunu belirten bir uyarı mesajı görüntüler. Bu uyarı mesajı PDF açıldığında gösterilir.

#### S: Sadece tarih yerine son kullanma tarihi için belirli bir zaman kullanabilir miyim?

 A: Evet, JavaScript kodunda son kullanma tarihi için belirli bir zaman belirleyebilirsiniz.`expiry` JavaScript kodunda istediğiniz zamanı ekleyebileceğiniz bir değişken kullanarak, son kullanma tarihi için belirli bir zaman belirleyebilirsiniz.