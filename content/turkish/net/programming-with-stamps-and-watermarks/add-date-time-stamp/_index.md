---
title: PDF Dosyasına Tarih Saat Damgası Ekle
linktitle: PDF Dosyasına Tarih Saat Damgası Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzla Aspose.PDF for .NET kullanarak PDF dosyalarınıza tarih ve saat damgası eklemeyi öğrenin. Belgenin gerçekliğini artırmak için mükemmeldir.
type: docs
weight: 10
url: /tr/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
## giriiş

Belgeleri, özellikle PDF'leri yönetmeye gelince, tarih ve saat damgası eklemek oyunun kurallarını değiştirebilir. İster yasal belgeler, ister proje raporları veya faturalar üzerinde çalışıyor olun, bir zaman damgası yalnızca özgünlük katmakla kalmaz, aynı zamanda belgenin ne zaman oluşturulduğuna veya değiştirildiğine dair net bir kayıt da sağlar. Bu kılavuzda, .NET için Aspose.PDF kitaplığını kullanarak bir PDF dosyasına tarih ve saat damgası ekleme sürecini adım adım anlatacağız. 

Bu makale anlaşılır ve takip etmesi kolay olacak şekilde tasarlanmıştır, bu nedenle programlamaya veya Aspose.PDF kütüphanesine yeni başlamış olsanız bile bu özelliği güvenle uygulayabilirsiniz. Hadi başlayalım!

## Ön koşullar

Başlamadan önce, yerine getirmeniz gereken birkaç ön koşul var:

