---
title: Yatay ve Dikey Radyo Düğmeleri
linktitle: Yatay ve Dikey Radyo Düğmeleri
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinizde kolayca yatay ve dikey radyo düğmeleri oluşturun.
type: docs
weight: 180
url: /tr/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesinde yatay ve dikey olarak düzenlenmiş radyo düğmelerinin nasıl oluşturulacağını göstereceğiz. Bu süreçte size rehberlik etmek için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kütüphaneleri içe aktardığınızdan ve belgelerinizin dizinine giden yolu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Belgeyi yükleyin

Mevcut PDF belgesini yükleyin:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## Adım 3: Radyo düğmesi seçeneklerini özelleştirin

Aşağıdaki özellikleri ayarlayarak radyo düğmesi seçeneklerini özelleştirin:

```csharp
formEditor. RadioGap = 4; // İki radyo düğmesi seçeneği arasındaki mesafe
formEditor. RadioHoriz = true; //Radyo düğmelerinin yatay düzeni
formEditor.RadioButtonItemSize = 20; // Radyo düğmelerinin boyutu
formEditor.Facade.BorderWidth = 1; // Radyo düğmesi kenarlığının genişliği
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Radyo düğmesi kenarlık rengi
```

## Adım 4: Yatay Radyo Düğmeleri Ekleyin

Alanın seçeneklerini ve konumunu belirterek yatay olarak düzenlenmiş radyo düğmeleri ekleyin:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## Adım 5: Dikey radyo düğmeleri ekleyin

Alanın seçeneklerini ve konumunu belirterek dikey olarak düzenlenmiş radyo düğmeleri ekleyin:

```csharp
formEditor. RadioHoriz = false; // Radyo düğmelerinin dikey düzeni
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## Adım 6: Belgeyi kaydedin

Değiştirilen PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### .NET için Aspose.PDF kullanarak Yatay ve Dikey Radyo Düğmeleri için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizinine giden yol.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Daha önce kaydedilmiş belgeyi yükleyin
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap, iki radyo düğmesi seçeneği arasındaki mesafedir.
	formEditor.RadioGap = 4;
	// Yatay radyo düğmesi ekle
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize, radyo düğmesi öğesinin boyutunu belirtir.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Dikey olarak konumlandırılmış başka bir radyo düğmesi ekleyin
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// PDF belgesini kaydedin
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesinde yatay ve dikey olarak düzenlenmiş radyo düğmelerinin nasıl oluşturulacağını öğrendik. Bu adımları izleyerek, radyo düğmelerinin düzenini kolayca özelleştirebilir ve bunları Aspose.PDF kullanarak PDF belgelerinize ekleyebilirsiniz.

### SSS

#### S: PDF belgesinde yatay ve dikey olarak düzenlenmiş radyo düğmeleri nelerdir?

A: Bir PDF belgesinde yatay ve dikey olarak düzenlenmiş radyo düğmeleri, radyo düğmesi seçeneklerinin düzen yönelimini ifade eder. Yatay düzen, radyo düğmesi seçeneklerini yan yana yerleştirir ve kullanıcıların soldan sağa doğru seçim yapmasını sağlar. Öte yandan dikey düzen, radyo düğmesi seçeneklerini üst üste istifler ve kullanıcıların yukarıdan aşağıya doğru seçim yapmasını sağlar.

#### S: Aspose.PDF for .NET'te radyo düğmesi seçeneklerinin görünümünü nasıl özelleştirebilirim?

A: Aspose.PDF for .NET'te radyo düğmesi seçeneklerinin görünümünü çeşitli özellikleri ayarlayarak özelleştirebilirsiniz. API, iki radyo düğmesi seçeneği arasındaki mesafeyi ayarlamak için seçenekler sunar (`RadioGap`), düzen yönü (`RadioHoriz`), radyo düğmesi öğelerinin boyutu (`RadioButtonItemSize`), radyo düğmelerinin kenarlık genişliği ve rengi ve daha fazlası.

#### S: Aynı PDF belgesine hem yatay hem de dikey radyo düğmeleri ekleyebilir miyim?

A: Evet, Aspose.PDF for .NET kullanarak aynı PDF belgesine hem yatay hem de dikey radyo düğmeleri ekleyebilirsiniz. Eğitimde sağlanan örnek kaynak kodu, önce yatay olarak düzenlenmiş radyo düğmelerinin nasıl ekleneceğini ve ardından aynı PDF belgesine dikey olarak düzenlenmiş başka bir radyo düğmesi setinin nasıl ekleneceğini gösterir.

#### S: Her bir radyo düğmesi grubu için farklı radyo düğmesi seçenekleri belirleyebilir miyim?

 A: Evet, her bir radyo düğmesi grubu için farklı radyo düğmesi seçenekleri ayarlayabilirsiniz. Her grubun kendine özgü bir`RadioButtonField` nesne ve`RadioButtonOptionField` her gruptaki nesneler aynı sayfayı ve seçenekleri için benzersiz adları paylaşmalıdır. Bu, her gruptaki radyo düğmelerinin doğru şekilde çalışmasını ve seçimlerin karşılıklı olarak özel olmasını sağlar.

#### S: Radyo düğmelerinin düzen ve görünüm ayarları tüm PDF görüntüleyicilerinde ve uygulamalarında destekleniyor mu?

A: Evet, radyo düğmelerinin düzeni ve görünüm ayarları tüm standart uyumlu PDF görüntüleyicilerinde ve uygulamalarında desteklenir. PDF belirtimi radyo düğmelerini ve çeşitli niteliklerini tanımlar ve bunları PDF formatında evrensel olarak tanınır hale getirir. Ancak, çeşitli platformlarda tutarlı bir işleme sağlamak için radyo düğmelerinin görünümünü ve davranışını farklı PDF görüntüleyicilerinde test etmek önemlidir.