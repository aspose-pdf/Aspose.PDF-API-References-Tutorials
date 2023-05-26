---
title: احصل على XMP Metadata
linktitle: احصل على XMP Metadata
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام ميزة GetXmpMetadata في Aspose.PDF for .NET لاستخراج بيانات XMP الوصفية من مستند PDF باستخدام كود مصدر C #.
type: docs
weight: 200
url: /ar/net/programming-with-document/getxmpmetadata/
---

 Aspose.PDF for .NET هي مكتبة شائعة لمعالجة ملفات PDF تتيح للمطورين إنشاء ملفات PDF وتحريرها وتحويلها في تطبيقات .NET الخاصة بهم. تتمثل إحدى الميزات التي توفرها هذه المكتبة في القدرة على استخراج بيانات تعريف XMP من مستند PDF. سيرشدك هذا البرنامج التعليمي خلال خطوات استخدام ملف`GetXmpMetadata` ميزة Aspose.PDF for .NET لاستخراج بيانات XMP الوصفية من مستند PDF.

## الخطوة 1: قم بتثبيت Aspose.PDF for .NET

 لاستخدام Aspose.PDF for .NET في تطبيقات .NET ، يجب عليك أولاً تثبيت المكتبة. يمكنك تنزيل أحدث إصدار من المكتبة من ملف[Aspose.PDF لصفحة تنزيل .NET](https://releases.aspose.com/pdf/net).

بمجرد تنزيل المكتبة ، قم باستخراج محتويات ملف ZIP إلى مجلد على جهاز الكمبيوتر الخاص بك. ستحتاج بعد ذلك إلى إضافة مرجع إلى Aspose.PDF لـ .NET DLL في مشروع .NET الخاص بك.

## الخطوة 2: قم بتحميل مستند PDF

 بمجرد تثبيت Aspose.PDF for .NET وإضافة مرجع إلى DLL في مشروع .NET الخاص بك ، يمكنك البدء في استخدام`GetXmpMetadata` ميزة لاستخراج بيانات XMP الأولية من مستند PDF.

تتمثل الخطوة الأولى في استخدام هذه الميزة في تحميل مستند PDF الذي تريد استخراج بيانات XMP الوصفية منه. للقيام بذلك ، يمكنك استخدام الكود التالي:

```csharp
// المسار إلى وثيقة PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//افتح مستند PDF
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");
```

 في الكود أعلاه ، استبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يوجد مستند PDF الخاص بك. سيقوم هذا الرمز بتحميل مستند PDF إلى ملف`Document` الذي يمكنك استخدامه بعد ذلك لاستخراج بيانات تعريف XMP.

## الخطوة 3: استخراج بيانات XMP الوصفية

لاستخراج بيانات XMP الأولية من مستند PDF ، يمكنك استخدام الكود التالي:

```csharp
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 في الكود أعلاه ،`xmp:CreateDate`, `xmp:Nickname` ، و`xmp:CustomProperty`هي أمثلة على خصائص بيانات XMP الأولية التي يمكنك استخلاصها من مستند PDF. يمكنك استبدال أسماء الخصائص هذه بأسماء أي خصائص بيانات أولية لـ XMP تريد استخراجها.

## مثال التعليمات البرمجية المصدر للحصول على بيانات تعريف XMP باستخدام Aspose.PDF لـ .NET

 إليك التعليمات البرمجية المصدر الكاملة لاستخراج بيانات XMP الوصفية من مستند PDF باستخدام ملف`GetXmpMetadata` ميزة Aspose.PDF لـ .NET:

```csharp
// المسار إلى وثيقة PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//افتح مستند PDF
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");

// استخراج بيانات تعريف XMP
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 في الكود أعلاه ، استبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يوجد مستند PDF الخاص بك. سيقوم هذا الرمز باستخراج بيانات XMP الوصفية من مستند PDF وإخراجها إلى وحدة التحكم.