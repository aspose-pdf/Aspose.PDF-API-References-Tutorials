---
title: Radyo düğmesi
linktitle: Radyo düğmesi
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinize kolayca radyo düğmeleri ekleyin.
type: docs
weight: 220
url: /tr/net/programming-with-forms/radio-button/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesine nasıl radyo düğmesi ekleyeceğinizi göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kitaplıkları içe aktardığınızdan emin olun ve yolu belgeler dizininize ayarlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Bir Belge Nesnesi Oluşturun

Yeni bir PDF belgesi oluşturmak için bir Belge nesnesi örneği oluşturun:

```csharp
Document pdfDocument = new Document();
```

## 3. Adım: Bir sayfa ekleyin

PDF belgesine bir sayfa ekleyin:

```csharp
pdfDocument.Pages.Add();
```

## 4. Adım: Bir RadioButtonField Nesnesi Başlatın

Sayfa numarasını bağımsız değişken olarak belirterek bir RadioButtonField nesnesi oluşturun:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## 5. Adım: Radyo düğmesi seçeneklerini ekleyin

Her seçeneğin koordinatlarını bir Rectangle nesnesiyle belirterek RadioButtonField nesnesine radyo düğmesi seçenekleri ekleyin:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## 6. Adım: Radyo düğmesini forma ekleyin

Radyo düğmesini belgenin Form nesnesine ekleyin:

```csharp
pdfDocument.Form.Add(radio);
```

## 7. Adım: PDF Belgesini Kaydedin

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
	// Belge nesnesini örneklendir
	Document pdfDocument = new Document();
	// PDF dosyasına bir sayfa ekleyin
	pdfDocument.Pages.Add();
	// Bağımsız değişken olarak sayfa numarasıyla RadioButtonField nesnesini başlat
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// İlk radyo düğmesi seçeneğini ekleyin ve ayrıca Dikdörtgen nesnesini kullanarak kaynağını belirtin
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// İkinci radyo düğmesi seçeneği ekle
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Belge nesnesinin nesnesini oluşturmak için radyo düğmesi ekle
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

Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesine radyo düğmesi eklemeyi öğrendik. Bu adımları izleyerek kolayca bir radyo düğmesi oluşturabilir ve bunu PDF belgenizdeki belirli bir sayfaya yerleştirebilirsiniz.