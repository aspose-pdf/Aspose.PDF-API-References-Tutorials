---
title: Radyo Düğmesini Seçin
linktitle: Radyo Düğmesini Seçin
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesinde bir radyo düğmesini nasıl seçeceğinizi öğrenin.
type: docs
weight: 250
url: /tr/net/programming-with-forms/select-radio-button/
---

Burada, Aspose.PDF for .NET kullanarak bir radyo düğmesinin nasıl seçileceğine dair ayrıntılı bir öğretici bulunmaktadır. Bu adımları takip et:

##  Adım 1: Belgelerinizin dizinini tanımlayarak başlayın.`dataDir` variable.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  Adım 2: PDF belgesini kullanarak açın.`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## Adım 3: Belge formundan radyo düğmesi alanını alın.

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## Adım 4: Gruptan seçilecek radyo düğmesinin dizinini belirtin.

```csharp
radioField. Selected = 2;
```

## Adım 5: Düzenlenen PDF dosyası için çıktı yolunu ayarlayın.

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## Adım 6: Değiştirilen PDF dosyasını kaydedin.

```csharp
pdfDocument.Save(dataDir);
```

## Adım 7: Bir onay mesajı ve kaydedilen dosyanın konumunu görüntüleyin.

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### Aspose.Words for .NET kullanan Select Radio Button için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Belgeyi aç
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	// bir alan al
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	// Gruptan radyo düğmesinin dizinini belirtin
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	// PDF dosyasını kaydedin
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kullanarak bir radyo düğmesini nasıl seçeceğimizi öğrendik. Yukarıda özetlenen adımları izleyerek, Aspose.PDF for .NET kullanarak PDF belgelerinizdeki radyo düğmelerini işleyebilir ve değiştirebilirsiniz.