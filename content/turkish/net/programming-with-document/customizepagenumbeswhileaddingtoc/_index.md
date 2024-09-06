---
title: İçindekiler Tablosu Eklenirken Sayfa Numaralarını Özelleştir
linktitle: İçindekiler Tablosu Eklenirken Sayfa Numaralarını Özelleştir
second_title: Aspose.PDF for .NET API Referansı
description: Bu kapsamlı eğitimde Aspose.PDF for .NET kullanarak PDF belgelerinize İçindekiler Tablosu eklerken sayfa numaralarını nasıl özelleştireceğinizi öğrenin.
type: docs
weight: 100
url: /tr/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
## giriiş

Belge yönetimi dünyasında PDF'ler en üst sıradadır. Çeşitli platformlarda belgeleri paylaşmak ve korumak için başvurulan formattır. Peki PDF belgelerinizi İçindekiler Tablosu (TOC) gibi özelliklerle geliştirmek istediğinizde ne olur? İşte tam bu noktada Aspose.PDF for .NET devreye giriyor! Bu güçlü kütüphane, geliştiricilerin PDF dosyalarını kolaylıkla düzenlemelerine olanak tanır ve içerikleri zahmetsizce eklemelerini, değiştirmelerini ve özelleştirmelerini sağlar. Bu eğitimde, Aspose.PDF for .NET kullanarak PDF belgelerinize bir TOC eklerken sayfa numaralarını nasıl özelleştireceğinizi derinlemesine inceleyeceğiz. O halde kodlama şapkanızı alın ve başlayalım!

## Ön koşullar

Koda geçmeden önce, yerinde olması gereken birkaç şey var:

