---
title: Form Alanını Sekme Sırasıyla Al
linktitle: Form Alanını Sekme Sırasıyla Al
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak form alanlarını sekme sırasıyla nasıl alacağınızı öğrenin.
type: docs
weight: 240
url: /tr/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
Aspose.PDF for .NET kullanarak C#'ta PDF belgeleriyle çalışırken, form alanlarını belirli bir sekme sırasıyla almanız gereken bir senaryoyla karşılaşabilirsiniz. Bu, form alanlarında sekme sırasına göre işlemler gerçekleştirmek istediğinizde yararlı olabilir. Bu eğitimde, Aspose.PDF for .NET'i kullanarak form alanlarının sekme sırasına göre nasıl alınacağı konusunda size adım adım rehberlik edeceğiz.

## Gereksinimler

Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- Sisteminizde Visual Studio yüklü
- Aspose.PDF for .NET kütüphanesi kuruldu

Şimdi form alanlarını sekme sırasına göre alma adımlarına geçelim.

## Adım 1: Belge Dizinini Ayarlama

 Başlangıç olarak PDF belgenizin bulunduğu belge dizinini ayarlamanız gerekir. Bunu, dizinin yolunu belirterek yapabilirsiniz.`dataDir` değişken.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

## Adım 2: PDF Belgesini Yükleme

 Bu adımda Aspose.PDF for .NET kullanarak PDF belgesini yükleyeceğiz.`Document` class, PDF belgelerini yükleme ve değiştirme yeteneği sağlar.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Burada,`"Test2.pdf"`yüklemek istediğiniz PDF belgesinin adıdır. Belgenin belirtilen belge dizininde bulunduğundan emin olun.

## 3. Adım: Form Alanlarını Sekme Sırasıyla Alma

 Form alanlarını sekme sırasına göre almak için şuraya erişmemiz gerekir:`FieldsInTabOrder` mülkiyeti`Page` sınıf. Bu özellik, sekme sırasına göre sıralanmış form alanlarının bir listesini döndürür.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

Yukarıdaki kod parçasında form alanlarını ikinci sayfadan alıyoruz (`doc.Pages[1]` ) ve kısmi adlarını birleştirmek için her alanı yineleyin.`s` değişken. Bu kod pasajını özel gereksinimlerinize göre değiştirebilirsiniz.

## Adım 4: Sekme Sırasını Değiştirme

 Form alanlarının sekme sırasını değiştirmek istiyorsanız bunu şu adrese erişerek yapabilirsiniz:`TabOrder` her alanın özelliği ve yeni bir sekme sırası değeri atanması. İşte bir örnek:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

Yukarıdaki kod parçacığında, üç form alanına (`doc.Form[3]`, `doc.Form[1]` , Ve`doc.Form[2]`). Alan endekslerini ve sekme sırası değerlerini özel gereksinimlerinize göre ayarlayın.

## Adım 5: Değiştirilen Belgeyi Kaydetme

 Form alanlarının sekme sırasını değiştirdikten sonra değiştirilen belgeyi kaydetmeniz gerekir. Bunu kullanarak yapabilirsiniz`Save` yöntemi`Document` sınıf.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Burada,`"39522_out.pdf"` değiştirilen belgenin kaydedileceği çıktı dosyasının adıdır. Çıktı dosyası için istediğiniz adı ve konumu belirtin.

### Aspose.PDF for .NET kullanarak Sekme Sırasındaki Form Alanını Alma için örnek kaynak kodu 
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

Bu eğitimde Aspose.PDF for .NET kullanarak form alanlarının sekme sırasına göre nasıl alınacağını öğrendik. Bir PDF belgesi yükleme, form alanlarını sekme sırasına göre alma, sekme sırasını değiştirme ve değiştirilen belgeyi kaydetme ile ilgili adımları ele aldık. Bu adımları izleyerek form alanlarıyla verimli bir şekilde çalışabilir ve sekme sırasını ihtiyaçlarınıza göre özelleştirebilirsiniz.


### SSS'ler

#### S: C# kodumda alınan form alanlarını daha ileri işlemler için nasıl kullanabilirim?

 C: Alınan form alanlarını C# kodunuzdaki gibi özelliklerine erişerek kullanabilirsiniz.`Value`, `Name`, `Rect`vb. Bu özellikler, form alanı verilerini gerektiği gibi okumanıza ve değiştirmenize olanak tanır.

#### S: Form alanlarını PDF belgesinin tüm sayfalarından sekme sırasına göre alabilir miyim?

 C: Evet, her sayfayı yineleyerek ve PDF belgesinin tüm sayfalarından form alanlarına erişerek form alanlarını alabilirsiniz.`FieldsInTabOrder` özelliği öğreticide gösterildiği gibi. Bu size tüm sayfalarda sekme sırasına göre sıralanmış form alanları verecektir.

#### S: Metin alanları veya onay kutuları gibi yalnızca belirli türdeki form alanlarını sekme sırasına göre almak mümkün müdür?

C: Evet, form alanlarını sekme sırasına göre aldıktan sonra metin alanları veya onay kutuları gibi türlerine göre filtreleyebilirsiniz. Her form alanının türünü kontrol etmek ve bunları buna göre işlemek için koşullu ifadeleri kullanabilirsiniz.

#### S: Form alanlarını sekme sırası yerine adlarına göre alabilir miyim?

 C: Evet, form alanlarını isimlerine göre alabilirsiniz.`doc.Form` toplama ve alan adının indeks olarak belirtilmesi. Örneğin,`doc.Form["fieldName"]`belirtilen addaki form alanını alacaktır.

#### S: Aspose.PDF for .NET şifreli PDF belgeleriyle çalışmayı destekliyor mu?

C: Evet, Aspose.PDF for .NET şifreli PDF belgeleriyle çalışma desteği sağlar. Uygun şifre parametrelerini kullanarak şifrelenmiş PDF dosyalarını yükleyebilir ve değiştirebilirsiniz.