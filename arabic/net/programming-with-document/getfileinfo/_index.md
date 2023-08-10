---
title: الحصول على معلومات الملف في ملف PDF
linktitle: الحصول على معلومات الملف في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام ميزة GetFileInfo في ملف PDF في Aspose.PDF for .NET لاسترداد معلومات البيانات الوصفية حول مستند PDF.
type: docs
weight: 180
url: /ar/net/programming-with-document/getfileinfo/
---
Aspose.PDF for .NET هي مكتبة شائعة لمعالجة ملفات PDF تتيح للمطورين إنشاء ملفات PDF وتحريرها وتحويلها في تطبيقات .NET الخاصة بهم. تتمثل إحدى الميزات التي توفرها هذه المكتبة في القدرة على استرداد المعلومات حول البيانات الوصفية لمستند PDF. سيرشدك هذا البرنامج التعليمي خلال خطوات استخدام ملف`GetFileInfo` ميزة Aspose.PDF for .NET لاسترداد معلومات حول البيانات الوصفية لمستند PDF.

## الخطوة 1: قم بتثبيت Aspose.PDF for .NET

 لاستخدام Aspose.PDF for .NET في تطبيقات .NET ، يجب عليك أولاً تثبيت المكتبة. يمكنك تنزيل أحدث إصدار من المكتبة من ملف[Aspose.PDF لصفحة تنزيل .NET](https://releases.aspose.com/pdf/net).

بمجرد تنزيل المكتبة ، قم باستخراج محتويات ملف ZIP إلى مجلد على جهاز الكمبيوتر الخاص بك. ستحتاج بعد ذلك إلى إضافة مرجع إلى Aspose.PDF لـ .NET DLL في مشروع .NET الخاص بك.

## الخطوة 2: قم بتحميل مستند PDF

 بمجرد تثبيت Aspose.PDF for .NET وإضافة مرجع إلى DLL في مشروع .NET الخاص بك ، يمكنك البدء في استخدام`GetFileInfo` ميزة لاسترداد معلومات حول البيانات الوصفية لمستند PDF.

تتمثل الخطوة الأولى في استخدام هذه الميزة في تحميل مستند PDF الذي تريد استرداد معلومات عنه. للقيام بذلك ، يمكنك استخدام الكود التالي:

```csharp
// المسار إلى وثيقة PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//افتح مستند PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 في الكود أعلاه ، استبدل`"YOUR DOCUMENT DIRECTORY"`مع المسار إلى الدليل حيث يوجد مستند PDF الخاص بك. سيقوم هذا الرمز بتحميل مستند PDF في ملف`Document` ، والذي يمكنك استخدامه بعد ذلك لاسترداد معلومات حول البيانات الوصفية للمستند.

## الخطوة 3: استرجع البيانات الوصفية للمستند

لاسترداد معلومات حول البيانات الأولية لمستند PDF ، يمكنك استخدام الكود التالي:

```csharp
// احصل على معلومات الوثيقة
DocumentInfo docInfo = pdfDocument.Info;

// إظهار معلومات المستند
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

في الكود أعلاه ، يسترد كل سطر خاصية بيانات وصفية مختلفة لمستند PDF ويخرجها إلى وحدة التحكم. يمكنك تخصيص هذا الرمز لاسترداد الخصائص التي تهتم بها فقط.

### مثال على كود المصدر للحصول على معلومات ملف PDF باستخدام Aspose.PDF لـ .NET

 فيما يلي رمز المصدر الكامل لاسترداد البيانات الوصفية لمستند PDF باستخدام امتداد`GetFileInfo` ميزة Aspose.PDF لـ .NET:

```csharp
// المسار إلى وثيقة PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//افتح مستند PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

// احصل على معلومات الوثيقة
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

في هذا البرنامج التعليمي ، ناقشنا كيفية استخدام Aspose.PDF لـ .NET لاسترداد معلومات حول البيانات الوصفية لمستند PDF. عن طريق تحميل مستند PDF والوصول إلى خصائص البيانات الأولية الخاصة به ، يمكنك جمع معلومات حول خصائص وخصائص المستند. يوفر Aspose.PDF for .NET واجهة برمجة تطبيقات بسيطة وسهلة الاستخدام للعمل مع مستندات PDF ، بما في ذلك استرداد معلومات البيانات الوصفية ، مما يجعلها أداة قيمة لمعالجة ملفات PDF في تطبيقات .NET.

### التعليمات

#### س: ما هي البيانات الوصفية في وثيقة PDF؟

ج: تشير البيانات الأولية في وثيقة PDF إلى المعلومات التي تصف خصائص وخصائص الوثيقة. تتضمن هذه المعلومات عادةً عنوان المستند والمؤلف والموضوع والكلمات الرئيسية وتاريخ الإنشاء وتاريخ التعديل والمزيد.

#### س: كيف يمكنني تثبيت Aspose.PDF for .NET في مشروع .NET الخاص بي؟

 ج: لتثبيت Aspose.PDF for .NET ، تحتاج إلى تنزيل المكتبة من ملف[Aspose.PDF لصفحة تنزيل .NET](https://releases.aspose.com/pdf/net)بعد التنزيل ، استخرج محتويات ملف ZIP وأضف مرجعًا إلى Aspose.PDF لـ .NET DLL في مشروع .NET الخاص بك.

#### س: هل يمكنني تخصيص الكود لاسترداد خصائص بيانات وصفية معينة فقط؟

ج: نعم ، يمكنك تخصيص الكود لاسترداد خصائص بيانات وصفية محددة عن طريق التعليق على الأسطر التي لا تحتاج إليها. يتوافق كل سطر في الكود مع خاصية بيانات وصفية محددة ، لذا يمكنك تضمين أو استبعاد الخصائص بناءً على متطلباتك.

#### س: ما أنواع خصائص البيانات الوصفية التي يمكنني استردادها باستخدام Aspose.PDF for .NET؟

ج: باستخدام Aspose.PDF for .NET ، يمكنك استرداد خصائص البيانات الوصفية المختلفة لمستند PDF ، بما في ذلك المؤلف والعنوان والموضوع والكلمات الرئيسية وتاريخ الإنشاء وتاريخ التعديل.