---
title: Katman Ekle
linktitle: Katman Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyalarına nasıl katman ekleyeceğinizi öğrenin. Katmanlı PDF'ler oluşturmak ve kaydetmek için kod eğitimlerini içeren adım adım kılavuz.
type: docs
weight: 20
url: /tr/net/programming-with-document/addlayers/
---

Bir PDF dosyasına katman eklemek için Aspose.PDF for .NET'i kullanacağız. Bu kitaplık, .NET uygulamalarında PDF dosyalarıyla verimli bir şekilde çalışmamızı sağlar. Aspose.PDF for .NET kullanarak katman eklemek için aşağıdaki adım adım talimatları izleyin.

## 1. Adım: Yeni bir PDF Belgesi Oluşturun

 Yeni bir örneğini oluşturarak başlayın.`Document` Aspose.PDF for .NET tarafından sağlanan sınıf. Bu, katmanları ekleyeceğimiz PDF belgesi olarak hizmet edecektir.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

## Adım 2: Belgeye Sayfa Ekleyin

Ardından, kullanarak belgeye bir sayfa ekleyin.`Add` yöntemi`Pages` koleksiyonunda`Document` sınıf.

```csharp
Page page = doc.Pages.Add();
```

## 3. Adım: Sayfaya Katmanlar Oluşturun ve Ekleyin

 Örneklerini oluşturun`Layer` PDF dosyasına eklemek istediğiniz her katman için sınıf. Her katman için benzersiz bir tanımlayıcı ve bir ad belirtin.

```csharp
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new List<Layer>();
page.Layers.Add(layer);

layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);

layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
```

Bu eğitimde, sayfaya farklı renk ve adlara sahip üç katman ekledik.

## 4. Adım: PDF Dosyasını Kaydedin

 Değiştirilen PDF dosyasını kullanarak kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);
```

Bu kod, değiştirilen PDF dosyasını belirtilen dizine kaydedecektir.

### Aspose.PDF for .NET kullanarak PDF Sayfalarına Katman Eklemek için örnek kaynak kodu

```csharp            
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new  List<Layer>();
page.Layers.Add(layer);
layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);

```

## Çözüm

Bu makalede, Aspose.PDF for .NET kullanarak PDF dosyalarına katman eklemek için adım adım bir kılavuz sağladık. Talimatları izleyerek ve sağlanan kod eğitimlerini kullanarak, katmanları PDF belgelerinize kolayca dahil edebilirsiniz. Katmanlar, kullanıcılarınız için daha etkileşimli ve özelleştirilebilir bir deneyim sunarak içeriğin görünürlüğünü düzenlemenize ve kontrol etmenize olanak tanır.