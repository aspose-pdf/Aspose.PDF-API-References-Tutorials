---
title: Seçenekli Radyo Düğmesi
linktitle: Seçenekli Radyo Düğmesi
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesine seçeneklerle kolayca bir radyo düğmesi ekleyin.
type: docs
weight: 230
url: /tr/net/programming-with-forms/radio-button-with-options/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesine seçenekler içeren bir radyo düğmesini nasıl ekleyeceğinizi göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kitaplıkları içe aktardığınızdan emin olun ve yolu belgeler dizininize ayarlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Bir Belge Nesnesi Oluşturun

Yeni bir PDF belgesi oluşturmak için bir Belge nesnesi örneği oluşturun:

```csharp
Document doc = new Document();
```

## 3. Adım: Sayfa ve tablo ekleyin

Belgeye bir sayfa ekleyin ve radyo düğmesi seçeneklerini tutmak için bir tablo oluşturun:

```csharp
Page page = doc.Pages.Add();
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "120 120 120";
page.Paragraphs.Add(table);
```

## 4. Adım: Bir RadioButtonField Nesnesi Başlatın

Radyo düğmesini temsil etmesi için bir RadioButtonField nesnesi oluşturun:

```csharp
RadioButtonField rf = new RadioButtonField(page);
rf. PartialName = "radio";
doc.Form.Add(rf, 1);
```

## 5. Adım: Radyo düğmesi seçeneklerini ekleyin

Radyo düğmesi seçeneklerini RadioButtonField nesnesine ekleyin:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
RadioButtonOptionField opt2 = new RadioButtonOptionField();
RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt1.OptionName = "Item1";
opt2.OptionName = "Item2";
opt3.OptionName = "Item3";
opt1.Width = 15;
opt1. Height = 15;
opt2.Width = 15;
opt2. Height = 15;
opt3.Width = 15;
opt3. Height = 15;
rf.Add(opt1);
rf.Add(opt2);
rf.Add(opt3);
```

## 6. Adım: Radyo düğmesi seçeneklerini özelleştirin

Kenarlık, metin rengi ve başlık metni gibi nitelikleri ayarlayarak radyo düğmesi seçeneklerini özelleştirin:

```csharp
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Border.Style = BorderStyle.Solid;
opt1.Characteristics.Border = System.Drawing.Color.Black;
opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
opt1.Caption = new TextFragment("Item1");

// opt2 ve opt3 için aynı adımları tekrarlayın

```

## 7. Adım: Radyo düğmesi seçeneklerini tabloya ekleyin

Radyo düğmesi seçeneklerini görüntülemek için tabloya ekleyin:

```csharp
Cell c1 = table.Rows.Add().Cells.Add();
Cell c2 = table.Rows[table.Rows.Count].Cells.Add();
Cell c3 = table.Rows[table.Rows.Count].Cells.Add();

c1.Paragraphs.Add(opt1);
c2.Paragraphs.Add(opt2);
c3.Paragraphs.Add(opt3);
```

## 8. Adım: PDF Belgesini Kaydedin

Oluşturulan PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET kullanan Radio Button With Options için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	Page page = doc.Pages.Add();
	Aspose.Pdf.Table table = new Aspose.Pdf.Table();
	table.ColumnWidths = "120 120 120";
	page.Paragraphs.Add(table);
	Row r1 = table.Rows.Add();
	Cell c1 = r1.Cells.Add();
	Cell c2 = r1.Cells.Add();
	Cell c3 = r1.Cells.Add();
	RadioButtonField rf = new RadioButtonField(page);
	rf.PartialName = "radio";
	doc.Form.Add(rf, 1);
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt1.OptionName = "Item1";
	opt2.OptionName = "Item2";
	opt3.OptionName = "Item3";
	opt1.Width = 15;
	opt1.Height = 15;
	opt2.Width = 15;
	opt2.Height = 15;
	opt3.Width = 15;
	opt3.Height = 15;
	rf.Add(opt1);
	rf.Add(opt2);
	rf.Add(opt3);
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt1.Caption = new TextFragment("Item1");
	opt2.Border = new Border(opt1);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	opt2.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt2.Caption = new TextFragment("Item2");
	opt3.Border = new Border(opt1);
	opt3.Border.Width = 1;
	opt3.Border.Style = BorderStyle.Solid;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	opt3.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt3.Caption = new TextFragment("Item3");
	c1.Paragraphs.Add(opt1);
	c2.Paragraphs.Add(opt2);
	c3.Paragraphs.Add(opt3);
	dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
	//PDF dosyasını kaydedin
	doc.Save(dataDir);
	Console.WriteLine("\nRadio button field with three options added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesine seçenekler içeren bir radyo düğmesini başarıyla eklediniz. Artık PDF belgelerinizde etkileşimli formlar oluşturmak için bu yöntemi kullanabilirsiniz.