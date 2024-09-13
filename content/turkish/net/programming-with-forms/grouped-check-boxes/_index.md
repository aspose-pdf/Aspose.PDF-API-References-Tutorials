---
title: PDF Belgesinde Gruplandırılmış Onay Kutuları
linktitle: PDF Belgesinde Gruplandırılmış Onay Kutuları
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım eğitimle Aspose.PDF for .NET kullanarak bir PDF belgesinde gruplanmış onay kutularının (radyo düğmeleri) nasıl oluşturulacağını öğrenin.
type: docs
weight: 170
url: /tr/net/programming-with-forms/grouped-check-boxes/
---
## giriiş

Etkileşimli PDF'ler oluşturmak, özellikle Aspose.PDF for .NET gibi güçlü araçlarınız olduğunda, kulağa geldiği kadar zor değildir. PDF belgelerinize eklemeniz gerekebilecek etkileşimli öğelerden biri, gruplanmış onay kutuları veya daha spesifik olarak, kullanıcıların bir dizi seçenekten birini seçmesine izin veren radyo düğmeleridir. Bu eğitim, Aspose.PDF for .NET kullanarak bir PDF belgesine gruplanmış onay kutuları (radyo düğmeleri) ekleme sürecini adım adım anlatacaktır. İster yeni başlayan ister deneyimli bir geliştirici olun, bu kılavuzu ilgi çekici, ayrıntılı ve takip etmesi kolay bulacaksınız.

## Ön koşullar

Adım adım kılavuza dalmadan önce, bazı temel ön koşulları ele alalım:

