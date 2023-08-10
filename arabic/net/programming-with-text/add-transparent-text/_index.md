---
title: أضف نصًا شفافًا
linktitle: أضف نصًا شفافًا
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة نص شفاف إلى مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 100
url: /ar/net/programming-with-text/add-transparent-text/
---

سيرشدك هذا البرنامج التعليمي خلال عملية إضافة نص شفاف إلى مستند PDF باستخدام Aspose.PDF for .NET. يوضح كود المصدر C # المقدم الخطوات الضرورية.

## متطلبات
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C # آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: قم بإعداد المشروع
1. قم بإنشاء مشروع C # جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية حيث تريد إضافة نص شفاف ، أضف ما يلي باستخدام التوجيهات في أعلى الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود ، حدد موقع السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: إنشاء مثيل مستند جديد
 تجسيد ملف`Document` عن طريق إضافة السطر التالي من التعليمات البرمجية:

```csharp
Document doc = new Document();
```

## الخطوة 5: أضف صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام ملف`Add` طريقة`Pages` مجموعة. في الكود المقدم ، يتم تخصيص الصفحة الجديدة للمتغير`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## الخطوة 6: إنشاء كائن الرسم البياني
 إنشاء ملف`Graph` مع عرض وارتفاع محددين.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## الخطوة 7: قم بإنشاء مستطيل بالشفافية
 قم بإنشاء مستطيل بأبعاد محددة واضبط لون التعبئة على لون شفاف باستخدام`Color.FromRgb` طريقة.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## الخطوة 8: أضف كائن الرسم البياني إلى الصفحة
 أضف ال`Graph` تعترض على مجموعة فقرات الصفحة.

```csharp
page.Paragraphs.Add(canvas);
```

## الخطوة 9: تعيين موضع كائن الرسم البياني
 تعيين`IsChangePosition` ممتلكات`Graph` يعترض على`false` لمنعه من تغيير الموقف.

```csharp
canvas. IsChangePosition = false;
```

## الخطوة 10: قم بإنشاء جزء نصي بشفافية
 إنشاء`TextFragment` الكائن وتعيين محتواه على النص المطلوب. تعيين`ForegroundColor` ممتلكات`TextState` للون مع الشفافية باستخدام`Color.FromArgb` طريقة.

```csharp
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
text.TextState.ForegroundColor = color;
page.Paragraphs.Add(text);
```

## الخطوة 11: احفظ مستند PDF
 احفظ مستند PDF باستخدام ملف`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "AddTransparentText_out.pdf");
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لإضافة نص شفاف باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء مثيل المستند
Document doc = new Document();
// إنشاء صفحة لمجموعة صفحات من ملف PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// إنشاء كائن الرسم البياني
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// إنشاء مثيل مستطيل بأبعاد معينة
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
// إنشاء كائن لون من قناة ألوان ألفا
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// أضف المستطيل إلى مجموعة الأشكال لكائن الرسم البياني
canvas.Shapes.Add(rect);
// أضف كائن الرسم البياني إلى مجموعة فقرات كائن الصفحة
page.Paragraphs.Add(canvas);
// قم بتعيين القيمة على عدم تغيير موضع كائن الرسم البياني
canvas.IsChangePosition = false;
// إنشاء مثيل TextFragment مع قيمة العينة
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// إنشاء كائن لون من قناة ألفا
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
// تعيين معلومات اللون لمثيل النص
text.TextState.ForegroundColor = color;
// إضافة نص إلى مجموعة فقرات نسخة الصفحة
page.Paragraphs.Add(text);
dataDir = dataDir + "AddTransparentText_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```


## خاتمة
لقد نجحت في إضافة نص شفاف إلى مستند PDF الخاص بك باستخدام Aspose.PDF for .NET. يمكن الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.