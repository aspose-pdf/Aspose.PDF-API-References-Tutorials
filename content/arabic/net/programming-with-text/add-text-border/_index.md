---
title: إضافة حدود النص في ملف PDF
linktitle: إضافة حدود النص في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة حد نص في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 70
url: /ar/net/programming-with-text/add-text-border/
---
سيرشدك هذا البرنامج التعليمي خلال عملية إضافة حد نص في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C# آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية الذي تريد إضافة حد النص إليه، أضف ما يلي باستخدام التوجيه في أعلى الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: إنشاء كائن مستند جديد
 إنشاء مثيل جديد`Document` كائن عن طريق إضافة السطر التالي من التعليمات البرمجية:

```csharp
Document pdfDocument = new Document();
```

## الخطوة 5: إضافة صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages`مجموعة. في الكود المقدم، يتم تعيين الصفحة الجديدة للمتغير`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## الخطوة 6: إنشاء TextFragment
 إنشاء`TextFragment` الكائن وتقديم النص المطلوب. اضبط موضع جزء النص باستخدام`Position` ملكية. في الكود المقدم، تم تعيين النص على "النص الرئيسي" ووضعه عند (100، 600) على الصفحة.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## الخطوة 7: تعيين خصائص النص
قم بتخصيص خصائص النص مثل حجم الخط ونوع الخط ولون الخلفية ولون المقدمة وما إلى ذلك. في التعليمات البرمجية المتوفرة، يتم تعيين خصائص مثل حجم الخط والخط ولون الخلفية ولون المقدمة ولون التمسيد لجزء النص.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## الخطوة 8: تمكين حدود النص
 لتمكين حدود النص، قم بتعيين`DrawTextRectangleBorder`خاصية جزء النص`TextState` ل`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## الخطوة 9: أضف TextFragment إلى الصفحة
 استخدم ال`TextBuilder` فئة لإضافة`TextFragment` الاعتراض على الصفحة.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## الخطوة 10: احفظ مستند PDF
 احفظ مستند PDF باستخدام`Save` طريقة`Document` هدف. حدد مسار ملف الإخراج الذي قمت بتعيينه في الخطوة 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لإضافة حدود النص باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء كائن مستند جديد
Document pdfDocument = new Document();
// الحصول على صفحة معينة
Page pdfPage = (Page)pdfDocument.Pages.Add();
// إنشاء جزء من النص
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// تعيين خصائص النص
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// قم بتعيين خاصية StrokingColor لرسم الحدود (التمسيد) حول مستطيل النص
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// قم بتعيين قيمة الخاصية DrawTextRectangleBorder إلى true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// احفظ المستند
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## خاتمة
لقد نجحت في إضافة حد نص إلى مستند PDF الخاص بك باستخدام Aspose.PDF لـ .NET. يمكن الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو التركيز الرئيسي لهذا البرنامج التعليمي؟

ج: يرشدك هذا البرنامج التعليمي خلال عملية إضافة حد نص إلى ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم الخطوات اللازمة لتحقيق ذلك.

#### س: ما هي مساحات الأسماء التي أحتاج إلى استيرادها لهذا البرنامج التعليمي؟

ج: في ملف التعليمات البرمجية الذي تريد إضافة حد النص إليه، قم باستيراد مساحات الأسماء التالية في بداية الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### س: كيف أحدد دليل المستندات؟

 ج: في الكود، حدد موقع السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

#### س: كيف أقوم بإنشاء كائن مستند؟

 ج: في الخطوة 4، ستقوم بإنشاء نسخة جديدة`Document` كائن باستخدام السطر التالي من التعليمات البرمجية:

```csharp
Document pdfDocument = new Document();
```

#### س: كيف يمكنني إضافة صفحة إلى المستند؟

 ج: في الخطوة 5، ستضيف صفحة جديدة إلى المستند باستخدام الملف`Add` طريقة`Pages` مجموعة:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### س: كيف يمكنني إنشاء TextFragment وتعيين موضعه؟

 ج: في الخطوة 6، ستقوم بإنشاء ملف`TextFragment`كائن وتعيين موضعه على الصفحة باستخدام`Position` ملكية:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### س: كيف يمكنني تخصيص خصائص النص، بما في ذلك حدود النص؟

ج: في الخطوة 7، ستقوم بتخصيص خصائص النص المختلفة مثل حجم الخط ونوع الخط ولون الخلفية ولون المقدمة وحدود النص:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### س: كيف يمكنني إضافة TextFragment إلى مستند PDF؟

 ج: في الخطوة 9، ستستخدم`TextBuilder` فئة لإضافة`TextFragment` الاعتراض على الصفحة:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### س: كيف يمكنني حفظ مستند PDF الناتج؟

 ج: بعد إضافة النص بحدود، استخدم`Save` طريقة`Document` كائن لحفظ مستند PDF:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### س: ما هي الوجبات الرئيسية من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، تكون قد تعلمت بنجاح كيفية تحسين مستند PDF الخاص بك عن طريق إضافة حد نص باستخدام Aspose.PDF لـ .NET. يمكن أن يكون هذا مفيدًا بشكل خاص للتأكيد على محتوى نصي محدد داخل ملفات PDF الخاصة بك.