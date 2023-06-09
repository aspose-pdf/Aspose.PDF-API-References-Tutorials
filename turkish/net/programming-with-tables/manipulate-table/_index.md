---
title: Tabloyu Yönet
linktitle: Tabloyu Yönet
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerindeki tabloları kolayca değiştirin.
type: docs
weight: 130
url: /tr/net/programming-with-tables/manipulate-table/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki tabloları işlemek için adım adım ilerleyeceksiniz. Tablolar, PDF belgelerinde ortak bir öğedir ve içeriklerini programlı olarak değiştirebilmek, çeşitli senaryolarda oldukça faydalı olabilir. Süreci göstermek için sağlanan C# kaynak kodunu kullanacağız.

## Gereksinimler

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya başka herhangi bir C# geliştirme ortamı kurulu.
- Aspose.PDF for .NET kitaplığı projenize referans olarak eklendi.

Şimdi Aspose.PDF for .NET kullanarak bir PDF belgesindeki tabloları işlemek için gereken adımları inceleyelim.

## 1. Adım: PDF Belgesini Yükleme

İlk adım, mevcut PDF belgesini C# uygulamanıza yüklemektir. Belgenizin bulunduğu dizine giden yolu sağlamanız gerekir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "input.pdf");
```

"BELGE DİZİNİNİZİ", PDF belgenizin bulunduğu dizinin gerçek yolu ile değiştirin.

## 2. Adım: Belgede Tablo Bulma

Tabloları manipüle etmek için, onları PDF belgesinde bulmamız gerekir. Aspose.PDF for .NET, belgeden tabloları çıkarmamıza izin veren bir TableAbsorber sınıfı sağlar. TableAbsorber sınıfının bir örneğini oluşturacağız ve belgenin istenen sayfasını ziyaret edeceğiz.

```csharp
TableAbsorber absorber = new TableAbsorber();
absorb.Visit(pdfDocument.Pages[1]);
```

Bu örnekte, belgenin ilk sayfasını ziyaret ediyoruz. Sayfa numarasını ihtiyaçlarınıza göre değiştirebilirsiniz.

## 3. Adım: Tablo Hücrelerine ve Metin Parçalarına Erişim

Tablolara sahip olduğumuzda, manipülasyon için hücrelerine ve metin parçalarına erişebiliriz. Sağlanan kaynak kodda, ilk tabloya, ilk satırının ilk hücresine ve o hücre içindeki ikinci metin parçasına erişiyoruz.

```csharp
TextFragment fragment = absorb.TableList[0].RowList[0].CellList[0].TextFragments[1];
```

Özel ihtiyaçlarınıza göre farklı tabloları, hücreleri veya metin parçalarını hedeflemek için kodu değiştirebilirsiniz.

## 4. Adım: Tablo Metnini Değiştirme

Erişilen metin parçasıyla artık içeriğini değiştirebiliriz. Verilen örnekte, metni "hi world" olarak değiştiriyoruz.

```csharp
fragment.Text = "hi world";
```

"Merhaba dünya" ifadesini istediğiniz metinle değiştirmekten çekinmeyin.

## Adım 5: Değiştirilen Belgeyi Kaydetme

İstenen değişiklikler yapıldıktan sonra, değiştirilen PDF belgesini kaydetmemiz gerekir.

```csharp
dataDir = dataDir + "ManipulateTable_out.pdf";
pdfDocument.Save(dataDir);
```

Değiştirilen belge için yol ve dosya adını sağladığınızdan emin olun.


### Aspose.PDF for .NET kullanarak Tabloyu Yönetmek için örnek kaynak kodu

```csharp
try
{
	
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Mevcut PDF dosyasını yükle
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// Tabloları bulmak için TableAbsorber nesnesi oluşturun
	TableAbsorber absorber = new TableAbsorber();

	// Emici ile ilk sayfayı ziyaret edin
	absorber.Visit(pdfDocument.Pages[1]);

	// Sayfadaki ilk tabloya, ilk hücrelerine ve içindeki metin parçalarına erişin
	TextFragment fragment = absorber.TableList[0].RowList[0].CellList[0].TextFragments[1];

	// Hücredeki ilk metin parçasının metnini değiştir
	fragment.Text = "hi world";
	dataDir = dataDir + "ManipulateTable_out.pdf";
	pdfDocument.Save(dataDir);
	
	Console.WriteLine("\nTable manipulated successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesindeki tabloları nasıl değiştireceğimizi öğrendik. Adım adım kılavuzu izleyerek bir PDF belgesini kolayca yükleyebilir, tabloları bulabilir, hücrelere ve metin parçalarına erişebilir, tablo içeriğini değiştirebilir ve değiştirilen belgeyi kaydedebilirsiniz. Bu yaklaşım, PDF belgelerinde tablo manipülasyonu ile uğraşırken esneklik ve verimlilik sağlar.