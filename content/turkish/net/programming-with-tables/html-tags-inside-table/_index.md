---
title: PDF Dosyasındaki Tablo İçindeki HTML Etiketleri
linktitle: PDF Dosyasındaki Tablo İçindeki HTML Etiketleri
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzla .NET için Aspose.PDF kullanarak bir PDF'deki tablo hücrelerine HTML etiketlerinin nasıl yerleştirileceğini öğrenin. Dinamik, profesyonel PDF belgeleri oluşturun.
type: docs
weight: 100
url: /tr/net/programming-with-tables/html-tags-inside-table/
---
## giriiş

.NET'te PDF'lerle çalışırken, Aspose.PDF kitaplığı PDF belgeleri oluşturmak, düzenlemek ve dönüştürmek için olağanüstü bir araçtır. Aspose.PDF'nin sunduğu gelişmiş özelliklerden biri, bir PDF dosyasındaki tablo hücrelerinin içine HTML içeriği ekleme yeteneğidir. Bu eğitim, .NET için Aspose.PDF'yi kullanarak bunu nasıl başaracağınız konusunda size rehberlik edecektir. Bu kılavuzun sonunda, hücrelere gömülü HTML içeriğiyle tabloları dinamik olarak oluşturabileceksiniz.

## Ön koşullar

Adım adım kılavuza dalmadan önce, takip etmeniz için gerekli araç ve kaynaklara sahip olduğunuzdan emin olalım.

-  .NET için Aspose.PDF: Aspose.PDF'in en son sürümüne ihtiyacınız olacak.[Buradan indirin](https://releases.aspose.com/pdf/net/).
- .NET Ortamı: .NET Framework ile Visual Studio veya uyumlu başka bir IDE'nin kurulu olduğundan emin olun.
-  Lisans: Aspose.PDF'nin lisanslı bir sürümünü kullanmıyorsanız, bir tane edinebilirsiniz[geçici lisans](https://purchase.aspose.com/temporary-license/).
- C# Temel Anlayışı: C# ve nesne yönelimli programlamaya aşinalık faydalıdır.
- HTML Bilgisi: Bu eğitim için HTML yapısı hakkında biraz bilgi sahibi olmak faydalı olacaktır.

## Gerekli Paketleri İçe Aktarma

Kodu yazmaya başlamadan önce, gerekli ad alanlarını içe aktarmak çok önemlidir. Bu ad alanları, PDF belgelerini işlemek için kullanacağımız Aspose.PDF sınıfları ve yöntemleriyle çalışmamızı sağlar.

```csharp
using System;
using System.Data;
```

Şimdi görevi, sürecin her bir bölümünü açık ve öz bir şekilde açıkladığımız ayrıntılı adımlara bölelim.

## Adım 1: Belge Dizininizi Ayarlayın

İlk adım, belgeler dizininize giden yolu tanımlamaktır. PDF'yi oluşturduktan ve düzenledikten sonra buraya kaydedilecektir.

```csharp
// Belgeler dizinine giden yolu tanımlayın.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"`PDF dosyanızın kaydedilmesini istediğiniz gerçek yol ile. Bu, belge oluşturulduğunda onu kolayca bulabilmeniz için önemlidir.

## Adım 2: DataTable'ı Oluşturun ve HTML İçeriğiyle Doldurun

 Şimdi bir tane yaratıyoruz`DataTable` PDF'imizdeki tablonun içinde görüntülenecek verileri tutmak için. Bu`DataTable` HTML içeriğini depolayacaktır, örneğin`<li>` Hücrelerin içine yerleştirmek istediğimiz etiketler.

```csharp
// Bir DataTable oluşturun ve sütunlar ekleyin
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));
```

 Bir kez`DataTable` oluşturulduğunda, tabloda görünmesini istediğiniz HTML içeriğiyle doldurmanız gerekir. Bu durumda, adresli HTML liste öğeleri ekliyoruz.

