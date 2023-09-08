---
title: PDF Dosyasında Tablo Sonunu Belirleme
linktitle: PDF Dosyasında Tablo Sonunu Belirleme
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki tablo sonlarını nasıl belirleyeceğinizi öğrenin.
type: docs
weight: 60
url: /tr/net/programming-with-tables/determine-table-break/
---
Bu derste Aspose.PDF for .NET kullanarak PDF dosyasındaki tablo sonlarının nasıl belirleneceğini öğreneceğiz. C#'ta kaynak kodunu adım adım anlatacağız. Bu eğitimin sonunda bir tablonun sayfa kenar boşluklarını aşıp aşmadığını nasıl belirleyeceğinizi öğreneceksiniz. Hadi başlayalım!

## 1. Adım: Ortamı ayarlama
Öncelikle Aspose.PDF for .NET ile C# geliştirme ortamınızı kurduğunuzdan emin olun. Referansı kitaplığa ekleyin ve gerekli ad alanlarını içe aktarın.

## Adım 2: PDF belgesini oluşturma
 Bu adımda yeni bir tane oluşturuyoruz.`Document` PDF belgesini temsil edecek nesne.

```csharp
pdf-Document = new Document();
```

Bu belge bölüm ve tablo eklemek için kullanılacaktır.

## 3. Adım: Bölüm ve tablo ekleme
Şimdi PDF belgemize bir bölüm ekleyeceğiz ve bu bölümün içinde bir tablo oluşturacağız.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

Ayrıca tablo için 300 puanlık bir üst kenar boşluğu belirliyoruz. Bu değeri ihtiyaçlarınıza göre ayarlayabilirsiniz.

## Adım 4: Tablo Kurulumu
Bu adımda sütun genişlikleri ve kenarlıklar gibi tablo özelliklerini yapılandırıyoruz.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Burada tablo sütunlarının genişliğini ve hücre kenarlıklarını tanımlıyoruz. Bu değerleri tercihlerinize göre ayarlayabilirsiniz.

## 5. Adım: Tabloya satır ve hücre ekleyin
Şimdi döngü kullanarak tabloda satırlar ve hücreler oluşturacağız.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

Burada tabloda 17 satır oluşturup her satıra üç hücre ekliyoruz. Tokayı ihtiyaçlarınıza göre ayarlayabilirsiniz.

## Adım 6: Tablo Sonlarını Belirleme
Şimdi sayfanın yüksekliğini tablodaki nesnelerin toplam yüksekliğiyle karşılaştırarak tablonun sayfa kenar boşluklarını aşıp aşmadığını belirleyeceğiz.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

Kenar boşluklarını dikkate alarak sayfanın yüksekliğini ve nesnelerin toplam yüksekliğini hesaplıyoruz. Fark 10 veya daha az ise tablo sayfa kenar boşluklarını aşıyor demektir.

## Adım 7: PDF belgesini kaydetme
Son olarak sonuçları içeren PDF belgesini kaydediyoruz.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

Doğru belge dizinini belirttiğinizden emin olun. Ortaya çıkan PDF dosyası belirlenen tablo sonlarıyla birlikte kaydedilecektir.

