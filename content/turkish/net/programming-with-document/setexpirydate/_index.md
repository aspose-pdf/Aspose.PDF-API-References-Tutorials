---
title: PDF Dosyasında Son Kullanma Tarihini Ayarlayın
linktitle: PDF Dosyasında Son Kullanma Tarihini Ayarlayın
second_title: .NET API Referansı için Aspose.PDF
description: Bu adım adım kılavuzla Aspose.PDF for .NET kullanarak PDF dosyasında son kullanma tarihini nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 300
url: /tr/net/programming-with-document/setexpirydate/
---
Aspose.PDF for .NET, PDF dosyalarıyla çalışmak için çeşitli özellikler sağlayan güçlü bir kütüphanedir. Bu özelliklerden biri, bir PDF belgesi için son kullanma tarihi belirleme yeteneğidir. Bu eğitimde, Aspose.PDF for .NET'i kullanarak bir PDF belgesi için son kullanma tarihi belirleme sürecinde size yol göstereceğiz. 

## 1. Adım: Belge dizininin yolunu ayarlayın

Başlamadan önce PDF belgemizin bulunduğu dizinin yolunu ayarlamamız gerekiyor. Bu yolu "dataDir" adlı bir değişkende saklayacağız.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Yeni bir PDF belgesi oluşturma

 Yeni bir PDF belgesi oluşturmak için yeni bir örnek oluşturmamız gerekiyor`Aspose.Pdf.Document` nesne. Bunu aşağıdaki kodu kullanarak yapabiliriz:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## 3. Adım: PDF belgesine yeni bir sayfa ekleme

PDF belgesini oluşturduktan sonra ona yeni bir sayfa ekleyebiliriz. Bunu aşağıdaki kodu kullanarak yapabiliriz:

```csharp
doc.Pages.Add();
```

## Adım 4: PDF Belgesine Metin Ekleme

PDF belgesine bir sayfa ekledikten sonra ona metin ekleyebiliriz.`Paragraphs` Toplamak. Bunu aşağıdaki kodu kullanarak yapabiliriz:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## 5. Adım: JavaScript kullanarak PDF'nin son kullanma tarihini ayarlama

PDF'nin son kullanma tarihini ayarlamak için bir JavaScript nesnesi oluşturmamız gerekir. Bunu aşağıdaki kodu kullanarak yapabiliriz:

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// JavaScript'i PDF açma eylemi olarak ayarla
doc.OpenAction = javaScript;
```

Bu kodda son kullanma tarihini Mayıs 2017 olarak ayarlıyoruz.

## Adım 6: PDF Dosyasını Kaydedin

 Son kullanma tarihini belirledikten sonra PDF dosyasını kaydetmeniz gerekir. Bunu yapmak için şunları kullanabilirsiniz:`Save` yöntemi`Document` nesneyi seçin ve güncellenmiş PDF dosyasını kaydetmek istediğiniz yere giden yolu iletin.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// PDF Belgesini Kaydet
doc.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Sona Erme Tarihini Ayarla için örnek kaynak kodu

Aspose.PDF for .NET'i kullanarak son kullanma tarihini ayarlamak için kaynak kodunun tamamını burada bulabilirsiniz:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge nesnesini somutlaştır
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// PDF dosyasının sayfa koleksiyonuna sayfa ekle
doc.Pages.Add();
// Sayfa nesnesinin paragraf koleksiyonuna metin parçası ekleme
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// PDF'nin son kullanma tarihini ayarlamak için JavaScript nesnesi oluşturun
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// JavaScript'i PDF açma eylemi olarak ayarla
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// PDF Belgesini Kaydet
doc.Save(dataDir);
```

## Çözüm

Aspose.PDF for .NET kullanarak bir PDF belgesi için son kullanma tarihi belirlemek, belgenin yalnızca belirli bir süre için geçerli olmasını sağlayan kullanışlı bir özelliktir. Geliştiriciler, adım adım kılavuzu izleyerek ve sağlanan C# kaynak kodunu kullanarak son kullanma tarihini kolayca ayarlayabilir ve süresi sınırlı geçerliliğe sahip PDF'ler oluşturabilir. Bu özellik, sınırlı bir süre boyunca erişilmesi veya dağıtılması gereken belgeler için özellikle yararlı olabilir.

### PDF dosyasında son kullanma tarihini ayarlamak için SSS

#### S: PDF belgesi için farklı bir son kullanma tarihi ayarlayabilir miyim?

 C: Evet, 5. Adımda JavaScript kodunu değiştirerek PDF belgesi için farklı bir son kullanma tarihi belirleyebilirsiniz. Verilen örnekte son kullanma tarihi Mayıs 2017 olarak ayarlanmıştır. Farklı bir son kullanma tarihi ayarlamak için,`year` Ve`month` JavaScript kodundaki değişkenleri istenen yıl ve aya göre ayarlayın.

#### S: PDF belgesinin süresi dolduğunda ne olur?

C: JavaScript kodunda belirtildiği gibi PDF belgesinin süresi dolduğunda, görüntüleyici dosyanın süresinin dolduğunu ve kullanıcının yeni bir dosyaya ihtiyacı olduğunu belirten bir uyarı mesajı görüntüler. Bu uyarı mesajı PDF açıldığında gösterilecektir.

#### S: Son kullanma tarihi olarak yalnızca tarih yerine belirli bir saati kullanabilir miyim?

 C: Evet, JavaScript kodunda son kullanma tarihi için belirli bir zaman ayarlayabilirsiniz. Değiştirerek`expiry` İstenilen süreyi eklemek için JavaScript kodundaki değişkene, son kullanma tarihi için belirli bir süre ayarlayabilirsiniz.