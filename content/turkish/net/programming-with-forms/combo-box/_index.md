---
title: Kombo Kutusu
linktitle: Kombo Kutusu
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF belgelerinizde kolayca birleşik liste kutusu oluşturun.
type: docs
weight: 30
url: /tr/net/programming-with-forms/combo-box/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak bir birleşik kutu listesinin nasıl oluşturulacağını göstereceğiz. Bu süreçte size rehberlik etmek için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Öncelikle gerekli kütüphaneleri içeri aktardığınızdan ve belgeler dizinine giden yolu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Bir Belge Nesnesi Oluşturun

PDF formunu tutacak bir Belge nesnesi oluşturun:

```csharp
Document doc = new Document();
```

## Adım 3: Bir sayfa ekleyin

Belgeye bir sayfa ekleyin:

```csharp
doc.Pages.Add();
```

## Adım 4: Bir ComboBoxField Nesnesi Oluşturun

İstenilen boyutlara sahip bir ComboBoxField nesnesi oluşturun:

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## Adım 5: Açılır listeye seçenekler ekleyin

İstediğiniz seçenekleri açılır listeye ekleyin:

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## Adım 6: Açılır listeyi forma ekleyin

ComboBoxField nesnesini Belge Form Alanları koleksiyonuna ekleyin:

```csharp
doc.Form.Add(combo);
```

## Adım 7: Belgeyi kaydedin

PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### .NET için Aspose.PDF kullanılarak Combo Box için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizinine giden yol.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Belge nesnesi oluştur
	Document doc = new Document();
	// Belge nesnesine sayfa ekle
	doc.Pages.Add();
	// ComboBox Alan nesnesini örneklendir
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// ComboBox'a seçenek ekle
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// Belge nesnesinin form alanları koleksiyonuna birleşik kutu nesnesi ekleyin
	doc.Form.Add(combo);
	dataDir = dataDir + "ComboBox_out.pdf";
	// PDF belgesini kaydedin
	doc.Save(dataDir);
	Console.WriteLine("\nCombobox field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak bir birleşik kutu listesinin nasıl oluşturulacağını öğrendik. Bu adımları izleyerek, Aspose.PDF kullanarak PDF belgelerinize kolayca bir birleşik kutu listesi ekleyebilirsiniz.

### SSS

#### S: Aspose.PDF for .NET'i kullanarak birleşik kutu listesinin görünümünü özelleştirebilir miyim?

A: Evet, Aspose.PDF for .NET kullanarak birleşik kutu listesinin görünümünü özelleştirebilirsiniz. Yazı tipi boyutu, renk, arka plan rengi, kenarlık stili ve daha fazlası gibi özellikleri istediğiniz görünüm ve hisle eşleşecek şekilde ayarlayabilirsiniz.

#### S: Combobox listesinde varsayılan seçili seçenekleri ayarlayabilir miyim?

 A: Evet, Aspose.PDF for .NET kullanarak birleşik kutu listesindeki varsayılan seçili seçenekleri ayarlayabilirsiniz.`Selected` mülkiyeti`ComboBoxField` Bir veya daha fazla seçeneğin varsayılan olarak seçili olarak işaretlenmesini sağlayan nesne.

#### S: Kullanıcı bir seçim yaptıktan sonra, açılan kutu listesinden seçilen değeri nasıl alabilirim?

 A: Aspose.PDF for .NET kullanarak, birleşik kutu listesinden seçili değeri alabilirsiniz. Kullanıcı bir seçim yaptıktan sonra,`Value` mülkiyeti`ComboBoxField`Seçilen değeri elde etmek için nesne.

#### S: Combo box listesine olay işleyicileri veya eylemler eklemek mümkün müdür?

 A: Evet, Aspose.PDF for .NET, birleşik kutu listesine olay işleyicileri veya eylemler eklemenize olanak tanır. JavaScript eylemlerini şu şekilde ilişkilendirebilirsiniz:`OnValueChanged`, kullanıcı bir seçeneği seçtiğinde belirli eylemleri gerçekleştirmek için birleşik kutu listesine.

#### S: Birleşik kutu listesindeki seçeneklere araç ipuçları veya açıklamalar ekleyebilir miyim?

 A: Evet, Aspose.PDF for .NET kullanarak birleşik kutu listesindeki seçeneklere araç ipuçları veya açıklamalar ekleyebilirsiniz.`AlternateName` Kullanıcı seçeneğin üzerine geldiğinde görüntülenecek bir araç ipucu veya açıklama sağlamak için her seçeneğin özelliği.