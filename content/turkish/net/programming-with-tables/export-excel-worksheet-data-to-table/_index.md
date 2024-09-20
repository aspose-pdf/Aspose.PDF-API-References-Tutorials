---
title: Excel Çalışma Sayfası Verilerini Tabloya Aktar
linktitle: Excel Çalışma Sayfası Verilerini Tabloya Aktar
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak Excel çalışma sayfası verilerini PDF tablosuna nasıl aktaracağınızı öğrenin. Kod örnekleri, ön koşullar ve faydalı ipuçları içeren adım adım eğitim.
type: docs
weight: 70
url: /tr/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
## giriiş

Hiç Excel çalışma sayfasından bir PDF dosyasına, düzgün bir şekilde tablo biçiminde düzenlenmiş bir şekilde veri aktarmanız gerekti mi? Excel'de bir sürü veriniz olduğunu ancak bunları profesyonel görünümlü bir PDF olarak paylaşmanız gerektiğini düşünün. Kulağa karmaşık gelebilir, değil mi? Ancak .NET için Aspose.PDF ile bu görevi çok kolay hale getirebilirsiniz. Bu eğitimde, .NET için Aspose.PDF kullanarak Excel çalışma sayfası verilerini bir PDF belgesinin içindeki bir tabloya aktarma sürecini adım adım ele alacağız. Her şeyi parçalara ayırarak sizi adım adım yönlendireceğiz, böylece bu konuda yeni olsanız bile sonunda kendinizi bir profesyonel gibi hissedeceksiniz.

## Ön koşullar

Kodlamaya başlamadan önce birkaç şeyi ayarlayalım:

