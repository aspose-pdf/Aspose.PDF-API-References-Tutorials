---
title: الحصول على تحذيرات لاستبدال الخط
linktitle: الحصول على تحذيرات لاستبدال الخط
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام ميزة GetWarningsForFontSubstitution الخاصة بـ Aspose.PDF for .NET لاكتشاف تحذيرات استبدال الخط عند فتح مستند PDF.
type: docs
weight: 190
url: /ar/net/programming-with-document/getwarningsforfontsubstitution/
---

 Aspose.PDF for .NET هي مكتبة شائعة لمعالجة ملفات PDF تتيح للمطورين إنشاء ملفات PDF وتحريرها وتحويلها في تطبيقات .NET الخاصة بهم. تتمثل إحدى الميزات التي توفرها هذه المكتبة في القدرة على اكتشاف تحذيرات استبدال الخط عند فتح مستند PDF. سيرشدك هذا البرنامج التعليمي خلال خطوات استخدام ملف`GetWarningsForFontSubstitution` ميزة Aspose.PDF for .NET لاكتشاف تحذيرات استبدال الخط عند فتح مستند PDF.

## الخطوة 1: قم بتثبيت Aspose.PDF for .NET

 لاستخدام Aspose.PDF for .NET في تطبيقات .NET ، يجب عليك أولاً تثبيت المكتبة. يمكنك تنزيل أحدث إصدار من المكتبة من ملف[Aspose.PDF لصفحة تنزيل .NET](https://relases.aspose.com/pdf/net).

بمجرد تنزيل المكتبة ، قم باستخراج محتويات ملف ZIP إلى مجلد على جهاز الكمبيوتر الخاص بك. ستحتاج بعد ذلك إلى إضافة مرجع إلى Aspose.PDF لـ .NET DLL في مشروع .NET الخاص بك.

## الخطوة 2: قم بتحميل مستند PDF

 بمجرد تثبيت Aspose.PDF for .NET وإضافة مرجع إلى DLL في مشروع .NET الخاص بك ، يمكنك البدء في استخدام`GetWarningsForFontSubstitution` ميزة لاكتشاف تحذيرات استبدال الخط عند فتح مستند PDF.

تتمثل الخطوة الأولى في استخدام هذه الميزة في تحميل مستند PDF الذي تريد اكتشاف تحذيرات استبدال الخط فيه. للقيام بذلك ، يمكنك استخدام الكود التالي:

```csharp
// المسار إلى وثيقة PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//افتح مستند PDF
Document doc = new Document(dataDir + "input.pdf");
```

 في الكود أعلاه ، استبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يوجد مستند PDF الخاص بك. سيقوم هذا الرمز بتحميل مستند PDF إلى ملف`Document` الذي يمكنك استخدامه بعد ذلك لاكتشاف تحذيرات استبدال الخط.

## الخطوة 3: الكشف عن تحذيرات استبدال الخط

لاكتشاف تحذيرات استبدال الخط عند فتح مستند PDF ، يمكنك استخدام التعليمات البرمجية التالية:

```csharp
doc.FontSubstitution += new Document.FontSubstitutionHandler(OnFontSubstitution);
```

 في الكود أعلاه ،`OnFontSubstitution` هي طريقة سيتم استدعاؤها كلما تم اكتشاف تحذير استبدال الخط. يمكنك تخصيص هذه الطريقة للتعامل مع تحذير استبدال الخط بأي طريقة تريدها.

 هنا مثال على تنفيذ`OnFontSubstitution` طريقة:

```csharp
private void OnFontSubstitution(object sender, Document.FontSubstitutionEventArgs e)
{
    Console.WriteLine("Font substitution: {0} => {1}", e.OriginalFontName, e.SubstitutedFontName);
}
```

 في الكود أعلاه ، فإن ملف`OnFontSubstitution` تقوم الطريقة ببساطة بإخراج اسم الخط الأصلي واسم الخط البديل إلى وحدة التحكم كلما تم اكتشاف تحذير استبدال الخط. يمكنك تخصيص هذه الطريقة للتعامل مع تحذير استبدال الخط بأي طريقة تريدها.

### مثال على كود المصدر للحصول على تحذيرات لاستبدال الخط باستخدام Aspose.NET لـ PDF

 فيما يلي رمز المصدر الكامل لاكتشاف تحذيرات استبدال الخط عند فتح مستند PDF باستخدام ملف`GetWarningsForFontSubstitution` ميزة Aspose.PDF لـ .NET:

```csharp
// المسار إلى وثيقة PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//افتح مستند PDF
Document doc = new Document(dataDir + "input.pdf");

// كشف تحذيرات استبدال الخط
doc.FontSubstitution += new Document.FontSubstitutionHandler(OnFontSubstitution);

// التعامل مع تحذير استبدال الخط
private void OnFontSubstitution(object sender, Document.FontSubstitutionEventArgs e)
{
    Console.WriteLine("Font substitution: {0} => {1}", e.OriginalFontName, e.SubstitutedFontName);
}
```