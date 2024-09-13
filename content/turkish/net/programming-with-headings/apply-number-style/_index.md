---
title: PDF Dosyasına Sayı Stili Uygula
linktitle: PDF Dosyasına Sayı Stili Uygula
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzla Aspose.PDF for .NET'i kullanarak bir PDF'deki başlıklara farklı sayı stilleri (Romen rakamları, alfabetik) uygulamayı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-headings/apply-number-style/
---
## giriiş

PDF belgelerinize güzel numaralandırılmış listeler ekleme ihtiyacı hissettiniz mi hiç? İster yasal belgeleri, ister raporları veya sunumları biçimlendiriyor olun, bilgileri düzenlemek için doğru numaralandırma stilleri olmazsa olmazdır. Aspose.PDF for .NET ile PDF dosyanızın başlıklarına çeşitli numaralandırma stilleri uygulayabilir, iyi yapılandırılmış ve profesyonel belgeler oluşturabilirsiniz. 

## Ön koşullar

Kodlamaya başlamadan önce, neye ihtiyacınız olacağına bir bakalım:

1. .NET için Aspose.PDF: Aspose.PDF'in en son sürümünü şu adresten indirin:[Burada](https://releases.aspose.com/pdf/net/).
2. Geliştirme Ortamı: Visual Studio veya herhangi bir .NET uyumlu IDE'ye sahip olduğunuzdan emin olun.
3. .NET Framework: .NET Framework 4.0 veya üzeri sürümün yüklü olduğundan emin olun.
4.  Lisans: Geçici bir lisans kullanabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/) veya keşfedin[ücretsiz deneme](https://releases.aspose.com/) seçenekler.

## Paketleri İçe Aktar

Başlamak için projenize aşağıdaki ad alanlarının aktarıldığından emin olun:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Adım 1: Belgeyi Ayarlama

Yeni bir PDF belgesi oluşturarak ve sayfa ayarlarını yapılandırarak başlayalım. İçeriğimizin düzenini kontrol etmek için sayfa boyutunu ve kenar boşluklarını ayarlayacağız.

Açıklama: Bu adımda, tutarlı biçimlendirme için sayfa boyutunu, yüksekliğini ve kenar boşluklarını tanımlamayı içeren PDF'nin temel yapısını kuruyoruz.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

// Sayfa boyutlarını ve kenar boşluklarını ayarlayın
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

Bunu yaptığınızda, belgeniz 8,5 x 11 inçlik bir sayfaya eşdeğer standart bir sayfa boyutuna ve her tarafta 72 puntoluk (veya 1 inçlik) bir kenar boşluğuna sahip olacaktır.

## Adım 2: PDF'ye Sayfa Ekleme

Daha sonra PDF belgesine numaralandırma stillerini uygulayacağımız yeni bir sayfa ekleyeceğiz.

Açıklama: Her PDF'in sayfalara ihtiyacı vardır! Bu adım PDF'e boş bir sayfa ekler ve kenar boşluklarını belge düzeyindeki ayarlarla eşleşecek şekilde ayarlar.

```csharp
// PDF belgesine yeni bir sayfa ekleyin
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
```

## Adım 3: Yüzen Kutu Oluşturun

Bir FloatingBox, içeriği (metin veya başlıklar gibi) sayfanın akışından bağımsız davranan bir kutunun içine yerleştirmenize olanak tanır. Bu, içeriğinizin düzeni üzerinde tam kontrole sahip olmak istediğinizde faydalıdır.

Açıklama: Burada, sayı stilleri uygulanacak başlıkları içerecek bir FloatingBox ayarlıyoruz.

```csharp
// Yapılandırılmış içerik için bir FloatingBox oluşturun
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

## Adım 4: İlk Başlığı Roma Rakamlarıyla Ekleyin

Şimdi heyecan verici kısma geliyoruz! İlk başlığı küçük harfli Roma rakamlarıyla ekleyelim.

Açıklama: Başlığa NumberingStyle.NumeralsRomanLowercase stilini uyguluyoruz. Bu stil numaralandırmayı Roma rakamlarıyla (i, ii, iii, vb.) görüntüleyecektir.

```csharp
// İlk başlığı Roma rakamlarıyla oluşturun
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
```

## Adım 5: İkinci Bir Roma Rakamı Başlığı Ekleyin

Örnek amaçlı olarak ikinci bir Roma rakamı başlığı ekleyelim, ancak bu sefer 13'ten başlayalım.

Açıklama: StartNumber özelliği numaralandırmaya özel bir sayıdan başlamanızı sağlar; bu durumda 13'ten başlıyoruz.

```csharp
// Roma rakamı 13'ten başlayarak ikinci bir başlık oluşturun
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
```

## Adım 6: Alfabetik Numaralandırma ile Başlık Ekleyin

Çeşitlilik olsun diye üçüncü bir başlık ekleyelim; ancak bu sefer küçük harflerle alfabetik numaralandırma kullanalım (a, b, c, vb.).

Açıklama: NumberingStyle'ı LettersLowercase olarak değiştirmek, başlıklarımıza alfabetik numaralandırma uygulamamızı sağlar.

```csharp
// Alfabetik numaralandırma ile bir başlık oluşturun
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan on account of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

## Adım 7: PDF'yi kaydetme

Son olarak tüm başlık ve numaralandırma stillerini uyguladıktan sonra PDF dosyasını istediğiniz dizine kaydedelim.

Açıklama: Bu adım, tüm biçimlendirilmiş başlıkları içeren PDF dosyasını uygulanan numaralandırma stilleriyle kaydeder.

```csharp
// PDF belgesini kaydedin
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);
```

## Çözüm

İşte karşınızda! Aspose.PDF for .NET kullanarak bir PDF dosyasındaki başlıklara numaralandırma stilleri (Romen rakamları ve alfabetik) başarıyla uyguladınız. Aspose.PDF'nin sayfa düzenini, numaralandırma stillerini ve içerik konumlandırmasını kontrol etmek için sağladığı esneklik, iyi organize edilmiş, profesyonel PDF belgeleri oluşturmanız için güçlü bir araç seti sunar.

## SSS

### Aynı PDF belgesine farklı numara stilleri uygulayabilir miyim?  
Evet, Aspose.PDF for .NET, aynı belge içerisinde Roma rakamları, Arap rakamları ve alfabetik numaralandırma gibi farklı numaralandırma stillerini karıştırmanıza olanak tanır.

### Başlıkların başlangıç numarasını nasıl özelleştirebilirim?  
 Herhangi bir başlık için başlangıç numarasını, kullanarak ayarlayabilirsiniz.`StartNumber` mülk.

### Numaralandırma sırasını sıfırlamanın bir yolu var mı?  
Evet, numaralandırmayı ayarlayarak sıfırlayabilirsiniz.`StartNumber` Her başlık için özellik.

### Numaralandırmaya ek olarak başlıklara kalın veya italik stili uygulayabilir miyim?  
 Kesinlikle! Yazı tipi, boyut, kalın ve italik gibi özellikleri değiştirerek başlık stillerini özelleştirebilirsiniz.`TextState` nesne.

### Aspose.PDF için geçici lisansı nasıl alabilirim?  
 Geçici lisansı şuradan alabilirsiniz:[Burada](https://purchase.aspose.com/temporary-license/) Aspose.PDF'yi kısıtlama olmaksızın test etmek için.