```csharp
// HTML içerikli satırlar ekleyin
DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

Bu adım, tablo hücrelerinin HTML biçimli içerik içermesini ve bu içeriğin PDF belgesinin içinde düzgün bir şekilde işlenmesini sağlar.

## Adım 3: Yeni bir PDF Belgesi Oluşturun

Verilerimiz olduğunda, bir sonraki adım yeni bir PDF belgesi başlatmaktır. Bu belge, tablomuzu ekleyeceğimiz tuval görevi görecektir.

```csharp
// Yeni bir PDF Belgesi Başlat
Document doc = new Document();
doc.Pages.Add();
```

Bu basit kod parçacığı boş bir PDF belgesi oluşturur ve daha sonra tabloyu içerecek olan yeni bir sayfa ekler.

## Adım 4: Tabloyu Kurun

Şimdi, PDF belgesinin içinde tabloyu oluşturup ayarlayacağız. Bu tablo sütun genişliklerini ve kenarlık ayarlarını tanımlayacaktır.

```csharp
// Tablonun yeni bir örneğini başlatın
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
// Tablonun sütun genişliklerini ayarlayın
tableProvider.ColumnWidths = "400 50";
// Tablo kenarlık rengini Açık Gri olarak ayarla
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Tek tek tablo hücreleri için kenarlığı ayarlayın
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

Bu adımda, bir tabloyu başarıyla oluşturdunuz ve hem tablo hem de hücreleri için özel sütun genişlikleri ve kenarlıklar ayarladınız. Sütun genişlikleri, tablonun içindeki verilerin düzgün hizalanmasını sağlar.

## Adım 5: Dolguyu Tanımlayın ve Verileri İçeri Aktarın

 Tablonun görsel estetiğini geliştirmek için hücreler için dolgu tanımlayacağız. Ardından,`DataTable` HTML içerikli PDF tablosuna.

```csharp
// Tablo hücreleri için dolguyu ayarlayın
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

// DataTable'ı PDF Tablosuna Aktar
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

Kenar boşlukları ayarlayarak tablo hücrelerine biraz nefes alma alanı veriyoruz ve içeriği görsel olarak daha çekici hale getiriyoruz.`ImportDataTable` yöntem içeri çeker`DataTable` Daha önce oluşturduğumuz HTML içeriğinin hücrelere gömülmesini sağlayarak.

## Adım 6: Tabloyu PDF'e Ekleyin ve Kaydedin

Son olarak tabloyu PDF belgesinin ilk sayfasına ekleyip dosyayı kaydediyoruz.

```csharp
// Tabloyu PDF belgesinin ilk sayfasına ekleyin
doc.Pages[1].Paragraphs.Add(tableProvider);

// PDF belgesini kaydedin
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

Bu adımda HTML içeriği olan tablo PDF'in ilk sayfasına yerleştirilir ve dosya belirtilen dizine kaydedilir.

## Çözüm

Yukarıdaki adımları izleyerek, .NET için Aspose.PDF kullanarak bir PDF belgesindeki tablo hücrelerine HTML etiketlerini başarıyla yerleştirdiniz. Bu eğitim, .NET uygulamalarınızda dinamik ve görsel olarak çekici PDF belgeleri oluşturmak için Aspose.PDF'nin güçlü özelliklerinden nasıl yararlanabileceğinizi gösterir. Faturalar, raporlar veya HTML içerikli ayrıntılı tablolar oluşturuyor olun, bu yöntem PDF düzenleme ihtiyaçlarınız için sağlam bir temel sağlar.

## SSS

### Aspose.PDF tablo hücreleri içindeki karmaşık HTML içeriğini işleyebilir mi?  
Evet, Aspose.PDF listeler, resimler ve bağlantılar dahil olmak üzere tablo hücreleri içindeki çok çeşitli HTML etiketlerini işleyebilir ve oluşturabilir.

### Tablodaki sütunların boyutunu nasıl ayarlayabilirim?  
 Sütunların genişliğini kullanarak kontrol edebilirsiniz.`ColumnWidths` Her sütun için genişliği belirterek özelliği.

### Tablo hücrelerinin içindeki metni biçimlendirmek mümkün müdür?  
 Kesinlikle! HTML etiketlerini şu şekilde kullanabilirsiniz:`<b>`, `<i>` , Ve`<u>` Tablo hücrelerinin içindeki metni biçimlendirmek için içerik içinde.

### HTML içeriğim tablo hücresi için çok büyük olursa ne olur?  
İçerik hücrenin dışına taşarsa tablo otomatik olarak ayarlanır; ancak içeriğin nasıl görüntüleneceğini kontrol etmek için hücre boyutunu ve sözcük kaydırma seçeneklerini özelleştirebilirsiniz.

### Bir PDF belgesine birden fazla tablo ekleyebilir miyim?  
Evet, tablo ekleme adımlarını tekrarlayarak, her birini PDF'in yeni bir sayfasında veya bölümünde olmak üzere PDF belgesine birden fazla tablo ekleyebilirsiniz.