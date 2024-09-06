---
title: إضافة نص شفاف في ملف PDF
linktitle: إضافة نص شفاف في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إضافة نص شفاف في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 100
url: /ar/net/programming-with-text/add-transparent-text/
---
سيرشدك هذا البرنامج التعليمي خلال عملية إضافة نص شفاف إلى مستند PDF باستخدام Aspose.PDF لـ .NET. يوضح كود المصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مُجمِّع C# آخر مُثبت على جهازك.
- مكتبة Aspose.PDF لـ .NET. يمكنك تنزيلها من موقع Aspose الرسمي أو استخدام مدير حزم مثل NuGet لتثبيتها.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات المطلوبة
في ملف الكود الذي تريد إضافة نص شفاف إليه، أضف ما يلي باستخدام التوجيهات في الجزء العلوي من الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## الخطوة 3: تعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل الذي يتم تخزين مستنداتك فيه.

## الخطوة 4: إنشاء مثيل مستند جديد
 إنشاء مثيل جديد`Document` الكائن عن طريق إضافة سطر التعليمات البرمجية التالي:

```csharp
Document doc = new Document();
```

## الخطوة 5: إضافة صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages`المجموعة. في الكود المقدم، يتم تعيين الصفحة الجديدة للمتغير`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## الخطوة 6: إنشاء كائن رسم بياني
 إنشاء جديد`Graph` كائن ذو عرض وارتفاع محددين.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## الخطوة 7: إنشاء مستطيل بالشفافية
 قم بإنشاء مستطيل بأبعاد محددة واضبط لون تعبئته على لون شفاف باستخدام`Color.FromRgb` طريقة.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## الخطوة 8: إضافة كائن الرسم البياني إلى الصفحة
 أضف`Graph` الاعتراض على مجموعة الفقرات في الصفحة.

```csharp
page.Paragraphs.Add(canvas);
```

## الخطوة 9: تعيين موضع كائن الرسم البياني
 ضبط`IsChangePosition` ممتلكات`Graph` الاعتراض على`false` لمنعه من تغيير موقعه.

```csharp
canvas. IsChangePosition = false;
```

## الخطوة 10: إنشاء جزء نصي شفاف
 إنشاء`TextFragment` الكائن وضبط محتواه على النص المطلوب. اضبط`ForegroundColor` ممتلكات`TextState` إلى لون شفاف باستخدام`Color.FromArgb` طريقة.

```csharp
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
text.TextState.ForegroundColor = color;
page.Paragraphs.Add(text);
```

## الخطوة 11: احفظ مستند PDF
 احفظ مستند PDF باستخدام`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "AddTransparentText_out.pdf");
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```

### عينة من كود المصدر لإضافة نص شفاف باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء مثيل المستند
Document doc = new Document();
// إنشاء مجموعة من الصفحات لملف PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// إنشاء كائن الرسم البياني
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// إنشاء مثيل مستطيل بأبعاد معينة
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
// إنشاء كائن ملون من قناة ألوان ألفا
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// إضافة مستطيل إلى مجموعة الأشكال الخاصة بكائن الرسم البياني
canvas.Shapes.Add(rect);
//إضافة كائن الرسم البياني إلى مجموعة فقرات كائن الصفحة
page.Paragraphs.Add(canvas);
// تعيين القيمة لعدم تغيير الموضع لكائن الرسم البياني
canvas.IsChangePosition = false;
// إنشاء مثيل TextFragment بقيمة العينة
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// إنشاء كائن ملون من قناة ألفا
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
// تعيين معلومات اللون لنسخة النص
text.TextState.ForegroundColor = color;
// إضافة نص إلى مجموعة فقرات من مثيلات الصفحة
page.Paragraphs.Add(text);
dataDir = dataDir + "AddTransparentText_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```


## خاتمة
لقد نجحت في إضافة نص شفاف إلى مستند PDF الخاص بك باستخدام Aspose.PDF لـ .NET. يمكنك الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو التركيز في هذا البرنامج التعليمي؟

ج: يركز هذا البرنامج التعليمي على إضافة نص شفاف إلى مستند PDF باستخدام مكتبة Aspose.PDF for .NET. يوضح كود المصدر C# المقدم الخطوات اللازمة لتحقيق هذا التأثير.

#### س: ما هي المساحات الأسماء التي تحتاج إلى استيرادها لهذا البرنامج التعليمي؟

أ: في ملف الكود الذي تريد إضافة نص شفاف إليه، قم باستيراد المساحات التالية في بداية الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### س: كيف أحدد دليل المستند؟

 أ: في الكود، ابحث عن السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

#### س: كيف أقوم بإنشاء مثيل مستند جديد؟

 أ: في الخطوة 4، ستقوم بإنشاء مثيل جديد`Document` الكائن باستخدام الكود المقدم.

#### س: كيف أضيف صفحة إلى المستند؟

 أ: في الخطوة 5، ستضيف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages` مجموعة.

#### س: كيف أقوم بإنشاء كائن رسم بياني؟

 أ: في الخطوة 6، ستقوم بإنشاء ملف جديد`Graph` كائن ذو عرض وارتفاع محددين.

#### س: كيف أقوم بإنشاء مستطيل مع الشفافية؟

أ: في الخطوة 7، ستقوم بإنشاء مستطيل بأبعاد محددة وتعيين لون تعبئته إلى لون شفاف باستخدام`Color.FromRgb` طريقة.

#### س: كيف أضيف كائن الرسم البياني إلى الصفحة؟

 أ: في الخطوة 8، ستضيف`Graph` الاعتراض على مجموعة الفقرات في الصفحة.

#### س: كيف أقوم بتعيين موضع كائن الرسم البياني؟

 أ: في الخطوة 9، ستقوم بتعيين`IsChangePosition` ممتلكات`Graph` الاعتراض على`false` لمنعه من تغيير موقعه.

#### س: كيف أقوم بإنشاء TextFragment مع الشفافية؟

 أ: في الخطوة 10، ستقوم بإنشاء`TextFragment` الكائن وتعيين محتواه و`ForegroundColor` خاصية لتحقيق نص شفاف.

#### س: كيف أحفظ مستند PDF؟

 أ: في الخطوة 11، ستحفظ مستند PDF باستخدام`Save` طريقة`Document` هدف.

#### س: ما هو الدرس الرئيسي المستفاد من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، ستتعلم كيفية إضافة نص شفاف إلى مستند PDF باستخدام Aspose.PDF for .NET. يمكن أن يكون هذا مفيدًا لإنشاء مستندات PDF جذابة بصريًا وإبداعية.