1.  .NET için Aspose.PDF: Aspose.PDF kütüphanesinin yüklü olduğundan emin olun. Değilse,[buradan indirin](https://releases.aspose.com/pdf/net/).
2. IDE: Visual Studio gibi bir geliştirme ortamınız olmalı.
3. .NET Framework: Projenin Aspose.PDF ile uyumlu bir .NET Framework sürümünü hedeflemesi gerekir.
4. Temel C# Bilgisi: Akıcı bir şekilde takip edebilmek için C# ve PDF düzenleme konusunda bilgi sahibi olmak gerekir.
5.  Lisans: Aspose.PDF'in tam işlevsellik için bir lisansa ihtiyacı vardır.[geçici lisans almak](https://purchase.aspose.com/temporary-license/) eğer gerekirse.

## Paketleri İçe Aktar

Başlamadan önce, gerekli ad alanlarını projenize aktardığınızdan emin olun:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Forms;
```

Bu paketler, radyo düğmeleri oluşturma ve özelliklerini tanımlama dahil olmak üzere PDF belgelerini düzenlemek için gereken tüm sınıflara ve yöntemlere erişmenizi sağlayacaktır.

Bu bölümde, gruplanmış onay kutuları (radyo düğmeleri) oluşturma sürecini net ve anlaşılması kolay adımlara ayıracağız.

## Adım 1: Yeni bir PDF Belgesi Oluşturun

 İlk adım, bir örnek oluşturmaktır`Document` nesne, PDF dosyanızı temsil edecektir. Ardından, gruplanmış onay kutularınızı yerleştireceğiniz belgenize boş bir sayfa ekleyin.

```csharp
// Belge nesnesini örnekle
Document pdfDocument = new Document();

// PDF dosyasına bir sayfa ekleyin
Page page = pdfDocument.Pages.Add();
```

Bu, PDF'ye radyo düğmeleri gibi herhangi bir öğe eklemek için temel oluşturur.

## Adım 2: Radyo Düğmesi Alanını Başlatın

Daha sonra, bir tane oluşturmamız gerekiyor`RadioButtonField` gruplanmış onay kutularını (radyo düğmeleri) tutacak nesne. Bu alan, onay kutularının görüneceği belirli sayfaya eklenir.

```csharp
// RadioButtonField nesnesini örneklendirin ve ilk sayfaya atayın
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

Bunu, bireysel radyo düğmesi seçeneklerini bir araya toplayacak bir kapsayıcı olarak düşünün.

## Adım 3: Radyo Düğmesi Seçeneklerini Ekleyin

 Şimdi, alana bireysel radyo düğmesi seçeneklerini ekleyelim. Bu örnekte, iki radyo düğmesi ekleyeceğiz ve konumlarını kullanarak belirteceğiz`Rectangle` nesne.

```csharp
// İlk radyo düğmesi seçeneğini ekleyin ve konumunu Dikdörtgen kullanarak belirtin
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));

// Tanımlama için seçenek adlarını ayarlayın
opt1.OptionName = "Option1";
opt2.OptionName = "Option2";
```

 Burada,`Rectangle` nesnesi sayfadaki her bir radyo düğmesinin koordinatlarını ve boyutunu tanımlar.

## Adım 4: Radyo Düğmelerinin Stilini Özelleştirin

 Radyo düğmelerinin görünümünü, bunların ayarlarını yaparak özelleştirebilirsiniz.`Style` Örneğin, kare şeklinde onay kutuları veya çapraz şeklinde onay kutuları isteyebilirsiniz.

```csharp
// Radyo düğmelerinin stilini ayarlayın
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Cross;
```

Bu, onay kutularının görünümünü ve hissini kontrol etmenizi sağlayarak onları daha kullanıcı dostu ve görsel olarak çekici hale getirir.

## Adım 5: Kenarlık Özelliklerini Yapılandırın

Kenarlıklar, onay kutularının kolayca tanımlanabilir hale getirilmesinde önemli bir rol oynar. Burada, her bir radyo düğmesi seçeneğinin etrafına katı kenarlıklar ekleyeceğiz ve bunların genişliğini ve rengini tanımlayacağız.

```csharp
// İlk radyo düğmesinin sınırını yapılandırın
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt1.Characteristics.Border = Color.Black;

// İkinci radyo düğmesinin sınırını yapılandırın
opt2.Border = new Border(opt2);
opt2.Border.Style = BorderStyle.Solid;
opt2.Border.Width = 1;
opt2.Characteristics.Border = Color.Black;
```

Bu adım, her radyo düğmesinin iyi tanımlanmış bir kenarlığa sahip olmasını sağlayarak belgenin okunabilirliğini artırır.

## Adım 6: Forma Radyo Düğmesi Seçenekleri Ekleyin

Şimdi, radyo düğmelerini belgenin formuna ekleyeceğiz. Bu, onay kutularını tek bir alan altında gruplamanın son adımıdır.

```csharp
// Belgenin form nesnesine radyo düğmesi alanı ekleyin
pdfDocument.Form.Add(radio);
```

Form nesnesi, gruplanmış onay kutularımız da dahil olmak üzere tüm etkileşimli öğeler için bir kapsayıcı görevi görür.

## Adım 7: PDF Belgesini Kaydedin

Son olarak her şey ayarlandıktan sonra PDF dokümanını istediğiniz yere kaydedebilirsiniz.

```csharp
// Çıktı dosyası yolunu tanımlayın
string dataDir = "YOUR DOCUMENT DIRECTORY" + "GroupedCheckBoxes_out.pdf";

// PDF belgesini kaydedin
pdfDocument.Save(dataDir);

// Başarılı oluşturmayı onayla
Console.WriteLine("Grouped checkboxes added successfully. File saved at " + dataDir);
```

Ve işte bu kadar! Aspose.PDF for .NET kullanarak gruplanmış onay kutularına sahip bir PDF'yi başarıyla oluşturdunuz.

## Çözüm

PDF belgelerine gruplanmış onay kutuları gibi etkileşimli öğeler eklemek ilk başta zor görünebilir, ancak Aspose.PDF for .NET ile bu çok kolay hale gelir. Bu adım adım kılavuzu izleyerek, temel bir PDF belgesini nasıl ayarlayacağınızı, gruplanmış radyo düğmeleri nasıl ekleyeceğinizi, görünümlerini nasıl özelleştireceğinizi ve nihai sonucu nasıl kaydedeceğinizi öğrendiniz. Formlar, anketler veya başka herhangi bir tür etkileşimli PDF oluşturuyor olun, bu kılavuz size başlamak için sağlam bir temel sağlar.

## SSS

### Bir gruba ikiden fazla radyo düğmesi ekleyebilir miyim?
 Kesinlikle! Sadece ek örnek oluşturun`RadioButtonOptionField` nesneleri ekleyin ve bunları`RadioButtonField` eğitimde gösterildiği gibi.

### Bir belgede birden fazla onay kutusu grubunu nasıl işlerim?
Birden fazla grup oluşturmak için ayrı gruplar oluşturun`RadioButtonField` Her grup için nesneler.

### Ekleyebileceğim onay kutusu sayısında bir sınırlama var mı?
Hayır, Aspose.PDF for .NET, bir PDF'ye ekleyebileceğiniz onay kutusu sayısına herhangi bir sınırlama getirmez.

### Onay kutularının görünümünü eklendikten sonra değiştirebilir miyim?
Evet, onay kutuları eklendikten sonra kenarlık stili, genişliği ve rengi gibi özellikleri değiştirebilirsiniz.

### Görüntüleri radyo düğmesi olarak kullanmak mümkün müdür?
 Evet, Aspose.PDF, özel görüntüleri radyo düğmeleri olarak kullanmanıza olanak tanır.`Appearance` Her radyo düğmesi seçeneğinin özelliği.