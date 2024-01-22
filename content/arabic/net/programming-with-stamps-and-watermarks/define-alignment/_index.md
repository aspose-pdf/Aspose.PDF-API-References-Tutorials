---
title: تحديد المحاذاة في ملف PDF
linktitle: تحديد المحاذاة في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية ضبط محاذاة النص بسهولة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 70
url: /ar/net/programming-with-stamps-and-watermarks/define-alignment/
---
في هذا البرنامج التعليمي، سنأخذك خطوة بخطوة حول كيفية ضبط محاذاة النص في ملف PDF باستخدام Aspose.PDF لـ .NET. سنوضح لك كيفية استخدام كود مصدر C# المقدم لإنشاء ختم نصي مركزي في ملف PDF.

## الخطوة 1: تهيئة البيئة

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF الخاصة بـ .NET والإشارة إليها في مشروعك.

## الخطوة 2: تحميل مستند PDF

الخطوة الأولى هي تحميل مستند PDF الموجود في مشروعك. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء كائن مستند باستخدام ملف الإدخال
Document doc = new Document(dataDir + "DefineAlignment.pdf");
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي للدليل الذي يوجد به مستند PDF الخاص بك.

## الخطوة 3: تحديد المحاذاة

الآن بعد أن قمت بتحميل مستند PDF، يمكنك ضبط محاذاة ختم النص. إليك الطريقة:

```csharp
// إنشاء كائن FormattedText باستخدام سلسلة المثال
FormattedText text = new FormattedText("This");

// أضف سطرًا جديدًا من النص إلى FormattedText
text.AddNewLineText("is an example");
text.AddNewLineText("Center aligned");
text.AddNewLineText("Text buffer");
text.AddNewLineText("Subject");

// قم بإنشاء كائن TextStamp باستخدام FormattedText
TextStamp stamp = new TextStamp(text);

// حدد المحاذاة الأفقية للمخزن المؤقت للنص في المنتصف
stamp.HorizontalAlignment = HorizontalAlignment.Center;

// حدد المحاذاة الرأسية للمخزن المؤقت للنص في المنتصف
stamp.VerticalAlignment = VerticalAlignment.Center;

// حدد المحاذاة الأفقية للنص في TextStamp كتوسيط
stamp.TextAlignment = HorizontalAlignment.Center;

// تعيين الهامش العلوي لكائن المخزن المؤقت
stamp. TopMargin = 20;

// قم بإضافة كائن الطابع إلى الصفحة الأولى من المستند
doc.Pages[1].AddStamp(stamp);
```

يقوم الكود أعلاه بإنشاء مخزن مؤقت للنص في المنتصف باستخدام فئة FormattedText لتحديد المحتوى وتعيين المحاذاة الأفقية والرأسية للمخزن المؤقت للنص.

## الخطوة 4: احفظ مستند الإخراج

بمجرد قيامك بتعيين محاذاة ختم النص، يمكنك حفظ مستند PDF المعدل. إليك الطريقة:

```csharp
// احفظ المستند المحدث
doc.Save(dataDir);
```

يحفظ الكود أعلاه مستند PDF المحرر في الدليل المحدد.

### نموذج التعليمات البرمجية المصدر لـ Define Alignment باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن المستند مع ملف الإدخال
Document doc = new Document(dataDir+ "DefineAlignment.pdf");

// إنشاء كائن FormattedText باستخدام سلسلة عينة
FormattedText text = new FormattedText("This");

// إضافة سطر نص جديد إلى FormattedText
text.AddNewLineText("is sample");
text.AddNewLineText("Center Aligned");
text.AddNewLineText("TextStamp");
text.AddNewLineText("Object");

// قم بإنشاء كائن TextStamp باستخدام FormattedText
TextStamp stamp = new TextStamp(text);

// حدد المحاذاة الأفقية لختم النص كمحاذاة للوسط
stamp.HorizontalAlignment = HorizontalAlignment.Center;

// حدد المحاذاة العمودية لختم النص كمحاذاة للوسط
stamp.VerticalAlignment = VerticalAlignment.Center;

// حدد محاذاة النص الأفقية لـ TextStamp كمحاذاة للوسط
stamp.TextAlignment = HorizontalAlignment.Center;

// تعيين الهامش العلوي لكائن الطوابع
stamp.TopMargin = 20;

// قم بإضافة كائن الختم على الصفحة الأولى من المستند
doc.Pages[1].AddStamp(stamp);
dataDir = dataDir + "StampedPDF_out.pdf";

