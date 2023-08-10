---
title: PDF Dosyasında Son Kullanma Tarihini Ayarla
linktitle: PDF Dosyasında Son Kullanma Tarihini Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuz ile Aspose.PDF for .NET kullanarak PDF dosyasında son kullanma tarihini nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 300
url: /tr/net/programming-with-document/setexpirydate/
---
Aspose.PDF for .NET, PDF dosyalarıyla çalışmak için çeşitli özellikler sağlayan güçlü bir kitaplıktır. Böyle bir özellik, bir PDF belgesi için bir son kullanma tarihi belirleme yeteneğidir. Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesi için son kullanma tarihi belirleme sürecinde size yol göstereceğiz. 

## 1. Adım: Belge dizinine giden yolu ayarlayın

Başlamadan önce, PDF belgemizin bulunduğu dizinin yolunu belirlememiz gerekiyor. Bu yolu "dataDir" adlı bir değişkende saklayacağız.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Yeni bir PDF belgesi oluşturma

 Yeni bir PDF belgesi oluşturmak için yeni bir PDF belgesi oluşturmamız gerekir.`Aspose.Pdf.Document` nesne. Bunu aşağıdaki kodu kullanarak yapabiliriz:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## 3. Adım: PDF belgesine yeni bir sayfa ekleme

PDF belgesini oluşturduktan sonra ona yeni bir sayfa ekleyebiliriz. Bunu aşağıdaki kodu kullanarak yapabiliriz:

```csharp
doc.Pages.Add();
```

## 4. Adım: PDF Belgesine Metin Ekleme

PDF belgesine bir sayfa ekledikten sonra, onu kullanarak metin ekleyebiliriz.`Paragraphs` Toplamak. Bunu aşağıdaki kodu kullanarak yapabiliriz:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## 5. Adım: JavaScript kullanarak PDF son kullanma tarihini ayarlama

PDF son kullanma tarihini ayarlamak için bir JavaScript nesnesi oluşturmamız gerekiyor. Bunu aşağıdaki kodu kullanarak yapabiliriz:

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

## 6. Adım: PDF Dosyasını Kaydedin

 Son kullanma tarihini ayarladıktan sonra, PDF dosyasını kaydetmeniz gerekir. Bunu yapmak için,`Save` yöntemi`Document` nesnesini seçin ve yolu güncellenmiş PDF dosyasını kaydetmek istediğiniz yere iletin.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// PDF Belgesini Kaydet
doc.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Set Expiry Date için örnek kaynak kodu

Aspose.PDF for .NET kullanarak son kullanım tarihini ayarlamak için eksiksiz örnek kaynak kodunu burada bulabilirsiniz:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge nesnesini örneklendir
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// PDF dosyasının sayfa koleksiyonuna sayfa ekle
doc.Pages.Add();
// Sayfa nesnesinin paragraf koleksiyonuna metin parçası ekleyin
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// PDF son kullanma tarihini ayarlamak için JavaScript nesnesi oluşturun
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

Aspose.PDF for .NET kullanarak bir PDF belgesi için son kullanma tarihi belirlemek, belgenin yalnızca belirli bir süre boyunca geçerli olmasını sağlamak için yararlı bir özelliktir. Geliştiriciler, adım adım kılavuzu izleyerek ve sağlanan C# kaynak kodunu kullanarak son kullanma tarihini kolayca ayarlayabilir ve zaman sınırlı geçerliliği olan PDF'ler oluşturabilir. Bu özellik, sınırlı bir süre için erişilmesi veya dağıtılması gereken belgeler için özellikle yararlı olabilir.

### PDF dosyasında son kullanma tarihi belirlemek için SSS

#### S: PDF belgesi için farklı bir son kullanma tarihi belirleyebilir miyim?

 C: Evet, 5. Adımda JavaScript kodunu değiştirerek PDF belgesi için farklı bir son kullanma tarihi belirleyebilirsiniz. Sağlanan örnekte, son kullanma tarihi Mayıs 2017 olarak ayarlanmıştır. Farklı bir son kullanma tarihi ayarlamak için,`year` Ve`month` JavaScript kodundaki değişkenleri istenen yıl ve aya ayarlayın.

#### S: PDF belgesinin süresi dolduğunda ne olur?

Y: JavaScript kodunda belirtildiği gibi PDF belgesinin süresi dolduğunda, görüntüleyici dosyanın süresinin dolduğunu ve kullanıcının yeni bir belgeye ihtiyacı olduğunu belirten bir uyarı mesajı görüntüler. Bu uyarı mesajı, PDF açıldığında gösterilecektir.

#### S: Son kullanma tarihi için sadece tarih yerine belirli bir zaman kullanabilir miyim?

 C: Evet, JavaScript kodunda son kullanma tarihi için belirli bir zaman belirleyebilirsiniz. değiştirerek`expiry` JavaScript kodundaki değişkene istediğiniz süreyi dahil etmek için, son kullanma tarihi için belirli bir saat ayarlayabilirsiniz.