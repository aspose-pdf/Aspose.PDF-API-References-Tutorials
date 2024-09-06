---
title: إضافة حدود نصية في ملف PDF
linktitle: إضافة حدود نصية في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إضافة حدود نصية في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 70
url: /ar/net/programming-with-text/add-text-border/
---
سيرشدك هذا البرنامج التعليمي خلال عملية إضافة حدود نصية في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود المصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مُجمِّع C# آخر مُثبت على جهازك.
- مكتبة Aspose.PDF لـ .NET. يمكنك تنزيلها من موقع Aspose الرسمي أو استخدام مدير حزم مثل NuGet لتثبيتها.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات المطلوبة
في ملف الكود الذي تريد إضافة حدود النص إليه، أضف التوجيه التالي باستخدام في الجزء العلوي من الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 3: تعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل الذي يتم تخزين مستنداتك فيه.

## الخطوة 4: إنشاء كائن مستند جديد
 إنشاء مثيل جديد`Document` الكائن عن طريق إضافة سطر التعليمات البرمجية التالي:

```csharp
Document pdfDocument = new Document();
```

## الخطوة 5: إضافة صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages`المجموعة. في الكود المقدم، يتم تعيين الصفحة الجديدة للمتغير`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## الخطوة 6: إنشاء جزء نصي
 إنشاء`TextFragment` الكائن وتوفير النص المطلوب. اضبط موضع جزء النص باستخدام`Position` في الكود المقدم، يتم تعيين النص على "النص الرئيسي" ووضعه عند (100، 600) على الصفحة.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## الخطوة 7: تعيين خصائص النص
تخصيص خصائص النص مثل حجم الخط ونوع الخط ولون الخلفية ولون المقدمة وما إلى ذلك. في الكود المقدم، يتم تعيين خصائص مثل حجم الخط والخط ولون الخلفية ولون المقدمة ولون التحديد لشظية النص.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## الخطوة 8: تمكين حدود النص
 لتمكين حدود النص، اضبط`DrawTextRectangleBorder`خاصية جزء النص`TextState` ل`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## الخطوة 9: إضافة TextFragment إلى الصفحة
 استخدم`TextBuilder` الصف لإضافة`TextFragment` الاعتراض على الصفحة.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## الخطوة 10: احفظ مستند PDF
 احفظ مستند PDF باستخدام`Save` طريقة`Document` حدد مسار ملف الإخراج الذي قمت بتعيينه في الخطوة 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### عينة من كود المصدر لإضافة حدود نصية باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء كائن مستند جديد
Document pdfDocument = new Document();
// الحصول على صفحة معينة
Page pdfPage = (Page)pdfDocument.Pages.Add();
// إنشاء جزء نصي
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// تعيين خصائص النص
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// تعيين خاصية StrokingColor لرسم الحدود (الرسم) حول مستطيل النص
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// تعيين قيمة خاصية DrawTextRectangleBorder إلى true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// حفظ المستند
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## خاتمة
لقد نجحت في إضافة حدود نصية إلى مستند PDF الخاص بك باستخدام Aspose.PDF لـ .NET. يمكنك الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو التركيز الرئيسي لهذا البرنامج التعليمي؟

ج: يرشدك هذا البرنامج التعليمي خلال عملية إضافة إطار نصي إلى ملف PDF باستخدام مكتبة Aspose.PDF for .NET. يوضح كود المصدر C# المقدم الخطوات اللازمة لتحقيق ذلك.

#### س: ما هي المساحات الأسماء التي أحتاج إلى استيرادها لهذا البرنامج التعليمي؟

أ: في ملف الكود الذي تريد إضافة حدود النص إليه، قم باستيراد المساحات التالية في بداية الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### س: كيف أحدد دليل المستند؟

 أ: في الكود، حدد السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

#### س: كيف أقوم بإنشاء كائن مستند؟

 أ: في الخطوة 4، ستقوم بإنشاء مثيل جديد`Document` الكائن باستخدام سطر التعليمات البرمجية التالي:

```csharp
Document pdfDocument = new Document();
```

#### س: كيف أضيف صفحة إلى المستند؟

 أ: في الخطوة 5، ستضيف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages` مجموعة:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### س: كيف أقوم بإنشاء TextFragment وتعيين موضعه؟

 أ: في الخطوة 6، ستقوم بإنشاء`TextFragment`الكائن وتعيين موضعه على الصفحة باستخدام`Position` ملكية:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### س: كيف يمكنني تخصيص خصائص النص، بما في ذلك حدود النص؟

أ: في الخطوة 7، ستقوم بتخصيص خصائص نصية مختلفة مثل حجم الخط ونوع الخط ولون الخلفية ولون المقدمة وحدود النص:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### س: كيف أضيف TextFragment إلى مستند PDF؟

 أ: في الخطوة 9، سوف تستخدم`TextBuilder` الصف لإضافة`TextFragment` الاعتراض على الصفحة:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### س: كيف أحفظ مستند PDF الناتج؟

 أ: بعد إضافة النص مع الحدود، استخدم`Save` طريقة`Document` كائن لحفظ مستند PDF:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### س: ما هو الدرس الرئيسي المستفاد من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، ستتعلم بنجاح كيفية تحسين مستند PDF الخاص بك عن طريق إضافة حدود نصية باستخدام Aspose.PDF لـ .NET. يمكن أن يكون هذا مفيدًا بشكل خاص للتأكيد على محتوى نصي معين داخل ملفات PDF الخاصة بك.