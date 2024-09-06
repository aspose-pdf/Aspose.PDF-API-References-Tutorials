---
title: PDF Belgesinde Gruplandırılmış Onay Kutuları
linktitle: PDF Belgesinde Gruplandırılmış Onay Kutuları
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinde kolayca gruplanmış onay kutuları oluşturun.
type: docs
weight: 170
url: /tr/net/programming-with-forms/grouped-check-boxes/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesinde gruplanmış onay kutularının nasıl oluşturulacağını göstereceğiz. Bu süreçte size rehberlik etmek için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kütüphaneleri içe aktardığınızdan ve belgelerinizin dizinine giden yolu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Bir Belge Nesnesi Oluşturun

Bir Belge nesnesi örneği oluşturun:

```csharp
Document pdfDocument = new Document();
```

## Adım 3: Sayfayı PDF belgesine ekleyin

PDF belgesine bir sayfa ekleyin:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Adım 4: Bir RadioButtonField Nesnesi Oluşturun

Sayfa numarasını argüman olarak kullanarak bir RadioButtonField nesnesi oluşturun:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Adım 5: Radyo düğmesi seçeneklerini ekleyin

RadioButtonOptionField nesnesini kullanarak radyo düğmesi seçenekleri ekleyin ve Rectangle nesnesini kullanarak konumlarını belirtin:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## Adım 6: Radyo düğmesi seçeneklerini özelleştirin

Stil, kenarlık ve görünümlerini ayarlayarak radyo düğmesi seçeneklerini özelleştirin:

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

## Adım 7: Radyo düğmelerini forma ekleyin

Belge form nesnesine radyo düğmelerini ekleyin:

```csharp
pdfDocument.Form.Add(radio);
```

## Adım 8: Belgeyi kaydedin

PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### .NET için Aspose.PDF kullanılarak Gruplandırılmış Onay Kutuları için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizinine giden yol.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Belge nesnesini örnekle
	Document pdfDocument = new Document();
	// PDF dosyasına bir sayfa ekle
	Page page = pdfDocument.Pages.Add();
	// Sayfa numarasını argüman olarak kullanarak RadioButtonField nesnesini oluşturun
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// İlk radyo düğmesi seçeneğini ekleyin ve ayrıca Rectangle nesnesini kullanarak kökenini belirtin
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
	// Belge nesnesinin form nesnesine radyo düğmesi ekle
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

Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesinde gruplanmış onay kutularının nasıl oluşturulacağını öğrendik. Bu adımları izleyerek, özel radyo düğmesi seçeneklerini kolayca ekleyebilir ve bunları Aspose.PDF kullanarak PDF belgelerinizde bir araya getirebilirsiniz.

### SSS

#### S: PDF belgesinde gruplanmış onay kutuları nelerdir?

A: Bir PDF belgesindeki gruplanmış onay kutuları, birlikte gruplanmış bir dizi radyo düğmesi seçeneğini ifade eder. Radyo düğmeleri, kullanıcıların karşılıklı olarak birbirini dışlayan seçenekler grubundan yalnızca bir seçeneği seçmesine olanak tanır. Bir radyo düğmesi seçildiğinde, aynı gruptaki diğerleri otomatik olarak seçilmez. Bu gruplama davranışı, kullanıcılara birden fazla seçenek sunmak ancak seçimlerini yalnızca bir seçenekle sınırlamak istediğinizde yararlıdır.

#### S: Aspose.PDF for .NET'te gruplanmış onay kutularının görünümünü özelleştirebilir miyim?

A: Evet, Aspose.PDF for .NET'te gruplanmış onay kutularının görünümünü özelleştirebilirsiniz. API, radyo düğmesi seçeneklerinin stilini, kenarlığını ve görünümünü ayarlamak için çeşitli seçenekler sunar. Her seçeneğin konumunu tanımlayabilir, farklı kutu stilleri (örneğin, kare, daire, çarpı) arasından seçim yapabilir ve istediğiniz görsel temsili elde etmek için kenarlık özelliklerini ayarlayabilirsiniz.

#### S: PDF belgesinde belirli bir sayfaya gruplanmış onay kutuları nasıl eklerim?

A: PDF belgesinde belirli bir sayfaya gruplanmış onay kutuları eklemek için bir örnek oluşturmanız gerekir`RadioButtonField` İstenilen sayfa numarasını argüman olarak içeren nesne. Ardından, oluşturun`RadioButtonOptionField` her bir radyo düğmesi seçeneğini temsil eden nesneleri seçin ve konumlarını kullanarak belirtin`Rectangle` nesne. Son olarak, bu seçenekleri nesneye ekleyin`RadioButtonField` ve eklemeden önce görünümlerini gerektiği gibi özelleştirin`RadioButtonField` belge formuna.

#### S: Tek bir PDF belgesine birden fazla onay kutusu grubu ekleyebilir miyim?

 A: Evet, tek bir PDF belgesine birden fazla onay kutusu grubu ekleyebilirsiniz. Her grubun benzersiz bir`RadioButtonField` nesne ve`RadioButtonOptionField` her gruptaki nesneler aynı sayfayı ve seçenekleri için benzersiz adları paylaşmalıdır. Bu, her gruptaki radyo düğmelerinin doğru şekilde çalışmasını ve seçimlerin karşılıklı olarak özel olmasını sağlar.

#### S: Gruplanmış onay kutuları tüm PDF görüntüleyicilerinde ve uygulamalarında destekleniyor mu?

C: Evet, gruplanmış onay kutuları tüm standart uyumlu PDF görüntüleyicilerinde ve uygulamalarında desteklenir. PDF spesifikasyonu, radyo düğmelerini ve bunların gruplama davranışlarını tanımlar ve bunları PDF formatında evrensel olarak tanınır hale getirir. Ancak, çeşitli platformlarda tutarlı davranışı sağlamak için işlevselliği farklı PDF görüntüleyicilerinde test etmek önemlidir.