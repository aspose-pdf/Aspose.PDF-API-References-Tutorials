---
title: Gruplanmış Onay Kutuları
linktitle: Gruplanmış Onay Kutuları
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinizde kolayca gruplandırılmış onay kutuları oluşturun.
type: docs
weight: 170
url: /tr/net/programming-with-forms/grouped-check-boxes/
---

Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesinde gruplandırılmış onay kutularının nasıl oluşturulacağını göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kitaplıkları içe aktardığınızdan emin olun ve yolu belgeler dizininize ayarlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Bir Belge Nesnesi Oluşturun

Bir Belge nesnesi oluşturun:

```csharp
Document pdfDocument = new Document();
```

## 3. Adım: PDF belgesine sayfa ekleyin

PDF belgesine bir sayfa ekleyin:

```csharp
Page page = pdfDocument.Pages.Add();
```

## 4. Adım: Bir RadioButtonField Nesnesi Başlatın

Bağımsız değişken olarak sayfa numarasıyla bir RadioButtonField nesnesi oluşturun:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## 5. Adım: Radyo düğmesi seçeneklerini ekleyin

RadioButtonOptionField nesnesini kullanarak radyo düğmesi seçenekleri ekleyin ve Rectangle nesnesini kullanarak konumlarını belirtin:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## 6. Adım: Radyo düğmesi seçeneklerini özelleştirin

Stillerini, kenarlıklarını ve görünümlerini ayarlayarak radyo düğmesi seçeneklerini özelleştirin:

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## 7. Adım: Radyo düğmelerini forma ekleyin

Belge formu nesnesine radyo düğmelerini ekleyin:

```csharp
pdfDocument.Form.Add(radio);
```

## 8. Adım: Belgeyi kaydedin

PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET kullanan Gruplanmış Onay Kutuları için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Belge nesnesini örneklendir
	Document pdfDocument = new Document();
	// PDF dosyasına bir sayfa ekleyin
	Page page = pdfDocument.Pages.Add();
	// Bağımsız değişken olarak sayfa numarasıyla RadioButtonField nesnesini başlat
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// İlk radyo düğmesi seçeneğini ekleyin ve ayrıca Dikdörtgen nesnesini kullanarak kaynağını belirtin
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	// Belge nesnesinin nesnesini oluşturmak için radyo düğmesi ekle
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// PDF belgesini kaydedin
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesinde gruplandırılmış onay kutuları oluşturmayı öğrendik. Bu adımları izleyerek özel radyo düğmesi seçeneklerini kolayca ekleyebilir ve Aspose.PDF kullanarak bunları PDF belgelerinizde gruplandırabilirsiniz.