---
title: تحديد المحاذاة في ملف PDF
linktitle: تحديد المحاذاة في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية ضبط محاذاة النص بسهولة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 70
url: /ar/net/programming-with-stamps-and-watermarks/define-alignment/
---
في هذا البرنامج التعليمي، سنوضح لك خطوة بخطوة كيفية ضبط محاذاة النص في ملف PDF باستخدام Aspose.PDF لـ .NET. وسنوضح لك كيفية استخدام كود المصدر C# المقدم لإنشاء ختم نصي مركزي في ملف PDF.

## الخطوة 1: إعداد البيئة

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والإشارة إليها في مشروعك.

## الخطوة 2: تحميل مستند PDF

الخطوة الأولى هي تحميل مستند PDF الموجود في مشروعك. وإليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء كائن مستند باستخدام ملف الإدخال
Document doc = new Document(dataDir + "DefineAlignment.pdf");
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي إلى الدليل الذي يوجد به مستند PDF الخاص بك.

## الخطوة 3: تحديد المحاذاة

الآن بعد أن قمت بتحميل مستند PDF، يمكنك ضبط محاذاة ختم النص. إليك الطريقة:

```csharp
// إنشاء كائن FormattedText باستخدام سلسلة المثال
FormattedText text = new FormattedText("This");

// إضافة سطر جديد من النص إلى FormattedText
text.AddNewLineText("is an example");
text.AddNewLineText("Center aligned");
text.AddNewLineText("Text buffer");
text.AddNewLineText("Subject");

// إنشاء كائن TextStamp باستخدام FormattedText
TextStamp stamp = new TextStamp(text);

// تحديد المحاذاة الأفقية لمخزن النص كمحور
stamp.HorizontalAlignment = HorizontalAlignment.Center;

// تحديد المحاذاة الرأسية لمخزن النص كمحور
stamp.VerticalAlignment = VerticalAlignment.Center;

// حدد المحاذاة الأفقية للنص في TextStamp كمنتصف
stamp.TextAlignment = HorizontalAlignment.Center;

// تعيين الهامش العلوي لكائن المخزن المؤقت
stamp. TopMargin = 20;

// أضف كائن الختم إلى الصفحة الأولى من المستند
doc.Pages[1].AddStamp(stamp);
```

يقوم الكود أعلاه بإنشاء مخزن نص مركزي باستخدام فئة FormattedText لتحديد المحتوى وتعيين المحاذاة الأفقية والرأسية لمخزن النص.

## الخطوة 4: احفظ المستند الناتج

بمجرد ضبط محاذاة ختم النص، يمكنك حفظ مستند PDF المعدّل. إليك الطريقة:

```csharp
// حفظ المستند المحدث
doc.Save(dataDir);
```

يقوم الكود أعلاه بحفظ مستند PDF المحرر في الدليل المحدد.

### عينة من كود المصدر لتحديد المحاذاة باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن مستند باستخدام ملف الإدخال
Document doc = new Document(dataDir+ "DefineAlignment.pdf");

// إنشاء كائن FormattedText باستخدام سلسلة عينة
FormattedText text = new FormattedText("This");

// إضافة سطر نص جديد إلى FormattedText
text.AddNewLineText("is sample");
text.AddNewLineText("Center Aligned");
text.AddNewLineText("TextStamp");
text.AddNewLineText("Object");

// إنشاء كائن TextStamp باستخدام FormattedText
TextStamp stamp = new TextStamp(text);

// حدد محاذاة النص الأفقية بحيث تكون محاذية للوسط
stamp.HorizontalAlignment = HorizontalAlignment.Center;

// حدد المحاذاة الرأسية لختم النص بحيث تكون محاذية للمركز
stamp.VerticalAlignment = VerticalAlignment.Center;

// تحديد محاذاة النص الأفقية لـ TextStamp كمحاذاة مركزية
stamp.TextAlignment = HorizontalAlignment.Center;

// تعيين الهامش العلوي لكائن الطوابع
stamp.TopMargin = 20;

// أضف كائن الختم فوق الصفحة الأولى من المستند
doc.Pages[1].AddStamp(stamp);
dataDir = dataDir + "StampedPDF_out.pdf";

