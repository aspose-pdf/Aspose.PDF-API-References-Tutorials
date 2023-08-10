---
title: Java Komut Dosyasını Ayarla
linktitle: Java Komut Dosyasını Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: PDF dosyalarındaki form alanlarında JavaScript'i ayarlamak için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 270
url: /tr/net/programming-with-forms/set-java-script/
---
Bu kılavuzda, bir PDF belgesinin form alanında JavaScript'i tanımlamak için Aspose.PDF kitaplığının .NET için nasıl kullanılacağını adım adım açıklayacağız. Metin alanında belirli işlemleri gerçekleştirmek için JavaScript eylemlerini nasıl yapılandıracağınızı göstereceğiz.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Sisteminizde yüklü bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kitaplığı. Aspose resmi sitesinden indirebilirsiniz.

## 1. Adım: Belge dizinini yapılandırma

 İlk adım, üzerinde çalışmak istediğiniz PDF dosyasının bulunduğu belge dizinini yapılandırmaktır. kullanabilirsiniz`dataDir` dizin yolunu belirtmek için değişken.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` belgeler dizininize giden gerçek yolla.

## 2. Adım: Giriş PDF dosyasını yükleme

 Bu adımda, giriş PDF dosyasını kullanarak yükleyeceğiz.`Document` Aspose.PDF sınıfı.

```csharp
// Giriş PDF dosyasını yükle
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Giriş PDF dosyasının belirtilen belgeler dizininde bulunduğundan emin olun.

## 3. Adım: Metin Kutusu alanına erişme

 JavaScript'i belirli bir metin alanına uygulamak için önce o alana erişmemiz gerekir. Bu örnekte, metin alanının "textbox1" olarak adlandırıldığını varsayıyoruz. Kullan`doc.Form["textbox1"]` karşılık gelen almak için yöntem`TextBoxField` nesne.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Giriş PDF dosyasında belirtilen metin alanının bulunduğundan emin olun.

## 4. Adım: JavaScript eylemlerini yapılandırın

Artık metin alanına eriştiğimize göre, bu alanla ilişkili JavaScript eylemlerini yapılandırabiliriz. Bu örnekte iki eylem kullanacağız:`OnModifyCharacter` Ve`OnFormat` . Bu eylemler kullanılarak tanımlanacaktır.`JavascriptAction` nesneler.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

JavaScript eylemlerini ihtiyaçlarınıza göre özelleştirdiğinizden emin olun.

## Adım 5: İlk alan değerinin ayarlanması

Ortaya çıkan PDF'yi kaydetmeden önce, metin alanı için bir başlangıç değeri belirleyebiliriz. Bu örnekte, alan için "123" değerini ayarlayacağız.

```csharp
field.Value = "123";
```

Bu değeri ihtiyaçlarınıza göre özelleştirin.

## 6. Adım: Elde Edilen PDF'yi Kaydetme

 Artık metin alanını ve JavaScript eylemlerini ayarlamayı bitirdiğimize göre, ortaya çıkan PDF'yi kullanarak kaydedebiliriz.`Save` yöntemi`Document` sınıf.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Ortaya çıkan PDF'yi kaydet
doc.Save(dataDir);
```

Ortaya çıkan PDF için tam yolu ve dosya adını belirttiğinizden emin olun.


### Aspose.PDF for .NET kullanarak Set Java Script için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Giriş PDF dosyasını yükle
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// Noktadan sonra 2 hane
// Ayırıcı yok
// Neg stili = eksi
// Para birimi yok
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// İlk alan değerini ayarla
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Ortaya çıkan PDF'yi kaydet
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Çözüm

Bu kılavuzda, bir PDF belgesinin form alanında JavaScript'i ayarlamak için Aspose.PDF kitaplığının .NET için nasıl kullanılacağını öğrendik. Belirtilen adımları izleyerek, metin alanlarında çeşitli işlemler gerçekleştirmek için JavaScript eylemlerini özelleştirebilirsiniz. PDF dosyalarını işleme olanaklarını genişletmek için Aspose.PDF for .NET'in özelliklerini daha fazla keşfetmekten çekinmeyin.


### SSS

#### S: Onay kutuları ve radyo düğmeleri gibi diğer form öğelerine JavaScript eklemek için Aspose.PDF for .NET'i kullanabilir miyim?

 C: Evet, Aspose.PDF for .NET JavaScript'i onay kutuları, radyo düğmeleri ve açılır listeler gibi çeşitli form öğelerine eklemenizi sağlar. kullanabilirsiniz`JavascriptAction` Farklı form öğeleri için JavaScript eylemlerini tanımlamak için sınıf.

#### S: Form alanlarında JavaScript kullanarak kullanıcı girişini doğrulamak mümkün müdür?

 C: Evet, form alanlarındaki kullanıcı girişini doğrulamak için JavaScript kullanabilirsiniz. Gibi JavaScript eylemlerini tanımlayarak`OnBlur` veya`OnKeystroke` bir form alanı için girilen verileri doğrulayabilir ve gerekirse hata mesajlarını görüntüleyebilirsiniz.

#### S: Aspose.PDF for .NET kullanarak karmaşık JavaScript işlevlerini yürütebilir miyim?

 C: Evet, Aspose.PDF for .NET kullanarak karmaşık JavaScript işlevlerini çalıştırabilirsiniz. Özel JavaScript işlevleri tanımlama ve bunları`JavascriptAction`.

#### S: Aspose.PDF for .NET, bu eğitimde belirtilenler dışındaki JavaScript olaylarını destekliyor mu?

 C: Evet, Aspose.PDF for .NET, aşağıdakiler de dahil olmak üzere çok çeşitli JavaScript olaylarını destekler:`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , Ve`OnMouseUp`, diğerleri arasında. Kullanıcı etkileşimlerine dayalı olarak JavaScript işlemlerini tetiklemek için bu olayları kullanabilirsiniz.

#### S: Aspose.PDF for .NET'i mevcut PDF belgelerinden JavaScript kodunu çıkarmak için kullanabilir miyim?

 Y: Aspose.PDF for .NET, mevcut PDF belgelerinden JavaScript kodu çıkarma yeteneği sağlar. kullanabilirsiniz`JavascriptAction` PDF formundaki JavaScript eylemlerine erişmek ve bunları analiz etmek için sınıf ve diğer ilgili yöntemler.