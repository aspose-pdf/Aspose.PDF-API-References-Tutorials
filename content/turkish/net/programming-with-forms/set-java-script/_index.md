---
title: Java Komut Dosyasını Ayarla
linktitle: Java Komut Dosyasını Ayarla
second_title: .NET API Referansı için Aspose.PDF
description: PDF dosyalarındaki form alanlarında JavaScript'i ayarlamak için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 270
url: /tr/net/programming-with-forms/set-java-script/
---
Bu kılavuzda, bir PDF belgesinin form alanında JavaScript'i tanımlamak için Aspose.PDF kütüphanesinin .NET için nasıl kullanılacağını adım adım açıklayacağız. Metin alanında belirli işlemleri gerçekleştirmek için JavaScript eylemlerini nasıl yapılandıracağınızı size göstereceğiz.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Sisteminizde kurulu bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kütüphanesi. Aspose'un resmi web sitesinden indirebilirsiniz.

## 1. Adım: Belge dizinini yapılandırma

 İlk adım, üzerinde çalışmak istediğiniz PDF dosyasının bulunduğu belge dizinini yapılandırmaktır. Şunu kullanabilirsiniz:`dataDir` Dizin yolunu belirtmek için değişken.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` Belgeler dizininizin gerçek yolu ile.

## 2. Adım: Giriş PDF dosyasını yükleme

Bu adımda, giriş PDF dosyasını kullanarak yükleyeceğiz.`Document` Aspose.PDF sınıfı.

```csharp
// Giriş PDF dosyasını yükle
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Giriş PDF dosyasının belirtilen belgeler dizininde bulunduğundan emin olun.

## 3. Adım: TextBox alanına erişme

 JavaScript'i belirli bir metin alanına uygulamak için öncelikle o alana erişmemiz gerekir. Bu örnekte metin alanının "textbox1" olarak adlandırıldığını varsayıyoruz. Kullan`doc.Form["textbox1"]` karşılık gelen değeri elde etme yöntemi`TextBoxField` nesne.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Girilen PDF dosyasında belirtilen metin alanının mevcut olduğundan emin olun.

## 4. Adım: JavaScript eylemlerini yapılandırın

 Artık metin alanına eriştiğimize göre bu alanla ilişkili JavaScript eylemlerini yapılandırabiliriz. Bu örnekte iki eylem kullanacağız:`OnModifyCharacter` Ve`OnFormat` . Bu eylemler kullanılarak tanımlanacaktır.`JavascriptAction` nesneler.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

JavaScript eylemlerini ihtiyaçlarınıza göre özelleştirdiğinizden emin olun.

## Adım 5: Başlangıç alan değerinin ayarlanması

Ortaya çıkan PDF'yi kaydetmeden önce metin alanı için bir başlangıç değeri ayarlayabiliriz. Bu örnekte alan için "123" değerini ayarlayacağız.

```csharp
field.Value = "123";
```

Bu değeri ihtiyaçlarınıza göre özelleştirin.

## Adım 6: Ortaya Çıkan PDF'yi Kaydetme

 Artık metin alanını ve JavaScript eylemlerini ayarlamayı bitirdiğimize göre, ortaya çıkan PDF'yi aşağıdaki komutu kullanarak kaydedebiliriz:`Save` yöntemi`Document` sınıf.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Ortaya çıkan PDF'yi kaydet
doc.Save(dataDir);
```

Ortaya çıkan PDF'nin tam yolunu ve dosya adını belirttiğinizden emin olun.


### Aspose.PDF for .NET kullanarak Java Komut Dosyasını Ayarlama için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Giriş PDF dosyasını yükle
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// Noktadan sonra 2 hane
// Ayırıcı yok
// Negatif stil = eksi
// Para birimi yok
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Başlangıç alan değerini ayarla
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Ortaya çıkan PDF'yi kaydet
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Çözüm

Bu kılavuzda, bir PDF belgesinin form alanında JavaScript'i ayarlamak için .NET için Aspose.PDF kütüphanesinin nasıl kullanılacağını öğrendik. Özetlenen adımları izleyerek, metin alanlarında çeşitli işlemler gerçekleştirmek için JavaScript eylemlerini özelleştirebilirsiniz. PDF dosyalarını değiştirme olanaklarını genişletmek için Aspose.PDF for .NET'in özelliklerini daha fazla keşfetmekten çekinmeyin.


### SSS'ler

#### S: Onay kutuları ve radyo düğmeleri gibi diğer form öğelerine JavaScript eklemek için Aspose.PDF for .NET'i kullanabilir miyim?

 C: Evet, Aspose.PDF for .NET, onay kutuları, radyo düğmeleri ve açılır listeler dahil olmak üzere çeşitli form öğelerine JavaScript eklemenizi sağlar. Şunu kullanabilirsiniz:`JavascriptAction` Farklı form öğeleri için JavaScript eylemlerini tanımlamak için sınıf.

#### S: Form alanlarında JavaScript kullanarak kullanıcı girişini doğrulamak mümkün mü?

 C: Evet, form alanlarındaki kullanıcı girişini doğrulamak için JavaScript'i kullanabilirsiniz. Gibi JavaScript eylemlerini tanımlayarak`OnBlur` veya`OnKeystroke` bir form alanı için girilen verileri doğrulayabilir ve gerekirse hata mesajlarını görüntüleyebilirsiniz.

#### S: Aspose.PDF for .NET'i kullanarak karmaşık JavaScript fonksiyonlarını çalıştırabilir miyim?

 C: Evet, Aspose.PDF for .NET'i kullanarak karmaşık JavaScript işlevlerini çalıştırabilirsiniz. Özel JavaScript işlevlerini tanımlama ve bunları`JavascriptAction`.

#### S: Aspose.PDF for .NET bu eğitimde bahsedilenlerin dışındaki JavaScript olaylarını destekliyor mu?

 C: Evet, Aspose.PDF for .NET çok çeşitli JavaScript olaylarını destekler;`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , Ve`OnMouseUp`, diğerleri arasında. Bu olayları, kullanıcı etkileşimlerine dayalı olarak JavaScript eylemlerini tetiklemek için kullanabilirsiniz.

#### S: Mevcut PDF belgelerinden JavaScript kodunu çıkarmak için Aspose.PDF for .NET'i kullanabilir miyim?

 C: Aspose.PDF for .NET, mevcut PDF belgelerinden JavaScript kodunu çıkarma olanağı sağlar. Şunu kullanabilirsiniz:`JavascriptAction` PDF formundaki JavaScript eylemlerine erişmek ve bunları analiz etmek için class ve diğer ilgili yöntemler.