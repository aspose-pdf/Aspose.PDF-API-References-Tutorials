---
title: البحث والحصول على الصور
linktitle: البحث والحصول على الصور
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة للبحث والحصول على الصور في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 260
url: /ar/net/programming-with-images/search-and-get-images/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية البحث والحصول على الصور في مستند PDF باستخدام Aspose.PDF for .NET. اتبع هذه الخطوات لإجراء هذه العملية بسهولة.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي بيئة تطوير أخرى مثبتة ومهيأة.
- معرفة أساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET. يمكنك تنزيله من موقع Aspose الرسمي.

## الخطوة 1: تحميل مستند PDF

للبدء ، استخدم الكود التالي لتحميل مستند PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// افتح المستند
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

تأكد من توفير المسار الصحيح لوثيقة PDF الخاصة بك.

## الخطوة 2: البحث في مواقع الصور

للبحث في مواقع الصور في مستند PDF ، استخدم الكود التالي:

```csharp
// قم بإنشاء كائن ImagePlacementAbsorber للبحث عن مواقع الصور
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();

// تقبل الممتص لجميع صفحات الوثيقة
doc.Pages.Accept(abs);
```

سيجمع هذا مواقع الصور في الممتص.

## الخطوة 3: تصفح مواقع الصور واحصل على الصور وخصائصها

بعد ذلك ، سوف نتصفح مواقع الصور المجمعة ونحصل على الصور وخصائصها. استخدم الكود التالي:

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     //احصل على الصورة باستخدام كائن ImagePlacement
     XImage image = imagePlacement.Image;

     // عرض خصائص موقع الصورة
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal image resolution: " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);
}
```

سيؤدي هذا إلى تصفح جميع مواقع الصور والحصول على صور مطابقة وعرض خصائصها.

### عينة من التعليمات البرمجية المصدر للبحث والحصول على الصور باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "SearchAndGetImages.pdf");
// قم بإنشاء كائن ImagePlacementAbsorber لإجراء بحث عن موضع الصورة
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// تقبل الممتص لجميع الصفحات
doc.Pages.Accept(abs);
// قم بإجراء حلقة عبر جميع ImagePlacements ، واحصل على خصائص Image و ImagePlacement
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// احصل على الصورة باستخدام كائن ImagePlacement
	XImage image = imagePlacement.Image;
	// عرض خصائص وضع الصور لجميع المواضع
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

## خاتمة

تهنئة ! لقد نجحت في البحث والحصول على صور في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن تطبيق هذه الطريقة على مشاريعك الخاصة لاستخراج الصور والحصول على خصائصها من ملفات PDF.