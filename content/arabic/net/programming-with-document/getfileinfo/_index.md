---
title: الحصول على معلومات الملف في ملف PDF
linktitle: الحصول على معلومات الملف في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام ميزة GetFileInfo في ملف PDF الخاصة بـ Aspose.PDF لـ .NET لاسترداد معلومات البيانات التعريفية حول مستند PDF.
type: docs
weight: 180
url: /ar/net/programming-with-document/getfileinfo/
---
 Aspose.PDF for .NET هي مكتبة شائعة لمعالجة ملفات PDF تتيح للمطورين إنشاء ملفات PDF وتحريرها وتحويلها في تطبيقات .NET الخاصة بهم. إحدى الميزات التي تقدمها هذه المكتبة هي القدرة على استرداد المعلومات حول البيانات التعريفية لمستند PDF. سيرشدك هذا البرنامج التعليمي خلال خطوات استخدام`GetFileInfo` ميزة Aspose.PDF لـ .NET لاسترداد معلومات حول البيانات التعريفية لمستند PDF.

## الخطوة 1: تثبيت Aspose.PDF لـ .NET

 لاستخدام Aspose.PDF لـ .NET في تطبيقات .NET الخاصة بك، يجب عليك أولاً تثبيت المكتبة. يمكنك تنزيل أحدث إصدار من المكتبة من[صفحة تنزيل Aspose.PDF لـ .NET](https://releases.aspose.com/pdf/net).

بمجرد تنزيل المكتبة، قم باستخراج محتويات الملف المضغوط إلى مجلد على جهاز الكمبيوتر الخاص بك. ستحتاج بعد ذلك إلى إضافة مرجع إلى Aspose.PDF لـ .NET DLL في مشروع .NET الخاص بك.

## الخطوة 2: قم بتحميل مستند PDF

بمجرد تثبيت Aspose.PDF لـ .NET وإضافة مرجع إلى DLL في مشروع .NET الخاص بك، يمكنك البدء في استخدام`GetFileInfo` ميزة لاسترداد معلومات حول البيانات التعريفية لمستند PDF.

الخطوة الأولى في استخدام هذه الميزة هي تحميل مستند PDF الذي تريد استرداد معلومات عنه. للقيام بذلك، يمكنك استخدام الكود التالي:

```csharp
// المسار إلى وثيقة PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//افتح مستند بي دي إف
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 في الكود أعلاه، استبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل الذي يوجد به مستند PDF الخاص بك. سيقوم هذا الرمز بتحميل مستند PDF إلى ملف`Document` كائن، والذي يمكنك بعد ذلك استخدامه لاسترداد معلومات حول البيانات التعريفية للمستند.

## الخطوة 3: استرداد البيانات التعريفية للمستند

لاسترداد معلومات حول البيانات التعريفية لمستند PDF، يمكنك استخدام الكود التالي:

```csharp
// الحصول على معلومات الوثيقة
DocumentInfo docInfo = pdfDocument.Info;

// إظهار معلومات الوثيقة
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

في الكود أعلاه، يسترد كل سطر خاصية بيانات تعريف مختلفة لمستند PDF ويخرجها إلى وحدة التحكم. يمكنك تخصيص هذا الرمز لاسترداد الخصائص التي تهمك فقط.

### مثال على كود المصدر للحصول على معلومات ملف PDF باستخدام Aspose.PDF لـ .NET

 إليك الكود المصدري الكامل لاسترداد البيانات التعريفية لمستند PDF باستخدام ملف`GetFileInfo` ميزة Aspose.PDF لـ .NET:

```csharp
// المسار إلى وثيقة PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//افتح مستند بي دي إف
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

// الحصول على معلومات الوثيقة
DocumentInfo docInfo = pdfDocument.Info;

// إظهار معلومات الوثيقة
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

## خاتمة

في هذا البرنامج التعليمي، ناقشنا كيفية استخدام Aspose.PDF لـ .NET لاسترداد معلومات حول البيانات التعريفية لمستند PDF. من خلال تحميل مستند PDF والوصول إلى خصائص بيانات التعريف الخاصة به، يمكنك جمع معلومات حول خصائص المستند وخصائصه. يوفر Aspose.PDF for .NET واجهة برمجة تطبيقات بسيطة وسهلة الاستخدام للعمل مع مستندات PDF، بما في ذلك استرداد معلومات البيانات التعريفية، مما يجعلها أداة قيمة لمعالجة PDF في تطبيقات .NET.

### الأسئلة الشائعة

#### س: ما هي البيانات الوصفية في وثيقة PDF؟

ج: تشير البيانات الوصفية في مستند PDF إلى المعلومات التي تصف خصائص المستند وخصائصه. تتضمن هذه المعلومات عادةً عنوان المستند ومؤلفه وموضوعه والكلمات الرئيسية وتاريخ الإنشاء وتاريخ التعديل والمزيد.

#### س: كيف يمكنني تثبيت Aspose.PDF لـ .NET في مشروع .NET الخاص بي؟

 ج: لتثبيت Aspose.PDF لـ .NET، تحتاج إلى تنزيل المكتبة من ملف[صفحة تنزيل Aspose.PDF لـ .NET](https://releases.aspose.com/pdf/net). بعد التنزيل، قم باستخراج محتويات الملف المضغوط وإضافة مرجع إلى Aspose.PDF لـ .NET DLL في مشروع .NET الخاص بك.

#### س: هل يمكنني تخصيص التعليمات البرمجية لاسترداد خصائص بيانات التعريف المحددة فقط؟

ج: نعم، يمكنك تخصيص التعليمات البرمجية لاسترداد خصائص بيانات التعريف المحددة عن طريق التعليق على السطور التي لا تحتاج إليها. يتوافق كل سطر في التعليمات البرمجية مع خاصية بيانات تعريف محددة، بحيث يمكنك تضمين الخصائص أو استبعادها بناءً على متطلباتك.

#### س: ما هي أنواع خصائص البيانات التعريفية التي يمكنني استردادها باستخدام Aspose.PDF لـ .NET؟

ج: باستخدام Aspose.PDF لـ .NET، يمكنك استرداد خصائص البيانات التعريفية المتنوعة لمستند PDF، بما في ذلك المؤلف والعنوان والموضوع والكلمات الأساسية وتاريخ الإنشاء وتاريخ التعديل.