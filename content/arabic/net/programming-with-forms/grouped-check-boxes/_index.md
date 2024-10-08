---
title: مربعات الاختيار المجمعة في مستند PDF
linktitle: مربعات الاختيار المجمعة في مستند PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إنشاء مربعات اختيار مجمعة (أزرار اختيارية) في مستند PDF باستخدام Aspose.PDF لـ .NET من خلال هذا البرنامج التعليمي خطوة بخطوة.
type: docs
weight: 170
url: /ar/net/programming-with-forms/grouped-check-boxes/
---
## مقدمة

إن إنشاء ملفات PDF تفاعلية ليس بالأمر الصعب كما قد يبدو، وخاصة عندما تكون لديك أدوات قوية مثل Aspose.PDF for .NET تحت تصرفك. أحد العناصر التفاعلية التي قد تحتاج إلى إضافتها إلى مستندات PDF الخاصة بك هي مربعات الاختيار المجمعة، أو بالأحرى أزرار الاختيار التي تسمح للمستخدمين باختيار خيار واحد من مجموعة. سيرشدك هذا البرنامج التعليمي خلال عملية إضافة مربعات الاختيار المجمعة (أزرار الاختيار) إلى مستند PDF باستخدام Aspose.PDF for .NET. سواء كنت مبتدئًا أو مطورًا متمرسًا، فستجد هذا الدليل جذابًا ومفصلًا وسهل المتابعة.

## المتطلبات الأساسية

قبل أن نتعمق في الدليل خطوة بخطوة، دعنا نغطي بعض المتطلبات الأساسية:

