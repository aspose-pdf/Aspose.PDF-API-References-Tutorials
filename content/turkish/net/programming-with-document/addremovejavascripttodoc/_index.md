---
title: Javascript'i PDF Belgesine Ekle Kaldır
linktitle: Javascript'i Dokümana Ekle Kaldır
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF belgesine JavaScript eklemeyi ve kaldırmayı öğrenin. Belge düzeyinde komut dosyası oluşturmaya yönelik kod eğitimlerini içeren adım adım kılavuz.
type: docs
weight: 30
url: /tr/net/programming-with-document/addremovejavascripttodoc/
---
PDF belgesine JavaScript eklemek ve kaldırmak için Aspose.PDF for .NET kitaplığını kullanacağız. Bu güçlü kitaplık, .NET uygulamalarında PDF dosyalarını yönetmemize olanak tanır. Aspose.PDF for .NET'i kullanarak JavaScript eklemek ve kaldırmak için aşağıdaki adım adım talimatları izleyin.

## 1. Adım: Yeni Bir PDF Belgesi Oluşturun

 Yeni bir örneğini oluşturarak başlayın`Document` sınıf Aspose.PDF for .NET tarafından sağlanmıştır. Bu, JavaScript'i ekleyeceğimiz PDF belgesi olarak görev yapacak.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## 2. Adım: Belge Düzeyinde JavaScript ekleyin

 Belge düzeyinde JavaScript eklemek için`JavaScript` mülkiyeti`Document` sınıf. JavaScript sözlüğündeki tuşlara JavaScript işlevleri atayın.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

 Bu eğitimde iki JavaScript işlevi ekledik,`func1` Ve`func2`, PDF belgesine.

## 3. Adım: Belge Düzeyinde JavaScript'i Kaldırma

 JavaScript'i belge düzeyinde kaldırmak için PDF belgesini yükleyin ve`JavaScript`sözlük. Tuşlar üzerinde yineleyin ve istediğiniz JavaScript işlevini kaldırın.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

 Bu eğitimde, şunları kaldırıyoruz:`func1` PDF belgesinden JavaScript işlevi.

## 4. Adım: Değişiklikleri Kaydedin ve Doğrulayın

Değiştirilen PDF belgesini kaydedin ve değişiklikleri doğrulayın.

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

Bu kod, değiştirilen PDF belgesini kaydedecek ve başarı mesajını görüntüleyecektir.

### Aspose.PDF for .NET kullanarak PDF belgelerinden Ekle Kaldırma Javascript'i için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");

// Belge düzeyindeki JavaScript'i kaldır
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
	Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
Console.WriteLine("=============================== ");

Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

## Çözüm

Bu makalede Aspose.PDF for .NET kullanarak PDF belgelerine JavaScript ekleme ve kaldırma konusunda adım adım bir kılavuz sunduk. Talimatları takip ederek ve sağlanan kod eğitimlerinden yararlanarak, JavaScript'i PDF belgelerinize kolayca dahil edebilir ve gerektiğinde kaldırabilirsiniz. JavaScript, PDF dosyalarınızda dinamik işlevsellik ve etkileşim sağlayarak kullanıcı deneyimini geliştirir.


### PDF belgesine javascript eklemek ve kaldırmak için SSS

#### S: Aspose.PDF for .NET nedir?

C: Aspose.PDF for .NET, geliştiricilerin .NET uygulamalarındaki PDF dosyalarını etkili bir şekilde işlemesine olanak tanıyan güçlü bir kitaplıktır. PDF belgeleriyle programlı olarak çalışmak için kapsamlı özellikler sağlar.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesine nasıl JavaScript ekleyebilirim?

 C: JavaScript'i belge düzeyinde ekleyebilirsiniz.`JavaScript` mülkiyeti`Document` sınıf. JavaScript sözlüğündeki tuşlara JavaScript işlevlerini atamanız yeterlidir.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinden JavaScript'i kaldırabilir miyim?

 C: Evet, PDF belgesinden JavaScript'i şuraya erişerek kaldırabilirsiniz:`JavaScript` sözlük ve istenen JavaScript işlevinin kaldırılması.

#### S: Aspose.PDF for .NET profesyonel projeler için uygun mudur?

C: Aspose.PDF for .NET kesinlikle profesyonel projelerde PDF düzenleme ve oluşturma görevlerinde yaygın olarak kullanılıyor. Yüksek performans ve güvenilir işlevsellik sunar.

#### S: Bir PDF belgesine JavaScript eklemek ne gibi faydalar sağlar?

C: Bir PDF belgesine JavaScript eklemek, etkileşimli ve dinamik PDF dosyaları oluşturmanıza olanak tanır. Kullanıcı deneyimini geliştirmek için form doğrulama uygulayabilir, hesaplamalar yapabilir ve çeşitli etkileşim özellikleri ekleyebilirsiniz.