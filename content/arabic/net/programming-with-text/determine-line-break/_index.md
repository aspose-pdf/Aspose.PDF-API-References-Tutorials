---
title: تحديد كسر السطر في ملف PDF
linktitle: تحديد كسر السطر في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تحديد فواصل الأسطر في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 130
url: /ar/net/programming-with-text/determine-line-break/
---
سيرشدك هذا البرنامج التعليمي خلال عملية تحديد فواصل الأسطر في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود المصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مُجمِّع C# آخر مُثبت على جهازك.
- مكتبة Aspose.PDF لـ .NET. يمكنك تنزيلها من موقع Aspose الرسمي أو استخدام مدير حزم مثل NuGet لتثبيتها.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات المطلوبة
في ملف الكود الذي تريد تحديد فواصل الأسطر فيه، أضف التعليمات التالية باستخدام التوجيهات في الجزء العلوي من الملف:

```csharp
using Aspose.Pdf;
using System.IO;
```

## الخطوة 3: تعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل الذي يتم تخزين مستنداتك فيه.

## الخطوة 4: إنشاء مثيل مستند جديد
 إنشاء مثيل جديد`Document` الكائن عن طريق إضافة سطر التعليمات البرمجية التالي:

```csharp
Document doc = new Document();
```

## الخطوة 5: إضافة صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages`المجموعة. في الكود المقدم، يتم تعيين الصفحة الجديدة للمتغير`page`.

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 6: إضافة أجزاء نصية مع فواصل الأسطر
قم بإنشاء حلقة لإضافة أجزاء نصية متعددة إلى الصفحة، بحيث تحتوي كل منها على فقرة مع فواصل للأسطر.

```csharp
for (int i = 0; i < 4; i++)
{
     TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
     text.TextState.FontSize = 20;
     page.Paragraphs.Add(text);
}
```

## الخطوة 7: احفظ مستند PDF واستخرج معلومات كسر السطر
 احفظ مستند PDF باستخدام`Save` طريقة`Document` الكائن. ثم، قم باستخراج معلومات كسر السطر باستخدام`GetNotifications` طريقة الصفحة المطلوبة.

```csharp
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

### عينة من كود المصدر لتحديد فاصل الأسطر باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
	text.TextState.FontSize = 20;
	page.Paragraphs.Add(text);
}
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

## خاتمة
لقد نجحت في تحديد فواصل الأسطر في مستند PDF باستخدام Aspose.PDF لـ .NET. تم استخراج معلومات فواصل الأسطر وحفظها في ملف نصي.

### الأسئلة الشائعة

#### س: ما هو التركيز الرئيسي لهذا البرنامج التعليمي؟

ج: يركز هذا البرنامج التعليمي على إرشادك خلال عملية تحديد فواصل الأسطر في ملف PDF باستخدام مكتبة Aspose.PDF for .NET. يوضح كود المصدر C# المقدم الخطوات اللازمة لتحقيق ذلك.

#### س: ما هي المساحات الأسماء التي ينبغي لي استيرادها لهذا البرنامج التعليمي؟

أ: في ملف الكود الذي تريد تحديد فواصل الأسطر فيه، قم باستيراد المساحات التالية في بداية الملف:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### س: كيف أحدد دليل المستند؟

 أ: في الكود، ابحث عن السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

#### س: كيف أقوم بإنشاء مثيل مستند جديد؟

 أ: في الخطوة 4، ستقوم بإنشاء مثيل جديد`Document` الكائن باستخدام الكود المقدم.

#### س: كيف أضيف صفحة إلى المستند؟

 أ: في الخطوة 5، ستضيف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages` مجموعة.

#### س: كيف أضيف أجزاء نصية مع فواصل الأسطر؟

أ: في الخطوة 6، ستقوم بإنشاء حلقة لإضافة أجزاء نصية متعددة إلى الصفحة، كل منها تحتوي على فقرة مع فواصل للأسطر.

#### س: كيف يمكنني حفظ مستند PDF واستخراج معلومات كسر السطر؟

 أ: في الخطوة 7، ستحفظ مستند PDF باستخدام`Save` طريقة`Document` الكائن. بعد ذلك، ستستخرج معلومات كسر السطر باستخدام`GetNotifications`طريقة الصفحة المطلوبة وحفظها في ملف نصي.

#### س: ما هو الغرض من استخراج معلومات كسر السطر؟

ج: توفر معلومات فواصل الأسطر المستخرجة تفاصيل حول فواصل الأسطر والإشعارات الموجودة في مستند PDF. ويمكن أن يكون هذا مفيدًا لتحليل وفهم كيفية هيكلة النص والفقرات داخل المستند.

#### س: ما هو الدرس الرئيسي المستفاد من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، ستتعلم كيفية تحديد فواصل الأسطر في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذه المعرفة لاستخراج معلومات فواصل الأسطر وتحليلها من ملفات PDF برمجيًا.