---
title: Metnin Genişliğini Dinamik Olarak Alın
linktitle: Metnin Genişliğini Dinamik Olarak Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak metnin genişliğini dinamik olarak nasıl alacağınızı öğrenin.
type: docs
weight: 220
url: /tr/net/programming-with-text/get-width-of-text-dynamically/
---
Bu eğitimde, C# dilinde metnin genişliğini dinamik olarak ölçmek için Aspose.PDF for .NET'in nasıl kullanılacağını açıklayacağız. Bu, bir PDF belgesinde işlemeden önce bir metin dizesinin boyutunu belirlemeniz gerektiğinde faydalı olabilir. Sağlanan C# kaynak kodunda adım adım size rehberlik edeceğiz.

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kütüphanesi kuruldu.
- Visual Studio veya herhangi bir C# geliştirme ortamı.

## Adım 1: Belge Dizinini Ayarlayın

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgelerinizin bulunduğu dizinin yolu ile. Bu, oluşturulan tüm PDF dosyalarını depolamak için kullanılacaktır.

## Adım 2: Yazı Tipini Bulun

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("Arial");
```

 Yukarıdaki kod, Arial yazı tipini şu şekilde bulur:`FindFont`yöntemden`FontRepository` sınıf. Farklı bir yazı tipi kullanmak istiyorsanız, şunu değiştirin`"Arial"` İstediğiniz yazı tipi adıyla.

## Adım 3: Metin Durumunu Ayarlayın

```csharp
TextState ts = new TextState();
ts.Font = font;
ts.FontSize = 14;
```

 Burada yeni bir tane yaratıyoruz`TextState` nesneyi ve özelliklerini ayarlayın. Daha önce bulunan yazı tipini (`font`) ve yazı tipi boyutunu 14 olarak ayarlayın. Yazı tipi boyutunu gerektiği gibi ayarlayın.

## Adım 4: Metnin Genişliğini Ölçün

```csharp
if (Math.Abs(font.MeasureString("A", 14) - 9.337) > 0.001)
	Console.WriteLine("Unexpected font string measure!");

if (Math.Abs(ts.MeasureString("z") - 7.0) > 0.001)
	Console.WriteLine("Unexpected font string measure!");

for (char c = 'A'; c <= 'z'; c++)
{
	double fnMeasure = font.MeasureString(c.ToString(), 14);
	double tsMeasure = ts.MeasureString(c.ToString());
	if (Math.Abs(fnMeasure - tsMeasure) > 0.001)
		Console.WriteLine("Font and state string measuring doesn't match!");
}
```

Yukarıdaki kod, hem yazı tipini hem de doğrudan yazı tipini kullanarak metnin genişliğinin nasıl ölçüleceğini göstermektedir (`font.MeasureString`) ve metin durumu (`ts.MeasureString`). Ölçümlerin doğruluğunu garantilemek için bazı doğrulama kontrolleri içerir.

### .NET için Aspose.PDF kullanarak Metnin Genişliğini Dinamik Olarak Almak için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Text.Font font = FontRepository.FindFont("Arial");
TextState ts = new TextState();
ts.Font = font;
ts.FontSize = 14;
if (Math.Abs(font.MeasureString("A", 14) - 9.337) > 0.001)
	Console.WriteLine("Unexpected font string measure!");
if (Math.Abs(ts.MeasureString("z") - 7.0) > 0.001)
	Console.WriteLine("Unexpected font string measure!");
for (char c = 'A'; c <= 'z'; c++)
{
	double fnMeasure = font.MeasureString(c.ToString(), 14);
	double tsMeasure = ts.MeasureString(c.ToString());
	if (Math.Abs(fnMeasure - tsMeasure) > 0.001)
		Console.WriteLine("Font and state string measuring doesn't match!");
}
```


## Çözüm

C# dilinde metnin genişliğini dinamik olarak ölçmek için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrendiniz. Bu eğitimde özetlenen adımları izleyerek, metin dizelerinin genişliğini PDF belgesinde işlemeden önce doğru bir şekilde belirleyebilirsiniz.

## SSS

#### S: "Metnin Genişliğini Dinamik Olarak Alma" eğitiminin amacı nedir?

A: "Metnin Genişliğini Dinamik Olarak Al" öğreticisi, C# dilinde metnin genişliğini dinamik olarak ölçmek için Aspose.PDF for .NET'in nasıl kullanılacağını açıklar. Bu, özellikle bir metin dizesinin boyutunu bir PDF belgesinde işlemeden önce belirlemeniz gerektiğinde faydalıdır.

#### S: Metnin genişliğini dinamik olarak ölçmem neden gerekir?

A: Metin genişliğini dinamik olarak ölçmek, metni işlemeden önce gereken alanı doğru bir şekilde belirlemenizi sağlar. Bu, düzen tasarımı, hizalama ve metnin PDF belgenizdeki belirlenmiş alanlara doğru şekilde sığmasını sağlamak için önemlidir.

#### S: Metin ölçümünde kullanılacak yazı tipini nasıl bulabilirim?

 A: Eğitimde şunu kullanıyorsunuz:`FontRepository.FindFont` İstenen yazı tipini bulma yöntemi. Örnek Arial yazı tipini kullanır, ancak değiştirebilirsiniz`"Arial"` kullanmak istediğiniz herhangi bir diğer yazı tipinin adını yazın.

####  S: Amacı nedir?`TextState` class?

 A:`TextState` sınıfı, yazı tipi ve yazı tipi boyutu gibi metin biçimlendirme özelliklerini ayarlamak için kullanılır. Metnin nasıl sunulacağını tanımlamanıza olanak tanır.

#### S: Font ve text state kullanarak metnin genişliğini nasıl ölçerim?

A: Eğitimde, hem yazı tipini hem de doğrudan yazı tipini kullanarak metnin genişliğinin nasıl ölçüleceği gösterilmektedir.`font.MeasureString`) ve metin durumu (`ts.MeasureString`). Ölçüm doğruluğunu garantilemek için doğrulama kontrolleri içerir.

#### S: Bu tekniği farklı yazı boyutları ve stilleri için kullanabilir miyim?

 A: Evet, yazı tipi boyutunu ve diğer özellikleri değiştirebilirsiniz.`TextState` Farklı boyut ve stiller için metin genişliğini ölçmeye yarayan nesne.

#### S: Dersin sonunda neyi vurguluyor?

A: Sonuç, eğitimin içeriğini özetler ve .NET ve C# için Aspose.PDF kullanarak bir PDF belgesindeki metin genişliğini dinamik olarak nasıl ölçeceğinizi öğrendiğinizi vurgular. Bu bilgi, PDF düzen tasarımınızı ve işleme doğruluğunuzu iyileştirmenize katkıda bulunabilir.