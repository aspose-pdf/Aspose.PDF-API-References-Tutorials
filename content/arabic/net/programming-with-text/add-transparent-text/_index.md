---
title: إضافة نص شفاف في ملف PDF
linktitle: إضافة نص شفاف في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة نص شفاف في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 100
url: /ar/net/programming-with-text/add-transparent-text/
---
سيرشدك هذا البرنامج التعليمي خلال عملية إضافة نص شفاف إلى مستند PDF باستخدام Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C# آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية الذي تريد إضافة نص شفاف إليه، أضف ما يلي باستخدام التوجيهات الموجودة في أعلى الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: إنشاء مثيل مستند جديد
 إنشاء مثيل جديد`Document` كائن عن طريق إضافة السطر التالي من التعليمات البرمجية:

```csharp
Document doc = new Document();
```

## الخطوة 5: إضافة صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages`مجموعة. في الكود المقدم، يتم تعيين الصفحة الجديدة للمتغير`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## الخطوة 6: إنشاء كائن الرسم البياني
 إنشاء جديد`Graph` كائن له عرض وارتفاع محدد.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## الخطوة 7: إنشاء مستطيل بشفافية
 أنشئ مستطيلاً بأبعاد محددة واضبط لون تعبئته على لون شفاف باستخدام الملف`Color.FromRgb` طريقة.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## الخطوة 8: أضف كائن الرسم البياني إلى الصفحة
 أضف ال`Graph` الاعتراض على مجموعة الفقرات من الصفحة.

```csharp
page.Paragraphs.Add(canvas);
```

## الخطوة 9: تعيين موضع كائن الرسم البياني
 تعيين`IsChangePosition` ملكية`Graph` يعترض على`false` لمنعه من تغيير الموقف.

```csharp
canvas. IsChangePosition = false;
```

## الخطوة 10: إنشاء TextFragment بشفافية
 إنشاء`TextFragment` الكائن وتعيين محتواه على النص المطلوب. تعيين`ForegroundColor` ملكية`TextState` إلى لون ذو شفافية باستخدام`Color.FromArgb` طريقة.

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
// إنشاء كائن اللون من قناة لون ألفا
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// إضافة مستطيل إلى مجموعة الأشكال لكائن الرسم البياني
canvas.Shapes.Add(rect);
//إضافة كائن الرسم البياني إلى مجموعة الفقرات من كائن الصفحة
page.Paragraphs.Add(canvas);
// قم بتعيين القيمة لعدم تغيير موضع كائن الرسم البياني
canvas.IsChangePosition = false;
// قم بإنشاء مثيل TextFragment بقيمة العينة
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// إنشاء كائن اللون من قناة ألفا
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
// قم بتعيين معلومات اللون لمثيل النص
text.TextState.ForegroundColor = color;
// إضافة نص إلى مجموعة الفقرات من مثيل الصفحة
page.Paragraphs.Add(text);
dataDir = dataDir + "AddTransparentText_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```


## خاتمة
لقد نجحت في إضافة نص شفاف إلى مستند PDF الخاص بك باستخدام Aspose.PDF لـ .NET. يمكن الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو محور هذا البرنامج التعليمي؟

ج: يركز هذا البرنامج التعليمي على إضافة نص شفاف إلى مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم الخطوات اللازمة لتحقيق هذا التأثير.

#### س: ما هي مساحات الأسماء التي يجب استيرادها لهذا البرنامج التعليمي؟

ج: في ملف التعليمات البرمجية الذي تريد إضافة نص شفاف إليه، قم باستيراد مساحات الأسماء التالية في بداية الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### س: كيف أحدد دليل المستندات؟

 ج: في الكود، ابحث عن السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

#### س: كيف يمكنني إنشاء مثيل مستند جديد؟

 ج: في الخطوة 4، ستقوم بإنشاء نسخة جديدة`Document` الكائن باستخدام الكود المقدم.

#### س: كيف يمكنني إضافة صفحة إلى المستند؟

 ج: في الخطوة 5، ستضيف صفحة جديدة إلى المستند باستخدام الملف`Add` طريقة`Pages` مجموعة.

#### س: كيف أقوم بإنشاء كائن رسم بياني؟

 ج: في الخطوة 6، ستقوم بإنشاء ملف جديد`Graph` كائن له عرض وارتفاع محدد.

#### س: كيف أقوم بإنشاء مستطيل ذو شفافية؟

ج: في الخطوة 7، ستقوم بإنشاء مستطيل بأبعاد محددة وتعيين لون تعبئته إلى لون شفاف باستخدام`Color.FromRgb` طريقة.

#### س: كيف يمكنني إضافة كائن الرسم البياني إلى الصفحة؟

 ج: في الخطوة 8، ستضيف`Graph` الاعتراض على مجموعة الفقرات من الصفحة.

#### س: كيف أقوم بتعيين موضع كائن الرسم البياني؟

 ج: في الخطوة 9، ستقوم بتعيين`IsChangePosition` ملكية`Graph` يعترض على`false` لمنعه من تغيير الموقف.

#### س: كيف يمكنني إنشاء TextFragment بشفافية؟

 ج: في الخطوة 10، ستقوم بإنشاء ملف`TextFragment` الكائن وتعيين محتواه و`ForegroundColor` خاصية لتحقيق نص شفاف.

#### س: كيف أحفظ وثيقة PDF؟

 ج: في الخطوة 11، ستحفظ مستند PDF باستخدام ملف`Save` طريقة`Document` هدف.

#### س: ما هي الوجبات الرئيسية من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، تعلمت كيفية إضافة نص شفاف إلى مستند PDF باستخدام Aspose.PDF لـ .NET. يمكن أن يكون هذا مفيدًا لإنشاء مستندات PDF جذابة ومبتكرة.