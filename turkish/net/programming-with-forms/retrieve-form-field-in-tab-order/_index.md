---
title: Form Alanını Sekme Sırasında Al
linktitle: Form Alanını Sekme Sırasında Al
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak form alanlarını sekme sırasına göre nasıl alacağınızı öğrenin.
type: docs
weight: 240
url: /tr/net/programming-with-forms/retrieve-form-field-in-tab-order/
---

Aspose.PDF for .NET kullanarak C#'ta PDF belgeleriyle çalışırken, form alanlarını belirli bir sekme sırasında almanız gereken bir senaryoyla karşılaşabilirsiniz. Bu, form alanlarında sekme sıralarına göre işlemler gerçekleştirmek istediğinizde faydalı olabilir. Bu eğitimde, Aspose.PDF for .NET kullanarak form alanlarını sekme düzeninde nasıl alacağınız konusunda adım adım rehberlik edeceğiz.

## Gereksinimler

Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- Sisteminizde yüklü Visual Studio
- Aspose.PDF for .NET library yüklü

Şimdi, form alanlarını sekme sırasına göre alma adımlarına geçelim.

## 1. Adım: Belge Dizininin Ayarlanması

Başlamak için, PDF belgenizin bulunduğu belge dizinini ayarlamanız gerekir. Bunu, dizinin yolunu belirterek yapabilirsiniz.`dataDir` değişken.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

## 2. Adım: PDF Belgesini Yükleme

 Bu adımda, Aspose.PDF for .NET kullanarak PDF belgesini yükleyeceğiz. bu`Document` class, PDF belgelerini yükleme ve değiştirme yeteneği sağlar.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Burada,`"Test2.pdf"` yüklemek istediğiniz PDF belgesinin adıdır. Belgenin belirtilen belge dizininde bulunduğundan emin olun.

## 3. Adım: Form Alanlarını Sekme Sırasında Alma

 Form alanlarını sekme sırasına göre almak için,`FieldsInTabOrder` mülkiyeti`Page` sınıf. Bu özellik, sekme sırasına göre sıralanmış form alanlarının bir listesini döndürür.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

Yukarıdaki kod parçacığında, form alanlarını ikinci sayfadan alıyoruz (`doc.Pages[1]` ) ve kısmi adlarını birleştirmek için her alanı yineleyin.`s` değişken. Bu kod parçacığını özel gereksinimlerinize göre değiştirebilirsiniz.

## 4. Adım: Sekme Sırasını Değiştirme

 Form alanlarının sekme sırasını değiştirmek isterseniz, bunu`TabOrder` her alanın özelliği ve yeni bir sekme sırası değeri atama. İşte bir örnek:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

Yukarıdaki kod parçacığında, üç form alanına (`doc.Form[3]`, `doc.Form[1]` , Ve`doc.Form[2]`). Alan indekslerini ve sekme sırası değerlerini özel gereksinimlerinize göre ayarlayın.

## Adım 5: Değiştirilen Belgeyi Kaydetme

 Form alanlarının sekme sırasını değiştirdikten sonra değiştirilen belgeyi kaydetmeniz gerekir. Bunu kullanarak yapabilirsiniz`Save` yöntemi`Document` sınıf.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Burada,`"39522_out.pdf"` değiştirilen belgenin kaydedileceği çıktı dosyasının adıdır. Çıktı dosyası için istediğiniz adı ve konumu belirtin.

### Aspose.Words for .NET kullanarak Form Alanını Sekme Sırasında Al için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Test2.pdf");
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
	s += field.PartialName;
}
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
doc.Save(dataDir + "39522_out.pdf");
Document doc1 = new Document(dataDir + "39522_out.pdf");
s = "";
foreach (Field field in doc1.Pages[1].FieldsInTabOrder)
{
	s += field.PartialName;
}
string index = "";
foreach (Field field in doc1.Form)
{
	index += field.TabOrder;
}
```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kullanarak form alanlarını sekme sırasına göre nasıl alacağımızı öğrendik. Bir PDF belgesi yükleme, form alanlarını sekme sırasına göre alma, sekme sırasını değiştirme ve değiştirilen belgeyi kaydetme ile ilgili adımları ele aldık. Bu adımları izleyerek, form alanlarıyla verimli bir şekilde çalışabilir ve sekme sırasını ihtiyaçlarınıza göre özelleştirebilirsiniz.