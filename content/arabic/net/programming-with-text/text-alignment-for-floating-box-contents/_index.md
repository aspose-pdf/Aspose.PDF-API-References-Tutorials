---
title: محاذاة النص لمحتويات المربع العائم في ملف PDF
linktitle: محاذاة النص لمحتويات المربع العائم في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية محاذاة النص داخل المربعات العائمة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 520
url: /ar/net/programming-with-text/text-alignment-for-floating-box-contents/
---
يوضح هذا البرنامج التعليمي كيفية محاذاة النص داخل المربعات العائمة في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود المصدر C# المقدم العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل المتابعة بالبرنامج التعليمي، تأكد من توفر ما يلي:

- المعرفة الأساسية للغة البرمجة C#.
- تم تثبيت مكتبة Aspose.PDF لـ .NET. يمكنك الحصول عليها من موقع Aspose على الويب أو استخدام NuGet لتثبيتها في مشروعك.

## الخطوة 1: إعداد المشروع

ابدأ بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك وأضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات الأساسية الضرورية

أضف التوجيهات التالية في بداية ملف C# الخاص بك لاستيراد المساحات المطلوبة:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 3: تعيين المسار إلى دليل المستند

 قم بتعيين المسار إلى دليل المستند الخاص بك باستخدام`dataDir` عامل:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 4: إنشاء مستند جديد

 إنشاء جديد`Document` هدف:

```csharp
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

## الخطوة 5: إنشاء مربعات عائمة باستخدام أجزاء نصية

 إنشاء متعددة`FloatingBox` الأشياء ذات المحاذاة الرأسية والأفقية المختلفة:

```csharp
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);

Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);

Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
```

 تعديل النص وتنسيقه`TextFragment` الأشياء حسب الرغبة.

## الخطوة 6: احفظ مستند PDF

حفظ مستند PDF المعدل:

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

 تأكد من الاستبدال`"FloatingBox_alignment_review_out.pdf"` مع اسم ملف الإخراج المطلوب.

### نموذج لمصدر التعليمات البرمجية لمحاذاة النص لمحتويات المربع العائم باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);
Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);
Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

## خاتمة

مبروك! لقد تعلمت بنجاح كيفية محاذاة النص داخل المربعات العائمة في مستند PDF باستخدام Aspose.PDF for .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، من إعداد المشروع إلى حفظ المستند المعدل. يمكنك الآن دمج هذا الكود في مشاريع C# الخاصة بك لتخصيص محاذاة النص داخل المربعات العائمة في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "محاذاة النص لمحتويات المربع العائم في ملف PDF"؟

أ: يهدف البرنامج التعليمي "محاذاة النص لمحتويات المربعات العائمة في ملف PDF" إلى توجيه المستخدمين حول كيفية محاذاة النص داخل المربعات العائمة في مستند PDF باستخدام Aspose.PDF لـ .NET. يوفر البرنامج التعليمي تعليمات خطوة بخطوة وعينات من التعليمات البرمجية بلغة C# لتوضيح العملية.

#### س: كيف يساعد هذا البرنامج التعليمي في محاذاة النص داخل المربعات العائمة؟

ج: يساعد هذا البرنامج التعليمي المستخدمين على فهم كيفية استخدام Aspose.PDF for .NET لمحاذاة النص داخل المربعات العائمة في مستند PDF. باتباع الخطوات وأمثلة التعليمات البرمجية المقدمة، يمكن للمستخدمين تخصيص المحاذاة الرأسية والأفقية للنص داخل المربعات العائمة.

#### س: ما هي المتطلبات الأساسية المطلوبة لمتابعة هذا البرنامج التعليمي؟

ج: قبل البدء في البرنامج التعليمي، يجب أن يكون لديك فهم أساسي للغة البرمجة C#. بالإضافة إلى ذلك، يجب أن يكون لديك مكتبة Aspose.PDF for .NET مثبتة. يمكنك الحصول عليها من موقع Aspose على الويب أو تثبيتها في مشروعك باستخدام NuGet.

#### س: كيف أقوم بإعداد مشروعي لمتابعة هذا البرنامج التعليمي؟

ج: للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك وأضف مرجعًا إلى مكتبة Aspose.PDF for .NET. يتيح لك هذا الاستفادة من ميزات المكتبة للعمل مع مستندات PDF ومحاذاة النص داخل المربعات العائمة.

#### س: هل يمكنني استخدام هذا البرنامج التعليمي لمحاذاة النص داخل أي نوع من المربعات العائمة؟

ج: نعم، يوفر هذا البرنامج التعليمي إرشادات حول كيفية محاذاة النص داخل المربعات العائمة في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك استخدام عينات التعليمات البرمجية المقدمة لتخصيص المحاذاة الرأسية والأفقية للنص داخل المربعات العائمة.

#### س: كيف يمكنني تحديد محاذاة النص داخل مربع عائم؟

 أ: يوضح البرنامج التعليمي كيفية إنشاء`FloatingBox`الأشياء وتعيينها`VerticalAlignment` و`HorizontalAlignment` خصائص للتحكم في محاذاة النص المضمن. يمكنك تعديل هذه الخصائص وفقًا لمتطلباتك.

#### س: كيف يمكنني تخصيص مظهر الصناديق العائمة؟

 ج: يمكنك تخصيص مظهر المربعات العائمة عن طريق تعديل خصائص مثل الحدود والحجم ومحتوى النص. يوفر البرنامج التعليمي عينات من التعليمات البرمجية التي توضح كيفية إنشاء المربعات العائمة وتصميمها.`FloatingBox` أشياء.

#### س: هل يمكنني إضافة عدة مربعات عائمة ذات محاذات مختلفة في نفس مستند PDF؟

 ج: نعم، يوضح البرنامج التعليمي كيفية إنشاء العديد من`FloatingBox` يمكنك إضافة كائنات ذات محاذاة رأسية وأفقية مختلفة إلى نفس مستند PDF. يتيح لك هذا رؤية تأثيرات المحاذاة المختلفة داخل نفس المستند.

#### س: كيف أحفظ مستند PDF المعدل؟

 أ: لحفظ مستند PDF المعدّل، يمكنك استخدام`Save` طريقة`Document` يوفر البرنامج التعليمي عينات من التعليمات البرمجية التي توضح كيفية حفظ مستند PDF الناتج.