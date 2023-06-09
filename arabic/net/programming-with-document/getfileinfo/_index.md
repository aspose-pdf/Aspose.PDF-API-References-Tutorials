---
title: الحصول على معلومات الملف
linktitle: الحصول على معلومات الملف
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام ميزة GetFileInfo في Aspose.PDF for .NET لاسترداد معلومات البيانات الوصفية حول مستند PDF.
type: docs
weight: 180
url: /ar/net/programming-with-document/getfileinfo/
---

 Aspose.PDF for .NET هي مكتبة شائعة لمعالجة ملفات PDF تتيح للمطورين إنشاء ملفات PDF وتحريرها وتحويلها في تطبيقات .NET الخاصة بهم. تتمثل إحدى الميزات التي توفرها هذه المكتبة في القدرة على استرداد المعلومات حول البيانات الوصفية لمستند PDF. سيرشدك هذا البرنامج التعليمي خلال خطوات استخدام ملف`GetFileInfo`ميزة Aspose.PDF for .NET لاسترداد معلومات حول البيانات الوصفية لمستند PDF.

## الخطوة 1: قم بتثبيت Aspose.PDF for .NET

 لاستخدام Aspose.PDF for .NET في تطبيقات .NET ، يجب عليك أولاً تثبيت المكتبة. يمكنك تنزيل أحدث إصدار من المكتبة من ملف[Aspose.PDF لصفحة تنزيل .NET](https://releases.aspose.com/pdf/net).

بمجرد تنزيل المكتبة ، قم باستخراج محتويات ملف ZIP إلى مجلد على جهاز الكمبيوتر الخاص بك. ستحتاج بعد ذلك إلى إضافة مرجع إلى Aspose.PDF لـ .NET DLL في مشروع .NET الخاص بك.

## الخطوة 2: قم بتحميل مستند PDF

 بمجرد تثبيت Aspose.PDF for .NET وإضافة مرجع إلى DLL في مشروع .NET الخاص بك ، يمكنك البدء في استخدام`GetFileInfo` ميزة لاسترداد معلومات حول البيانات الوصفية لمستند PDF.

تتمثل الخطوة الأولى في استخدام هذه الميزة في تحميل مستند PDF الذي تريد استرداد معلومات عنه. للقيام بذلك ، يمكنك استخدام الكود التالي:

```csharp
// المسار إلى وثيقة PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح مستند PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 في الكود أعلاه ، استبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يوجد مستند PDF الخاص بك. سيقوم هذا الرمز بتحميل مستند PDF إلى ملف`Document` ، والذي يمكنك استخدامه بعد ذلك لاسترداد معلومات حول البيانات الوصفية للمستند.

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

// افتح مستند PDF
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