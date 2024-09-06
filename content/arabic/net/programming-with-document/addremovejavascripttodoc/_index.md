---
title: إضافة إزالة Javascript إلى مستند PDF
linktitle: إضافة إزالة Javascript إلى المستند
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إضافة وإزالة JavaScript من مستند PDF باستخدام Aspose.PDF for .NET. دليل خطوة بخطوة مع دروس تعليمية حول البرمجة النصية على مستوى المستند.
type: docs
weight: 30
url: /ar/net/programming-with-document/addremovejavascripttodoc/
---
## مقدمة

في هذا الدليل، سنشرح كيفية استخدام Aspose.PDF لـ .NET لإدراج JavaScript في ملف PDF وكيفية إزالته عند الضرورة. بحلول نهاية هذا البرنامج التعليمي، ستكون لديك فكرة واضحة عن كيفية التعامل مع JavaScript في ملفات PDF دون عناء.

## المتطلبات الأساسية

قبل أن نتعمق في الكود، هناك بعض الأشياء التي ستحتاج إلى إعدادها:

1.  Aspose.PDF for .NET: ستحتاج إلى تثبيت مكتبة Aspose.PDF for .NET في مشروعك. إذا لم تكن لديك المكتبة بعد، فاحصل عليها من[صفحة تنزيل Aspose.PDF لـ .NET](https://releases.aspose.com/pdf/net/).
2. IDE أو محرر النصوص: يمكنك استخدام أي IDE متوافق مع .NET مثل Visual Studio.
3. المعرفة الأساسية بلغة C#: يفترض هذا البرنامج التعليمي أنك مرتاح في استخدام لغة C# ومتمرس في التعامل مع ملفات PDF.
4. الترخيص: تأكد من الحصول على ترخيص ساري المفعول لتجنب القيود. يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).

## استيراد الحزم

للبدء في استخدام Aspose.PDF لـ .NET، ستحتاج إلى استيراد المساحات الأساسية اللازمة إلى مشروعك. إليك كيفية القيام بذلك:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.Collections;
```

 هذه المساحتان الاسميتان ضروريتان.`Aspose.Pdf` يسمح لك بالعمل مع مستندات PDF، بينما`System.Collections` سيتم استخدامه للتعامل مع مفاتيح JavaScript.

دعونا نقوم بتقسيم العملية برمتها لإضافة وإزالة JavaScript من ملف PDF إلى خطوات سهلة المتابعة.

## الخطوة 1: تهيئة مستند PDF جديد

أول شيء عليك القيام به هو إنشاء مستند PDF جديد. سيعمل هذا المستند كلوحة فارغة لإضافة JavaScript.

```csharp
Document doc = new Document();
doc.Pages.Add();
```

 هنا، نقوم بتهيئة ملف جديد`Document` كائن وإضافة صفحة فارغة إليه. فكر في هذا باعتباره أساس ملف PDF الخاص بك.

## الخطوة 2: إضافة JavaScript إلى ملف PDF

الآن بعد أن أصبح لدينا مستند، حان الوقت لإضافة بعض JavaScript إليه. يمكن استخدام JavaScript في ملفات PDF لإضافة سلوكيات مخصصة، مثل التنبيهات أو التحقق من صحة النماذج.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
```

في مقتطف التعليمات البرمجية هذا، نضيف دالتين JavaScript (`func1` و`func2` ) إلى ملف PDF. يمكن لهذه الوظائف تنفيذ مهام مختلفة، اعتمادًا على احتياجاتك. هنا، نقوم فقط باستدعاء وظيفة مؤقتة تسمى`hello()`.

## الخطوة 3: حفظ ملف PDF باستخدام JavaScript

بمجرد إضافة JavaScript المطلوب، حان الوقت لحفظ ملف PDF.

```csharp
doc.Save(dataDir + "AddJavascript.pdf");
```

 سيؤدي هذا إلى حفظ المستند باستخدام JavaScript تحت الاسم`AddJavascript.pdf` في الدليل المحدد (`dataDir`).

## الخطوة 4: تحميل وعرض JavaScript في ملف PDF الموجود

لنفترض أنك بحاجة إلى التحقق من وظائف JavaScript أو تعديلها داخل ملف PDF موجود. الخطوة الأولى هي تحميل ملف PDF والوصول إلى مفاتيح JavaScript.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
```

 نحن نقوم بتحميل الموجود`AddJavascript.pdf` وتخزين مفاتيح JavaScript في قائمة.`Keys` تقوم الخاصية بإرجاع أسماء جميع وظائف JavaScript المرفقة بالمستند.

## الخطوة 5: عرض وظائف JavaScript

بعد ذلك، يمكننا تكرار وظائف JavaScript لمعرفة ما هو متاح في المستند.

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
```

سيؤدي هذا إلى طباعة اسم كل وظيفة JavaScript والرمز المقابل لها على وحدة التحكم. وهو أمر مفيد إذا كنت تريد التحقق من الوظائف الموجودة حاليًا في المستند.

## الخطوة 6: إزالة JavaScript من ملف PDF

 الآن، لنفترض أنك تريد إزالة وظيفة JavaScript معينة، مثل`func1`. إليك كيفية القيام بذلك:

```csharp
doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
```

 ال`Remove` تأخذ الطريقة اسم دالة JavaScript كحجة وتحذفها من المستند.

## الخطوة 7: التحقق من إزالة JavaScript

 بعد إزالة JavaScript، يمكنك إعادة طباعة الوظائف المتبقية للتأكيد على ذلك`func1` تم الحذف بنجاح.

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
Console.WriteLine("Javascript added/removed successfully.");
```

يضمن هذا الجزء الأخير من الكود أن كل شيء في مكانه وأن وظائف JavaScript يتم تحديثها بشكل صحيح.

## خاتمة

تهانينا! لقد تعلمت للتو كيفية إضافة JavaScript وإزالته من مستند PDF باستخدام Aspose.PDF for .NET. يمكن الاستفادة من هذه الميزة القوية في مجموعة متنوعة من المهام، من إضافة رسائل ديناميكية إلى إجراء حسابات أو عمليات تحقق مخصصة. من خلال معالجة JavaScript داخل ملف PDF، يمكنك تحسين تجربة المستخدم بشكل كبير.

## الأسئلة الشائعة

### هل يمكنني إضافة وظائف JavaScript متعددة إلى ملف PDF واحد؟
 بالتأكيد! يمكنك إضافة عدد لا حصر له من وظائف JavaScript باستخدام`doc.JavaScript` مجموعة.

### ماذا يحدث إذا حاولت إزالة وظيفة JavaScript غير موجودة؟
 إذا لم تكن الوظيفة موجودة،`Remove` لن تؤدي الطريقة إلى حدوث خطأ، ولكنها لن تزيل أي شيء أيضًا.

### هل من الممكن تشغيل JavaScript بمجرد فتح ملف PDF؟
نعم! يمكنك تكوين JavaScript لتشغيله عند تشغيل عوامل تشغيل معينة، مثل فتح المستند أو النقر فوق زر.

### هل يمكنني تعديل JavaScript بعد إضافته إلى ملف PDF؟
نعم، يمكنك تحميل ملف PDF موجود، والوصول إلى JavaScript الخاص به، وتعديل الكود، وحفظ المستند مرة أخرى.

### هل يؤثر إزالة JavaScript على بقية محتوى PDF؟
لا، إن إزالة JavaScript تؤثر فقط على النص البرمجي، أما محتوى ملف PDF فيظل كما هو.