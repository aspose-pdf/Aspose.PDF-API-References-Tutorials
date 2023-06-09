---
title: Metin kutusu
linktitle: Metin kutusu
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesinde metin alanı oluşturmayı öğrenin.
type: docs
weight: 290
url: /tr/net/programming-with-forms/text-box/
---

Bu kılavuzda, bir PDF belgesinde bir metin alanı oluşturmak için Aspose.PDF kitaplığının .NET için nasıl kullanılacağını adım adım açıklayacağız. Belgeyi nasıl açacağınızı, metin alanını nasıl oluşturacağınızı, özelliklerini özelleştireceğinizi ve düzenlenen PDF'yi nasıl kaydedeceğinizi göstereceğiz.

## 1. Adım: Belge dizinini yapılandırma

 İlk adım, üzerinde çalışmak istediğiniz PDF dosyasının bulunduğu belge dizinini yapılandırmaktır. kullanabilirsiniz`dataDir`dizin yolunu belirtmek için değişken.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` belgeler dizininize giden gerçek yolla.

## 2. Adım: PDF belgesini açma

 Bu adımda, PDF belgesini kullanarak açacağız.`Document`Aspose.PDF sınıfı.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

PDF dosyasının belirtilen belgeler dizininde bulunduğundan emin olun.

## 3. Adım: Metin alanını oluşturma

 kullanarak bir metin alanı oluşturacağız.`TextBoxField` sınıf. kullanarak konum koordinatlarını ve alan boyutunu belirleyebilirsiniz.`Rectangle` sınıf.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

Koordinatları, boyutu, kısmi adı ve metin alanı değerini gerektiği gibi özelleştirin.

## 4. Adım: Metin alanı özelliklerini özelleştirin

Bu adımda, kenarlık, renk vb. metin alanı özelliklerini özelleştireceğiz.

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

Metin alanı özelliklerini tercihlerinize göre özelleştirin.

## Adım 5: Alanı belgeye ekleme

Artık metin alanını oluşturup yapılandırdığımıza göre, onu PDF belgesine ekleyebiliriz.

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## 6. Adım: Değiştirilen PDF'yi kaydetme

 Son olarak, değiştirilmiş PDF'yi kullanarak kaydedebiliriz.`Save` yöntemi`Document` sınıf.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

Düzenlenen PDF için tam yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.PDF for .NET kullanan Text Box için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "TextField.pdf");
// Bir alan oluştur
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
// TextBoxField.Border = yeni Kenarlık(
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
// Belgeye alan ekle
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
// Değiştirilmiş PDF'yi kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## Çözüm

Bu kılavuzda, bir PDF belgesinde metin alanı oluşturmak için Aspose.PDF kitaplığının .NET için nasıl kullanılacağını öğrendik. Açıklanan adımları izleyerek, metin alanının özelliklerini özelleştirebilir ve gerektiğinde belgeye ekleyebilirsiniz. PDF dosyalarını işleme olanaklarını genişletmek için Aspose.PDF for .NET'in özelliklerini daha fazla keşfetmekten çekinmeyin.