// احفظ المستند المحدث
doc.Save(dataDir);
Console.WriteLine("\nAlignment defined successfully for text stamp.\nFile saved at " + dataDir);

```

## خاتمة

تهنئة ! لقد تعلمت كيفية ضبط محاذاة النص في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن تطبيق هذه المعرفة لإنشاء طوابع نصية بمحاذاة مختلفة في مستندات PDF الخاصة بك.

### الأسئلة الشائعة لتحديد المحاذاة في ملف PDF

#### س: ما هي محاذاة النص في مستند PDF، ولماذا هي مهمة؟

ج: تشير محاذاة النص في مستند PDF إلى موضع النص داخل منطقة معينة، مثل فقرة أو ختم نص. تعمل محاذاة النص الصحيحة على تحسين إمكانية القراءة والجاذبية المرئية للمستند، مما يسهل على القراء متابعة المحتوى.

#### س: كيف يمكنني محاذاة النص إلى المنتصف داخل مستند PDF باستخدام Aspose.PDF لـ .NET؟

 ج: يوضح كود مصدر C# كيفية إنشاء طابع نصي مركزي باستخدام مكتبة Aspose.PDF. وذلك بتحديد`HorizontalAlignment` و`VerticalAlignment` خصائص`TextStamp` كائن، يمكنك تحقيق محاذاة المركز أفقيًا وعموديًا.

#### س: هل يمكنني محاذاة النص بشكل مختلف لأجزاء مختلفة من مستند PDF؟

ج: نعم، يمكنك ضبط محاذاة النص لأجزاء مختلفة من مستند PDF عن طريق إنشاء عدة أجزاء`TextStamp` الكائنات وتعيين خصائص المحاذاة الخاصة بها وفقًا لذلك. يتيح لك ذلك تحقيق توافقات مختلفة داخل نفس المستند.

####  س: ما هو الغرض من استخدام`FormattedText` class in the code?
 ج: ال`FormattedText` يتيح لك class إنشاء محتوى نص منظم يحتوي على أسطر متعددة وخيارات تنسيق. يتم استخدامه لتحديد محتوى ختم النص بأسطر نصية متعددة وفواصل أسطر جديدة.

#### س: كيف يمكنني تعديل محاذاة ختم نص موجود في مستند PDF؟

 ج: لتعديل محاذاة ختم نص موجود، تحتاج إلى الوصول إلى العنصر المحدد`TextStamp` الكائن وتحديث خصائص المحاذاة الخاصة به (`HorizontalAlignment`, `VerticalAlignment`, `TextAlignment`) كما هو موضح في كود المصدر المقدم.

#### س: هل من الممكن ضبط الهوامش حول ختم النص للحصول على تخطيط أفضل؟

 ج: نعم، يمكنك ضبط الهامش العلوي لل`TextStamp` كائن باستخدام`TopMargin`ملكية. يتيح لك ذلك التحكم في التباعد بين ختم النص والعناصر الأخرى الموجودة على الصفحة.

#### س: هل يمكنني محاذاة النص بزوايا أو اتجاهات مختلفة باستخدام هذا الأسلوب؟

 ج: بينما يركز هذا البرنامج التعليمي على المحاذاة المركزية، يمكنك ضبط`RotationAngle` ملكية`TextStamp` كائن لمحاذاة النص في زوايا أو اتجاهات مختلفة، وتحقيق تأثيرات مثل المحاذاة القطرية أو الرأسية.

#### س: ماذا لو كنت أرغب في محاذاة النص بشكل مختلف على صفحات مختلفة من مستند PDF؟

 ج: يمكنك تعديل الكود المصدري لإنشاء وتطبيق مختلف`TextStamp` كائنات ذات محاذاة محددة لصفحات مختلفة من مستند PDF. من خلال تكرار العملية لكل صفحة، يمكنك تحقيق محاذاة نصية متنوعة في جميع أنحاء المستند.

#### س: كيف يمكنني تطبيق هذه المعرفة لإنشاء أنواع أخرى من الطوابع أو التعليقات التوضيحية بمحاذاة محددة؟

ج: يمكنك توسيع هذه المعرفة لإنشاء أنواع أخرى من الطوابع أو التعليقات التوضيحية (مثل طوابع الصور أو الرسومات المخصصة) باستخدام مبادئ محاذاة مماثلة والفئات المناسبة من مكتبة Aspose.PDF.
