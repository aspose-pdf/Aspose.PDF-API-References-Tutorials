---
title: PDF Dosyasında Metin Ve Resim Paragraf Olarak
linktitle: PDF Dosyasında Metin Ve Resim Paragraf Olarak
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak metin ve resimlerle PDF'ler oluşturun. Adım adım metin ve satır içi resimlerin nasıl ekleneceğini öğrenin.
type: docs
weight: 530
url: /tr/net/programming-with-text/text-and-image-as-paragraph/
---
## giriiş

Günümüzün dijital dünyasında, PDF'ler çoğumuzun günlük olarak karşılaştığı evrensel bir belge biçimidir. İster bir rapor, ister bir e-kitap veya bir işletme faturası olsun, PDF'ler çeşitli platformlar arasında bilgi paylaşımını kolaylaştırır. Peki ya bir PDF'yi programatik olarak özelleştirmek isterseniz? İşte tam bu noktada Aspose.PDF for .NET devreye girer. Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasına satır içi paragraflar olarak metin ve resim ekleme konusunda size rehberlik edeceğiz.

## Ön koşullar

Koda dalmadan önce, sorunsuz bir şekilde takip edebilmeniz için ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

-  Aspose.PDF for .NET Kütüphanesi: Aspose.PDF for .NET'i yüklemeniz gerekecek. İndirebilirsiniz[Burada](https://releases.aspose.com/pdf/net/).
- Visual Studio: .NET'i destekleyen herhangi bir sürüm sorunsuz çalışacaktır.
- C# ile İlgili Temel Bilgiler: C# ile ilgili bazı bilgilere sahip olmak faydalı olacaktır ancak endişelenmeyin; her adımda size yol göstereceğim!
- PDF Belgesi Hazır: Özel bir resim eklemek istiyorsanız, hazır bulundurun.

 Ayrıca kütüphanenin ücretsiz deneme sürümünü de alabilirsiniz[Burada](https://releases.aspose.com/) veya büyük ölçekli bir proje üzerinde çalışıyorsanız, satın almayı düşünün[Burada](https://purchase.aspose.com/buy) . Daha fazla ayrıntıya mı ihtiyacınız var? Belgelere göz atın[Burada](https://reference.aspose.com/pdf/net/).

## Paketleri İçe Aktar

.NET için Aspose.PDF'ye başlamak için gerekli ad alanlarını içe aktarmanız gerekir. Bu ad alanları, C# kodunuzun Aspose.PDF işlevleriyle etkileşime girmesini sağlar.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
using System;
```

Basit, değil mi? Şimdi eğlenceli kısma geçelim: Kendi PDF dosyanızı oluşturma.

## Adım Adım Kılavuz: Metin ve Satır İçi Resimli PDF Oluşturma

Bunu sindirilebilir, takip etmesi kolay adımlara bölelim. Bir bulmacayı birleştirdiğinizi düşünün; her adım doğru parçayı bulup yerleştirmek gibidir.

## Adım 1: PDF Belgesini Başlatın

İlk adım, Aspose.PDF kullanarak yeni bir PDF belgesi başlatmaktır. Bu belge, metin ve resim eklemek için temel görevi görecektir.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge örneğini örneklendir
Document doc = new Document();
```

 Burada neler oluyor? Biz sadece şunu kullanarak yeni bir belge oluşturuyoruz:`Document`sınıfını ve PDF'yi kaydetmek istediğiniz dizini tanımlayın. Bu, şaheseriniz için yeni bir tuval açmak gibi!

## Adım 2: PDF'nize Bir Sayfa Ekleyin

Sayfalar olmadan bir belgenin pek bir faydası olmaz, değil mi? Belgenize boş bir sayfa ekleyelim.

```csharp
// Belge örneğinin sayfalar koleksiyonuna sayfa ekle
Page page = doc.Pages.Add();
```

Bu kod parçacığı belgenizin sayfa koleksiyonuna yeni bir sayfa ekler. Bunu bir not defterinde boş bir sayfayı açmak gibi düşünün.

## Adım 3: Metni Paragraf Olarak Ekleyin

Sırada bir metin paragrafı ekleyeceğiz. Mesajınızı veya başlığınızı buraya ekleyebilirsiniz.

```csharp
// TextFragment Oluştur
TextFragment text = new TextFragment("Hello World.. ");
// Sayfa nesnesinin paragraf koleksiyonuna metin parçası ekle
page.Paragraphs.Add(text);
```

 Burada bir tane yaratıyoruz`TextFragment` "Merhaba Dünya.." metnini tutan nesne, daha sonra sayfaya bir paragraf olarak eklenir. PDF belgenizin ilk cümlesini yazmak gibidir.

## Adım 4: Bir Resmi Satır İçi Paragraf Olarak Ekleme

Artık metnimiz olduğuna göre, satır içi paragraf olarak bir resim ekleyerek işleri biraz renklendirelim. Satır içi paragraf, resmin metnin hemen ardından görüneceği anlamına gelir, tıpkı Word belgelerinde resimlerin görüntülendiği gibi.

```csharp
// Bir görüntü örneği oluşturun
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Resmi satır içi paragraf olarak ayarlayın, böylece hemen sonra görünür
// Önceki paragraf nesnesi (TextFragment)
image.IsInLineParagraph = true;
// Görüntü dosya yolunu belirtin
image.File = dataDir + "aspose-logo.jpg";
```

 Bu kod parçacığında bir tane oluşturuyoruz`Image` nesne, metinle aynı hizada hizalanmasını söyleyin ve resim dosyasının yolunu belirtin. Bu, bir belgedeki bir cümlenin hemen ardından bir resim yapıştırmakla eşdeğerdir. "aspose-logo.jpg"yi istediğiniz resimle değiştirebilirsiniz.

## Adım 5: Görüntü Boyutunu Ayarlayın (İsteğe bağlı)

Resmi yeniden boyutlandırmak mı istiyorsunuz? Sorun değil. Aspose.PDF, resmi belgenize eklemeden önce resmin yüksekliğini ve genişliğini ayarlama seçeneği sunar.

```csharp
// Resim Yüksekliğini Ayarla (isteğe bağlı)
image.FixHeight = 30;
// Resim Genişliğini Ayarla (isteğe bağlı)
image.FixWidth = 100;
```

Bu kısım isteğe bağlıdır, ancak PDF'nizde görüntünün ne kadar büyük veya küçük görüneceğini kontrol etmenize yardımcı olur. Bu, bir fotoğrafı yazdırmadan önce yeniden boyutlandırmaya benzer.

## Adım 6: Paragraf Koleksiyonuna Resim Ekleme

Resmi hazırladık. Şimdi onu satır içi paragraf olarak belgeye ekleyelim.

```csharp
// Sayfa nesnesinin paragraf koleksiyonuna resim ekle
page.Paragraphs.Add(image);
```

Bu satır, paragraf koleksiyonundaki metnin hemen sonrasına resmi ekler. Bir metin düzenleyicide "Resim Ekle" düğmesine basmak gibidir.

## Adım 7: Başka Bir Satır İçi Metin Paragrafı Ekleyin

Ya resmin hemen ardından daha fazla metin eklemek isterseniz? Bunu başka bir satır içi metin parçası ekleyerek yapalım.

```csharp
// TextFragment nesnesini farklı içeriklerle yeniden başlatın
text = new TextFragment(" Hello Again..");
// TextFragment'ı satır içi paragraf olarak ayarla
text.IsInLineParagraph = true;
// Yeni oluşturulan TextFragment'ı sayfanın paragraf koleksiyonuna ekle
page.Paragraphs.Add(text);
```

 Biz yeniden kullanıyoruz`TextFragment`nesneyi buraya yeni metinle ("Merhaba Tekrar..") ekleyin ve onu satır içi olarak, resmin hemen sonrasına yerleştirin. Bu, PDF'nize akıcı, tutarlı bir görünüm kazandırır.

## Adım 8: PDF Belgesini Kaydedin

Neredeyse bitti! Şimdi belgeyi belirttiğiniz dizine kaydedelim.

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as inline paragraphs.\nFile saved at " + dataDir);
```

Bu son adım dosyayı "TextAndImageAsParagraph_out.pdf" adıyla dizininize kaydeder. Tebrikler—hem metin hem de satır içi resimler içeren bir PDF oluşturdunuz!

## Çözüm

Ve işte karşınızda—Aspose.PDF for .NET kullanarak satır içi paragraflar halinde metin ve resimler içeren bir PDF oluşturmak bu adımları takip etmek kadar basit. Sadece birkaç satır kodla PDF dosyalarınıza dinamik içerik ekleyebilir, onları görsel olarak daha çekici ve profesyonel hale getirebilirsiniz. İster bir iş raporu ister bir e-Kitap olsun, PDF'lerinizin düzeni üzerinde kontrol sahibi olmak büyük fark yaratabilir.

## SSS

### Satır içi paragraflara birden fazla resim ekleyebilir miyim?  
 Evet, ayrı ayrı resimler oluşturarak birden fazla resim ekleyebilirsiniz.`Image` nesneleri ve paragraf koleksiyonuna ekleme.

### PDF'deki metnin ve görselin konumunu kontrol edebilir miyim?  
Evet, kenar boşlukları gibi özellikleri kullanarak metninizin ve görsellerinizin tam yerleşimini kontrol edebilirsiniz.

### Aspose.PDF for .NET ücretsiz mi?  
 Hayır, lisanslı bir ürün ama bir tane alabilirsiniz[ücretsiz deneme](https://releases.aspose.com/) veya bir lisans satın alın[Burada](https://purchase.aspose.com/buy).

### Metne köprü metni ekleyebilir miyim?  
 Evet, Aspose.PDF metin parçalarına köprüler eklemenize olanak tanır.[belgeleme](https://reference.aspose.com/pdf/net/) Daha detaylı bilgi için.

### Metnin yazı tipini ve stilini özelleştirebilir miyim?  
Kesinlikle! Metin parçalarının yazı tiplerini, renklerini ve diğer stil özelliklerini kolayca özelleştirebilirsiniz.