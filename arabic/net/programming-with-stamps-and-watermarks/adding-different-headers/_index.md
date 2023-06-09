---
title: إضافة رؤوس مختلفة
linktitle: إضافة رؤوس مختلفة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة رؤوس مختلفة بسهولة إلى كل صفحة من صفحات مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 30
url: /ar/net/programming-with-stamps-and-watermarks/adding-different-headers/
---
في هذا البرنامج التعليمي ، سوف نأخذك خطوة بخطوة حول كيفية إضافة رؤوس مختلفة إلى مستند PDF باستخدام Aspose.PDF for .NET. سنوضح لك كيفية استخدام شفرة المصدر C # المقدمة لإضافة رؤوس مخصصة لكل صفحة من مستند PDF.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والمشار إليها في مشروعك.

## الخطوة الثانية: تحميل مستند PDF

تتمثل الخطوة الأولى في تحميل مستند PDF الحالي في مشروعك. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// افتح المستند المصدر
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "AddingDifferentHeaders.pdf");
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث يوجد مستند PDF الخاص بك.

## الخطوة 3: إنشاء مخازن الرؤوس

الآن بعد أن قمت بتحميل مستند PDF ، يمكنك إنشاء أختام رأس لإضافتها. إليك الطريقة:

```csharp
// إنشاء ثلاثة مخازن رأس
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");
```

ينشئ الكود أعلاه ثلاثة مخازن رأس جديدة تحتوي على النص المحدد.

## الخطوة 4: تكوين خصائص المخزن المؤقت للرأس

قبل إضافة أختام الرأس إلى مستند PDF ، يمكنك تكوين خصائص مختلفة لكل ختم ، مثل المحاذاة والحجم واللون وما إلى ذلك ، وإليك الطريقة:

```csharp
// تكوين المخزن المؤقت للرأس الأول
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp1.TextState.FontStyle = FontStyles.Bold;
stamp1.TextState.ForegroundColor = Color.Red;
stamp1.TextState.FontSize = 14;

// تكوين المخزن المؤقت للرأس الثاني
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp2.Zoom = 10;

// تكوين المخزن المؤقت للرأس الثالث
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp3.RotateAngle = 35;
stamp3.TextState.BackgroundColor = Color.Pink;
stamp3.TextState.Font = FontRepository.FindFont("Verdana");
```

يمكنك ضبط هذه الخصائص حسب الحاجة لكل مخزن رأس مؤقت.

## الخطوة 5: إضافة أختام الرأس إلى ملف PDF

الآن بعد أن أصبحت أختام الرأس جاهزة ، يمكنك إضافتها إلى كل صفحة محددة من مستند PDF. إليك الطريقة:

```csharp
// إضافة مخازن رأس إلى صفحات معينة
doc.Pages[1].AddStamp(stamp1);
doc.Pages[2].AddStamp(stamp2);
doc.Pages[3].AddStamp(stamp3);
```

يضيف الرمز أعلاه كل ختم رأس إلى الصفحة المقابلة لمستند PDF.

## الخطوة 6: احفظ المستند الناتج

بمجرد إضافة أختام الرأس ، يمكنك حفظ مستند PDF المحرر. إليك الطريقة:

```csharp
// احفظ المستند المحدث
doc.Save(dataDir);
```

يحفظ الكود أعلاه مستند PDF المحرر في الدليل المحدد.

### نموذج التعليمات البرمجية المصدر لإضافة رؤوس مختلفة باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// وثيقة مفتوحة المصدر
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddingDifferentHeaders.pdf");

// قم بإنشاء ثلاثة طوابع
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");

//ضبط محاذاة الختم (ختم مكان على أعلى الصفحة ، توسيط أفقياً)
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// حدد نمط الخط على أنه غامق
stamp1.TextState.FontStyle = FontStyles.Bold;

// قم بتعيين معلومات لون المقدمة الأمامية للنص باللون الأحمر
stamp1.TextState.ForegroundColor = Color.Red;

// حدد حجم الخط على أنه 14
stamp1.TextState.FontSize = 14;

// نحتاج الآن إلى ضبط المحاذاة الرأسية لكائن الختم الثاني على أنها Top
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// قم بتعيين معلومات المحاذاة الأفقية للختم كمحاذاة للوسط
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// اضبط عامل التكبير لكائن الختم
stamp2.Zoom = 10;

// اضبط تنسيق كائن الطابع الثالث
// حدد معلومات المحاذاة الرأسية لكائن الطوابع على أنها TOP
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// قم بتعيين معلومات المحاذاة الأفقية لكائن الطوابع كمحاذة للوسط
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// اضبط زاوية الدوران لكائن الختم
stamp3.RotateAngle = 35;

// تعيين اللون الوردي كخلفية للطابع
stamp3.TextState.BackgroundColor = Color.Pink;

// قم بتغيير معلومات وجه الخط للطابع إلى Verdana
stamp3.TextState.Font = FontRepository.FindFont("Verdana");

// يضاف الطابع الأول على الصفحة الأولى ؛
doc.Pages[1].AddStamp(stamp1);

// يضاف الطابع الثاني على الصفحة الثانية ؛
doc.Pages[2].AddStamp(stamp2);

// يضاف الطابع الثالث على الصفحة الثالثة.
doc.Pages[3].AddStamp(stamp3);
dataDir = dataDir + "multiheader_out.pdf";

// احفظ المستند المحدث
doc.Save(dataDir);
Console.WriteLine("\nDifferent headers added successfully.\nFile saved at " + dataDir);

```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة رؤوس مختلفة لكل صفحة من مستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن تطبيق هذه المعرفة على مشاريعك الخاصة لتخصيص رؤوس مستندات PDF الخاصة بك.
