---
title: PDF Dosyasındaki Kenarlığı Çıkar
linktitle: PDF Dosyasındaki Kenarlığı Çıkar
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF dosyasından kenarlıkları nasıl çıkaracağınızı ve bunları bir resim olarak nasıl kaydedeceğinizi öğrenin. Başarı için kod örnekleri ve ipuçları içeren adım adım kılavuz.
type: docs
weight: 80
url: /tr/net/programming-with-tables/extract-border/
---
## giriiş

PDF'lerle çalışırken, kenarlıklar veya grafiksel yollar gibi belirli öğeleri çıkarmak zorlu bir görev gibi görünebilir. Ancak .NET için Aspose.PDF ile bir PDF dosyasından kolayca kenarlıklar veya şekiller çıkarabilir ve bunları bir resim olarak kaydedebilirsiniz. Bu eğitimde, bir PDF'den kenarlık çıkarma ve bunu PNG resmi olarak kaydetme sürecine dalacağız. PDF'nizin grafiksel içeriklerinin kontrolünü ele geçirmeye hazır olun!

## Ön koşullar

Koda dalmadan önce her şeyin ayarlandığından emin olun:

1.  .NET için Aspose.PDF: Aspose.PDF kitaplığını henüz yüklemediyseniz,[buradan indirin](https://releases.aspose.com/pdf/net/)Ayrıca, ücretsiz deneme veya satın alınan lisans aracılığıyla lisansı uygulamanız gerekecektir.
2. IDE Kurulumu: Visual Studio'da veya herhangi bir .NET IDE'de bir C# projesi kurun. Aspose.PDF kitaplığına gerekli referansları eklediğinizden emin olun.
3. Giriş PDF Dosyası: Kenarlıkları çıkaracağınız hazır bir PDF dosyanız olsun. Bu eğitim, şu adlı bir dosyaya referans verecektir:`input.pdf`.

## Gerekli Paketleri İçe Aktarma

Gerekli ad alanlarını içe aktararak başlayalım. Bu paketler PDF içeriğini düzenlemek için gereken araçları sağlar.

```csharp
using System.IO;
using System;
using System.Drawing.Drawing2D;
using System.Drawing.Imaging;
using System.Collections;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

Artık temelleri ele aldığımıza göre, kodun her bir bölümünü ayrıntılı olarak açıklayacağımız adım adım kılavuza geçelim.


## Adım 1: PDF Belgesini Yükleme

İlk adım, çıkarmak istediğiniz kenarlığı içeren PDF belgesini yüklemektir. Bunu, okumaya başlamadan önce bir kitabı açmak gibi düşünün — içeriğe erişmeniz gerekir!

 PDF dosyanızın saklandığı dizini belirterek başlayacağız ve belgeyi şu şekilde yükleyeceğiz:`Aspose.Pdf.Document` sınıf.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Bu kod şunu yükler:`input.pdf` Belirtilen dizinden dosyayı kaldırın. Dosya yolunun doğru olduğundan emin olun, aksi takdirde dosya bulunamadı hatası alabilirsiniz.

## Adım 2: Grafik ve Bitmap'i Ayarlama

Çıkarmaya başlamadan önce, üzerine çizim yapacağımız bir tuval oluşturmamız gerekir. .NET dünyasında bu, bir Bitmap ve Graphics nesnesi kurmak anlamına gelir. Bitmap, görüntüyü temsil eder ve Graphics nesnesi, PDF'den çıkarılan kenarlıklar gibi şekilleri çizmemize olanak tanır.

```csharp
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);
```

İşte bir özet:
- PDF'in ilk sayfasının boyutunda bir bitmap görüntüsü oluşturuyoruz.
- GraphicsPath şekilleri (bu durumda kenarlıkları) tanımlamak için kullanılır.
- Matris grafiklerin nasıl dönüştürüleceğini tanımlar; PDF ve .NET'in farklı koordinat sistemleri olduğundan bir ters matrise ihtiyacımız vardır.

## Adım 3: PDF İçeriklerinin İşlenmesi


PDF dosyası bir dizi çizim komutundan oluşur ve sınır bilgilerini belirlemek ve çıkarmak için bu komutların her birini işlememiz gerekir.

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // Durum kaydetme/geri yükleme, çizgi çizme, şekilleri doldurma vb. gibi işlem komutları.
}
```

