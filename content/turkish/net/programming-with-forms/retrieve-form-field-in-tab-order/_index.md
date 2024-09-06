---
title: Form Alanını Sekme Sırasında Al
linktitle: Form Alanını Sekme Sırasında Al
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak form alanlarının sekme sırasına göre nasıl alınacağını öğrenin.
type: docs
weight: 240
url: /tr/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
Aspose.PDF for .NET kullanarak C# dilinde PDF belgeleriyle çalışırken, form alanlarını belirli bir sekme sırasına göre almanız gereken bir senaryoyla karşılaşabilirsiniz. Bu, form alanlarında sekme sırasına göre işlemler yapmak istediğinizde faydalı olabilir. Bu eğitimde, Aspose.PDF for .NET kullanarak form alanlarını sekme sırasına göre nasıl alacağınız konusunda adım adım size rehberlik edeceğiz.

## Gereksinimler

Başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- Sisteminizde Visual Studio yüklü
- .NET kütüphanesi için Aspose.PDF yüklendi

Şimdi form alanlarını sekme sırasına göre alma adımlarına geçelim.

## Adım 1: Belge Dizinini Ayarlama

 Başlamak için, PDF belgenizin bulunduğu belge dizinini ayarlamanız gerekir. Bunu, dizinin yolunu belirterek yapabilirsiniz.`dataDir` değişken.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

## Adım 2: PDF Belgesini Yükleme

 Bu adımda, PDF belgesini .NET için Aspose.PDF kullanarak yükleyeceğiz.`Document` sınıfı PDF belgelerini yükleme ve düzenleme olanağı sağlar.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Burada,`"Test2.pdf"`yüklemek istediğiniz PDF belgesinin adıdır. Belgenin belirtilen belge dizininde mevcut olduğundan emin olun.

## Adım 3: Form Alanlarını Sekme Sırasına Göre Alma

 Form alanlarını sekme sırasına göre almak için, şuraya erişmemiz gerekir:`FieldsInTabOrder` mülkiyeti`Page` sınıf. Bu özellik, sekme sırasına göre sıralanmış form alanlarının bir listesini döndürür.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

Yukarıdaki kod parçacığında, form alanlarını ikinci sayfadan alıyoruz (`doc.Pages[1]` ) ve kısmi adlarını birleştirmek için her alanı yineleyin`s` değişken. Bu kod parçacığını özel gereksinimlerinize göre değiştirebilirsiniz.

## Adım 4: Sekme Sırasını Değiştirme

 Form alanlarının sekme sırasını değiştirmek istiyorsanız, bunu şuraya erişerek yapabilirsiniz:`TabOrder` her alanın özelliğini ve yeni bir sekme sırası değerini atayın. İşte bir örnek:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

Yukarıdaki kod parçacığında, üç form alanına yeni sekme sırası değerleri atıyoruz (`doc.Form[3]`, `doc.Form[1]` , Ve`doc.Form[2]`). Alan dizinlerini ve sekme sırası değerlerini özel gereksinimlerinize göre ayarlayın.

## Adım 5: Değiştirilen Belgeyi Kaydetme

 Form alanlarının sekme sırasını değiştirdikten sonra, değiştirilen belgeyi kaydetmeniz gerekir. Bunu kullanarak yapabilirsiniz`Save` yöntemi`Document` sınıf.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Burada,`"39522_out.pdf"` değiştirilen belgenin kaydedileceği çıktı dosyasının adıdır. Çıktı dosyası için istediğiniz adı ve konumu belirtin.

### .NET için Aspose.PDF kullanarak Sekme Sırasında Form Alanını Almak için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
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

Bu eğitimde, .NET için Aspose.PDF kullanarak form alanlarını sekme sırasına göre nasıl alacağımızı öğrendik. Bir PDF belgesini yükleme, form alanlarını sekme sırasına göre alma, sekme sırasını değiştirme ve değiştirilen belgeyi kaydetme adımlarını ele aldık. Bu adımları izleyerek form alanlarıyla verimli bir şekilde çalışabilir ve sekme sıralarını gereksinimlerinize göre özelleştirebilirsiniz.


### SSS

#### S: Alınan form alanlarını C# kodumda daha ileri işlemler için nasıl kullanabilirim?

 A: Alınan form alanlarını, özelliklerine erişerek C# kodunuzda kullanabilirsiniz.`Value`, `Name`, `Rect`vb. Bu özellikler, form alanı verilerini gerektiği gibi okumanıza ve değiştirmenize olanak tanır.

#### S: PDF belgesinin tüm sayfalarındaki form alanlarını sekme sırasına göre alabilir miyim?

 A: Evet, her sayfada gezinerek ve şuraya erişerek PDF belgesinin tüm sayfalarından form alanlarını alabilirsiniz:`FieldsInTabOrder` öğreticide gösterildiği gibi özellik. Bu size tüm sayfalarda sekme sırasına göre sıralanmış form alanları verecektir.

#### S: Metin alanları veya onay kutuları gibi yalnızca belirli türdeki form alanlarını sekme sırasına göre almak mümkün müdür?

A: Evet, form alanlarını sekme sırasına göre aldıktan sonra, metin alanları veya onay kutuları gibi türlerine göre filtreleyebilirsiniz. Her form alanının türünü kontrol etmek ve buna göre işlemek için koşullu ifadeler kullanabilirsiniz.

#### S: Sekme sırası yerine form alanlarını adlarına göre alabilir miyim?

 A: Evet, form alanlarını adlarına göre kullanarak alabilirsiniz.`doc.Form` toplama ve alan adını bir dizin olarak belirtme. Örneğin,`doc.Form["fieldName"]`Belirtilen isme sahip form alanını alacaktır.

#### S: Aspose.PDF for .NET şifreli PDF belgeleriyle çalışmayı destekliyor mu?

A: Evet, Aspose.PDF for .NET şifreli PDF belgeleriyle çalışma desteği sağlar. Uygun parola parametrelerini kullanarak şifreli PDF dosyalarını yükleyebilir ve düzenleyebilirsiniz.