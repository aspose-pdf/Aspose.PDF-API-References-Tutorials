---
title: Radyo Düğmesi
linktitle: Radyo Düğmesi
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinize kolayca radyo düğmeleri ekleyin.
type: docs
weight: 220
url: /tr/net/programming-with-forms/radio-button/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesine radyo düğmesi eklemeyi göstereceğiz. Bu süreçte size rehberlik etmek için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kütüphaneleri içe aktardığınızdan ve belgelerinizin dizinine giden yolu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Bir Belge Nesnesi Oluşturun

Yeni bir PDF belgesi oluşturmak için bir Belge nesnesi örneği oluşturun:

```csharp
Document pdfDocument = new Document();
```

## Adım 3: Bir sayfa ekleyin

PDF belgesine bir sayfa ekleyin:

```csharp
pdfDocument.Pages.Add();
```

## Adım 4: Bir RadioButtonField Nesnesi Oluşturun

Sayfa numarasını bir argüman olarak belirten bir RadioButtonField nesnesi oluşturun:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Adım 5: Radyo düğmesi seçeneklerini ekleyin

Her seçeneğin koordinatlarını bir Rectangle nesnesiyle belirterek RadioButtonField nesnesine radyo düğmesi seçenekleri ekleyin:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## Adım 6: Radyo düğmesini forma ekleyin

Belgenin Form nesnesine radyo düğmesini ekleyin:

```csharp
pdfDocument.Form.Add(radio);
```

## Adım 7: PDF Belgesini Kaydedin

Oluşturulan PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### .NET için Aspose.PDF kullanılarak Radyo Düğmesi için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizinine giden yol.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Belge nesnesini örnekle
	Document pdfDocument = new Document();
	// PDF dosyasına bir sayfa ekle
	pdfDocument.Pages.Add();
	// Sayfa numarasını argüman olarak kullanarak RadioButtonField nesnesini oluşturun
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// İlk radyo düğmesi seçeneğini ekleyin ve ayrıca Rectangle nesnesini kullanarak kökenini belirtin
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// İkinci radyo düğmesi seçeneğini ekle
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Belge nesnesinin form nesnesine radyo düğmesi ekle
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	// PDF dosyasını kaydedin
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesine radyo düğmesi eklemeyi öğrendik. Bu adımları izleyerek, kolayca bir radyo düğmesi oluşturabilir ve bunu PDF belgenizdeki belirli bir sayfaya yerleştirebilirsiniz.


### SSS

#### S: Radyo düğmesinin boyutunu ve rengini gibi görünümünü özelleştirebilir miyim?

 A: Evet, radyo düğmesinin görünümünü kullanarak özelleştirebilirsiniz.`Rectangle` nesnenin boyutunu ve konumunu tanımlamak için koordinatlarını kullanın. Aspose.PDF for .NET, radyo düğmesinin görünümünü ihtiyaçlarınıza uyacak şekilde ayarlamanıza olanak tanır.

#### S: Aynı sayfaya farklı gruplara sahip birden fazla radyo düğmesi ekleyebilir miyim?

A: Evet, aynı sayfaya farklı gruplara sahip birden fazla radyo düğmesi ekleyebilirsiniz. Her radyo düğmesi grubunun benzersiz bir adı olabilir ve her grupta aynı anda yalnızca bir seçenek seçilebilir.

#### S: Radyo düğmesi seçeneklerine nasıl etiket veya metin açıklaması ekleyebilirim?

 A: Radyo düğmesi seçeneklerine bir etiket veya metin açıklaması eklemek için şunu kullanabilirsiniz:`TextStamp`Aspose.PDF'den .NET için PDF belgesine belirli koordinatlarda metin yerleştirmek için bir sınıf.

#### S: Aspose.PDF for .NET, .NET Framework'ün tüm sürümleriyle uyumlu mudur?

C: Evet, Aspose.PDF for .NET, .NET Core ve .NET Standard dahil olmak üzere .NET Framework'ün tüm sürümleriyle uyumludur.

#### S: PDF belgesinde bir radyo düğmesi seçeneğinin seçimini programlı olarak kontrol edebilir miyim?

 A: Evet, bir radyo düğmesi seçeneğinin seçimini programatik olarak kontrol edebilirsiniz.`IsSelected` mülkiyeti`RadioButtonOption` sınıf. Bu özellik belirli bir seçeneği seçili olarak ayarlamanıza olanak tanır.