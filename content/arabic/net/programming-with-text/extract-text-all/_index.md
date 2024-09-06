---
title: استخراج النص بالكامل من ملف PDF
linktitle: استخراج النص من ملف PDF بالكامل
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية استخراج كافة النصوص في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 180
url: /ar/net/programming-with-text/extract-text-all/
---
سيرشدك هذا البرنامج التعليمي خلال عملية استخراج كل النص في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود المصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مُجمِّع C# آخر مُثبت على جهازك.
- مكتبة Aspose.PDF لـ .NET. يمكنك تنزيلها من موقع Aspose الرسمي أو استخدام مدير حزم مثل NuGet لتثبيتها.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات المطلوبة
في ملف الكود الذي تريد استخراج النص منه، أضف ما يلي باستخدام التوجيهات في أعلى الملف:

```csharp
using Aspose.Pdf;
using System.IO;
```

## الخطوة 3: تعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل الذي يتم تخزين مستنداتك فيه.

## الخطوة 4: افتح مستند PDF
 افتح مستند PDF موجودًا باستخدام`Document` المنشئ وتمرير المسار إلى ملف PDF المدخل.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## الخطوة 5: استخراج النص بأكمله
 إنشاء`TextAbsorber`استخدم الكائن لاستخراج النص من المستند. ثم اقبل الممتص لجميع الصفحات.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## الخطوة 6: الحصول على النص المستخرج
 الوصول إلى النص المستخرج من`TextAbsorber` هدف.

```csharp
string extractedText = textAbsorber.Text;
```

## الخطوة 7: احفظ النص المستخرج
 إنشاء`TextWriter` وافتح الملف الذي تريد حفظ النص المستخرج فيه. اكتب النص المستخرج في الملف وأغلق التدفق.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### عينة من كود المصدر لاستخراج النص بالكامل باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// إنشاء كائن TextAbsorber لاستخراج النص
TextAbsorber textAbsorber = new TextAbsorber();
// قبول الممتص لجميع الصفحات
pdfDocument.Pages.Accept(textAbsorber);
// احصل على النص المستخرج
string extractedText = textAbsorber.Text;
// إنشاء كاتب وفتح الملف
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// اكتب سطرًا من النص إلى الملف
tw.WriteLine(extractedText);
// اغلاق الدفق
tw.Close();
```

## خاتمة
لقد نجحت في استخراج النص بالكامل من مستند PDF باستخدام Aspose.PDF لـ .NET. تم حفظ النص المستخرج في ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: يعمل هذا البرنامج التعليمي كدليل لمساعدتك على استخراج كل النص من ملف PDF باستخدام Aspose.PDF لـ .NET. يوفر كود المصدر C# المصاحب تعليمات خطوة بخطوة لتحقيق هذه المهمة.

#### س: ما هي المساحات الأسماء التي يجب أن أستوردها؟

أ: في ملف الكود الذي تنوي استخراج النص منه، قم بتضمين ما يلي باستخدام التوجيهات في بداية الملف:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### س: كيف أحدد دليل المستند؟

 أ: حدد موقع الخط`string dataDir = "YOUR DOCUMENT DIRECTORY";` في الكود واستبداله`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

#### س: كيف يمكنني فتح مستند PDF موجود؟

 أ: في الخطوة 4، ستفتح مستند PDF موجودًا باستخدام`Document` المنشئ وتوفير المسار إلى ملف PDF المدخل.

#### س: كيف يمكنني استخراج النص بأكمله من المستند؟

 أ: تتضمن الخطوة 5 إنشاء`TextAbsorber` استخدم كائنًا لاستخراج النص من مستند PDF. بعد ذلك، ستقبل الممتص لجميع الصفحات.

#### س: كيف يمكنني الوصول إلى النص المستخرج؟

 أ: ترشدك الخطوة 6 خلال الوصول إلى النص المستخرج من`TextAbsorber` هدف.

#### س: كيف أحفظ النص المستخرج في ملف؟

 أ: في الخطوة 7، ستقوم بإنشاء`TextWriter`افتح الملف الذي تريد حفظ النص المستخرج فيه، واكتب النص المستخرج في الملف، ثم أغلق التدفق.

#### س: ما هو أهم ما يمكن تعلمه من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، ستتعلم كيفية استخراج كل النص من مستند PDF باستخدام Aspose.PDF لـ .NET. يتم حفظ النص المستخرج في ملف إخراج محدد، مما يتيح لك تحليل المحتوى النصي للمستند ومعالجته.