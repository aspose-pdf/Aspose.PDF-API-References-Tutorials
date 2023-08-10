---
title: تعريف المحاذاة في ملف PDF
linktitle: تعريف المحاذاة في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية ضبط محاذاة النص بسهولة في ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 70
url: /ar/net/programming-with-stamps-and-watermarks/define-alignment/
---
في هذا البرنامج التعليمي ، سوف نأخذك خطوة بخطوة حول كيفية ضبط محاذاة النص في ملف PDF باستخدام Aspose.PDF لـ .NET. سنوضح لك كيفية استخدام كود المصدر C # المقدم لإنشاء طابع نصي مركزي في ملف PDF.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والمشار إليها في مشروعك.

## الخطوة الثانية: تحميل مستند PDF

تتمثل الخطوة الأولى في تحميل مستند PDF الحالي في مشروعك. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء كائن مستند بملف الإدخال
Document doc = new Document(dataDir + "DefineAlignment.pdf");
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث يوجد مستند PDF الخاص بك.

## الخطوة 3: تحديد المحاذاة

الآن بعد أن قمت بتحميل مستند PDF ، يمكنك ضبط محاذاة ختم النص. إليك الطريقة:

```csharp
// إنشاء كائن FormattedText بسلسلة المثال
FormattedText text = new FormattedText("This");

// أضف سطرًا جديدًا من النص إلى FormattedText
text.AddNewLineText("is an example");
text.AddNewLineText("Center aligned");
text.AddNewLineText("Text buffer");
text.AddNewLineText("Subject");

// قم بإنشاء كائن TextStamp باستخدام FormattedText
TextStamp stamp = new TextStamp(text);

// حدد المحاذاة الأفقية للمخزن المؤقت للنص كتوسيط
stamp.HorizontalAlignment = HorizontalAlignment.Center;

// حدد المحاذاة الرأسية للمخزن المؤقت للنص كتوسيط
stamp.VerticalAlignment = VerticalAlignment.Center;

// حدد المحاذاة الأفقية للنص في TextStamp كتوسيط
stamp.TextAlignment = HorizontalAlignment.Center;

// تعيين الهامش العلوي لكائن المخزن المؤقت
stamp. TopMargin = 20;

// أضف كائن الختم إلى الصفحة الأولى من المستند
doc.Pages[1].AddStamp(stamp);
```

ينشئ الكود أعلاه مخزنًا مؤقتًا للنص المركزي باستخدام فئة FormattedText لتحديد المحتوى وتعيين المحاذاة الأفقية والرأسية لمخزن النص المؤقت.

## الخطوة 4: احفظ المستند الناتج

بمجرد تعيين محاذاة ختم النص ، يمكنك حفظ مستند PDF المعدل. إليك الطريقة:

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

// إنشاء كائن FormattedText بسلسلة نموذجية
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

// حدد المحاذاة الرأسية لختم النص كمحاذاة للوسط
stamp.VerticalAlignment = VerticalAlignment.Center;

// حدد محاذاة النص الأفقية لختم النص كمحاذاة للوسط
stamp.TextAlignment = HorizontalAlignment.Center;

// تعيين الهامش العلوي لكائن الطوابع
stamp.TopMargin = 20;

// أضف كائن الختم على الصفحة الأولى من المستند
doc.Pages[1].AddStamp(stamp);
dataDir = dataDir + "StampedPDF_out.pdf";

// احفظ المستند الذي تم تحديثه
doc.Save(dataDir);
Console.WriteLine("\nAlignment defined successfully for text stamp.\nFile saved at " + dataDir);

