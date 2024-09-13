---
title: PDF Dosyasında Tablo Kırılımını Belirle
linktitle: PDF Dosyasında Tablo Kırılımını Belirle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki tablo sonlarının nasıl belirleneceğini öğrenin.
type: docs
weight: 60
url: /tr/net/programming-with-tables/determine-table-break/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak PDF dosyasındaki tablo sonlarını nasıl belirleyeceğimizi öğreneceğiz. Kaynak kodunu adım adım C# dilinde açıklayacağız. Bu eğitimin sonunda, bir tablonun sayfa kenar boşluklarını aşıp aşmadığını nasıl belirleyeceğinizi öğreneceksiniz. Başlayalım!

## Adım 1: Ortamı kurma
Öncelikle, C# geliştirme ortamınızı .NET için Aspose.PDF ile kurduğunuzdan emin olun. Referansı kütüphaneye ekleyin ve gerekli ad alanlarını içe aktarın.

## Adım 2: PDF belgesinin oluşturulması
 Bu adımda yeni bir tane oluşturuyoruz`Document` PDF belgesini temsil eden nesne.

```csharp
pdf-Document = new Document();
```

Bu belge bölüm ve tablo eklemek için kullanılacaktır.

## Adım 3: Bir bölüm ve bir tablo ekleme
Şimdi PDF dokümanımıza bir bölüm ekleyeceğiz ve bu bölümün içerisinde bir tablo oluşturacağız.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

Ayrıca tablo için 300 puanlık bir üst marj belirliyoruz. Bu değeri ihtiyaçlarınıza göre ayarlayabilirsiniz.

## Adım 4: Tablo Kurulumu
Bu adımda sütun genişlikleri ve kenarlıklar gibi tablo özelliklerini yapılandırıyoruz.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Burada tablo sütunlarının genişliğini ve hücre kenarlıklarını tanımlıyoruz. Bu değerleri tercihlerinize göre ayarlayabilirsiniz.

## Adım 5: Tabloya satırlar ve hücreler ekleyin
Şimdi bir döngü kullanarak tabloda satırlar ve hücreler oluşturacağız.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

Burada tabloda 17 satır oluşturuyoruz ve her satıra üç hücre ekliyoruz. Tokayı ihtiyaçlarınıza göre ayarlayabilirsiniz.

## Adım 6: Tablo Sonlarını Belirleme
Şimdi tablonun sayfa kenar boşluklarını aşıp aşmadığını, tablo içindeki nesnelerin toplam yüksekliği ile sayfanın yüksekliğini karşılaştırarak belirleyeceğiz.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

Sayfanın yüksekliğini ve nesnelerin toplam yüksekliğini kenar boşluklarını dikkate alarak hesaplıyoruz. Fark 10 veya daha azsa, tablo sayfa kenar boşluklarını aşar.

## Adım 7: PDF belgesini kaydetme
Son olarak sonuçların yer aldığı PDF dokümanını kaydediyoruz.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

Doğru belge dizinini belirttiğinizden emin olun. Ortaya çıkan PDF dosyası belirlenen tablo sonlarıyla kaydedilecektir.

