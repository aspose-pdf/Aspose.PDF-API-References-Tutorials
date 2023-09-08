---
title: Yatay ve Dikey Radyo Düğmeleri
linktitle: Yatay ve Dikey Radyo Düğmeleri
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF belgelerinizde kolayca yatay ve dikey radyo düğmeleri oluşturun.
type: docs
weight: 180
url: /tr/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
Bu eğitimde size Aspose.PDF for .NET kullanarak bir PDF belgesinde yatay ve dikey olarak düzenlenmiş radyo düğmelerinin nasıl oluşturulacağını göstereceğiz. Bu süreçte size yol göstermek için C# kaynak kodunu adım adım açıklayacağız.

## Adım 1: Hazırlık

Gerekli kitaplıkları içe aktardığınızdan ve belgeler dizininizin yolunu ayarladığınızdan emin olun:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin

Mevcut PDF belgesini yükleyin:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## 3. Adım: Radyo düğmesi seçeneklerini özelleştirin

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

## 5. Adım: Dikey radyo düğmeleri ekleyin

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

### Aspose.PDF for .NET kullanan Yatay ve Dikey Radyo Düğmeleri için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Daha önce kaydedilen belgeyi yükleyin
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap, iki radyo düğmesi seçeneği arasındaki mesafedir.
	formEditor.RadioGap = 4;
	// Yatay radyo düğmesi ekle
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize eğer radyo düğmesi öğesinin boyutuysa.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Dikey olarak yerleştirilmiş başka bir radyo düğmesi ekleyin
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

Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF belgesinde yatay ve dikey olarak düzenlenmiş radyo düğmelerinin nasıl oluşturulacağını öğrendik. Bu adımları izleyerek radyo düğmelerinin düzenini kolayca özelleştirebilir ve Aspose.PDF'yi kullanarak bunları PDF belgelerinize ekleyebilirsiniz.

### SSS'ler

#### S: Bir PDF belgesinde yatay ve dikey olarak düzenlenmiş radyo düğmeleri nelerdir?

C: Bir PDF belgesindeki yatay ve dikey olarak düzenlenmiş radyo düğmeleri, radyo düğmesi seçeneklerinin düzen yönünü belirtir. Yatay düzen, radyo düğmesi seçeneklerini yan yana yerleştirerek kullanıcıların soldan sağa seçim yapmasına olanak tanır. Dikey düzen ise radyo düğmesi seçeneklerini üst üste istifleyerek kullanıcıların yukarıdan aşağıya seçim yapmasına olanak tanır.

#### S: Aspose.PDF for .NET'teki radyo düğmesi seçeneklerinin görünümünü nasıl özelleştiririm?

C: Çeşitli özellikleri ayarlayarak Aspose.PDF for .NET'teki radyo düğmesi seçeneklerinin görünümünü özelleştirebilirsiniz. API, iki radyo düğmesi seçeneği arasındaki mesafeyi ayarlama seçenekleri sunar (`RadioGap`), düzen yönü (`RadioHoriz`), radyo düğmesi öğelerinin boyutu (`RadioButtonItemSize`), kenarlık genişliği ve radyo düğmelerinin rengi ve daha fazlası.

#### S: Aynı PDF belgesine hem yatay hem de dikey radyo düğmeleri ekleyebilir miyim?

C: Evet, Aspose.PDF for .NET'i kullanarak aynı PDF belgesine hem yatay hem de dikey radyo düğmeleri ekleyebilirsiniz. Öğreticide sağlanan örnek kaynak kodu, aynı PDF belgesine ilk olarak yatay olarak düzenlenmiş radyo düğmelerinin nasıl ekleneceğini ve ardından dikey olarak düzenlenmiş başka bir radyo düğmesi kümesinin nasıl ekleneceğini gösterir.

#### S: Her radyo düğmesi grubu için farklı radyo düğmesi seçeneklerini ayarlayabilir miyim?

 C: Evet, her radyo düğmesi grubu için farklı radyo düğmesi seçeneklerini ayarlayabilirsiniz. Her grubun kendine özgü bir özelliği olmalı`RadioButtonField` nesne ve`RadioButtonOptionField` her gruptaki nesneler, seçenekleri için aynı sayfayı ve benzersiz adları paylaşmalıdır. Bu, her gruptaki radyo düğmelerinin doğru çalışmasını ve seçimlerin birbirini dışlamasını sağlar.

#### S: Radyo düğmelerinin düzeni ve görünüm ayarları tüm PDF görüntüleyicilerde ve uygulamalarda destekleniyor mu?

C: Evet, radyo düğmelerinin düzeni ve görünüm ayarları tüm standart uyumlu PDF görüntüleyicilerde ve uygulamalarda desteklenir. PDF spesifikasyonu, radyo düğmelerini ve bunların çeşitli niteliklerini tanımlayarak bunların evrensel olarak PDF formatında tanınmasını sağlar. Ancak çeşitli platformlarda tutarlı görüntüleme sağlamak için radyo düğmelerinin görünümünü ve davranışını farklı PDF görüntüleyicilerde test etmek önemlidir.