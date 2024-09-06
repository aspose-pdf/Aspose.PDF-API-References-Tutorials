---
title: الحصول على معلومات الملف في ملف PDF
linktitle: الحصول على معلومات الملف في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية استخدام ميزة GetFileInfo في ملف PDF في Aspose.PDF لـ .NET لاسترداد معلومات البيانات الوصفية حول مستند PDF.
type: docs
weight: 180
url: /ar/net/programming-with-document/getfileinfo/
---
 Aspose.PDF for .NET هي مكتبة معالجة PDF شائعة تتيح للمطورين إنشاء ملفات PDF وتحريرها وتحويلها في تطبيقات .NET الخاصة بهم. إحدى الميزات التي تقدمها هذه المكتبة هي القدرة على استرداد المعلومات حول بيانات التعريف الخاصة بمستند PDF. سيرشدك هذا البرنامج التعليمي خلال خطوات استخدام`GetFileInfo` ميزة Aspose.PDF لـ .NET لاسترجاع المعلومات حول البيانات الوصفية لمستند PDF.

## الخطوة 1: تثبيت Aspose.PDF لـ .NET

 لاستخدام Aspose.PDF لـ .NET في تطبيقات .NET الخاصة بك، يجب عليك أولاً تثبيت المكتبة. يمكنك تنزيل أحدث إصدار من المكتبة من[صفحة تنزيل Aspose.PDF لـ .NET](https://releases.aspose.com/pdf/net).

بمجرد تنزيل المكتبة، قم باستخراج محتويات ملف ZIP إلى مجلد على جهاز الكمبيوتر الخاص بك. ستحتاج بعد ذلك إلى إضافة مرجع إلى ملف Aspose.PDF for .NET DLL في مشروع .NET الخاص بك.

## الخطوة 2: تحميل مستند PDF

 بمجرد تثبيت Aspose.PDF لـ .NET وإضافة مرجع إلى DLL في مشروع .NET الخاص بك، يمكنك البدء في استخدام`GetFileInfo` ميزة لاسترجاع معلومات حول البيانات الوصفية لمستند PDF.

الخطوة الأولى لاستخدام هذه الميزة هي تحميل مستند PDF الذي تريد استرجاع معلومات عنه. للقيام بذلك، يمكنك استخدام الكود التالي:

```csharp
// المسار إلى مستند PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح مستند PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 في الكود أعلاه، استبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل الذي يوجد به مستند PDF الخاص بك. سيقوم هذا الكود بتحميل مستند PDF إلى`Document` الكائن، الذي يمكنك استخدامه بعد ذلك لاسترجاع المعلومات حول بيانات التعريف الخاصة بالمستند.

## الخطوة 3: استرداد بيانات التعريف الخاصة بالمستند

لاسترجاع معلومات حول البيانات الوصفية لمستند PDF، يمكنك استخدام الكود التالي:

```csharp
// الحصول على معلومات الوثيقة
DocumentInfo docInfo = pdfDocument.Info;

// إظهار معلومات المستند
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

في الكود أعلاه، يقوم كل سطر باسترداد خاصية بيانات وصفية مختلفة لمستند PDF وإخراجها إلى وحدة التحكم. يمكنك تخصيص هذا الكود لاسترداد الخصائص التي تهمك فقط.

### مثال على الحصول على معلومات ملف PDF باستخدام Aspose.PDF لـ .NET

 فيما يلي الكود المصدر الكامل لاسترجاع البيانات الوصفية لمستند PDF باستخدام`GetFileInfo` ميزات Aspose.PDF لـ .NET:

```csharp
// المسار إلى مستند PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح مستند PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

// الحصول على معلومات الوثيقة
DocumentInfo docInfo = pdfDocument.Info;

// إظهار معلومات المستند
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

## خاتمة

في هذا البرنامج التعليمي، ناقشنا كيفية استخدام Aspose.PDF for .NET لاسترداد معلومات حول البيانات الوصفية لمستند PDF. من خلال تحميل مستند PDF والوصول إلى خصائص البيانات الوصفية الخاصة به، يمكنك جمع معلومات حول خصائص المستند وخصائصه. يوفر Aspose.PDF for .NET واجهة برمجة تطبيقات بسيطة وسهلة الاستخدام للعمل مع مستندات PDF، بما في ذلك استرداد معلومات البيانات الوصفية، مما يجعله أداة قيمة لمعالجة PDF في تطبيقات .NET.

### الأسئلة الشائعة

#### س: ما هي البيانات الوصفية في مستند PDF؟

أ: تشير البيانات الوصفية في مستند PDF إلى المعلومات التي تصف خصائص المستند وسماته. تتضمن هذه المعلومات عادةً عنوان المستند ومؤلفه وموضوعه والكلمات الرئيسية وتاريخ إنشائه وتاريخ تعديله والمزيد.

#### س: كيف يمكنني تثبيت Aspose.PDF لـ .NET في مشروع .NET الخاص بي؟

 أ: لتثبيت Aspose.PDF لـ .NET، تحتاج إلى تنزيل المكتبة من[صفحة تنزيل Aspose.PDF لـ .NET](https://releases.aspose.com/pdf/net)بعد التنزيل، قم باستخراج محتويات ملف ZIP وأضف مرجعًا إلى Aspose.PDF for .NET DLL في مشروع .NET الخاص بك.

#### س: هل يمكنني تخصيص الكود لاسترجاع خصائص بيانات وصفية محددة فقط؟

ج: نعم، يمكنك تخصيص الكود لاسترجاع خصائص بيانات وصفية محددة من خلال التعليق على الأسطر التي لا تحتاج إليها. يتوافق كل سطر في الكود مع خاصية بيانات وصفية محددة، لذا يمكنك تضمين أو استبعاد الخصائص بناءً على متطلباتك.

#### س: ما هي أنواع خصائص البيانات الوصفية التي يمكنني استرجاعها باستخدام Aspose.PDF لـ .NET؟

ج: باستخدام Aspose.PDF لـ .NET، يمكنك استرداد خصائص البيانات الوصفية المختلفة لمستند PDF، بما في ذلك المؤلف والعنوان والموضوع والكلمات الأساسية وتاريخ الإنشاء وتاريخ التعديل.