1. Visual Studio: Makinenizde Visual Studio'nun yüklü olduğundan emin olun. Kodunuzu burada yazacak ve çalıştıracaksınız.
2. .NET için Aspose.PDF: Aspose.PDF kütüphanesini indirip yüklemeniz gerekir. En son sürümü bulabilirsiniz[Burada](https://releases.aspose.com/pdf/net/).
3. Temel C# Bilgisi: C# programlamaya aşina olmak örnekleri daha iyi anlamanıza yardımcı olacaktır, ancak yeni başlıyorsanız endişelenmeyin; her şeyi adım adım açıklayacağız.
4.  Bir PDF Dosyası: Hazır bir örnek PDF dosyanız olsun. Örneğimiz için, adlı bir dosya kullanacağız`AddTextStamp.pdf`.

Bu ön koşullara sahip olduğunuzda, PDF dosyalarınıza tarih ve saat damgaları eklemeye başlayabilirsiniz!

## Paketleri İçe Aktar

Başlamak için, C# projenize gerekli ad alanlarını içe aktarmanız gerekir. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

### Yeni Bir Proje Oluştur

1. Visual Studio'yu açın: Visual Studio uygulamanızı başlatın.
2. Yeni Proje Oluşturma: Başlangıç ekranından “Yeni proje oluştur” seçeneğini seçin.
3. Konsol Uygulamasını Seçin: Proje şablonları listesinden “Konsol Uygulaması (.NET Framework)” seçeneğini belirleyin.
4.  Projenize İsim Verin: Projenize bir isim verin, örneğin:`PDFDateTimeStamp`.

### Aspose.PDF Referansını Ekle

1. Referanslar’a sağ tıklayın: Çözüm Gezgini’nde projenizin “Referanslar” klasörüne sağ tıklayın.
2. “Referans Ekle”yi seçin: Bağlam menüsünden “Referans Ekle”yi seçin.
3. Aspose.PDF'yi arayın: Aspose.PDF'yi indirdiğiniz konuma gidin ve seçin. Projenize eklemek için "Tamam"a tıklayın.

### Gerekli Ad Alanlarını İçe Aktar

 En üstte`Program.cs` dosyanız varsa, aşağıdaki ad alanlarını içe aktarmanız gerekir:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Annotations;
```

Artık her şeyi ayarladığımıza göre, bir PDF dosyasına tarih ve saat damgası ekleme sürecini açık ve yönetilebilir adımlara bölelim.

## Adım 1: Belge Dizinini Ayarlayın

Öncelikle PDF dosyanızın bulunduğu dizini belirtmeniz gerekir. Bu önemlidir çünkü kod PDF'yi bu dizinde arayacaktır.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Gerçek yolunuzla değiştirin
```

 Değiştirdiğinizden emin olun`YOUR DOCUMENT DIRECTORY` PDF dosyanızın gerçek yolunu belirtin.

## Adım 2: PDF Belgesini açın

Daha sonra zaman damgasını eklemek istediğiniz PDF belgesini açacaksınız. 

```csharp
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 Bu kod satırı şunu başlatır:`Document` sınıfa yükleyin ve PDF dosyanızı yükleyin`pdfDocument` nesne.

## Adım 3: Tarih Saat Damgasını Oluşturun

Şimdi tarih ve saat damgasını oluşturma zamanı. Bunu belirli bir şekilde görüntülenecek şekilde biçimlendireceksiniz. 

```csharp
string annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");
```

 Burada,`DateTime.Now` geçerli tarih ve saati alır ve`ToString` istediğiniz formata dönüştürür.

## Adım 4: Bir Metin Damgası Oluşturun

Tarih ve saat dizesi hazır olduğuna göre artık PDF'nize eklenecek bir metin damgası oluşturabilirsiniz.

```csharp
// Metin damgası oluştur
TextStamp textStamp = new TextStamp(annotationText);
```

 Bu satır yeni bir örnek oluşturur`TextStamp` biçimlendirilmiş tarih ve saat dizesini kullanarak.

## Adım 5: Damganın Özelliklerini Ayarlayın

Damganın görünümünü ve konumunu özelleştirebilirsiniz. Özelliklerini ayarlama yöntemi şu şekildedir:

```csharp
// Damganın özelliklerini ayarla
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Bu adımda kenar boşluklarını ayarlıyoruz ve damgayı PDF sayfasının sağ alt köşesine hizalıyoruz.

## Adım 6: PDF'ye Damgayı Ekleyin

Artık PDF belgenize metin damgasını eklemenin zamanı geldi. 

```csharp
// Pul koleksiyonuna pul ekleme
pdfDocument.Pages[1].AddStamp(textStamp);
```

Bu satır, damgayı PDF'in ilk sayfasına ekler. Farklı bir sayfaya yerleştirmek isterseniz sayfa numarasını değiştirebilirsiniz.

## Adım 7: Ücretsiz Metin Açıklaması Oluşturun (İsteğe bağlı)

Damgaya bir açıklama eklemek istiyorsanız, bir`FreeTextAnnotation` aşağıdaki gibi:

```csharp
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;
```

Bu isteğe bağlı adım, pul hakkında ek bağlam veya bilgi sağlayabilen serbest metin açıklaması oluşturur.

## Adım 8: Açıklama Sınırını Yapılandırın

Eğer açıklamanızın kenarlığını özelleştirmek istiyorsanız bunu da yapabilirsiniz:

```csharp
Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

Bu kod parçacığı kenarlık genişliğini 0'a ayarlayarak görünmez hale getirir ve PDF'e açıklama ekler.

## Adım 9: PDF Belgesini Kaydedin

Son olarak değiştirdiğiniz PDF belgesini kaydetmeniz gerekiyor. 

```csharp
dataDir = dataDir + "AddDateTimeStamp_out.pdf"; // Çıktı dosya adını belirtin
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);
```

Bu satır eklenen zaman damgasıyla PDF'yi yeni bir dosyaya kaydeder. Çıktıyı görmek için belirtilen dizini kontrol edebilirsiniz.

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF dosyasına başarıyla tarih ve saat damgası eklediniz. Bu basit ama etkili özellik belgelerinizi geliştirebilir, onları daha profesyonel hale getirebilir ve ne zaman oluşturuldukları veya değiştirildikleri konusunda net bir kayıt sağlayabilir. 

## SSS

### Zaman damgasındaki tarih biçimini özelleştirebilir miyim?
 Evet, değiştirebilirsiniz`ToString`Tarih formatını kendi isteğinize göre değiştirme yöntemi.

### Aspose.PDF'i kullanmak ücretsiz mi?
 Aspose.PDF ücretsiz deneme sunuyor ancak tüm özellikler için bir lisans satın almanız gerekiyor. Geçici bir lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

### Bir PDF'e birden fazla zaman damgası ekleyebilir miyim?
 Kesinlikle! Birden fazla oluşturabilirsiniz`TextStamp` Örnekleri oluşturun ve bunları PDF'deki farklı sayfalara veya konumlara ekleyin.

### Ya Visual Studio'm yoksa?
Herhangi bir C# IDE'sini veya metin düzenleyicisini kullanabilirsiniz, ancak projenizi çalıştırmak ve hata ayıklamak için Visual Studio önerilir.

### Aspose.PDF kullanımına dair daha fazla örneği nerede bulabilirim?
 Daha fazla örnek ve öğreticiyi şu adreste inceleyebilirsiniz:[Aspose.PDF belgeleri](https://reference.aspose.com/pdf/net/).