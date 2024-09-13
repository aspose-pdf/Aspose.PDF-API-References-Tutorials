---
title: PDF Sayfa Boyutlarını Alın
linktitle: PDF Sayfa Boyutlarını Alın
second_title: Aspose.PDF for .NET API Referansı
description: Bu eğitimde, .NET için Aspose.PDF kullanarak PDF sayfa boyutlarının nasıl alınacağını ve düzenlemelerin nasıl yapılacağını açıklıyoruz. İşlem boyunca size rehberlik etmek için ayrıntılı adımlar sağlanmıştır.
type: docs
weight: 60
url: /tr/net/programming-with-pdf-pages/get-dimensions/
---
## giriiş

Hiç bir PDF belgesinin sayfa boyutlarını değiştirmeniz gerekti mi? Belki de bir sayfayı ihtiyaçlarınıza uyacak şekilde yeniden boyutlandırmak veya döndürmek istediniz? Öyleyse, doğru yerdesiniz! Bu eğitimde, .NET için Aspose.PDF kullanarak PDF sayfa boyutlarını alma ve değiştirme konusunda size yol göstereceğiz. İster yeni başlayan ister deneyimli bir geliştirici olun, bu kılavuzu basit ve takip etmesi kolay bulacaksınız.

Aspose.PDF for .NET, PDF dosyalarını zahmetsizce oluşturmanıza, düzenlemenize ve dönüştürmenize olanak tanıyan güçlü bir kütüphanedir. PDF'ler için bir İsviçre çakısı gibidir - her küçük ayrıntıyı tam gereksinimlerinize uyacak şekilde ayarlayabilirsiniz. O halde hemen başlayalım ve bu harika aracı kullanarak PDF sayfa boyutlarını nasıl alacağınızı ve güncelleyeceğinizi öğrenelim!

## Ön koşullar

Başlamadan önce, bu eğitimi sorunsuz bir şekilde takip edebilmek için birkaç şeye ihtiyacınız olacak:

1.  .NET için Aspose.PDF: Şunları yapabilirsiniz[en son sürümü buradan indirin](https://releases.aspose.com/pdf/net/) . Eğer bir lisansınız yoksa endişelenmeyin! Bir lisans talebinde bulunabilirsiniz.[ücretsiz deneme](https://releases.aspose.com/) veya birini seçin[geçici lisans](https://purchase.aspose.com/temporary-license/).
2. Visual Studio: Kod yazmak ve çalıştırmak için kullanacağınız geliştirme ortamı.
3. Temel C# bilgisi: İşleri basit tutacağız ancak C# konusunda biraz bilgi sahibi olmak süreci daha akıcı hale getirecektir.
4. Üzerinde çalışılacak PDF dosyası: Herhangi bir örnek PDF dosyasını alın veya test etmek için yeni bir dosya oluşturun.

## Paketleri İçe Aktar

Aspose.PDF for .NET ile çalışmak için birkaç temel ad alanını içe aktarmanız gerekir. Bu, PDF belgeleriyle etkileşime girmek için ortamı hazırlar. İşte nasıl yapılacağı:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Bu içe aktarımlar, özellikle sayfaları yönetmek ve boyutlarını almak için PDF dosyalarını yönetmek için gereken temel sınıflara erişiminizin olmasını sağlar.

Artık her şey yerli yerinde olduğuna göre, süreci takip etmesi kolay adımlara bölelim.

## Adım 1: Dosya Yolunu Tanımlayın ve Belgeyi Yükleyin

İlk adım, PDF belgenizin yolunu belirtmek ve Aspose.PDF kullanarak yüklemektir. Bu, PDF dosyasındaki sayfalarla etkileşime girmenizi sağlayacaktır.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

Bu adımda, esasen üzerinde çalışmak istediğiniz PDF dosyasını açıyorsunuz. Daha önce bir kitabı belirli bir sayfaya açtıysanız, bu oldukça benzerdir - ancak bunun yerine, sayfalarına erişmek için bir PDF belgesi açıyorsunuz.

## Adım 2: Sayfa yoksa boş bir sayfa ekleyin

Belgenizde sayfa yoksa ne olacak? Endişelenmeyin! Belgeye boş bir sayfa ekleyebilir ve üzerinde çalışabiliriz. Bir sayfanın olup olmadığını kontrol etmenin ve gerekirse yeni bir sayfa eklemenin yolu:

```csharp
// PDF belgesine boş bir sayfa ekler
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

Bu kod satırı belgede zaten bir sayfa olup olmadığını kontrol eder. Eğer varsa, ilk sayfayı seçer (`Pages[1]`). Aksi takdirde boş bir sayfa oluşturur ve bunu PDF'e ekler.

Bunu, boş bir defteri açıp, hiçbir şey yoksa ilk sayfasına bir şeyler yazmak gibi düşünün. Kolay, değil mi?

## Adım 3: Sayfa Yüksekliği ve Genişliği Bilgilerini Alın

 Artık üzerinde çalışacağımız bir sayfamız olduğuna göre, sayfanın boyutlarını alalım.`GetPageRect()` Yükseklik ve genişliği alma yöntemi.

```csharp
// Sayfa yüksekliği ve genişlik bilgilerini al
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

 Burada,`GetPageRect(true)` sayfanın yüksekliğini ve genişliğini içeren bir dikdörtgen döndürür. Bir kağıt parçasını cetvelle ölçmek gibidir. Çıktı konsolda görüntülenecek ve size geçerli sayfa boyutlarını verecektir.

## Adım 4: Sayfayı 90 Derece Döndürün

Sayfayı döndürmek mi istiyorsunuz? Sorun değil! Basit bir özellik ile sayfayı 90 derece döndürebilirsiniz.

```csharp
// Sayfayı 90 derecelik açıyla döndür
page.Rotate = Rotation.on90;
```

Bu adım sayfayı saat yönünde 90 derece döndürür. Masanızda basılı bir sayfayı çevirdiğinizi hayal edin - şimdi yatay modda!

## Adım 5: Döndürme Sonrası Sayfa Boyutlarını Tekrar Kontrol Edin

Sayfayı döndürdükten sonra boyutları tekrar kontrol etmek iyi bir fikirdir. Neden? Çünkü döndürme, yüksekliği ve genişliği nasıl yorumladığınızı etkileyebilir.

```csharp
// Sayfa yüksekliği ve genişlik bilgilerini al
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

Şimdi, sayfa boyutları yeni yönelime göre güncellenecek. Telefonunuzda bir fotoğrafı döndürmek gibi - aniden genişlik yükseklik olur ve tam tersi.


## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF sayfasının boyutlarını nasıl alacağınızı ve değiştireceğinizi başarıyla öğrendiniz. Artık bir PDF yükleyebilmeli, sayfa boyutlarını kontrol edebilmeli ve gerekirse sayfayı döndürebilmelisiniz.

PDF'leri düzenlemek karmaşık olmak zorunda değil. Aspose.PDF ile, birkaç adımı takip etmek ve sezgisel yöntemler kullanmak kadar basit. Yani bir dahaki sefere PDF sayfa boyutlarını düzenlemeniz gerektiğinde, tam olarak ne yapmanız gerektiğini bileceksiniz!

## SSS

### Sayfayı 90 derece dışında başka açılarla döndürebilir miyim?
 Evet, Aspose.PDF sayfaları 0, 90, 180 veya 270 derece döndürmenize olanak tanır.`Rotation` mülk.

### PDF dosyamın sayfası yoksa ne olur?
 PDF'nizde sayfa yoksa, boş bir sayfa ekleyebilirsiniz.`Pages.Add()` Bu eğitimde gösterildiği gibi bir yöntem.

### Birden fazla sayfayı aynı anda düzenleyebilir miyim?
Evet, birden fazla sayfada dolaşabilir ve hepsine yeniden boyutlandırma veya döndürme gibi dönüşümler uygulayabilirsiniz.

### Sayfa boyutları PDF'in içindeki içeriği etkiler mi?
Sayfa boyutları yalnızca tuvalin boyutunu değiştirir, içeriği değiştirmez. Ancak yeniden boyutlandırma, içeriğin sayfada nasıl göründüğünü değiştirebilir.

### Aspose.PDF for .NET hakkında daha fazla bilgiyi nerede bulabilirim?
 Ziyaret edebilirsiniz[belgeler burada](https://reference.aspose.com/pdf/net/) Daha detaylı bilgi ve gelişmiş kullanım örnekleri için.