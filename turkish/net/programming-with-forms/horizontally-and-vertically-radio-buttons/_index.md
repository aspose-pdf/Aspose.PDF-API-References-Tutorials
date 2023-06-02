---
title: Yatay ve Dikey Radyo Düğmeleri
linktitle: Yatay ve Dikey Radyo Düğmeleri
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinizde kolayca yatay ve dikey radyo düğmeleri oluşturun.
type: docs
weight: 180
url: /tr/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinde yatay ve dikey olarak düzenlenmiş radyo düğmelerinin nasıl oluşturulacağını göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kitaplıkları içe aktardığınızdan emin olun ve yolu belgeler dizininize ayarlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin

Mevcut PDF belgesini yükleyin:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## 3. Adım: Radyo düğmesi seçeneklerini özelleştirin

Aşağıdaki özellikleri ayarlayarak radyo düğmesi seçeneklerini özelleştirin:

```csharp
formEditor. RadioGap = 4; // İki radyo düğmesi seçeneği arasındaki mesafe
formEditor. RadioHoriz = true; // Radyo düğmelerinin yatay düzeni
formEditor.RadioButtonItemSize = 20; // Radyo düğmelerinin boyutu
formEditor.Facade.BorderWidth = 1; // Radyo düğmesi kenarlığının genişliği
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Radyo düğmesi kenarlık rengi
```

## 4. Adım: Yatay Radyo Düğmeleri Ekleyin

Alanın seçeneklerini ve konumunu belirterek yatay olarak düzenlenmiş radyo düğmeleri ekleyin:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## 5. Adım: Dikey radyo düğmeleri ekleyin

Alanın seçeneklerini ve konumunu belirterek dikey olarak düzenlenmiş radyo düğmeleri ekleyin:

```csharp
formEditor. RadioHoriz = false; // Radyo düğmelerinin dikey yerleşimi
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## 6. Adım: Belgeyi kaydedin

Değiştirilen PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Aspose.Words for .NET kullanan Yatay ve Dikey Radyo Düğmeleri için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Önceden kaydedilmiş belgeyi yükleyin
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap, iki radyo düğmesi seçeneği arasındaki mesafedir.
	formEditor.RadioGap = 4;
	// Yatay radyo düğmesi ekle
	formEditor.RadioHoriz = true;
	// Radyo düğmesi öğesinin boyutu ise RadioButtonItemSize.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Dikey olarak yerleştirilmiş başka bir radyo düğmesi ekle
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// PDF belgesini kaydedin
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinde yatay ve dikey olarak düzenlenmiş radyo düğmeleri oluşturmayı öğrendik. Bu adımları izleyerek radyo düğmelerinin düzenini kolayca özelleştirebilir ve Aspose.PDF kullanarak PDF belgelerinize ekleyebilirsiniz.