### .NET için Aspose.PDF kullanarak Tablo Sonunu Belirleme için örnek kaynak kodu

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Bir nesne PDF sınıfını örneklendirin
Document pdf = new Document();
// Bölümü PDF belge bölümleri koleksiyonuna ekleyin
Aspose.Pdf.Page page = pdf.Pages.Add();
// Bir tablo nesnesi örneği oluşturun
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// İstenilen bölümün paragraf koleksiyonuna tabloyu ekleyin
page.Paragraphs.Add(table1);
// Tablonun sütun genişlikleriyle ayarlayın
table1.ColumnWidths = "100 100 100";
// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlayın
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Başka bir özelleştirilmiş BorderInfo nesnesini kullanarak tablo kenarlığını ayarlayın
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// MarginInfo nesnesini oluşturun ve sol, alt, sağ ve üst kenar boşluklarını ayarlayın
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Varsayılan hücre dolgusunu MarginInfo nesnesine ayarlayın
table1.DefaultCellPadding = margin;
// Eğer sayacı 17'ye çıkarırsanız masa kırılır
// Çünkü bu sayfaya daha fazla yer verilemez
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	//Tabloda satırlar ve ardından satırlarda hücreler oluşturun
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// Sayfa Yüksekliği bilgilerini alın
float PageHeight = (float)pdf.PageInfo.Height;
// Sayfa Üstü ve Alt Kenar boşluğunun toplam yükseklik bilgisini alın,
// Tablo Üst kenar boşluğu ve tablo yüksekliği.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Sayfa Yüksekliğini, Tablo Yüksekliğini, Tablo Üst Kenar Boşluğunu ve Sayfa Üstünü Göster
// Ve Alt kenar boşluğu bilgisi
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// Sayfa üst kenar boşluğu + Sayfa alt kenar boşluğu toplamını düşüp düşmediğimizi kontrol edin
// + Sayfa yüksekliğinden ve daha azından Tablo Üstü kenar boşluğu ve tablo yüksekliği
// 10'dan fazla (ortalama bir satır 10'dan büyük olabilir)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// Eğer değer 10'dan küçükse mesajı göster.
	//Başka bir satırın yerleştirilemeyeceğini ve yeni bir satır eklersek,
	// Satır, tablo kırılacak. Satır yükseklik değerine bağlıdır.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// PDF belgesini kaydedin
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Çözüm
Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesindeki tablo sonlarını nasıl belirleyeceğimizi öğrendik. Kendi C# projelerinizde bir tablonun sayfa kenar boşluklarını aşıp aşmadığını kontrol etmek için bu adım adım kılavuzu kullanabilirsiniz.

### PDF dosyasında tablo sonunu belirlemeye ilişkin SSS

#### S: PDF belgesinde tablo sonlarını belirlemenin amacı nedir?

A: Bir PDF belgesinde tablo sonlarını belirlemenin amacı, tablonun sayfa kenar boşluklarını aşıp aşmadığını kontrol etmektir. Bu, tablonun içeriğinin kullanılabilir sayfa alanında doğru şekilde görüntülenmesini sağlar. Tablo sonlarını algılayarak, içerik taşmasını yönetebilir ve tablo düzenini buna göre ayarlayabilirsiniz.

#### S: Tablonun üst kenar boşluğunu nasıl ayarlayabilirim?

 A: Sağlanan C# kaynak kodunda, tablonun üst kenar boşluğunu, değerini değiştirerek ayarlayabilirsiniz.`table1.Margin.Top`özellik. Tablo için istenen üst kenar boşluğunu ayarlamak için gerektiği gibi değeri artırın veya azaltın.

#### S: Tablonun görünümünü, hücre renkleri ve yazı tipi boyutu gibi şeyleri özelleştirebilir miyim?

A: Evet, .NET için Aspose.PDF tarafından sağlanan çeşitli özellikler ve yöntemleri kullanarak tablonun ve hücrelerinin görünümünü özelleştirebilirsiniz. Örneğin, hücre arka plan renklerini, yazı tipi boyutunu, yazı tipi ailesini, metin hizalamasını ve daha fazlasını değiştirebilirsiniz. Tablo görünümünün nasıl özelleştirileceği hakkında daha fazla bilgi için resmi belgelere bakın.

#### S: Tablo sayfa kenar boşluklarını aşarsa ne olur?

A: Tablo sayfa kenar boşluklarını aşarsa, içerik kesilmesine veya üst üste binmesine neden olabilir ve PDF belgesi daha az okunabilir ve düzenli hale gelir. Tablo sonlarını algılayarak ve taşmayı işleyerek, içeriğin kullanılabilir sayfa alanında düzgün bir şekilde görüntülenmesini sağlayabilirsiniz.

#### S: Aynı PDF belgesinde birden fazla tablo için tablo sonlarını belirleyebilir miyim?

A: Evet, aynı PDF belgesinde birden fazla tablo için tablo sonlarını belirleyebilirsiniz. Analiz etmek istediğiniz her tablo için adımları tekrarlayın ve içerik taşmasını önlemek için tablo düzenini gerektiği gibi ayarlayın.