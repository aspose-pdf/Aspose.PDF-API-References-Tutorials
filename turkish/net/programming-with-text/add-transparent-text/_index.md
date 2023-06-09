---
title: Saydam Metin Ekle
linktitle: Saydam Metin Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesine şeffaf metin eklemeyi öğrenin.
type: docs
weight: 100
url: /tr/net/programming-with-text/add-transparent-text/
---

Bu eğitim, Aspose.PDF for .NET kullanarak bir PDF belgesine saydam metin ekleme sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu, gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya makinenizde kurulu başka bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi kurun
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
Saydam metin eklemek istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## 3. Adım: Belge dizinini ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile.

## 4. Adım: Yeni bir Belge örneği oluşturun
 Yeni bir örnek oluştur`Document` aşağıdaki kod satırını ekleyerek nesne:

```csharp
Document doc = new Document();
```

## 5. Adım: Belgeye bir sayfa ekleyin
 kullanarak belgeye yeni bir sayfa ekleyin.`Add` yöntemi`Pages` Toplamak. Sağlanan kodda, yeni sayfa değişkene atanır.`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 6. Adım: Bir Grafik nesnesi oluşturun
 Yeni bir tane oluştur`Graph` belirli bir genişliğe ve yüksekliğe sahip nesne.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## 7. Adım: Saydamlıkla bir dikdörtgen oluşturun
Belirli boyutlara sahip bir dikdörtgen oluşturun ve dolgu rengini kullanarak şeffaf bir renge ayarlayın.`Color.FromRgb` yöntem.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## 8. Adım: Grafik nesnesini sayfaya ekleyin
 Ekle`Graph` sayfanın paragraflar koleksiyonuna itiraz.

```csharp
page.Paragraphs.Add(canvas);
```

## 9. Adım: Grafik nesnesi için konumu ayarlayın
 Yı kur`IsChangePosition` mülkiyeti`Graph` itiraz etmek`false` pozisyon değiştirmesini önlemek için.

```csharp
canvas. IsChangePosition = false;
```

## Adım 10: Şeffaflık içeren bir TextFragment oluşturun
 Oluşturmak`TextFragment` nesneyi seçin ve içeriğini istediğiniz metne ayarlayın. Yı kur`ForegroundColor` mülkiyeti`TextState` kullanarak şeffaf bir renge dönüştürün.`Color.FromArgb` yöntem.

```csharp
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
text.TextState.ForegroundColor = color;
page.Paragraphs.Add(text);
```

## 11. Adım: PDF belgesini kaydedin
 kullanarak PDF belgesini kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "AddTransparentText_out.pdf");
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanarak Add Transparent Text için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge örneği oluştur
Document doc = new Document();
// PDF dosyasının sayfalarca koleksiyonunu oluşturun
Aspose.Pdf.Page page = doc.Pages.Add();
// Grafik nesnesi oluştur
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Belirli boyutlara sahip dikdörtgen örneği oluşturun
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
// Alfa renk kanalından renk nesnesi oluşturun
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Grafik nesnesinin şekiller koleksiyonuna dikdörtgen ekleme
canvas.Shapes.Add(rect);
// Sayfa nesnesinin paragraf koleksiyonuna grafik nesnesi ekleyin
page.Paragraphs.Add(canvas);
// Değeri, grafik nesnesinin konumunu değiştirmeyecek şekilde ayarlayın
canvas.IsChangePosition = false;
// Örnek değerle TextFragment örneği oluşturun
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// Alfa kanalından renkli nesne oluştur
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
//Metin örneği için renk bilgilerini ayarla
text.TextState.ForegroundColor = color;
// Sayfa örneğinin paragraf koleksiyonuna metin ekleyin
page.Paragraphs.Add(text);
dataDir = dataDir + "AddTransparentText_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```


## Çözüm
Aspose.PDF for .NET'i kullanarak PDF belgenize şeffaf metni başarıyla eklediniz. Ortaya çıkan PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.