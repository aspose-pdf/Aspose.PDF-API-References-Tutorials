---
title: Belge Oluştur
linktitle: Belge Oluştur
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak radyo düğmeleriyle kolayca bir belge oluşturun.
type: docs
weight: 40
url: /tr/net/programming-with-forms/create-doc/
---
Bu eğitimde size Aspose.PDF for .NET kullanarak radyo düğmeleriyle nasıl belge oluşturulacağını göstereceğiz. Bu süreçte size yol göstermek için C# kaynak kodunu adım adım açıklayacağız.

##1. Adım: Hazırlık

Öncelikle gerekli kitaplıkları içe aktardığınızdan ve belgeler dizininin yolunu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Yeni bir belge oluşturun

PDF belgesini tutacak yeni bir Belge nesnesi oluşturun:

```csharp
Document doc = new Document();
```

## 3. Adım: Sayfa ekleyin

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

İstediğiniz seçenekleri radyo düğmesi alanına ekleyin. Her seçeneğin koordinatlarını ve boyutunu gerektiği gibi ayarlayabilirsiniz:

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

### Aspose.PDF for .NET kullanarak Doküman Oluşturma için örnek kaynak kodu 
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
	// Radyo düğmesi seçeneklerini ekleyin. lütfen bu seçeneklerin yer aldığını unutmayın.
	// Ne yatay ne de dikey.
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

Bu eğitimde Aspose.PDF for .NET kullanarak radyo düğmeleriyle nasıl belge oluşturulacağını öğrendik. Bu adımları takip ederek Aspose.PDF'yi kullanarak PDF belgelerinize kolayca radyo düğmeleri ekleyebilirsiniz.

### SSS'ler

#### S: Aspose.PDF for .NET'i kullanarak belgedeki radyo düğmelerinin görünümünü özelleştirebilir miyim?

C: Evet, Aspose.PDF for .NET'i kullanarak belgedeki radyo düğmelerinin görünümünü özelleştirebilirsiniz. Radyo düğmelerinin görünümünü özelleştirmek için boyut, renk, kenarlık stili ve daha fazlası gibi özellikleri ayarlayabilirsiniz.

#### S: Birbirini dışlayan seçeneklere sahip radyo düğmesi gruplarını nasıl ekleyebilirim?

C: Birbirini dışlayan seçenekler oluşturmak için aynı ada sahip birden fazla radyo düğmesi alanı ekleyebilirsiniz. Bu, bir seçenek seçildiğinde aynı isimdeki diğer seçeneklerin seçiminin otomatik olarak kaldırılmasını sağlayacaktır.

#### S: Radyo düğmeleri için varsayılan seçili seçeneği ayarlamak mümkün müdür?

C: Evet, Aspose.PDF for .NET'i kullanarak radyo düğmeleri için varsayılan seçili seçeneği ayarlayabilirsiniz. Şunu kullanabilirsiniz:`Selected` mülkiyeti`RadioButtonOptionField` Bir seçeneği varsayılan olarak seçili olarak işaretlemek için nesneyi kullanın.

#### S: Radyo düğmelerine olay işleyicileri ekleyebilir miyim?

 C: Evet, Aspose.PDF for .NET'i kullanarak radyo düğmelerine olay işleyicileri ekleyebilirsiniz. Aşağıdaki gibi JavaScript eylemlerini ilişkilendirebilirsiniz:`OnValueChanged`Kullanıcı bir seçeneği seçtiğinde belirli eylemleri gerçekleştirmek için radyo düğmelerine.

#### S: Kullanıcı bir seçim yaptıktan sonra seçilen seçeneği radyo düğmesi grubundan nasıl alabilirim?

 C: Seçilen seçeneği Aspose.PDF for .NET'i kullanarak radyo düğmesi grubundan alabilirsiniz. Kullanıcı seçim yaptıktan sonra erişim sağlayabilirsiniz.`Selected` mülkiyeti`RadioButtonOptionField` Hangi seçeneğin seçildiğini kontrol etmek için nesne.