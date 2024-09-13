---
title: Gradyan Dolgulu Çizim Ekle
linktitle: Gradyan Dolgulu Çizim Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzla, .NET için Aspose.PDF'yi kullanarak PDF'lere çarpıcı degrade çizimlerin nasıl ekleneceğini öğrenin. Bu kılavuz, belge görsellerini geliştirmek için mükemmeldir.
type: docs
weight: 20
url: /tr/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
## giriiş

Günümüzün dijital dünyasında görsel olarak çekici belgeler oluşturmak olmazsa olmazdır. PDF belgelerinizi geliştirmek için çarpıcı bir teknik, degrade dolgulu çizimler eklemektir. Belge tasarım becerilerinizi geliştirmek istiyorsanız, doğru yerdesiniz! Bu kılavuzda, PDF'nize çarpıcı bir degrade dolgulu çizim eklemek için Aspose.PDF for .NET'i kullanma sürecinde size yol göstereceğim.

## Ön koşullar

Ayrıntılara dalmadan önce, yerinde olması gereken birkaç şey şunlardır:

1.  .NET Kütüphanesi için Aspose.PDF: Aspose.PDF kütüphanesinin yüklü olduğundan emin olun. Bunu şuradan alabilirsiniz:[indirme bağlantısı](https://releases.aspose.com/pdf/net/).
2. Geliştirme Ortamı: Kodunuzu yazabileceğiniz ve çalıştırabileceğiniz Visual Studio gibi bir .NET geliştirme ortamı kurun.
3. C# Temel Anlayışı: C# programlamaya aşina olmak, takip etmeyi kolaylaştıracaktır.

Yukarıdaki ön koşulların hepsini tamamladıktan sonra, uygulamaya geçelim!

## Paketleri İçe Aktar

İlk önce, gerekli paketleri projenize aktarmanız gerekir. İşte nasıl:

- C# projenizi Visual Studio’da açın.
- Aspose.PDF kütüphanesine bir referans ekleyin. Bunu NuGet Paket Yöneticisi aracılığıyla yapabilirsiniz:
  
```csharp
using Aspose.Pdf.Drawing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Şimdi süreci sindirilebilir adımlara bölelim. 

## Adım 1: Belge Dizinini Ayarlayın

Başlamak için belgeleriniz için bir yol ayarlamanız gerekir. Bu, oluşturulan PDF dosyalarınızı nereye kaydedeceğinizi düzenlemenize yardımcı olur.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Dizin yolunuzla değiştirin
```
 Bu kod satırı bir değişken oluşturur`dataDir` , çıktı PDF'nin kaydedileceği dizine giden yolu tutacak. Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` gerçek dizin yolunuzla.

## Adım 2: Yeni bir PDF Belgesi Oluşturun

Şimdi Aspose.PDF kütüphanesini kullanarak yeni bir PDF belgesi oluşturalım.

```csharp
Document doc = new Document();
```
 Burada bir örnek oluşturuyoruz`Document` nesne. Bu nesne PDF belgenizi temsil eder ve eklemeyi planladığınız tüm öğeler için bir kapsayıcı görevi görür.

## Adım 3: Belgeye Bir Sayfa Ekleyin

Artık belgemiz hazır olduğuna göre, ona bir sayfa eklemenin zamanı geldi.

```csharp
Page page = doc.Pages.Add();
```
Bu satır belgenize yeni bir sayfa ekler. Eklemek istediğiniz tüm grafikler ve metinler için alan sağlar.

## Adım 4: Grafik Nesne Oluşturun

Şekilleri çizebilmek için öncelikle sayfada bir grafik alanı oluşturmamız gerekiyor.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300.0, 300.0);
page.Paragraphs.Add(graph);
```
Bu durumda, 300 birim genişliğinde ve yüksekliğinde bir grafik nesnesi oluşturuyoruz. Bunu sayfanın paragraflarına ekleyerek çizimlerimiz için zemin hazırlıyoruz.

## Adım 5: Dikdörtgen Şeklini Tanımlayın

Daha sonra, degradeli bir renkle doldurmak istediğimiz dikdörtgen şeklini tanımlayacağız.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```
Burada, (0,0) koordinatlarından başlayıp genişlik ve yükseklikte 300 birim uzanan bir dikdörtgen oluşturuyoruz. Bu dikdörtgen daha sonra grafik nesnemize ekleniyor.

## Adım 6: Dikdörtgene Degrade Dolgu Uygula

Şimdi eğlenceli kısma geliyoruz! Dikdörtgenimize bir degrade dolgu uygulayacağız.

```csharp
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
    PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
    {
        Start = new Point(0, 0),
        End = new Point(300, 300)
    }
};
```
 Bu kod bloğunda, dikdörtgenin dolgu renginin kırmızıdan maviye doğru bir degrade olmasını belirtiyoruz.`GradientAxialShading`sınıfı, renkler arasında yumuşak bir geçiş oluşturmak için başlangıç ve bitiş noktalarını belirleyebileceğiniz bir degrade dolgunun tanımlanmasına olanak tanır.

## Adım 7: PDF Belgesini Kaydedin

Son olarak belgemizi tanımladığımız dizine kaydetmemiz gerekiyor.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```
 Bu komut, PDF'nizi daha önce tanımlanmış belirli bir adla kaydeder`dataDir`Sonuç, degradeyle dolu bir dikdörtgen içeren, güzelce hazırlanmış bir PDF'dir.

## Çözüm

Ve işte karşınızda! Aspose.PDF for .NET kullanarak PDF belgenize degrade dolgulu bir çizim eklemeyi öğrendiniz. Birkaç satır kodun basit bir PDF'yi görsel olarak çarpıcı bir şeye nasıl dönüştürebildiği şaşırtıcı değil mi? İster raporlar, ister faturalar veya başka bir belge oluşturun, grafik kullanmak okuyucunun deneyimini önemli ölçüde artırabilir.

## SSS

### Aspose.PDF for .NET nedir?
Aspose.PDF for .NET, geliştiricilerin PDF belgelerini programlı bir şekilde oluşturmalarına ve düzenlemelerine olanak tanıyan güçlü bir kütüphanedir.

### Aspose.PDF'yi ücretsiz kullanabilir miyim?
 Bir ile başlayabilirsiniz[ücretsiz deneme](https://releases.aspose.com/) İşlevselliğini keşfetmek için kullanılabilir, ancak kullanım sınırlamaları olabilir.

### Daha fazla dokümanı nerede bulabilirim?
Ayrıntılı dokümantasyon şu adreste mevcuttur:[Aspose PDF referans sayfası](https://reference.aspose.com/pdf/net/).

### Aspose.PDF'i nasıl satın alabilirim?
 Aspose.PDF kütüphanesini şu adresten satın alabilirsiniz:[satın alma bağlantısı](https://purchase.aspose.com/buy).

### Aspose.PDF'i kullanırken yardıma ihtiyacım olursa ne yapmalıyım?
 Herhangi bir sorunla karşılaşırsanız, yardım isteyebilirsiniz.[Aspose destek forumu](https://forum.aspose.com/c/pdf/10).