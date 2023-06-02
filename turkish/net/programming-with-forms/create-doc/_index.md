---
title: Doküman Oluştur
linktitle: Doküman Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak radyo düğmeleriyle kolayca bir belge oluşturun.
type: docs
weight: 40
url: /tr/net/programming-with-forms/create-doc/
---

Bu eğitimde size Aspose.PDF for .NET kullanarak radyo düğmeleriyle nasıl belge oluşturacağınızı göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

##1. Adım: Hazırlık

İlk olarak, gerekli kitaplıkları içe aktardığınızdan ve belgeler dizinine giden yolu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Yeni bir belge oluşturun

PDF belgesini tutmak için yeni bir Belge nesnesi oluşturun:

```csharp
Document doc = new Document();
```

## 3. Adım: Bir sayfa ekleyin

Belgeye yeni bir sayfa ekleyin:

```csharp
Page page = doc.Pages.Add();
```

## 4. Adım: Bir radyo düğmesi alanı ekleyin

Bir radyo düğmesi alanı oluşturun ve konumunu ve boyutunu ayarlayın:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## 5. Adım: Radyo düğmesi seçeneklerini ekleyin

Radyo düğmesi alanına istediğiniz seçenekleri ekleyin. Her seçeneğin koordinatlarını ve boyutunu gerektiği gibi ayarlayabilirsiniz:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## 6. Adım: Radyo düğmesi alanını forma ekleyin

Radyo düğmesi alanını Belge Formu Alanları koleksiyonuna ekleyin:

```csharp
doc.Form.Add(field);
```

## 7. Adım: Belgeyi kaydedin

PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### Aspose.Words for .NET kullanarak Create Doc için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Yeni bir belge oluştur
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// Radyo düğmesi alanı ekle
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// Radyo düğmesi seçenekleri ekleyin. lütfen bu seçeneklerin yer aldığını unutmayın.
	// Ne yatay ne dikey.
	// Onlar için herhangi bir koordinat (ve hatta boyut) ayarlamayı deneyebilirsiniz.
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// PDF belgesini kaydedin
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak radyo düğmeleriyle nasıl belge oluşturacağımızı öğrendik. Bu adımları izleyerek, Aspose.PDF kullanarak PDF belgelerinize kolayca radyo butonları ekleyebilirsiniz.