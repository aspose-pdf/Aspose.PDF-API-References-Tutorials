---
title: PDF Belgesinde Gruplanmış Onay Kutuları
linktitle: PDF Belgesinde Gruplanmış Onay Kutuları
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgesinde kolayca gruplandırılmış onay kutuları oluşturun.
type: docs
weight: 170
url: /tr/net/programming-with-forms/grouped-check-boxes/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinde gruplandırılmış onay kutularının nasıl oluşturulacağını göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

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

### SSS

#### S: Bir PDF belgesindeki gruplandırılmış onay kutuları nelerdir?

A: Bir PDF belgesindeki gruplandırılmış onay kutuları, birlikte gruplandırılmış bir dizi radyo düğmesi seçeneğine atıfta bulunur. Radyo düğmeleri, kullanıcıların birbirini dışlayan seçenekler grubundan yalnızca bir seçeneği belirlemesine olanak tanır. Bir radyo düğmesi seçildiğinde, aynı gruptaki diğerlerinin seçimi otomatik olarak kaldırılır. Bu gruplama davranışı, kullanıcılara birden çok seçenek sunmak, ancak seçimlerini yalnızca bir seçenekle sınırlamak istediğinizde kullanışlıdır.

#### S: Aspose.PDF for .NET'te gruplanmış onay kutularının görünümünü özelleştirebilir miyim?

C: Evet, Aspose.PDF for .NET'te gruplandırılmış onay kutularının görünümünü özelleştirebilirsiniz. API, radyo düğmesi seçeneklerinin stilini, kenarlığını ve görünümünü ayarlamak için çeşitli seçenekler sunar. Her bir seçeneğin konumunu tanımlayabilir, farklı kutu stilleri arasından seçim yapabilir (örn. kare, daire, çapraz) ve istenen görsel temsili elde etmek için kenarlık özelliklerini ayarlayabilirsiniz.

#### S: Gruplanmış onay kutularını bir PDF belgesindeki belirli bir sayfaya nasıl eklerim?

Y: Bir PDF belgesindeki belirli bir sayfaya gruplandırılmış onay kutuları eklemek için,`RadioButtonField` Argüman olarak istenen sayfa numarasına sahip nesne. Ardından, oluştur`RadioButtonOptionField` her bir radyo düğmesi seçeneğini temsil eden nesneler ve`Rectangle` nesne. Son olarak, bu seçenekleri`RadioButtonField` eklemeden önce görünümlerini gerektiği gibi özelleştirin.`RadioButtonField` belge formuna.

#### S: Tek bir PDF belgesine birden çok onay kutusu grubu ekleyebilir miyim?

 C: Evet, tek bir PDF belgesine birden çok onay kutusu grubu ekleyebilirsiniz. Her grubun benzersiz bir`RadioButtonField` nesne ve`RadioButtonOptionField` her grup içindeki nesneler, seçenekleri için aynı sayfayı ve benzersiz adları paylaşmalıdır. Bu, her gruptaki radyo düğmelerinin düzgün çalışmasını ve seçimlerin birbirini dışlamasını sağlar.

#### S: Gruplanmış onay kutuları tüm PDF görüntüleyicilerde ve uygulamalarda destekleniyor mu?

Y: Evet, gruplandırılmış onay kutuları standart uyumlu tüm PDF görüntüleyicilerde ve uygulamalarda desteklenir. PDF spesifikasyonu, radyo düğmelerini ve bunların gruplama davranışlarını tanımlayarak, bunların evrensel olarak PDF formatında tanınmasını sağlar. Ancak, çeşitli platformlarda tutarlı davranış sağlamak için farklı PDF görüntüleyicilerde işlevselliği test etmek önemlidir.