---
title: PDF Dosyasına Resim Damgası Ekle
linktitle: PDF Dosyasına Resim Damgası Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyalarına resim damgası eklemeyi adım adım kılavuz ve örnek kodlarla öğrenin.
type: docs
weight: 20
url: /tr/net/programming-with-stamps-and-watermarks/add-image-stamp/
---
## giriiş

PDF dosyalarını düzenlemeye gelince, çok az araç Aspose.PDF for .NET kadar sağlam ve kullanıcı dostudur. İster açıklamalar eklemek, ister formlar oluşturmak veya resimlere damga basmak isteyin, bu kitaplık çeşitli PDF düzenleme ihtiyaçlarını karşılamak için kapsamlı işlevsellik sağlar. Bu eğitimde, belirli bir göreve odaklanacağız: PDF dosyasına resim damgası eklemek. Bu sadece bir sayfaya resim yapıştırmakla ilgili değil; belgelerinizi markalama ve görsel çekicilikle geliştirmekle ilgilidir!

## Ön koşullar

Kodun ince ayrıntılarına dalmadan önce, ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım. İşte ihtiyaç duyacağınız şeyler:

1. Visual Studio veya herhangi bir .NET IDE: Kod parçacıklarını uygulamak için bir .NET geliştirme ortamına sahip olmanız gerekir.
2.  Aspose.PDF for .NET Kütüphanesi: Bu, kullanacağımız ana araçtır. Kütüphanenin en son sürümünü şu adresten indirebilirsiniz:[Aspose sürüm sayfası](https://releases.aspose.com/pdf/net/).
3. Temel C# Bilgisi: C# programlamaya dair temel bir anlayışa sahip olmak, kodda sorunsuz bir şekilde gezinmenize yardımcı olacaktır.
4. Bir Resim Dosyası: Damga olarak kullanmak istediğiniz bir resim dosyasına ihtiyacınız var. Desteklenen bir formatta olduğundan emin olun (JPEG, PNG, vb. gibi).
5. Mevcut PDF Dosyası: Resim damgasını ekleyeceğiniz örnek bir PDF dosyanız olsun.

Artık her şey tamam olduğuna göre kodlara geçebiliriz!

## Paketleri İçe Aktar

İlk önce ilk şeyler—herhangi bir şey yapmadan önce, gerekli ad alanlarını içe aktarmanız gerekir. C# kodunuzda, bunu dosyanızın en üstüne aşağıdaki using yönergesini ekleyerek yapabilirsiniz:

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using Aspose.Pdf.Text;
```

Bu, Aspose.PDF kütüphanesi tarafından sağlanan çeşitli sınıflara ve yöntemlere erişmenizi sağlayacaktır.

## Adım 1: Belge Dizininizi Ayarlayın

 İlk adım, belgelerinize giden yolu belirtmektir. Belgenizi ve resimleri iyi tanımlanmış bir dizinde saklamak isteyeceksiniz. Basitlik açısından, bir değişken bildirin`dataDir` bunun gibi:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` sisteminizdeki gerçek yol ile.

## Adım 2: PDF Belgesini açın

Sonra, değiştirmek istediğimiz PDF belgesini açmamız gerekiyor. Aspose.PDF'in parladığı yer burası! Sadece birkaç satır koda ihtiyacınız var:

```csharp
Document pdfDocument = new Document(dataDir + "AddImageStamp.pdf");
```

 Bu satır yeni bir satır oluşturur`Document`Belirtilen PDF dosyanızı yükleyerek nesneyi bulun. Dosyanın belirtilen dizinde bulunduğundan emin olun; aksi takdirde, dosya bulunamadı hatasıyla karşılaşırsınız!

## Adım 3: Görüntü Damgasını Oluşturun

Şimdi eğlenceli kısma geliyoruz: resim damgasını ekleme! İlk olarak, resim dosyanızı kullanarak bir resim damgası nesnesi oluşturmamız gerekiyor:

```csharp
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
```

 Bu satır bir`ImageStamp` Eklemek istediğiniz resmi temsil eden nesne. Resim dosya yolunuzun doğru olduğundan emin olmak çok önemlidir.

## Adım 4: Görüntü Damgası Özelliklerini Yapılandırın

Burada yaratıcı olabilir ve damganızı özelleştirebilirsiniz. Konum, boyut, dönüş ve opaklık gibi özellikleri ayarlayabilirsiniz. İşte bunu nasıl yapacağınıza dair bir örnek:

```csharp
imageStamp.Background = true; // Damganın arka planda olmasını istiyorsanız doğru olarak ayarlayın
imageStamp.XIndent = 100; // Soldan pozisyon
imageStamp.YIndent = 100; // Üstten pozisyon
imageStamp.Height = 300; // Pulun yüksekliğini ayarlayın
imageStamp.Width = 300; // Pulun genişliğini ayarlayın
imageStamp.Rotate = Rotation.on270; // Gerekirse döndürün
imageStamp.Opacity = 0.5; // Opaklığı ayarla
```

Bu değerleri ihtiyaçlarınıza göre ayarlamakta özgürsünüz! Bu özelleştirme, damganızı tam olarak istediğiniz yere yerleştirmenizi sağlar.

## Adım 5: Damgayı Belirli Bir Sayfaya Ekleyin

Artık damgamızı yapılandırdığımıza göre, bir sonraki adım onu PDF belgesinde nereye yerleştirmek istediğimizi belirtmektir. Bu örnekte, onu ilk sayfaya ekleyeceğiz:

```csharp
pdfDocument.Pages[1].AddStamp(imageStamp);
```

Bu kod parçacığı Aspose'a damgayı belgenin ilk sayfasına eklemesini söyler.

## Adım 6: Belgeyi Kaydedin

Damga uygulandıktan sonra, değişikliklerinizi kaydetme zamanı geldi. Çıktı PDF dosyası için bir yol belirtmeniz gerekiyor:

```csharp
dataDir = dataDir + "AddImageStamp_out.pdf";
pdfDocument.Save(dataDir);
```

Belgeniz artık yeni resim damgası uygulanarak kaydedildi!

## Adım 7: Değişikliği Onaylayın

Son olarak, işleminizin başarılı olduğunu onaylamak her zaman iyidir. Bunu basit bir Konsol mesajıyla yapabilirsiniz:

```csharp
Console.WriteLine("\nImage stamp added successfully.\nFile saved at " + dataDir);
```

Bu mesaj, resim damgasının eklendiğini bildirecek ve yeni düzenlenmiş PDF'nizi nerede bulabileceğinizi bildirecektir.

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF'e resim damgası eklediniz. İlk başta karmaşık görünebilir, ancak biraz pratik yaparak PDF belgelerinizi sayısız şekilde özelleştirebilirsiniz. Buradaki anahtar nokta, Aspose'un sunduğu çeşitli özelliklerle denemeler yapmaktır; sınır hayal gücünüzdür.

## SSS

### Aspose.PDF for .NET'i kullanmak ücretsiz mi?  
 Aspose.PDF ücretsiz deneme sunar, ancak deneme süresinden sonra devam eden kullanım için bir lisans gereklidir. Şuraya göz atabilirsiniz:[fiyatlandırma seçenekleri burada](https://purchase.aspose.com/buy).

### Tek bir PDF'e birden fazla pul ekleyebilir miyim?  
 Kesinlikle! Birden fazla oluşturabilirsiniz`ImageStamp` nesneleri seçip PDF'deki herhangi bir sayfaya ekleyebilirsiniz.

### Pullar için hangi resim formatları destekleniyor?  
Aspose.PDF, JPEG, PNG ve BMP dahil olmak üzere çeşitli resim formatlarını destekler.

### Bir resim damgasını nasıl döndürebilirim?  
 Ayarlayabilirsiniz`Rotate` mülkiyeti`ImageStamp` nesneyi istenilen açıda döndürmek için. Seçenekler şunlardır`Rotation.on90`, `Rotation.on180`, vesaire.

### Aspose.PDF hakkında daha fazla dokümanı nerede bulabilirim?  
 Tam API referansını ve belgelerini inceleyebilirsiniz[Burada](https://reference.aspose.com/pdf/net/).