Kod, PDF'nin içerik akışındaki her çizim operatöründe döngü oluşturur. Her operatör bir çizgiyi, dikdörtgeni veya diğer grafiksel talimatları temsil edebilir.

## Adım 4: PDF Operatörlerini Kullanma

PDF dosyasındaki her operatör bir eylemi kontrol eder. Sınırı çıkarmak için "move to", "line to" ve "draw rectangle" gibi komutları tanımlamamız gerekir. Aşağıdaki operatörler bu eylemleri işler:

- MoveTo: İmleci bir başlangıç noktasına taşır.
- LineTo: Mevcut noktadan yeni bir noktaya bir çizgi çizer.
- Re: Bir dikdörtgen çizer (bu sınırın bir parçası olabilir).

```csharp
Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;

if (opMoveTo != null)
{
    lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
    System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
    graphicsPath.AddLine(lastPoint, linePoint);
    lastPoint = linePoint;
}
else if (opRe != null)
{
    System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
    graphicsPath.AddRectangle(re);
}
```

Bu adımda:
- Çizilen her çizgi veya şekil için noktaları yakalarız.
- Dikdörtgenler için (`opRe` ), bunları doğrudan ekliyoruz`graphicsPath`, daha sonra sınırı çizmek için kullanacağız.

## Adım 5: Sınırı Çizmek

Sınırı oluşturan çizgileri ve dikdörtgenleri tanımladığımızda, bunları Bitmap nesnesinin üzerine çizmemiz gerekir. İşte Graphics nesnesinin devreye girdiği yer burasıdır.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
    gr.SmoothingMode = SmoothingMode.HighQuality;
    gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
}
```

- Bitmap'e dayalı bir Graphics nesnesi oluşturuyoruz.
- SmoothingMode.HighQuality güzel ve pürüzsüz bir görüntü elde etmemizi sağlar.
- Son olarak DrawPath'i kullanarak sınırı çiziyoruz.

## Adım 6: Çıkarılan Kenarlığın Kaydedilmesi

Artık kenarlığı çıkardığımıza göre, onu bir resim dosyası olarak kaydetme zamanı geldi. Bu, kenarlığı PNG olarak kaydedecektir.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

- Bitmap PNG resmi olarak kaydedilir.
- Artık bu görseli açarak çıkarılan kenarlığı görebilirsiniz.

## Çözüm

Aspose.PDF for .NET kullanarak bir PDF dosyasından kenarlıkları çıkarmak ilk başta zor görünebilir, ancak bir kez parçalara ayırdığınızda, basit hale gelir. Bir PDF'deki çizim operatörlerini anlayarak ve güçlü .NET kitaplıklarını kullanarak, grafiksel içeriği verimli bir şekilde işleyebilir ve çıkarabilirsiniz. Bu kılavuz, PDF işlemeye başlamak için size sağlam bir temel sağlar!

## SSS

### PDF'deki birden fazla sayfayı nasıl idare edebilirim?  
 Belgedeki her sayfada yineleme yaparak dolaşabilirsiniz`doc.Pages` sabit kodlama yerine`doc.Pages[1]`.

### Aynı yaklaşımı kullanarak metin gibi diğer öğeleri de çıkarabilir miyim?  
Evet, Aspose.PDF, PDF dosyalarından metin, resim ve diğer içerikleri çıkarmak için zengin API'ler sağlar.

### Sınırlamalardan kaçınmak için lisans başvurusunu nasıl yapabilirim?  
 Yapabilirsiniz[lisans başvurusunda bulunmak](https://purchase.aspose.com/temporary-license/) yükleyerek`License` Aspose tarafından sağlanan sınıf.

### PDF dosyamın kenarlıkları yoksa ne olur?  
PDF'nizde görünür kenarlıklar yoksa, grafik çıkarma işlemi herhangi bir sonuç vermeyebilir. PDF içeriğinin çizilebilir kenarlıklar içerdiğinden emin olun.

### Çıktıyı PNG dışındaki formatlarda kaydedebilir miyim?  
 Evet, sadece şunu değiştirin:`ImageFormat.Png` desteklenen başka bir biçime örneğin`ImageFormat.Jpeg`.