1. Visual Studio: Makinenizde Visual Studio'nun yüklü olduğundan emin olun. Bu bizim geliştirme ortamımız olacak.
2. .NET için Aspose.PDF: Aspose.PDF kütüphanesini indirip yüklemeniz gerekir. Bunu bulabilirsiniz[Burada](https://releases.aspose.com/pdf/net/).
3. Temel C# Bilgisi: C# programlamaya aşina olmak, kod parçacıklarını daha iyi anlamanıza yardımcı olacaktır.
4. Örnek PDF Dosyası: Üzerinde çalışabileceğimiz hazır bir örnek PDF dosyanız olsun. Basit bir tane oluşturabilir veya mevcut bir PDF'yi indirebilirsiniz.

## Paketleri İçe Aktar

Başlamak için gerekli paketleri içe aktarmamız gerekiyor. Visual Studio projenizi açın ve Aspose.PDF kütüphanesine bir referans ekleyin. Bunu NuGet Paket Yöneticisi'ni kullanarak yapabilirsiniz:

1. Çözüm Gezgini’nde projenizin üzerine sağ tıklayın.
2. "NuGet Paketlerini Yönet" seçeneğini seçin.
3. "Aspose.PDF" dosyasını arayın ve yükleyin.

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Kütüphaneyi kurduktan sonra kodlamaya başlayabilirsiniz!

## Adım 1: Belge Dizininizi Ayarlayın

İlk önce, belge dizinimizi ayarlamamız gerekiyor. Giriş ve çıkış PDF dosyalarımızı burada saklayacağız. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
```

Bu kod parçacığında şunu değiştirin:`YOUR DOCUMENT DIRECTORY` PDF dosyalarınızın bulunduğu gerçek yol ile. Bu, mevcut PDF'yi yüklememize ve değiştirilmiş sürümü kaydetmemize yardımcı olacaktır.

## Adım 2: Mevcut PDF Dosyasını Yükleyin

Artık belge dizinimizi ayarladığımıza göre, mevcut PDF dosyasını yükleyelim. 

```csharp
Document doc = new Document(inFile);
```

 Burada yeni bir tane yaratıyoruz`Document` Giriş dosya yolunu geçirerek nesne. Bu, PDF içeriğini programatik olarak düzenlememize olanak tanır.

## Adım 3: İçindekiler için Yeni Bir Sayfa Ekleyin

Daha sonra PDF'imizde İçindekiler bölümünün bulunacağı yeni bir sayfa oluşturmamız gerekiyor.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

Bu satır belgenin başına yeni bir sayfa ekler. İçindekiler bu sayfada görüntülenecektir.

## Adım 4: İçindekiler Bilgilerini Oluşturun

Şimdi TOC bilgisini temsil edecek bir nesne oluşturalım.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

 Bu adımda bir tane oluşturuyoruz`TocInfo` nesneyi seçin ve başlığını "İçindekiler" olarak ayarlayın. Ayrıca yazı tipi boyutunu ve stilini de özelleştiriyoruz.`PageNumbersPrefix` İçindekiler tablosundaki sayfa numaralarının önüne "P" gelecek şekilde ayarlanmıştır.

## Adım 5: İçindekiler Tablosuna Başlıklar Ekleyin

Şimdi eğlenceli kısma geliyoruz! Belgenin sayfaları arasında dolaşacağız ve İçindekiler'imize başlıklar ekleyeceğiz.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    heading2.DestinationPage = doc.Pages[i + 1];
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    segment2.Text = "Page " + i.ToString();
    tocPage.Paragraphs.Add(heading2);
}
```

 Bu döngüde yeni bir tane oluşturuyoruz`Heading` her sayfa için nesne. Her başlık için hedef sayfayı ayarlıyoruz ve görüntülenecek metni belirliyoruz, bu da "Sayfa X"tir, burada X sayfa numarasıdır. Son olarak, başlığı TOC sayfasına ekliyoruz.

## Adım 6: Güncellenen Belgeyi Kaydedin

Gerekli tüm başlıkları ekledikten sonra güncellenmiş dokümanımızı kaydetme zamanı geldi.

```csharp
doc.Save(outFile);
```

Bu satır, TOC'yi içeren değiştirilmiş PDF'yi kaydeder. Artık çıktı dosyasını açabilir ve kişiselleştirilmiş İçindekiler Tablonuzu görebilirsiniz!

## Çözüm

Ve işte karşınızda! Aspose.PDF for .NET kullanarak PDF belgenize İçindekiler Tablosu eklerken sayfa numaralarını başarıyla özelleştirdiniz. Bu güçlü kütüphane PDF dosyalarını düzenlemeyi kolaylaştırır ve sadece birkaç satır kodla belgelerinizi önemli ölçüde geliştirebilirsiniz. İster raporlar, ister e-Kitaplar veya başka bir PDF türü oluşturun, bir İçindekiler Tablosuna sahip olmak okuyucularınız için gezinmeyi büyük ölçüde iyileştirebilir. Öyleyse, daha ne bekliyorsunuz? Aspose.PDF'e dalın ve bugün harika PDF'ler oluşturmaya başlayın!

## SSS

### Aspose.PDF for .NET nedir?
Aspose.PDF for .NET, geliştiricilerin PDF belgelerini programlı bir şekilde oluşturmalarına, düzenlemelerine ve dönüştürmelerine olanak tanıyan bir kütüphanedir.

### Aspose.PDF'yi ücretsiz kullanabilir miyim?
 Evet, Aspose kütüphanenin özelliklerini keşfetmeniz için kullanabileceğiniz ücretsiz bir deneme sürümü sunuyor. İndirebilirsiniz[Burada](https://releases.aspose.com/).

### Aspose.PDF için nasıl destek alabilirim?
 Aspose forumunu ziyaret ederek destek alabilirsiniz[Burada](https://forum.aspose.com/c/pdf/10).

### Geçici lisans var mı?
 Evet, Aspose.PDF için geçici bir lisans talep edebilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

### Aspose.PDF for .NET'i nereden satın alabilirim?
 .NET için Aspose.PDF'yi satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).