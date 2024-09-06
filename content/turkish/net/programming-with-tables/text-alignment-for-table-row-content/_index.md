---
title: Tablo Satır İçeriği İçin Metin Hizalaması
linktitle: Tablo Satır İçeriği İçin Metin Hizalaması
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF tablosundaki satır içeriğinin nasıl hizalanacağını öğrenin.
type: docs
weight: 210
url: /tr/net/programming-with-tables/text-alignment-for-table-row-content/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesinin tablosundaki bir satırın içeriğini adım adım hizalamanıza rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve nasıl uygulayacağınızı göstereceğiz.

## Adım 1: PDF belgesinin oluşturulması
Öncelikle PDF dokümanını oluşturacağız:

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Adım 2: Tablo başlatma
Daha sonra tabloyu başlatacağız:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Adım 3: Tablo kenarlık rengini ayarlama
Tablo kenarlık rengini yapılandıracağız:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Adım 4: Tablo hücresi kenarlığını yapılandırma
Tablo hücresi sınırını yapılandıracağız:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Adım 5: Tabloya 10 satır eklemek için döngü
Şimdi tabloya 10 satır eklemek için bir döngü kullanacağız:

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## Adım 6: Dikey çizgi hizalamasını yapılandırma
Tablonun satırlarının dikey hizalamasını yapılandıracağız:

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## Adım 7: Satır hücrelerine içerik ekleme
Satır hücrelerine içerik ekleyeceğiz:

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## Adım 8: Tabloyu belge sayfasına ekleme
Şimdi tabloyu belge sayfasına ekleyelim:

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## Adım 9: PDF belgesini kaydetme
Son olarak PDF dokümanını kaydedeceğiz:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### .NET için Aspose.PDF kullanılarak Tablo Satır İçeriği için Metin Hizalaması için örnek kaynak kodu

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF belgesi oluştur
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Tablonun yeni bir örneğini başlatır
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Tablo kenarlık rengini AçıkGri olarak ayarlayın
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// tablo hücreleri için kenarlığı ayarla
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// 10 satır eklemek için bir döngü oluşturun
for (int row_count = 0; row_count < 10; row_count++)
{
	// tabloya satır ekle
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
// Giriş belgesinin ilk sayfasına tablo nesnesi ekle
tocPage.Paragraphs.Add(table);
// Tablo nesnesini içeren güncellenmiş belgeyi kaydet
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## Çözüm
Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF belgesinde bir tablodaki satırın içeriklerini nasıl hizalayacağınızı öğrendiniz. Bu adım adım kılavuz size bir belge oluşturmayı, bir tabloyu başlatmayı, kenarlığı ve hizalamayı yapılandırmayı, içerik eklemeyi ve PDF belgesini kaydetmeyi gösterdi. Artık bu bilgiyi kendi projelerinize uygulayabilirsiniz.

### SSS

#### S: Tablo hücrelerinin içeriklerini yatay olarak nasıl hizalayabilirim?

 A: Tablo hücrelerinin içeriklerini yatay olarak hizalamak için,`HorizontalAlign` hücrenin özelliği`TextState` nesne. Örneğin, metni ortaya hizalamak için şunu kullanın:`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` Ayrıca bunu şu şekilde de ayarlayabilirsiniz:`HorizontalAlignment.Left` veya`HorizontalAlignment.Right` sırasıyla sol ve sağ hizalama için.

#### S: Tablodaki her bir hücreye farklı kenarlık stilleri ve renkleri uygulayabilir miyim?

 A: Evet, tablodaki her bir hücreye farklı kenarlık stilleri ve renkleri uygulayabilirsiniz. Belirli bir hücre için kenarlığı özelleştirmek için,`cell.Border` yeni bir mülke`BorderInfo`Nesneyi, kenarlık kenarları, genişliği ve rengi gibi istediğiniz ayarlarla oluşturun.

#### S: Hücreler içindeki tablo içeriğinin dikey hizalamasını nasıl ayarlayabilirim?

 A: Hücreler içindeki tablo içeriğinin dikey hizalamasını,`VerticalAlignment` satırın özelliği`VerticalAlignment.Center`, `VerticalAlignment.Top` , veya`VerticalAlignment.Bottom`Bu özellik, o satırdaki tüm hücrelerin dikey hizalamasını kontrol eder.

#### S: Tabloya dinamik olarak daha fazla sütun veya satır eklemek mümkün müdür?

 A: Evet, tabloya dinamik olarak daha fazla sütun ve satır ekleyebilirsiniz.`table.Rows.Add()` yeni satırlar ekleme yöntemi ve`row.Cells.Add()` satırlara yeni hücreler ekleme yöntemi. Bunu döngüler içinde veya özel gereksinimlerinize göre yapabilirsiniz.

#### S: Belirli hücreler veya tüm tablo için arka plan rengini nasıl ayarlayabilirim?

 A: Belirli hücreler veya tüm tablo için bir arka plan rengi ayarlamak için şunu kullanın:`BackgroundColor` mülkiyeti`Cell` veya`Table` nesne. Örneğin, bir hücrenin arka plan rengini ayarlamak için şunu kullanın:`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.