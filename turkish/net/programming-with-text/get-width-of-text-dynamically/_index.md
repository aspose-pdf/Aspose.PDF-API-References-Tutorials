---
title: Metnin Genişliğini Dinamik Olarak Alın
linktitle: Metnin Genişliğini Dinamik Olarak Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak metnin genişliğini dinamik olarak nasıl alacağınızı öğrenin.
type: docs
weight: 220
url: /tr/net/programming-with-text/get-width-of-text-dynamically/
---

Bu eğitimde, C# dilinde metnin genişliğini dinamik olarak ölçmek için Aspose.PDF for .NET'in nasıl kullanılacağını açıklayacağız. Bu, bir metin dizesini bir PDF belgesinde oluşturmadan önce boyutunu belirlemeniz gerektiğinde yararlı olabilir. Sağlanan C# kaynak kodunda size adım adım rehberlik edeceğiz.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kitaplığı yüklendi.
- Visual Studio veya başka herhangi bir C# geliştirme ortamı.

## 1. Adım: Belge Dizinini Ayarlayın

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgelerinizin bulunduğu dizinin yolu ile. Bu, oluşturulan herhangi bir PDF dosyasını depolamak için kullanılacaktır.

## 2. Adım: Yazı Tipini Bulun

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("Arial");
```

 Yukarıdaki kod, Arial yazı tipini kullanarak bulur.`FindFont` gelen yöntem`FontRepository` sınıf. Farklı bir yazı tipi kullanmak istiyorsanız, değiştirin`"Arial"` İstenen yazı tipi adıyla.

## 3. Adım: Metin Durumunu Ayarlayın

```csharp
TextState ts = new TextState();
ts.Font = font;
ts.FontSize = 14;
```

 Burada yeni bir tane oluşturuyoruz.`TextState` nesne ve özelliklerini ayarlayın. Önceden bulunan yazı tipini atarız (`font`) ve yazı tipi boyutunu 14 olarak ayarlayın. Yazı tipi boyutunu gerektiği gibi ayarlayın.

## 4. Adım: Metnin Genişliğini Ölçün

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

Yukarıdaki kod, hem yazı tipini doğrudan kullanarak metnin genişliğini nasıl ölçeceğinizi gösterir (`font.MeasureString`) ve metin durumu (`ts.MeasureString`). Ölçümlerin doğru olduğundan emin olmak için bazı doğrulama kontrolleri içerir.

### Aspose.PDF for .NET kullanarak Dinamik Olarak Metin Genişliğini Getir için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
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

C# dilinde metnin genişliğini dinamik olarak ölçmek için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrendiniz. Bu eğitimde özetlenen adımları izleyerek, bir PDF belgesinde oluşturmadan önce metin dizelerinin genişliğini doğru bir şekilde belirleyebilirsiniz.