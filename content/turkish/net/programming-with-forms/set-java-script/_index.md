---
title: Java Script'i Ayarla
linktitle: Java Script'i Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: PDF dosyalarındaki form alanlarına JavaScript eklemek için Aspose.PDF for .NET'in nasıl kullanılacağını öğrenin.
type: docs
weight: 270
url: /tr/net/programming-with-forms/set-java-script/
---
Bu kılavuzda, .NET için Aspose.PDF kütüphanesini kullanarak bir PDF belgesinin form alanında JavaScript'i nasıl tanımlayacağınızı adım adım açıklayacağız. JavaScript eylemlerini metin alanında belirli işlemleri gerçekleştirecek şekilde nasıl yapılandıracağınızı göstereceğiz.

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Sisteminizde yüklü bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kütüphanesi. Bunu Aspose resmi web sitesinden indirebilirsiniz.

## Adım 1: Belge dizinini yapılandırma

 İlk adım, üzerinde çalışmak istediğiniz PDF dosyasının bulunduğu belge dizinini yapılandırmaktır.`dataDir` dizin yolunu belirtmek için kullanılan değişken.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` Belgelerinizin bulunduğu dizinin gerçek yolunu belirtin.

## Adım 2: Girdi PDF dosyasını yükleme

 Bu adımda, giriş PDF dosyasını kullanarak yükleyeceğiz`Document` Aspose.PDF sınıfı.

```csharp
// Giriş PDF dosyasını yükle
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Giriş PDF dosyasının belirtilen belgeler dizininde mevcut olduğundan emin olun.

## Adım 3: TextBox alanına erişim

 Belirli bir metin alanına JavaScript uygulamak için, önce o alana erişmemiz gerekir. Bu örnekte, metin alanının "textbox1" olarak adlandırıldığını varsayıyoruz. Şunu kullanın:`doc.Form["textbox1"]` karşılık geleni elde etmek için yöntem`TextBoxField` nesne.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Belirtilen metin alanının giriş PDF dosyasında mevcut olduğundan emin olun.

## Adım 4: JavaScript eylemlerini yapılandırın

 Artık metin alanına eriştiğimize göre, bu alanla ilişkili JavaScript eylemlerini yapılandırabiliriz. Bu örnekte, iki eylem kullanacağız:`OnModifyCharacter` Ve`OnFormat` Bu eylemler kullanılarak tanımlanacaktır`JavascriptAction` nesneler.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

JavaScript eylemlerini ihtiyaçlarınıza göre özelleştirdiğinizden emin olun.

## Adım 5: Başlangıç alan değerini ayarlama

Elde edilen PDF'i kaydetmeden önce, metin alanı için bir başlangıç değeri ayarlayabiliriz. Bu örnekte, alan için "123" değerini ayarlayacağız.

```csharp
field.Value = "123";
```

Bu değeri ihtiyaçlarınıza göre özelleştirin.

## Adım 6: Ortaya Çıkan PDF'yi Kaydetme

 Artık metin alanını ve JavaScript eylemlerini ayarlamayı tamamladığımıza göre, ortaya çıkan PDF'yi şu şekilde kaydedebiliriz:`Save` yöntemi`Document` sınıf.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Sonuç PDF'ini kaydet
doc.Save(dataDir);
```

Elde edilen PDF için tam yolu ve dosya adını belirttiğinizden emin olun.


### .NET için Aspose.PDF kullanarak Set Java Script için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Giriş PDF dosyasını yükle
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// Noktadan sonra 2 rakam
// Ayırıcı yok
// Neg stili = eksi
// Para birimi yok
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Başlangıç alanı değerini ayarlayın
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Sonuç PDF'ini kaydet
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Çözüm

Bu kılavuzda, bir PDF belgesinin form alanına JavaScript yerleştirmek için Aspose.PDF kütüphanesini .NET için nasıl kullanacağınızı öğrendik. Belirtilen adımları izleyerek, metin alanlarında çeşitli işlemler gerçekleştirmek için JavaScript eylemlerini özelleştirebilirsiniz. PDF dosyalarını düzenleme olanaklarını genişletmek için Aspose.PDF for .NET'in özelliklerini daha fazla keşfetmekten çekinmeyin.


### SSS

#### S: Aspose.PDF for .NET'i onay kutuları ve radyo düğmeleri gibi diğer form öğelerine JavaScript eklemek için kullanabilir miyim?

 A: Evet, Aspose.PDF for .NET, onay kutuları, radyo düğmeleri ve açılır listeler dahil olmak üzere çeşitli form öğelerine JavaScript eklemenize olanak tanır.`JavascriptAction` Farklı form elemanları için JavaScript eylemlerini tanımlayan sınıf.

#### S: Form alanlarında JavaScript kullanarak kullanıcı girdisini doğrulamak mümkün müdür?

 A: Evet, form alanlarında kullanıcı girdisini doğrulamak için JavaScript kullanabilirsiniz. JavaScript eylemlerini şu şekilde tanımlayarak:`OnBlur` veya`OnKeystroke` Bir form alanı için girilen verileri doğrulayabilir ve gerekirse hata mesajları görüntüleyebilirsiniz.

#### S: Aspose.PDF for .NET kullanarak karmaşık JavaScript fonksiyonlarını çalıştırabilir miyim?

 A: Evet, .NET için Aspose.PDF'yi kullanarak karmaşık JavaScript işlevlerini yürütebilirsiniz. Özel JavaScript işlevlerini tanımlama ve bunları`JavascriptAction`.

#### S: Aspose.PDF for .NET bu eğitimde belirtilenlerin dışında JavaScript olaylarını da destekliyor mu?

 A: Evet, Aspose.PDF for .NET, JavaScript olaylarının geniş bir yelpazesini destekler; bunlara şunlar dahildir:`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , Ve`OnMouseUp`, diğerleri arasında. Bu olayları, kullanıcı etkileşimlerine dayalı JavaScript eylemlerini tetiklemek için kullanabilirsiniz.

#### S: Mevcut PDF belgelerinden JavaScript kodunu çıkarmak için Aspose.PDF for .NET'i kullanabilir miyim?

 A: Aspose.PDF for .NET, mevcut PDF belgelerinden JavaScript kodunu çıkarma olanağı sağlar.`JavascriptAction` PDF formunda JavaScript eylemlerine erişmek ve bunları analiz etmek için sınıf ve diğer ilgili yöntemler.