```

## خاتمة

تهنئة ! لقد تعلمت كيفية ضبط محاذاة النص في مستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن تطبيق هذه المعرفة لإنشاء أختام نصية بمحاذاة مختلفة في مستندات PDF الخاصة بك.

### أسئلة وأجوبة لتعريف المحاذاة في ملف PDF

#### س: ما هي محاذاة النص في مستند PDF ، ولماذا هي مهمة؟

ج: تشير محاذاة النص في مستند PDF إلى وضع النص داخل منطقة معينة ، مثل فقرة أو ختم نص. تعمل محاذاة النص المناسبة على تحسين قابلية القراءة والجاذبية المرئية للمستند ، مما يسهل على القراء متابعة المحتوى.

#### س: كيف يمكنني محاذاة النص في المنتصف داخل مستند PDF باستخدام Aspose.PDF لـ .NET؟

 ج: يوضح كود المصدر C # المقدم كيفية إنشاء طابع نصي مركزي باستخدام مكتبة Aspose.PDF. بتحديد`HorizontalAlignment` و`VerticalAlignment` خصائص`TextStamp` ، يمكنك تحقيق محاذاة المركز أفقيًا وعموديًا.

#### س: هل يمكنني محاذاة النص بشكل مختلف لأجزاء مختلفة من مستند PDF؟

ج: نعم ، يمكنك ضبط محاذاة النص لأجزاء مختلفة من مستند PDF عن طريق إنشاء عدة أجزاء`TextStamp` الكائنات وتعيين خصائص المحاذاة وفقًا لذلك. يتيح لك ذلك تحقيق محاذاة مختلفة داخل نفس المستند.

####  س: ما هو الغرض من استخدام ملف`FormattedText` class in the code?
 ج: إن`FormattedText` تسمح لك class بإنشاء محتوى نصي منظم بخيارات تنسيق وخيارات تنسيق متعددة. يتم استخدامه لتحديد محتوى ختم النص بأسطر نصية متعددة وفواصل أسطر جديدة.

#### س: كيف أقوم بتعديل محاذاة طابع نصي موجود في مستند PDF؟

 ج: لتعديل محاذاة طابع نصي موجود ، تحتاج إلى الوصول إلى المحدد`TextStamp` الكائن وتحديث خصائص المحاذاة (`HorizontalAlignment`, `VerticalAlignment`, `TextAlignment`) كما هو موضح في الكود المصدري المقدم.

#### س: هل من الممكن ضبط الهوامش حول ختم النص لتخطيط أفضل؟

 ج: نعم ، يمكنك ضبط الهامش العلوي لملف`TextStamp` كائن باستخدام`TopMargin`ملكية. يتيح لك ذلك التحكم في التباعد بين ختم النص والعناصر الأخرى على الصفحة.

#### س: هل يمكنني محاذاة النص في زوايا أو اتجاهات مختلفة باستخدام هذا النهج؟

 ج: بينما يركز هذا البرنامج التعليمي على المحاذاة المركزية ، يمكنك ضبط ملف`RotationAngle` ممتلكات`TextStamp` لمحاذاة النص في زوايا أو اتجاهات مختلفة ، وتحقيق تأثيرات مثل المحاذاة القطرية أو الرأسية.

#### س: ماذا لو أردت محاذاة النص بشكل مختلف على صفحات مختلفة من مستند PDF؟

 ج: يمكنك تعديل التعليمات البرمجية المصدر لإنشاء وتطبيق مختلف`TextStamp` كائنات ذات محاذاة محددة لصفحات مختلفة من وثيقة PDF. من خلال تكرار العملية لكل صفحة ، يمكنك تحقيق محاذاة متنوعة للنص في جميع أنحاء المستند.

#### س: كيف يمكنني تطبيق هذه المعرفة لإنشاء أنواع أخرى من الطوابع أو التعليقات التوضيحية بمحاذاة معينة؟

ج: يمكنك توسيع هذه المعرفة لإنشاء أنواع أخرى من الطوابع أو التعليقات التوضيحية (مثل طوابع الصور أو الرسومات المخصصة) باستخدام مبادئ محاذاة مماثلة والفئات المناسبة من مكتبة Aspose.PDF.
