---
title: Açılan kutu
linktitle: Açılan kutu
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'i kullanarak PDF belgelerinizde kolayca açılan kutu listesi oluşturun.
type: docs
weight: 30
url: /tr/net/programming-with-forms/combo-box/
---

Bu eğitimde size Aspose.PDF for .NET kullanarak birleşik giriş listesi oluşturmayı göstereceğiz. Bu süreçte size yol göstermesi için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

İlk olarak, gerekli kitaplıkları içe aktardığınızdan ve belgeler dizinine giden yolu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Bir Belge Nesnesi Oluşturun

PDF formunu tutmak için bir Belge nesnesi oluşturun:

```csharp
Document doc = new Document();
```

## 3. Adım: Bir sayfa ekleyin

Belgeye bir sayfa ekleyin:

```csharp
doc.Pages.Add();
```

## 4. Adım: Bir ComboBoxField Nesnesi Başlatın

İstenen boyutlara sahip bir ComboBoxField nesnesi örneği oluşturun:

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## 5. Adım: Açılır listeye seçenekler ekleyin

Açılır listeye istediğiniz seçenekleri ekleyin:

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## Adım 6: Açılan kutu listesini forma ekleyin

ComboBoxField nesnesini Document Form Fields koleksiyonuna ekleyin:

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
	// ComboBox Field nesnesinin örneğini oluştur
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// ComboBox'a seçenek ekle
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// Belge nesnesinin alan koleksiyonunu oluşturmak için birleşik giriş kutusu nesnesi ekleyin
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

Bu eğitimde, Aspose.PDF for .NET kullanarak birleşik giriş listesi oluşturmayı öğrendik. Bu adımları takip ederek, Aspose.PDF kullanarak PDF belgelerinize kolaylıkla bir açılan kutu listesi ekleyebilirsiniz.