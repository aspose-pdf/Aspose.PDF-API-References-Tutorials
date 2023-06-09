---
title: التحكم في المستطيل Z Order
linktitle: التحكم في المستطيل Z Order
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية التحكم في ترتيب المستطيلات على شكل حرف Z في ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 40
url: /ar/net/programming-with-graphs/control-rectangle-z-order/
---

في هذا البرنامج التعليمي ، سنرشدك خلال التعليمات البرمجية المصدر C # التالية خطوة بخطوة للتحكم في ترتيب Z للمستطيلات باستخدام Aspose.PDF for .NET.

تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك قبل أن تبدأ. لديك أيضًا معرفة أساسية ببرمجة C #.

## الخطوة 1: إعداد دليل المستند

في كود المصدر المقدم ، تحتاج إلى تحديد الدليل الذي تريد حفظ ملف PDF الناتج فيه. قم بتغيير متغير "dataDir" إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء كائن مستند وإضافة صفحة

نقوم بإنشاء مثيل لفئة المستند وإضافة صفحة إلى هذا المستند.

```csharp
Document doc1 = new Document();
Aspose.Pdf.Page page1 = doc1.Pages.Add();
```

## الخطوة 3: إعداد حجم الصفحة

قمنا بتعيين حجم صفحة PDF باستخدام طريقة SetPageSize.

```csharp
page1.SetPageSize(375, 300);
```

## الخطوة 4: ضبط هوامش الصفحة

يمكننا تكوين هوامش الصفحة باستخدام خصائص كائن PageInfo.

```csharp
page1.PageInfo.Margin.Left = 0;
page1.PageInfo.Margin.Top = 0;
```

## الخطوة 5: أضف مستطيلات بترتيب Z محدد

نقوم بإنشاء وإضافة مستطيلات إلى الصفحة بألوان مختلفة وأوامر Z محددة.

```csharp
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
```

## الخطوة 6: حفظ ملف PDF الناتج

أخيرًا ، نحفظ ملف PDF الناتج باسم "ControlRectangleZOrder_out.pdf" في الدليل المحدد.

```csharp
doc1.Save(dataDir);
```
### نموذج التعليمات البرمجية المصدر لـ Control Rectangle Z Order باستخدام Aspose.PDF for .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء كائن فئة المستند
Document doc1 = new Document();
/// إضافة صفحة إلى مجموعة صفحات من ملف PDF
Aspose.Pdf.Page page1 = doc1.Pages.Add();
// ضبط حجم صفحة PDF
page1.SetPageSize(375, 300);
//قم بتعيين الهامش الأيسر لكائن الصفحة على 0
page1.PageInfo.Margin.Left = 0;
// قم بتعيين الهامش العلوي لكائن الصفحة على 0
page1.PageInfo.Margin.Top = 0;
// قم بإنشاء مستطيل جديد بلون أحمر ، وترتيب Z على شكل 0 وأبعاد معينة
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
// قم بإنشاء مستطيل جديد بلون أزرق ، وترتيب Z على شكل 0 وأبعاد معينة
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
// قم بإنشاء مستطيل جديد مع Color as Green و Z-Order كـ 0 وأبعاد معينة
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
dataDir = dataDir + "ControlRectangleZOrder_out.pdf";
// حفظ ملف PDF الناتج
doc1.Save(dataDir);

```

## خاتمة

في هذا البرنامج التعليمي ، شرحنا كيفية التحكم في ترتيب Z للمستطيلات باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام هذه المعرفة لترتيب المستطيلات وطبقتها في ملفات PDF الخاصة بك بدقة.
