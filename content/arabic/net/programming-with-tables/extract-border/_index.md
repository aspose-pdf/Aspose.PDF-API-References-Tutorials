---
title: استخراج الحدود في ملف PDF
linktitle: استخراج الحدود في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية استخراج الحدود من ملف PDF وحفظها كصورة باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة مع عينات التعليمات البرمجية ونصائح للنجاح.
type: docs
weight: 80
url: /ar/net/programming-with-tables/extract-border/
---
## مقدمة

عند العمل مع ملفات PDF، قد يبدو استخراج عناصر معينة مثل الحدود أو المسارات الرسومية مهمة شاقة. ولكن باستخدام Aspose.PDF for .NET، يمكنك بسهولة استخراج الحدود أو الأشكال من ملف PDF وحفظها كصورة. في هذا البرنامج التعليمي، سنتعمق في عملية استخراج حدود من ملف PDF وحفظها كصورة PNG. استعد للتحكم في المحتويات الرسومية لملف PDF الخاص بك!

## المتطلبات الأساسية

قبل أن نتعمق في الكود، تأكد من إعداد كل شيء:

1.  Aspose.PDF لـ .NET: إذا لم تقم بتثبيت مكتبة Aspose.PDF بعد، فيمكنك[تحميله هنا](https://releases.aspose.com/pdf/net/)سيتعين عليك أيضًا تطبيق الترخيص، إما من خلال الإصدار التجريبي المجاني أو الترخيص الذي تم شراؤه.
2. إعداد IDE: قم بإعداد مشروع C# في Visual Studio أو أي .NET IDE آخر. تأكد من إضافة المراجع الضرورية إلى مكتبة Aspose.PDF.
3. إدخال ملف PDF: قم بإعداد ملف PDF لاستخراج الحدود منه. سيشير هذا البرنامج التعليمي إلى ملف باسم`input.pdf`.

## استيراد الحزم المطلوبة

لنبدأ باستيراد المساحات المطلوبة. توفر هذه الحزم الأدوات اللازمة للتعامل مع محتوى PDF.

```csharp
using System.IO;
using System;
using System.Drawing.Drawing2D;
using System.Drawing.Imaging;
using System.Collections;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

الآن بعد أن قمنا بتغطية الأساسيات، دعنا ننتقل إلى الدليل خطوة بخطوة حيث سنقوم بتقسيم كل جزء من الكود لشرحه بالتفصيل.


## الخطوة 1: تحميل مستند PDF

الخطوة الأولى هي تحميل مستند PDF الذي يحتوي على الحدود التي تريد استخراجها. فكر في الأمر كما لو كنت تفتح كتابًا قبل أن تبدأ في القراءة — فأنت بحاجة إلى الوصول إلى المحتوى!

 سنبدأ بتحديد الدليل الذي يتم تخزين ملف PDF الخاص بك فيه وتحميل المستند باستخدام`Aspose.Pdf.Document` فصل.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 يقوم هذا الكود بتحميل`input.pdf` الملف من الدليل المحدد. تأكد من صحة مسار الملف، وإلا فقد تتلقى خطأ عدم العثور على الملف.

## الخطوة 2: إعداد الرسومات والخرائط النقطية

قبل أن نبدأ في الاستخراج، نحتاج إلى إنشاء لوحة قماشية للرسم عليها. في عالم .NET، يعني هذا إعداد كائنات Bitmap وGraphics. تمثل Bitmap الصورة، وسيسمح لنا كائن Graphics برسم الأشكال، مثل الحدود، المستخرجة من ملف PDF.

```csharp
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);
```

فيما يلي تفصيل:
- نقوم بإنشاء صورة نقطية بحجم الصفحة الأولى من ملف PDF.
- يتم استخدام GraphicsPath لتحديد الأشكال (في هذه الحالة، الحدود).
- تعرف المصفوفة كيفية تحويل الرسومات؛ نحن بحاجة إلى مصفوفة عكسية لأن PDF و.NET لديهما أنظمة إحداثيات مختلفة.

## الخطوة 3: معالجة محتويات PDF


ملف PDF عبارة عن سلسلة من أوامر الرسم، ونحن بحاجة إلى معالجة كل من هذه الأوامر لتحديد معلومات الحدود واستخراجها.

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // معالجة الأوامر مثل حفظ/استعادة الحالة، رسم الخطوط، ملء الأشكال، وما إلى ذلك.
}
```