// حفظ المستند المحدث
doc.Save(dataDir);
Console.WriteLine("\nAlignment defined successfully for text stamp.\nFile saved at " + dataDir);

```

## خاتمة

تهانينا! لقد تعلمت كيفية ضبط محاذاة النص في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن تطبيق هذه المعرفة لإنشاء طوابع نصية بمحاذاة مختلفة في مستندات PDF الخاصة بك.

### الأسئلة الشائعة حول تحديد المحاذاة في ملف PDF

#### س: ما هو محاذاة النص في مستند PDF، ولماذا هو مهم؟

أ: يشير محاذاة النص في مستند PDF إلى وضع النص داخل منطقة معينة، مثل فقرة أو ختم نصي. تعمل محاذاة النص المناسبة على تعزيز قابلية القراءة والجاذبية البصرية للمستند، مما يجعل من الأسهل على القراء متابعة المحتوى.

#### س: كيف يمكنني محاذاة النص في المنتصف داخل مستند PDF باستخدام Aspose.PDF لـ .NET؟

 أ: يوضح كود المصدر C# المقدم كيفية إنشاء ختم نصي مركزي باستخدام مكتبة Aspose.PDF. من خلال تحديد`HorizontalAlignment` و`VerticalAlignment` خصائص`TextStamp` يمكنك تحقيق محاذاة المركز أفقيًا ورأسيًا.

#### س: هل يمكنني محاذاة النص بشكل مختلف لأجزاء مختلفة من مستند PDF؟

ج: نعم، يمكنك ضبط محاذاة النص لأجزاء مختلفة من مستند PDF عن طريق إنشاء أجزاء متعددة`TextStamp` الكائنات وتعيين خصائص محاذاتها وفقًا لذلك. يتيح لك هذا تحقيق محاذات مختلفة داخل نفس المستند.

####  س: ما هو الغرض من استخدام`FormattedText` class in the code?
 أ: ال`FormattedText` تتيح لك الفئة إنشاء محتوى نص منظم يحتوي على أسطر متعددة وخيارات تنسيق. يتم استخدامها لتحديد محتوى ختم النص باستخدام أسطر متعددة من النص وفواصل أسطر جديدة.

#### س: كيف يمكنني تعديل محاذاة ختم النص الموجود في مستند PDF؟

 أ: لتعديل محاذاة ختم النص الموجود، تحتاج إلى الوصول إلى ملف`TextStamp` الكائن وتحديث خصائص محاذاته (`HorizontalAlignment`, `VerticalAlignment`, `TextAlignment`) كما هو موضح في الكود المصدر المقدم.

#### س: هل من الممكن تعديل الهوامش حول ختم النص للحصول على تخطيط أفضل؟

 ج: نعم، يمكنك تعديل الهامش العلوي للورقة.`TextStamp` كائن باستخدام`TopMargin`يتيح لك هذا التحكم في المسافة بين ختم النص والعناصر الأخرى في الصفحة.

#### س: هل يمكنني محاذاة النص بزوايا أو اتجاهات مختلفة باستخدام هذا النهج؟

 أ: بينما يركز هذا البرنامج التعليمي على محاذاة المركز، يمكنك ضبط`RotationAngle` ممتلكات`TextStamp` كائن لمحاذاة النص في زوايا أو اتجاهات مختلفة، وتحقيق تأثيرات مثل المحاذاة القطرية أو الرأسية.

#### س: ماذا لو أردت محاذاة النص بشكل مختلف على صفحات مختلفة من مستند PDF؟

 أ: يمكنك تعديل الكود المصدر لإنشاء وتطبيق تطبيقات مختلفة`TextStamp` يمكنك تطبيق محاذاة نصية مختلفة على صفحات مختلفة من مستند PDF. من خلال تكرار العملية لكل صفحة، يمكنك تحقيق محاذاة نصية متنوعة في جميع أنحاء المستند.

#### س: كيف يمكنني تطبيق هذه المعرفة لإنشاء أنواع أخرى من الطوابع أو التعليقات ذات محاذاة محددة؟

ج: يمكنك توسيع هذه المعرفة لإنشاء أنواع أخرى من الطوابع أو التعليقات التوضيحية (مثل طوابع الصور أو الرسومات المخصصة) باستخدام مبادئ محاذاة مماثلة والفئات المناسبة من مكتبة Aspose.PDF.