1.  Aspose.PDF for .NET Library – En son sürümün yüklü olduğundan emin olun.[buradan indirin](https://releases.aspose.com/pdf/net/).
2.  Aspose.Cells for .NET Library – Excel işlemlerini halletmek için buna ihtiyacınız olacak. Buradan indirin[Burada](https://releases.aspose.com/cells/net/).
3. .NET Geliştirme Ortamı – Visual Studio gibi bir araç kodlama için mükemmel bir şekilde çalışacaktır.
4. Excel Dosyası – Dışa aktarmak istediğiniz verilerin bulunduğu bir Excel dosyanız hazır olsun.

 Aspose.PDF ve Aspose.Cells kitaplıklarınız yoksa, bir[ücretsiz deneme](https://releases.aspose.com/).

## Paketleri İçe Aktar

Başlamak için, projenize hem Aspose.PDF hem de Aspose.Cells kütüphanelerini yüklediğinizden emin olun. Bunları Visual Studio'daki NuGet Paket Yöneticisi'ni kullanarak yükleyebilirsiniz.

Gerekli paketleri C# kodunuza nasıl aktaracağınız aşağıda açıklanmıştır:

```csharp
using System.Data;
using System.IO;
using System.Linq;
```

Artık ön koşullar sağlandığı için, Excel sayfasından PDF belgesindeki bir tabloya veri aktarma sürecini inceleyelim.

## Adım 1: Excel Çalışma Kitabını yükleyin

Başlamak için Excel çalışma kitabınızı programa yüklemeniz gerekir. Bu adımda Excel dosyasını açmak için Aspose.Cells'i kullanacağız.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Excel çalışma kitabını yükleyin
Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

 Açıklama: Burada, Excel dosyamızın bulunduğu dizin yolunu belirtiyoruz ve çalışma kitabını kullanarak yüklüyoruz.`Aspose.Cells.Workbook` Ayarlamayı unutmayın`"YOUR DOCUMENT DIRECTORY"` dosyanızın konumunu belirtmek için.

## Adım 2: İlk Çalışma Sayfasına Erişim

Çalışma kitabını yükledikten sonra verilerimizin saklandığı ilk çalışma sayfasına erişmemiz gerekiyor.

```csharp
// Excel dosyasındaki ilk çalışma sayfasına erişim
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

Açıklama: Bu adım basittir; dışa aktarılacak verileri içeren çalışma kitabından ilk çalışma sayfasını alırız.

## Adım 3: Verileri DataTable'a Aktar

Şimdi Excel sayfasındaki verileri, verilerin PDF'e aktarılmasında aracı görevi görecek olan DataTable nesnesine aktaralım.

```csharp
// 1. hücreden başlayarak 7 satır ve 2 sütunun içeriğini DataTable'a aktarma
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

 Açıklama:`ExportDataTable` yöntem, çalışma sayfasının ilk hücresinden başlayarak verileri çıkarır ve tüm satır ve sütunlara yayılır. Bu veriler daha sonra bir`DataTable` daha sonraki kullanımlar için.

## Adım 4: Yeni bir PDF Belgesi Oluşturun

Daha sonra Aspose.PDF kullanarak yeni bir PDF belgesi oluşturmamız gerekiyor.

```csharp
// Bir Belge örneğini örneklendirin
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Belge örneğinde bir sayfa oluşturun
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

 Açıklama: Burada yeni bir tane başlatıyoruz`Aspose.Pdf.Document`ve buna bir sayfa ekleyin. Bu sayfa daha sonra Excel verilerinden oluşturduğumuz tabloyu içerecektir.

## Adım 5: PDF'de bir Tablo Nesnesi Oluşturun

Şimdi PDF dokümanının içerisinde tablo oluşturmaya geçelim.

```csharp
// Bir Tablo nesnesi oluşturun
Aspose.Pdf.Table table = new Aspose.Pdf.Table();

// Tablo nesnesini sayfanın paragraf koleksiyonuna ekleyin
page.Paragraphs.Add(table);
```

 Açıklama: Bir`Aspose.Pdf.Table` nesneyi seçin ve sayfanın paragraf koleksiyonuna ekleyin; bu, tablonun sayfada görüntülenmesini sağlar.

## Adım 6: Sütun Genişliklerini ve Kenarlıklarını Ayarlayın

PDF'deki tabloların tanımlanmış sütun genişliklerine ihtiyacı vardır. Ayrıca tabloyu daha okunabilir hale getirmek için kenarlıklar da ekleyeceğiz.

```csharp
// Tablonun sütun genişliklerini ayarlayın
table.ColumnWidths = "40 100 100";

// Varsayılan hücre kenarlığını ayarla
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

 Açıklama: Üç sütunun genişliklerini ayarlıyoruz ve tüm hücrelere varsayılan olarak kalınlığı olan bir kenarlık veriyoruz.`0.1F`.

## Adım 7: Verileri DataTable'dan PDF Tablosuna Aktarın

Şimdi sıra DataTable'daki verileri PDF tablomuza aktarmaya geldi.

```csharp
// DataTable'dan Tablo nesnesine veri aktarın
table.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Açıklama:`ImportDataTable`yöntem tüm verileri aktarır`DataTable` PDF tablosuna. Bu, tabloyu Excel sayfanızdaki verilerle doldurur.

## Adım 8: Başlık Satırını Biçimlendirin

Tablonun başlık satırını, arka plan rengini, yazı tipini ve hizalamasını değiştirerek biçimlendirelim.

```csharp
// Tablodan ilk satırı al
Aspose.Pdf.Row headerRow = table.Rows[0];

// Başlık satırı için stil ayarlayın
foreach (Aspose.Pdf.Cell cell in headerRow.Cells)
{
    cell.BackgroundColor = Color.Blue;
    cell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    cell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    cell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}
```

Açıklama: İlk satırdaki (başlık) tüm hücreleri dolaşıp arka plan renklerini maviye, metin rengini sarıya ayarlıyoruz ve metni ortaya hizalıyoruz.

## Adım 9: Kalan Satırları Şekillendirin

Başlık ile diğer satırlar arasındaki farkı ortaya çıkarmak için, kalan satırlar için farklı bir stil ekleyelim.

```csharp
for (int i = 1; i <= dataTable.Rows.Count; i++)
{
    foreach (Aspose.Pdf.Cell cell in table.Rows[i].Cells)
    {
        cell.BackgroundColor = Color.Gray;
        cell.DefaultCellTextState.ForegroundColor = Color.White;
    }
}
```

Açıklama: Başlık hariç tüm satırlar için gri arka plan ve beyaz metin rengi belirledik.

## Adım 10: PDF Belgesini Kaydedin

Son olarak tabloyu içeren PDF belgesini kaydedin.

```csharp
// PDF'yi kaydet
pdfDocument.Save(dataDir + "Exceldata_toPdf_table.pdf");
```

Açıklama: PDF'yi belirtilen dizine kaydediyoruz. Voilà! Excel verileriniz artık güzel biçimlendirilmiş bir PDF tablosunun içinde.

## Çözüm

İşte oldu! Sadece birkaç adımda, Aspose.PDF for .NET kullanarak bir Excel çalışma sayfasından bir PDF içindeki tabloya veri aktardınız. İşlemi parçalara ayırıp yol boyunca biçimlendirerek çıktınızı özelleştirebilir ve verilerinizin temiz ve profesyonel görünmesini sağlayabilirsiniz. Böylece bir dahaki sefere birisi size bir Excel dosyası verip bir PDF raporu istediğinde ne yapmanız gerektiğini tam olarak biliyorsunuz.

## SSS

### Tabloyu daha fazla özelleştirebilir miyim?
Kesinlikle! Renkleri, yazı tiplerini, hizalamayı değiştirebilir ve hatta belirli hücrelere kenarlıklar ekleyebilirsiniz.

### Aspose.PDF for .NET ücretsiz mi?
 Ücretsiz deneme sürümü sunar, ancak uzun süreli kullanım için bir lisansa ihtiyacınız olacak.[buradan satın al](https://purchase.aspose.com/buy).

### Sadece belirli satır ve sütunları mı dışa aktarabilirim?
 Evet, parametreleri değiştirebilirsiniz`ExportDataTable` Belirli aralıkları dışa aktarma yöntemi.

### Bu büyük Excel dosyalarında işe yarıyor mu?
Evet, Aspose.Cells büyük Excel dosyalarını etkili bir şekilde işleyecek şekilde tasarlanmıştır.

### PDF'e nasıl daha fazla sayfa ekleyebilirim?
 Kullanabilirsiniz`pdfDocument.Pages.Add()` İhtiyacınız kadar sayfa ekleyebilirsiniz.