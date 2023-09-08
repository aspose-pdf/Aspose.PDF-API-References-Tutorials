---
title: PDF Belgesinde Gruplandırılmış Onay Kutuları
linktitle: PDF Belgesinde Gruplandırılmış Onay Kutuları
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF belgesinde kolayca gruplandırılmış onay kutuları oluşturun.
type: docs
weight: 170
url: /tr/net/programming-with-forms/grouped-check-boxes/
---
Bu eğitimde size Aspose.PDF for .NET kullanarak bir PDF belgesinde gruplandırılmış onay kutularının nasıl oluşturulacağını göstereceğiz. Bu süreçte size yol göstermek için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kitaplıkları içe aktardığınızdan ve belgeler dizininizin yolunu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Bir Belge Nesnesini Örneklendirin

Bir Document nesnesinin örneğini oluşturun:

```csharp
Document pdfDocument = new Document();
```

## 3. Adım: PDF belgesine sayfa ekleyin

PDF belgesine bir sayfa ekleyin:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Adım 4: RadioButtonField Nesnesini Örneklendirin

Bağımsız değişken olarak sayfa numarasıyla bir RadioButtonField nesnesi örneği oluşturun:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## 5. Adım: Radyo düğmesi seçeneklerini ekleyin

RadioButtonOptionField nesnesini kullanarak radyo düğmesi seçeneklerini ekleyin ve Rectangle nesnesini kullanarak konumlarını belirtin:

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

## Adım 7: Radyo düğmelerini forma ekleyin

Radyo düğmelerini belge formu nesnesine ekleyin:

```csharp
pdfDocument.Form.Add(radio);
```

## Adım 8: Belgeyi kaydedin

PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET kullanan Gruplandırılmış Onay Kutuları için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Belge nesnesini somutlaştır
	Document pdfDocument = new Document();
	// PDF dosyasına sayfa ekleme
	Page page = pdfDocument.Pages.Add();
	// Bağımsız değişken olarak sayfa numarasıyla RadioButtonField nesnesini başlat
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
	// Belge nesnesinin nesnesini oluşturmak için radyo düğmesi ekleyin
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

Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF belgesinde gruplandırılmış onay kutularının nasıl oluşturulacağını öğrendik. Bu adımları izleyerek, özel radyo düğmesi seçeneklerini kolayca ekleyebilir ve bunları Aspose.PDF kullanarak PDF belgelerinizde paketleyebilirsiniz.

### SSS'ler

#### S: PDF belgesindeki gruplandırılmış onay kutuları nelerdir?

C: Bir PDF belgesindeki gruplandırılmış onay kutuları, birlikte gruplandırılmış bir dizi radyo düğmesi seçeneğini ifade eder. Radyo düğmeleri, kullanıcıların birbirini dışlayan bir grup seçenek arasından yalnızca bir seçeneği seçmesine olanak tanır. Bir radyo düğmesi seçildiğinde aynı gruptaki diğerlerinin seçimi otomatik olarak kaldırılır. Bu gruplandırma davranışı, kullanıcılara birden çok seçenek sunmak ancak seçimlerini yalnızca tek bir seçenekle sınırlamak istediğinizde kullanışlıdır.

#### S: Aspose.PDF for .NET'te gruplandırılmış onay kutularının görünümünü özelleştirebilir miyim?

C: Evet, Aspose.PDF for .NET'te gruplandırılmış onay kutularının görünümünü özelleştirebilirsiniz. API, radyo düğmesi seçeneklerinin stilini, kenarlığını ve görünümünü ayarlamak için çeşitli seçenekler sunar. Her seçeneğin konumunu tanımlayabilir, farklı kutu stilleri (örn. kare, daire, çarpı) arasından seçim yapabilir ve istediğiniz görsel temsili elde etmek için kenarlık özelliklerini ayarlayabilirsiniz.

#### S: Gruplandırılmış onay kutularını bir PDF belgesindeki belirli bir sayfaya nasıl eklerim?

C: Bir PDF belgesindeki belirli bir sayfaya gruplandırılmış onay kutuları eklemek için bir örnek oluşturmanız gerekir.`RadioButtonField` argüman olarak istenen sayfa numarasına sahip nesne. Daha sonra oluşturun`RadioButtonOptionField` Her bir radyo düğmesi seçeneğini temsil eden nesneler ve konumlarını kullanarak`Rectangle` nesne. Son olarak bu seçenekleri`RadioButtonField` ve eklemeden önce görünümlerini gerektiği gibi özelleştirin.`RadioButtonField` belge formuna gidin.

#### S: Tek bir PDF belgesine birden fazla onay kutusu grubu ekleyebilir miyim?

 C: Evet, tek bir PDF belgesine birden fazla onay kutusu grubu ekleyebilirsiniz. Her grubun kendine özgü bir özelliği olmalı`RadioButtonField` nesne ve`RadioButtonOptionField` her gruptaki nesneler, seçenekleri için aynı sayfayı ve benzersiz adları paylaşmalıdır. Bu, her gruptaki radyo düğmelerinin doğru çalışmasını ve seçimlerin birbirini dışlamasını sağlar.

#### S: Gruplandırılmış onay kutuları tüm PDF görüntüleyicilerde ve uygulamalarda destekleniyor mu?

C: Evet, gruplandırılmış onay kutuları tüm standart uyumlu PDF görüntüleyicilerde ve uygulamalarda desteklenir. PDF spesifikasyonu, radyo düğmelerini ve bunların gruplanma davranışlarını tanımlayarak bunların evrensel olarak PDF formatında tanınmasını sağlar. Ancak çeşitli platformlarda tutarlı davranış sağlamak için işlevselliği farklı PDF görüntüleyicilerde test etmek önemlidir.