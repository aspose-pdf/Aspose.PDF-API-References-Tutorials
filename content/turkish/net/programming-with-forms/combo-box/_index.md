---
title: Açılan kutu
linktitle: Açılan kutu
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak PDF belgelerinizde kolayca açılan kutu listesi oluşturun.
type: docs
weight: 30
url: /tr/net/programming-with-forms/combo-box/
---
Bu eğitimde size Aspose.PDF for .NET kullanarak bir açılır kutu listesinin nasıl oluşturulacağını göstereceğiz. Bu süreçte size yol göstermek için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Öncelikle gerekli kitaplıkları içe aktardığınızdan ve belgeler dizininin yolunu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Belge Nesnesi Oluşturun

PDF formunu tutacak bir Belge nesnesi oluşturun:

```csharp
Document doc = new Document();
```

## 3. Adım: Sayfa ekleyin

Belgeye bir sayfa ekleyin:

```csharp
doc.Pages.Add();
```

## Adım 4: ComboBoxField Nesnesini Örneklendirin

İstediğiniz boyutlara sahip bir ComboBoxField nesnesinin örneğini oluşturun:

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## 5. Adım: Açılır listeye seçenekleri ekleyin

İstediğiniz seçenekleri açılır listeye ekleyin:

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## Adım 6: Birleşik giriş kutusu listesini forma ekleyin

ComboBoxField nesnesini Belge Formu Alanları koleksiyonuna ekleyin:

```csharp
doc.Form.Add(combo);
```

## 7. Adım: Belgeyi kaydedin

PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET kullanan Combo Box için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Belge nesnesi oluştur
	Document doc = new Document();
	// Belge nesnesine sayfa ekle
	doc.Pages.Add();
	// ComboBox Field nesnesini örnekle
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// ComboBox'a seçenek ekle
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// Belge nesnesinin alan koleksiyonunu oluşturmak için açılan kutu nesnesini ekleyin
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

Bu eğitimde Aspose.PDF for .NET kullanarak birleşik giriş kutusu listesinin nasıl oluşturulacağını öğrendik. Bu adımları takip ederek Aspose.PDF'yi kullanarak PDF belgelerinize kolayca açılan kutu listesi ekleyebilirsiniz.

### SSS'ler

#### S: Açılan kutu listesinin görünümünü Aspose.PDF for .NET'i kullanarak özelleştirebilir miyim?

C: Evet, Aspose.PDF for .NET'i kullanarak açılan kutu listesinin görünümünü özelleştirebilirsiniz. İstediğiniz görünüm ve hisle eşleşecek şekilde yazı tipi boyutu, renk, arka plan rengi, kenarlık stili ve daha fazlası gibi özellikleri ayarlayabilirsiniz.

#### S: Birleşik giriş kutusu listesinde varsayılan seçili seçenekleri ayarlayabilir miyim?

 C: Evet, Aspose.PDF for .NET'i kullanarak açılan kutu listesindeki varsayılan seçili seçenekleri ayarlayabilirsiniz. Şunu kullanabilirsiniz:`Selected` mülkiyeti`ComboBoxField` Bir veya daha fazla seçeneği varsayılan olarak seçili olarak işaretlemek için nesneyi seçin.

#### S: Kullanıcı bir seçim yaptıktan sonra seçilen değeri açılan kutu listesinden nasıl alabilirim?

 C: Seçilen değeri Aspose.PDF for .NET'i kullanarak açılan kutu listesinden alabilirsiniz. Kullanıcı seçim yaptıktan sonra erişim sağlayabilirsiniz.`Value` mülkiyeti`ComboBoxField`Seçilen değeri elde etmek için nesne.

#### S: Birleşik giriş kutusu listesine olay işleyicileri veya eylemler eklemek mümkün mü?

 C: Evet, Aspose.PDF for .NET, birleşik giriş kutusu listesine olay işleyicileri veya eylemler eklemenizi sağlar. Aşağıdaki gibi JavaScript eylemlerini ilişkilendirebilirsiniz:`OnValueChanged`Kullanıcı bir seçeneği seçtiğinde belirli eylemleri gerçekleştirmek için açılan kutu listesine.

#### S: Birleşik giriş kutusu listesindeki seçeneklere araç ipuçları veya açıklamalar ekleyebilir miyim?

 C: Evet, Aspose.PDF for .NET'i kullanarak birleşik giriş kutusu listesindeki seçeneklere araç ipuçları veya açıklamalar ekleyebilirsiniz. Ayarlayabilirsiniz`AlternateName` Kullanıcı seçeneğin üzerine geldiğinde görüntülenecek bir araç ipucu veya açıklama sağlamak için her seçeneğin özelliği.