1.  Aspose.PDF لـ .NET: تأكد من تثبيت مكتبة Aspose.PDF. إذا لم يكن الأمر كذلك، فيمكنك[تحميله هنا](https://releases.aspose.com/pdf/net/).
2. IDE: يجب أن يكون لديك بيئة تطوير تم إعدادها، مثل Visual Studio.
3. .NET Framework: يجب أن يستهدف المشروع إصدارًا من .NET Framework متوافقًا مع Aspose.PDF.
4. المعرفة الأساسية بلغة C#: مطلوب الإلمام بلغة C# ومعالجة PDF لمتابعة العمل بسلاسة.
5.  الترخيص: يتطلب Aspose.PDF ترخيصًا للحصول على الوظائف الكاملة. يمكنك[الحصول على ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) إذا لزم الأمر.

## استيراد الحزم

قبل البدء، تأكد من استيراد المساحات الأساسية اللازمة إلى مشروعك:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Forms;
```

ستتيح لك هذه الحزم الوصول إلى جميع الفئات والطرق المطلوبة للتعامل مع مستندات PDF، بما في ذلك إنشاء أزرار الاختيار وتحديد خصائصها.

في هذا القسم، سنقوم بتقسيم عملية إنشاء مربعات الاختيار المجمعة (أزرار الاختيار) إلى خطوات واضحة وسهلة المتابعة.

## الخطوة 1: إنشاء مستند PDF جديد

 الخطوة الأولى هي إنشاء مثيل لـ`Document` الكائن الذي سيمثل ملف PDF الخاص بك. ثم أضف صفحة فارغة إلى مستندك حيث ستضع مربعات الاختيار المجمعة.

```csharp
// إنشاء كائن مستند
Document pdfDocument = new Document();

// إضافة صفحة إلى ملف PDF
Page page = pdfDocument.Pages.Add();
```

يؤدي هذا إلى إنشاء الأساس لإضافة أي عناصر، مثل أزرار الاختيار، إلى ملف PDF.

## الخطوة 2: تهيئة حقل زر الاختيار

بعد ذلك، نحتاج إلى إنشاء`RadioButtonField` الكائن الذي سيحمل مربعات الاختيار المجمعة (أزرار الاختيار). يُضاف هذا الحقل إلى الصفحة المحددة التي ستظهر فيها مربعات الاختيار.

```csharp
// إنشاء كائن RadioButtonField وتعيينه إلى الصفحة الأولى
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

فكر في هذا باعتباره الحاوية التي ستجمع خيارات أزرار الاختيار الفردية معًا.

## الخطوة 3: إضافة خيارات أزرار الاختيار

 الآن، دعنا نضيف خيارات أزرار الاختيار الفردية إلى الحقل. في هذا المثال، سنضيف زري اختيار ونحدد مواقعهما باستخدام`Rectangle` هدف.

```csharp
// أضف خيار زر الاختيار الأول وحدد موضعه باستخدام المستطيل
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));

// تعيين أسماء الخيارات للتعريف
opt1.OptionName = "Option1";
opt2.OptionName = "Option2";
```

 هنا،`Rectangle` يقوم الكائن بتعريف إحداثيات وحجم كل زر اختيار على الصفحة.

## الخطوة 4: تخصيص نمط أزرار الاختيار

 يمكنك تخصيص مظهر أزرار الاختيار عن طريق ضبطها`Style` على سبيل المثال، قد ترغب في مربعات اختيار على شكل مربع أو مربعات على شكل صليب.

```csharp
// ضبط نمط أزرار الراديو
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Cross;
```

يتيح لك هذا التحكم في مظهر ومظهر مربعات الاختيار، مما يجعلها أكثر سهولة في الاستخدام وجذابة بصريًا.

## الخطوة 5: تكوين خصائص الحدود

تلعب الحدود دورًا حيويًا في جعل مربعات الاختيار قابلة للتحديد بسهولة. هنا، سنضيف حدودًا صلبة حول كل خيار من خيارات أزرار الاختيار ونحدد عرضها ولونها.

```csharp
// تكوين حدود زر الاختيار الأول
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt1.Characteristics.Border = Color.Black;

// تكوين حدود زر الاختيار الثاني
opt2.Border = new Border(opt2);
opt2.Border.Style = BorderStyle.Solid;
opt2.Border.Width = 1;
opt2.Characteristics.Border = Color.Black;
```

تضمن هذه الخطوة أن يكون لكل زر اختيار حدود محددة جيدًا، مما يؤدي إلى تحسين قابلية قراءة المستند.

## الخطوة 6: إضافة خيارات أزرار الاختيار إلى النموذج

الآن، سنضيف أزرار الاختيار إلى نموذج المستند. هذه هي الخطوة الأخيرة في تجميع مربعات الاختيار معًا تحت حقل واحد.

```csharp
// إضافة حقل زر الاختيار إلى كائن النموذج الخاص بالمستند
pdfDocument.Form.Add(radio);
```

يعمل كائن النموذج كحاوية لجميع العناصر التفاعلية، بما في ذلك مربعات الاختيار المجمعة لدينا.

## الخطوة 7: احفظ مستند PDF

وأخيرًا، بمجرد إعداد كل شيء، يمكنك حفظ مستند PDF في الموقع المطلوب.

```csharp
// تحديد مسار ملف الإخراج
string dataDir = "YOUR DOCUMENT DIRECTORY" + "GroupedCheckBoxes_out.pdf";

// حفظ مستند PDF
pdfDocument.Save(dataDir);

// تأكيد الإنشاء الناجح
Console.WriteLine("Grouped checkboxes added successfully. File saved at " + dataDir);
```

وهذا كل شيء! لقد نجحت في إنشاء ملف PDF يحتوي على مربعات اختيار مجمعة باستخدام Aspose.PDF لـ .NET.

## خاتمة

قد يبدو إضافة عناصر تفاعلية مثل مربعات الاختيار المجمعة إلى مستندات PDF أمرًا صعبًا في البداية، ولكن مع Aspose.PDF لـ .NET، يصبح الأمر سهلاً. باتباع هذا الدليل التفصيلي، ستتعلم كيفية إعداد مستند PDF أساسي، وإضافة أزرار اختيار مجمعة، وتخصيص مظهرها، وحفظ النتيجة النهائية. سواء كنت تقوم ببناء نماذج أو استبيانات أو أي نوع آخر من ملفات PDF التفاعلية، فإن هذا الدليل يمنحك أساسًا قويًا للبدء به.

## الأسئلة الشائعة

### هل يمكنني إضافة أكثر من زرين اختياريين إلى مجموعة واحدة؟
 بالتأكيد! ما عليك سوى إنشاء مثيل إضافي`RadioButtonOptionField` الأشياء وإضافتها إلى`RadioButtonField` كما هو موضح في البرنامج التعليمي.

### كيف يمكنني التعامل مع مجموعات متعددة من مربعات الاختيار في مستند واحد؟
لإنشاء مجموعات متعددة، قم بإنشاء مجموعات منفصلة`RadioButtonField` الأشياء لكل مجموعة.

### هل هناك حد لعدد مربعات الاختيار التي يمكنني إضافتها؟
لا، لا يفرض Aspose.PDF لـ .NET أي حدود على عدد مربعات الاختيار التي يمكنك إضافتها إلى ملف PDF.

### هل يمكنني تغيير مظهر مربعات الاختيار بعد إضافتها؟
نعم، يمكنك تعديل الخصائص مثل نمط الحدود والعرض واللون بعد إضافة مربعات الاختيار.

### هل من الممكن استخدام الصور كأزرار اختيارية؟
 نعم، يسمح لك Aspose.PDF باستخدام الصور المخصصة كأزرار اختيار من خلال ضبط`Appearance` خاصية كل خيار زر الاختيار.