يتكرر الكود عبر كل عامل رسم في مجرى محتوى ملف PDF. قد يمثل كل عامل خطًا أو مستطيلًا أو تعليمات رسومية أخرى.

## الخطوة 4: التعامل مع مشغلات PDF

يتحكم كل عامل في ملف PDF في إجراء ما. لاستخراج الحدود، نحتاج إلى تحديد أوامر مثل "move to" و"line to" و"draw triangle". تتولى العوامل التالية التعامل مع هذه الإجراءات:

- MoveTo: نقل المؤشر إلى نقطة البداية.
- LineTo: يرسم خطًا من النقطة الحالية إلى نقطة جديدة.
- رد: رسم مستطيل (يمكن أن يكون جزءًا من الحدود).

```csharp
Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;

if (opMoveTo != null)
{
    lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
    System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
    graphicsPath.AddLine(lastPoint, linePoint);
    lastPoint = linePoint;
}
else if (opRe != null)
{
    System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
    graphicsPath.AddRectangle(re);
}
```

في هذه الخطوة:
- نقوم بالتقاط النقاط لكل خط أو شكل مرسوم.
- للمستطيلات (`opRe` ), نضيفها مباشرة إلى`graphicsPath`والتي سنستخدمها لاحقًا لرسم الحدود.

## الخطوة 5: رسم الحدود

بمجرد تحديد الخطوط والمستطيلات التي تشكل الحدود، نحتاج إلى رسمها فعليًا على كائن Bitmap. وهنا يأتي دور كائن Graphics.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
    gr.SmoothingMode = SmoothingMode.HighQuality;
    gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
}
```

- نقوم بإنشاء كائن رسومي بناءً على الخريطة النقطية.
- يضمن SmoothingMode.HighQuality الحصول على صورة ناعمة لطيفة.
- وأخيرًا، نستخدم DrawPath لرسم الحدود.

## الخطوة 6: حفظ الحدود المستخرجة

الآن بعد أن استخرجنا الحدود، حان الوقت لحفظها كملف صورة. سيؤدي هذا إلى حفظ الحدود بصيغة PNG.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

- يتم حفظ الخريطة النقطية كصورة PNG.
- يمكنك الآن فتح هذه الصورة لعرض الحدود المستخرجة.

## خاتمة

قد يبدو استخراج الحدود من ملف PDF باستخدام Aspose.PDF لـ .NET أمرًا صعبًا في البداية، ولكن بمجرد فهمه، يصبح الأمر بسيطًا. من خلال فهم عوامل الرسم في ملف PDF والاستفادة من مكتبات .NET القوية، يمكنك معالجة المحتوى الرسومي واستخراجه بكفاءة. يمنحك هذا الدليل أساسًا قويًا للبدء في معالجة PDF!

## الأسئلة الشائعة

### كيف أتعامل مع صفحات متعددة في ملف PDF؟  
 يمكنك التنقل عبر كل صفحة في المستند عن طريق التكرار`doc.Pages` بدلا من الترميز الثابت`doc.Pages[1]`.

### هل يمكنني استخراج عناصر أخرى، مثل النص، باستخدام نفس النهج؟  
نعم، يوفر Aspose.PDF واجهات برمجة تطبيقات غنية لاستخراج النصوص والصور والمحتويات الأخرى من ملفات PDF.

### كيف يمكنني التقدم بطلب الترخيص لتجنب القيود؟  
 أنت تستطيع[تطبيق الترخيص](https://purchase.aspose.com/temporary-license/) عن طريق تحميله من خلال`License` الفئة المقدمة من قبل Aspose.

### ماذا لو كان ملف PDF الخاص بي لا يحتوي على حدود؟  
إذا لم يكن ملف PDF الخاص بك يحتوي على حدود مرئية، فقد لا تسفر عملية استخراج الرسومات عن أي نتيجة. تأكد من أن محتوى ملف PDF يتضمن حدودًا قابلة للرسم.

### هل يمكنني حفظ الإخراج بتنسيق آخر غير PNG؟  
 نعم، قم بتغيير ببساطة`ImageFormat.Png` إلى تنسيق آخر مدعوم مثل`ImageFormat.Jpeg`.