### Aspose.PDF for .NET kullanarak Tablo Sonunu Belirleme için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Bir nesne PDF sınıfının örneğini oluşturma
Document pdf = new Document();
// Bölümü PDF belgesi bölümleri koleksiyonuna ekleyin
Aspose.Pdf.Page page = pdf.Pages.Add();
// Bir tablo nesnesinin örneğini oluşturma
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// Tabloyu istediğiniz bölümün paragraf koleksiyonuna ekleyin
page.Paragraphs.Add(table1);
// Tablonun sütun genişliklerine göre ayarlama
table1.ColumnWidths = "100 100 100";
// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlama
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Başka bir özelleştirilmiş BorderInfo nesnesini kullanarak tablo kenarlığını ayarlayın
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// MarginInfo nesnesi oluşturun ve sol, alt, sağ ve üst kenar boşluklarını ayarlayın
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Varsayılan hücre dolgusunu MarginInfo nesnesine ayarlayın
table1.DefaultCellPadding = margin;
// Sayacı 17'ye çıkarırsanız tablo bozulur
// Çünkü bu sayfaya daha fazla yer verilemez
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	// Tabloda satırlar ve ardından satırlarda hücreler oluşturun
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// Sayfa Yüksekliği bilgisini alın
float PageHeight = (float)pdf.PageInfo.Height;
// Sayfa Üst & Alt kenar boşluğunun toplam yükseklik bilgisini alın,
// Masa Üstü kenar boşluğu ve masa yüksekliği.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Sayfa Yüksekliğini, Tablo Yüksekliğini, tablo Üst kenar boşluğunu ve Sayfa Üstünü Görüntüle
// Ve Alt kenar boşluğu bilgisi
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// Sayfa üst kenar boşluğu + Sayfa Alt kenar boşluğunun toplamını çıkarıp çıkarmadığımızı kontrol edin
// + Tablo Üstü kenar boşluğu ve tablo yüksekliği Sayfa yüksekliğinden ve daha az
// 10'dan büyük (ortalama bir satır 10'dan büyük olabilir)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// Değer 10'dan küçükse mesajı görüntüleyin.
	//Bu, başka bir satırın yerleştirilemeyeceğini ve yeni eklersek gösterir
	// Sıra, masa kırılacak. Satır yüksekliği değerine bağlıdır.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// PDF belgesini kaydedin
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Çözüm
Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF belgesinde tablo sonlarının nasıl belirleneceğini öğrendik. Kendi C# projelerinizde bir tablonun sayfa kenar boşluklarını aşıp aşmadığını kontrol etmek için bu adım adım kılavuzu kullanabilirsiniz.

### PDF dosyasındaki tablo sonunu belirlemek için SSS

#### S: Bir PDF belgesindeki tablo sonlarını belirlemenin amacı nedir?

C: Bir PDF belgesindeki tablo sonlarını belirlemenin amacı, tablonun sayfa kenar boşluklarını aşıp aşmadığını kontrol etmektir. Bu, tablo içeriğinin mevcut sayfa alanı dahilinde doğru şekilde görüntülenmesini sağlar. Tablo kırılmalarını tespit ederek içerik taşmasını yönetebilir ve tablo düzenini buna göre ayarlayabilirsiniz.

#### S: Tablonun üst kenar boşluğunu nasıl ayarlayabilirim?

 C: Sağlanan C# kaynak kodunda, tablonun üst kenar boşluğunu değerini değiştirerek ayarlayabilirsiniz.`table1.Margin.Top`mülk. Tablo için istenen üst kenar boşluğunu ayarlamak için değeri gerektiği gibi artırın veya azaltın.

#### S: Hücre renkleri ve yazı tipi boyutu gibi tablonun görünümünü özelleştirebilir miyim?

C: Evet, Aspose.PDF for .NET tarafından sağlanan çeşitli özellik ve yöntemleri kullanarak tablonun ve hücrelerinin görünümünü özelleştirebilirsiniz. Örneğin, hücre arka planı renklerini, yazı tipi boyutunu, yazı tipi ailesini, metin hizalamasını ve daha fazlasını değiştirebilirsiniz. Tablo görünümünün nasıl özelleştirileceği hakkında daha fazla bilgi için resmi belgelere bakın.

#### S: Tablo sayfa kenar boşluklarını aşarsa ne olur?

C: Tablonun sayfa kenar boşluklarını aşması içeriğin kesilmesine veya çakışmasına yol açarak PDF belgesinin daha az okunabilir ve düzenli olmasına neden olabilir. Tablo kopmalarını tespit ederek ve taşmayı yöneterek içeriğin mevcut sayfa alanında düzgün şekilde görüntülenmesini sağlayabilirsiniz.

#### S: Aynı PDF belgesinde birden fazla tablo için tablo sonlarını belirleyebilir miyim?

C: Evet, aynı PDF belgesinde birden fazla tablo için tablo sonlarını belirleyebilirsiniz. Analiz etmek istediğiniz her tablo için adımları tekrarlamanız ve içerik taşmasını önlemek için tablo düzenini gerektiği şekilde ayarlamanız yeterlidir.