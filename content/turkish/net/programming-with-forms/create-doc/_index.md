---
title: Belge Oluştur
linktitle: Belge Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak radyo düğmeleriyle kolayca bir belge oluşturun.
type: docs
weight: 40
url: /tr/net/programming-with-forms/create-doc/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak radyo düğmeleriyle bir belgenin nasıl oluşturulacağını göstereceğiz. Bu süreçte size rehberlik etmek için C# kaynak kodunu adım adım açıklayacağız.

##Adım 1: Hazırlık

Öncelikle gerekli kütüphaneleri içeri aktardığınızdan ve belgeler dizinine giden yolu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Yeni bir belge oluşturun

PDF belgesini tutacak yeni bir Belge nesnesi oluşturun:

```csharp
Document doc = new Document();
```

## Adım 3: Bir sayfa ekleyin

Belgeye yeni bir sayfa ekleyin:

```csharp
Page page = doc.Pages.Add();
```

## Adım 4: Bir radyo düğmesi alanı ekleyin

Bir radyo düğmesi alanı oluşturun ve konumunu ve boyutunu ayarlayın:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## Adım 5: Radyo düğmesi seçeneklerini ekleyin

İstenilen seçenekleri radyo düğmesi alanına ekleyin. Her seçeneğin koordinatlarını ve boyutunu gerektiği gibi ayarlayabilirsiniz:

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

## Adım 6: Radyo düğmesi alanını forma ekleyin

Belge Form Alanları koleksiyonuna radyo düğmesi alanını ekleyin:

```csharp
doc.Form.Add(field);
```

## Adım 7: Belgeyi kaydedin

PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### .NET için Aspose.PDF kullanarak Belge Oluşturma için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizinine giden yol.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Yeni bir belge oluştur
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// Radyo düğmesi alanı ekle
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// Radyo düğmesi seçenekleri ekleyin. Lütfen bu seçeneklerin şu konumda olduğunu unutmayın:
	// Ne yatay, ne dikey.
	// Bunlara herhangi bir koordinat (ve hatta boyut) ayarlamayı deneyebilirsiniz.
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

Bu eğitimde, .NET için Aspose.PDF kullanarak radyo düğmeleri olan bir belgenin nasıl oluşturulacağını öğrendik. Bu adımları izleyerek, Aspose.PDF kullanarak PDF belgelerinize kolayca radyo düğmeleri ekleyebilirsiniz.

### SSS

#### S: Aspose.PDF for .NET'i kullanarak belgedeki radyo düğmelerinin görünümünü özelleştirebilir miyim?

A: Evet, Aspose.PDF for .NET kullanarak belgedeki radyo düğmelerinin görünümünü özelleştirebilirsiniz. Radyo düğmelerinin görünümünü özelleştirmek için boyut, renk, kenarlık stili ve daha fazlası gibi özellikler ayarlayabilirsiniz.

#### S: Karşılıklı olarak birbirini dışlayan seçeneklere sahip radyo düğmesi gruplarını nasıl ekleyebilirim?

A: Karşılıklı olarak birbirini dışlayan seçenekler oluşturmak için aynı ada sahip birden fazla radyo düğmesi alanı ekleyebilirsiniz. Bu, bir seçenek seçildiğinde aynı ada sahip diğer seçeneklerin otomatik olarak seçilmemesini sağlar.

#### S: Radyo düğmeleri için varsayılan seçili bir seçenek belirlemek mümkün müdür?

A: Evet, Aspose.PDF for .NET kullanarak radyo düğmeleri için varsayılan seçili bir seçenek ayarlayabilirsiniz.`Selected` mülkiyeti`RadioButtonOptionField` Bir seçeneği varsayılan olarak seçili olarak işaretlemek için kullanılan nesne.

#### S: Radyo düğmelerine olay işleyicileri ekleyebilir miyim?

 A: Evet, Aspose.PDF for .NET kullanarak radyo düğmelerine olay işleyicileri ekleyebilirsiniz. JavaScript eylemlerini şu şekilde ilişkilendirebilirsiniz:`OnValueChanged`, kullanıcı bir seçeneği seçtiğinde belirli eylemleri gerçekleştirmek için radyo düğmelerine.

#### S: Kullanıcı bir seçim yaptıktan sonra, seçili seçeneği radyo düğmesi grubundan nasıl alabilirim?

 A: Aspose.PDF for .NET kullanarak seçili seçeneği radyo düğmesi grubundan alabilirsiniz. Kullanıcı bir seçim yaptıktan sonra,`Selected` mülkiyeti`RadioButtonOptionField` Hangi seçeneğin seçildiğini kontrol etmek için nesne.