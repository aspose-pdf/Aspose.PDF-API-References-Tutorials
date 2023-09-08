---
title: PDF Belgesindeki Birden Çok Tabloyu Kaldırma
linktitle: PDF Belgesindeki Birden Çok Tabloyu Kaldırma
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF belgesindeki birden fazla tabloyu nasıl kaldıracağınızı öğrenin.
type: docs
weight: 150
url: /tr/net/programming-with-tables/remove-multiple-tables/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF belgesindeki birden fazla tabloyu kaldırmak için size adım adım rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve size nasıl uygulayacağınızı göstereceğiz.

## 1. Adım: Mevcut PDF belgesini yükleme
Öncelikle mevcut PDF belgesini aşağıdaki kodu kullanarak yüklemeniz gerekir:

```csharp
// Belgeler dizininin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Mevcut PDF belgesini yükleyin
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");
```

## Adım 2: Tabloları bulmak için TableAbsorber nesnesini oluşturma
Daha sonra, PDF belgesindeki tabloları bulmak için bir TableAbsorber nesnesi oluşturacağız:

```csharp
// Tabloları bulmak için bir TableAbsorber nesnesi oluşturun
TableAbsorber absorber = new TableAbsorber();
```

## Adım 3: Emicinin bulunduğu ikinci sayfayı ziyaret edin
Şimdi emiciyi kullanarak PDF belgesinin ikinci sayfasını ziyaret edeceğiz:

```csharp
// Emicinin bulunduğu ikinci sayfayı ziyaret edin
absorb.Visit(pdfDocument.Pages[1]);
```

## Adım 4: Tablo koleksiyonunun bir kopyasını alma
Tabloları bırakabilmek için tablo koleksiyonunun bir kopyasını almamız gerekir:

```csharp
//Tablo koleksiyonunun bir kopyasını alın
AbsorbedTable[] tables = new AbsorbedTable[absorb.TableList.Count];
absorb.TableList.CopyTo(tables, 0);
```

## 5. Adım: Koleksiyonun kopyasına göz atın ve tabloları kaldırın
Şimdi tablo koleksiyonunun kopyasını tekrarlayalım ve bunları birer birer kaldıralım:

```csharp
// Koleksiyonun kopyasına göz atın ve tabloları kaldırın
foreach(AbsorbedTable table in tables)
     absorb.Remove(table);
```

## Adım 6: Belgeyi kaydetme
Son olarak değiştirilen PDF belgesini kaydediyoruz:

```csharp
// Belgeyi kaydet
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

### Aspose.PDF for .NET kullanarak Çoklu Tabloları Kaldırmak için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mevcut PDF belgesini yükle
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");

// Tabloları bulmak için TableAbsorber nesnesi oluşturun
TableAbsorber absorber = new TableAbsorber();

// Emici ile ikinci sayfayı ziyaret edin
absorber.Visit(pdfDocument.Pages[1]);

// Tablo koleksiyonunun kopyasını alın
AbsorbedTable[] tables = new AbsorbedTable[absorber.TableList.Count];
absorber.TableList.CopyTo(tables, 0);

// Koleksiyonun kopyasında dolaşın ve tabloları kaldırın
foreach (AbsorbedTable table in tables)
	absorber.Remove(table);

// Belgeyi kaydet
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

## Çözüm
Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF belgesindeki birden fazla tabloyu nasıl kaldıracağınızı öğrendiniz. Bu adım adım kılavuz, belgeyi nasıl yükleyeceğinizi, tabloları nasıl bulacağınızı ve kaldıracağınızı gösterdi. Artık bu bilgiyi kendi projelerinize uygulayabilirsiniz.

### PDF belgesindeki birden fazla tabloyu kaldırmak için SSS

#### S: Bir PDF belgesindeki tüm tablolar yerine belirli tabloları kaldırabilir miyim?

C: Evet, Aspose.PDF for .NET'i kullanarak bir PDF belgesindeki tüm tablolar yerine belirli tabloları kaldırabilirsiniz. Verilen örnekte ikinci sayfadaki tüm tablolar kaldırılmıştır. Ancak gereksinimlerinize göre belirli tabloları hedeflemek ve kaldırmak için kodu değiştirebilirsiniz. Bunu yapmak için kaldırmak istediğiniz tabloları tanımlamanız ve ardından çağrı yapmanız gerekir.`absorber.Remove(table)` Silmek istediğiniz her bir tablo için yöntem.

#### S: PDF belgesindeki birden çok sayfadaki tabloları nasıl kaldırabilirim?

 C: PDF belgesindeki birden çok sayfadaki tabloları kaldırmak için işlemi her sayfa için tekrarlamanız gerekir. Verilen örnekte kod, tabloları yalnızca ikinci sayfadan şunu kullanarak kaldırır:`pdfDocument.Pages[1]` . Diğer sayfalardan tabloları kaldırmak için, sayfa dizinini değiştirerek istediğiniz her sayfa için benzer kodu kullanabilirsiniz (örn.`pdfDocument.Pages[2]`, `pdfDocument.Pages[3]`, ve benzeri).

#### S: Belirtilen sayfada bulunmayan bir tabloyu kaldırmaya çalışırsam ne olur?

C: Belirtilen sayfada bulunmayan bir tabloyu kaldırmaya çalışırsanız bu bir hatayla sonuçlanmayacaktır.`absorber.Remove(table)` yöntemi yalnızca kaldırma isteğini yok sayar ve PDF belgesi değişmeden kalır.

#### S: Belgeyi kaydettikten sonra tabloların kaldırılmasını geri alabilir miyim?

C: Hayır, tabloları kaldırdıktan sonra değiştirilen PDF belgesini kaydettiğinizde değişiklikler kalıcı olur ve tabloların kaldırılmasını geri alamazsınız. Bu nedenle, orijinal veriler kaybolacağından bir PDF belgesinden içerik kaldırırken dikkatli olmak önemlidir.

#### S: Bu yöntem kullanılarak kaldırılabilecek tablo türlerinde herhangi bir kısıtlama var mı?

C: Bu eğitimde gösterilen yöntem, tablonun içeriğine bağlı olarak kısıtlama olmaksızın bir PDF belgesinden tabloları kaldırmanıza olanak tanır. Ancak tabloların kaldırılmasının kalan içeriği ve okunabilirliği olumsuz etkilememesini sağlamak için belgenin genel yapısını ve düzenini dikkate almak önemlidir.