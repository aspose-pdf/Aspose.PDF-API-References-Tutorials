---
title: Radyo düğmesi
linktitle: Radyo düğmesi
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF belgelerinize kolayca radyo düğmeleri ekleyin.
type: docs
weight: 220
url: /tr/net/programming-with-forms/radio-button/
---
Bu eğitimde size Aspose.PDF for .NET kullanarak bir PDF belgesine nasıl radyo düğmesi ekleyeceğinizi göstereceğiz. Bu süreçte size yol göstermek için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kitaplıkları içe aktardığınızdan ve belgeler dizininizin yolunu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Bir Belge Nesnesini Örneklendirin

Yeni bir PDF belgesi oluşturmak için bir Belge nesnesi örneği oluşturun:

```csharp
Document pdfDocument = new Document();
```

## 3. Adım: Sayfa ekleyin

PDF belgesine bir sayfa ekleyin:

```csharp
pdfDocument.Pages.Add();
```

## Adım 4: RadioButtonField Nesnesini Örneklendirin

Bağımsız değişken olarak sayfa numarasını belirten bir RadioButtonField nesnesi oluşturun:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## 5. Adım: Radyo düğmesi seçeneklerini ekleyin

Her seçeneğin koordinatlarını bir Rectangle nesnesiyle belirterek RadioButtonField nesnesine radyo düğmesi seçenekleri ekleyin:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## Adım 6: Radyo düğmesini forma ekleyin

Radyo düğmesini belgenin Form nesnesine ekleyin:

```csharp
pdfDocument.Form.Add(radio);
```

## Adım 7: PDF Belgesini Kaydedin

Oluşturulan PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET kullanan Radio Button için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Belge nesnesini somutlaştır
	Document pdfDocument = new Document();
	// PDF dosyasına sayfa ekleme
	pdfDocument.Pages.Add();
	// Bağımsız değişken olarak sayfa numarasıyla RadioButtonField nesnesini başlat
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// İlk radyo düğmesi seçeneğini ekleyin ve ayrıca Rectangle nesnesini kullanarak kökenini belirtin
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// İkinci radyo düğmesi seçeneğini ekle
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Belge nesnesinin nesnesini oluşturmak için radyo düğmesi ekleyin
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

Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF belgesine nasıl radyo düğmesi ekleneceğini öğrendik. Bu adımları izleyerek kolayca bir radyo düğmesi oluşturabilir ve bunu PDF belgenizdeki belirli bir sayfaya yerleştirebilirsiniz.


### SSS'ler

#### S: Radyo düğmesinin boyutu ve rengi gibi görünümünü özelleştirebilir miyim?

 C: Evet, radyo düğmesinin görünümünü aşağıdaki düğmeyi kullanarak özelleştirebilirsiniz:`Rectangle` Boyutunu ve konumunu tanımlamak için nesnenin koordinatları. Aspose.PDF for .NET, radyo düğmesinin görünümünü ihtiyaçlarınıza uyacak şekilde ayarlamanıza olanak tanır.

#### S: Aynı sayfaya farklı gruplara sahip birden fazla radyo düğmesi ekleyebilir miyim?

C: Evet, aynı sayfaya farklı gruplara sahip birden fazla radyo düğmesi ekleyebilirsiniz. Her radyo düğmesi grubunun benzersiz bir adı olabilir ve her grup içinde aynı anda yalnızca bir seçenek seçilebilir.

#### S: Radyo düğmesi seçeneklerine nasıl etiket veya metin açıklaması ekleyebilirim?

 C: Radyo düğmesi seçeneklerine etiket veya metin açıklaması eklemek için`TextStamp`Metni PDF belgesinin üzerine belirli koordinatlarda yerleştirmek için Aspose.PDF for .NET'ten sınıf.

#### S: Aspose.PDF for .NET, .NET Framework'ün tüm sürümleriyle uyumlu mudur?

C: Evet, Aspose.PDF for .NET, .NET Core ve .NET Standard da dahil olmak üzere .NET Framework'ün tüm sürümleriyle uyumludur.

#### S: PDF belgesindeki radyo düğmesi seçeneğinin seçimini programlı olarak kontrol edebilir miyim?

 C: Evet, radyo düğmesi seçeneğinin seçimini programlı olarak kontrol edebilirsiniz.`IsSelected` mülkiyeti`RadioButtonOption` sınıf. Bu özellik, belirli bir seçeneği seçili olarak ayarlamanıza olanak tanır.