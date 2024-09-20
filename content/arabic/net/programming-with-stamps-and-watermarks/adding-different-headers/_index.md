---
title: إضافة عناوين مختلفة في ملف PDF
linktitle: إضافة عناوين مختلفة في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إضافة عناوين مختلفة إلى ملفات PDF باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة لتخصيص ملفات PDF الخاصة بك.
type: docs
weight: 30
url: /ar/net/programming-with-stamps-and-watermarks/adding-different-headers/
---
## مقدمة

في هذه المقالة، سنتعمق في استخدام Aspose.PDF لـ .NET لإضافة عناوين مختلفة إلى ملفات PDF. سواء كنت مطورًا متمرسًا أو مبتدئًا يخوض للتو عالم معالجة ملفات PDF الشاسع، فسيرشدك هذا الدليل خلال كل خطوة. هل أنت مستعد؟ لنبدأ!

## المتطلبات الأساسية

قبل أن ننتقل إلى جانب الترميز، هناك بعض الأشياء التي ستحتاج إلى التأكد من توفرها لديك حتى تتمكن من متابعة هذا البرنامج التعليمي:

- Visual Studio: تأكد من تثبيت Visual Studio على جهاز الكمبيوتر الخاص بك، حيث سنستخدمه لتشغيل كود .NET الخاص بنا.
-  مكتبة Aspose.PDF: ستحتاج إلى مكتبة Aspose.PDF. يمكنك تنزيلها من[هنا](https://releases.aspose.com/pdf/net/) إذا كنت جديدًا عليه، فقد ترغب في تجربة[نسخة تجريبية مجانية](https://releases.aspose.com/).
- .NET Framework: تأكد من تثبيت إصدار متوافق من .NET Framework لتشغيل مكتبة Aspose.PDF.

من خلال توفير هذه المتطلبات الأساسية، ستكون جاهزًا لإنشاء ملف PDF الخاص بك مع رؤوس قابلة للتخصيص!

## استيراد الحزم

الآن بعد اكتمال عملية الإعداد، فلنبدأ في استيراد الحزم اللازمة. هذه خطوة بالغة الأهمية، لأنها تسمح لنا بالاستفادة من كافة الميزات الرائعة التي يوفرها Aspose.PDF.

إليك كيفية استيراد مساحة اسم Aspose.PDF المطلوبة في مشروع C# الخاص بك:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

تأكد من أن هذه العبارات موجودة في أعلى ملف C# الخاص بك حتى تتمكن من الوصول إلى جميع الفئات والطرق التي سنستخدمها.

## الخطوة 1: تحديد المسار إلى مستندك

 أولاً، دعنا نحدد المسار إلى دليل مستندات PDF. هذا هو المكان الذي سنتمكن من خلاله من الوصول إلى ملف PDF وحفظ الملف المحدث. استبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي على نظامك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح مستند المصدر الخاص بك

 الآن بعد أن قمنا بتعيين دليل المستند، فإن الخطوة التالية هي فتح ملف PDF الذي نريد إضافة رؤوس إليه. سنستخدم`Aspose.Pdf.Document` الصف لهذا.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "AddingDifferentHeaders.pdf");
```

## الخطوة 3: إنشاء طوابع نصية

لنقم بإنشاء ثلاثة طوابع نصية مختلفة لاستخدامها كعناوين. فكر في الطوابع النصية على أنها ملصقات! يمكننا تخصيصها بالطريقة التي نريدها.

```csharp
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");
```

## الخطوة 4: تخصيص العنوان الأول

الآن حان الوقت لتخصيص رأس الصفحة الأول. سنقوم بتعيين محاذاة الرأس ونمطه ولونه وحجمه لجعله مميزًا.

```csharp
// تعيين محاذاة الطوابع
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// تفاصيل التنسيق
stamp1.TextState.FontStyle = FontStyles.Bold;
stamp1.TextState.ForegroundColor = Color.Red;
stamp1.TextState.FontSize = 14;
```

## الخطوة 5: تخصيص العنوان الثاني

بعد ذلك، دعونا نولي بعض الاهتمام للعنوان الثاني. وسنعمل أيضًا على تعديل مستوى التكبير الخاص به، مما قد يجعل النص يبدو أكبر أو أصغر في ملف PDF.

```csharp
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp2.Zoom = 10;
```

## الخطوة 6: تخصيص العنوان الثالث

بالنسبة لعنواننا الثالث، سنضيف بعض اللمسات الفنية من خلال ضبطه ليدور بزاوية وتغيير لون خلفيته إلى اللون الوردي. وإليك كيفية القيام بذلك:

```csharp
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp3.RotateAngle = 35;
stamp3.TextState.BackgroundColor = Color.Pink;
stamp3.TextState.Font = FontRepository.FindFont("Verdana");
```

## الخطوة 7: إضافة الطوابع إلى صفحات PDF

بعد أن أصبحت الطوابع جاهزة، حان الوقت لوضعها على الصفحات المخصصة لها. فكر في الأمر وكأنك تضع الملصقات على صفحات مختلفة من سجل القصاصات الخاص بك!

```csharp
doc.Pages[1].AddStamp(stamp1); // إضافة الطابع الأول
doc.Pages[2].AddStamp(stamp2); // إضافة الطابع الثاني
doc.Pages[3].AddStamp(stamp3); // إضافة الطابع الثالث
```

## الخطوة 8: حفظ المستند المحدث

الخطوة الأخيرة هي حفظ التغييرات. تمامًا كما هو الحال مع حفظ عملك في محرر المستندات، نحتاج إلى حفظ ملف PDF الذي تم تعديله حديثًا.

```csharp
dataDir = dataDir + "multiheader_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nDifferent headers added successfully.\nFile saved at " + dataDir);
```

هذا كل شيء! لقد نجحت في إضافة عناوين مختلفة إلى ملف PDF الخاص بك. 

## خاتمة

في هذا البرنامج التعليمي، قمنا بتغطية كيفية استخدام Aspose.PDF لـ .NET لإضافة رؤوس مخصصة إلى صفحات متعددة في مستند PDF. باستخدام القليل من التعليمات البرمجية، يمكنك بسهولة جعل مستنداتك أكثر احترافية وجاذبية بصريًا. 

## الأسئلة الشائعة

### هل يمكنني تغيير خط الرأس؟  
 نعم يمكنك ذلك! تعديل`stamp.TextState.Font` الخاصية لتطبيق أي خط من الخطوط المتوفرة في Aspose.

### هل هناك حد لعدد العناوين التي يمكنني إضافتها؟  
لا، يمكنك إضافة عدد كبير من العناوين كما تريد؛ فقط تأكد من إنشاء طابع مطابق لكل عنوان.

### هل يمكنني استخدام هذه الطريقة لإضافة الصور كعناوين؟  
يركز هذا البرنامج التعليمي حاليًا على طوابع النص، ولكن Aspose.PDF يسمح أيضًا بإضافة طوابع الصور.

### كيف يمكنني محاذاة رأس الصفحة بشكل عمودي في المنتصف؟  
 يمكنك استخدام`VerticalAlignment.Center` ولتحقيق ذلك، تأكد من محاذاته بشكل مثالي.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.PDF؟  
 يمكنك التحقق من[التوثيق](https://reference.aspose.com/pdf/net/) للحصول على أدلة وأمثلة مفصلة.