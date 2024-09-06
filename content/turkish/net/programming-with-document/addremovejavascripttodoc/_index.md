---
title: PDF Belgesine Javascript Ekle Kaldır
linktitle: Belgeye Javascript Ekle Kaldır
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF belgesine JavaScript eklemeyi ve kaldırmayı öğrenin. Belge düzeyinde komut dosyası oluşturma için kod eğitimleriyle adım adım kılavuz.
type: docs
weight: 30
url: /tr/net/programming-with-document/addremovejavascripttodoc/
---
## giriiş

Bu kılavuzda, JavaScript'i bir PDF dosyasına eklemek ve gerektiğinde kaldırmak için Aspose.PDF for .NET'in nasıl kullanılacağını ele alacağız. Bu eğitimin sonunda, JavaScript'i PDF'lerde zahmetsizce nasıl işleyebileceğinizi net bir şekilde anlayacaksınız.

## Ön koşullar

Koda dalmadan önce, ayarlamanız gereken birkaç şey var:

1.  .NET için Aspose.PDF: Projenizde .NET için Aspose.PDF kütüphanesinin yüklü olması gerekir. Eğer henüz yoksa, kütüphaneyi şuradan edinin:[Aspose.PDF for .NET indirme sayfası](https://releases.aspose.com/pdf/net/).
2. IDE veya Metin Düzenleyici: Visual Studio gibi herhangi bir .NET uyumlu IDE'yi kullanabilirsiniz.
3. Temel C# Bilgisi: Bu eğitimde C# konusunda rahat olduğunuzu ve PDF düzenleme konusunda bilginiz olduğunu varsayıyoruz.
4. Lisans: Sınırlamalardan kaçınmak için geçerli bir lisans uyguladığınızdan emin olun. Geçici bir lisansı şu adresten alabilirsiniz:[Burada](https://purchase.aspose.com/temporary-license/).

## Paketleri İçe Aktar

Aspose.PDF for .NET'i kullanmaya başlamak için, gerekli ad alanlarını projenize aktarmanız gerekir. İşte nasıl:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.Collections;
```

 Bu iki isim alanı önemlidir.`Aspose.Pdf` PDF belgeleriyle çalışmanıza olanak tanırken,`System.Collections` JavaScript anahtarlarının işlenmesinde kullanılacaktır.

PDF'e JavaScript ekleme ve kaldırma sürecini kolay takip edilebilir adımlara bölelim.

## Adım 1: Yeni bir PDF Belgesi Başlatın

Yapmanız gereken ilk şey yeni bir PDF belgesi oluşturmaktır. Bu belge JavaScript eklemek için boş tuvalimiz olarak hizmet edecektir.

```csharp
Document doc = new Document();
doc.Pages.Add();
```

 Burada yeni bir tane başlatıyoruz`Document` nesne ve ona boş bir sayfa eklemek. Bunu PDF'nizin temeli olarak düşünün.

## Adım 2: PDF'ye JavaScript ekleyin

Artık bir belgemiz olduğuna göre, ona biraz JavaScript eklemenin zamanı geldi. PDF'lerdeki JavaScript, uyarılar veya form doğrulaması gibi özel davranışlar eklemek için kullanılabilir.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
```

Bu kod parçacığında iki JavaScript fonksiyonu ekliyoruz (`func1` Ve`func2` ) PDF'ye. Bu işlevler ihtiyaçlarınıza bağlı olarak çeşitli görevler gerçekleştirebilir. Burada, yalnızca bir yer tutucu işlevi çağırıyoruz`hello()`.

## Adım 3: PDF'yi JavaScript ile kaydedin

İstediğiniz JavaScript'i ekledikten sonra PDF'i kaydetme zamanı geldi.

```csharp
doc.Save(dataDir + "AddJavascript.pdf");
```

 Bu, belgeyi JavaScript ile şu ad altında kaydedecektir:`AddJavascript.pdf` belirtilen dizinde (`dataDir`).

## Adım 4: Mevcut PDF'de JavaScript'i Yükleyin ve Görüntüleyin

Diyelim ki mevcut bir PDF içindeki JavaScript işlevlerini kontrol etmeniz veya değiştirmeniz gerekiyor. İlk adım PDF dosyasını yüklemek ve JavaScript anahtarlarına erişmektir.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
```

 Mevcut olanı yüklüyoruz`AddJavascript.pdf` ve JavaScript anahtarlarını bir listede depolamak.`Keys` property, belgeye eklenmiş tüm JavaScript fonksiyonlarının adlarını döndürür.

## Adım 5: JavaScript Fonksiyonlarını Görüntüle

Daha sonra, belgede nelerin mevcut olduğunu görmek için JavaScript fonksiyonlarını inceleyebiliriz.

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
```

Bu, her JavaScript fonksiyon adını ve karşılık gelen kodunu konsola yazdıracaktır. Belgede şu anda hangi fonksiyonların olduğunu doğrulamak istiyorsanız kullanışlıdır.

## Adım 6: PDF'den JavaScript'i kaldırın

 Şimdi, örneğin belirli bir JavaScript işlevini kaldırmak istediğinizi varsayalım.`func1`Bunu nasıl yapabileceğinizi anlatalım:

```csharp
doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
```

 The`Remove` method, JavaScript fonksiyonunun adını argüman olarak alır ve onu belgeden siler.

## Adım 7: JavaScript Kaldırmayı Doğrulayın

 JavaScript'i kaldırdıktan sonra, kalan işlevleri doğrulamak için yeniden yazdırabilirsiniz.`func1` Başarıyla silindi.

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
Console.WriteLine("Javascript added/removed successfully.");
```

Kodun bu son kısmı her şeyin yerli yerinde olmasını ve JavaScript fonksiyonlarının doğru şekilde güncellenmesini sağlar.

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesine JavaScript eklemeyi ve kaldırmayı öğrendiniz. Bu güçlü özellik, dinamik mesajlar eklemekten özel hesaplamalar veya doğrulamalar yapmaya kadar çeşitli görevler için kullanılabilir. Bir PDF içindeki JavaScript'i düzenleyerek kullanıcı deneyimini önemli ölçüde iyileştirebilirsiniz.

## SSS

### Tek bir PDF'e birden fazla JavaScript fonksiyonu ekleyebilir miyim?
 Kesinlikle! İhtiyacınız olan kadar JavaScript işlevi ekleyebilirsiniz.`doc.JavaScript` koleksiyon.

### Varolmayan bir JavaScript fonksiyonunu kaldırmaya çalışırsam ne olur?
 Eğer fonksiyon mevcut değilse,`Remove` Bu yöntem bir hata vermez ama aynı zamanda hiçbir şeyi de kaldırmaz.

### PDF açılır açılmaz JavaScript'i çalıştırmak mümkün müdür?
Evet! JavaScript'i, belgeyi açmak veya bir düğmeye tıklamak gibi belirli tetikleyicilerde çalışacak şekilde yapılandırabilirsiniz.

### JavaScript'i PDF'e ekledikten sonra düzenleyebilir miyim?
Evet, mevcut bir PDF'yi yükleyebilir, JavaScript'ine erişebilir, kodu değiştirebilir ve belgeyi tekrar kaydedebilirsiniz.

### JavaScript'i kaldırmak PDF içeriğinin geri kalanını etkiler mi?
Hayır, JavaScript'i kaldırmak yalnızca betiği etkiler. PDF'in içeriği değişmeden kalır.