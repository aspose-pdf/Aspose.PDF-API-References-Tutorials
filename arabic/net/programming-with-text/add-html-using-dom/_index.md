---
title: أضف HTML باستخدام DOM
linktitle: أضف HTML باستخدام DOM
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة محتوى HTML باستخدام DOM في Aspose.PDF for .NET.
type: docs
weight: 40
url: /ar/net/programming-with-text/add-html-using-dom/
---

سيرشدك هذا البرنامج التعليمي خلال عملية إضافة محتوى HTML باستخدام DOM (نموذج كائن المستند) في Aspose.PDF for .NET. يوضح كود المصدر C # المقدم الخطوات الضرورية.

## متطلبات
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C # آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: قم بإعداد المشروع
1. قم بإنشاء مشروع C # جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية حيث تريد إضافة محتوى HTML ، أضف ما يلي باستخدام التوجيهات في أعلى الملف:

```csharp
using Aspose.Pdf;
```

## الخطوة 3: قم بتعيين دليل المستند ومسار ملف الإخراج
 في الكود ، حدد موقع السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: إنشاء كائن مستند جديد
 تجسيد ملف`Document` عن طريق إضافة السطر التالي من التعليمات البرمجية:

```csharp
Document doc = new Document();
```

## الخطوة 5: أضف صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام ملف`Add` طريقة`Pages` مجموعة. في الكود المقدم ، يتم تخصيص الصفحة الجديدة للمتغير`page`.

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 6: إنشاء HtmlFragment مع محتوى HTML
تجسيد`HtmlFragment` كائن وتوفير محتوى HTML المطلوب. في الكود المقدم ، يتم تعيين محتوى HTML للمتغير`titel`. يمكنك تعديل محتوى HTML حسب الحاجة.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## الخطوة 7: ضبط معلومات الهامش
اضبط الهامش السفلي والعلوي لجزء HTML إذا لزم الأمر. في الكود المقدم ، تم تعيين الهامش السفلي على 10 والهامش العلوي مضبوطًا على 200.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## الخطوة 8: أضف جزء HtmlFragment إلى الصفحة
 أضف ال`HtmlFragment` تعترض على مجموعة فقرات الصفحة.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## الخطوة 9: احفظ مستند PDF
 احفظ مستند PDF باستخدام ملف`Save` طريقة`Document` هدف. حدد مسار ملف الإخراج الذي قمت بتعيينه في الخطوة 3.

```csharp
doc.Save(dataDir);
```

## الخطوة 10: اعرض رسالة النجاح
اعرض رسالة نجاح مع المسار حيث تم حفظ ملف PDF.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لإضافة HTMLUsing DOM باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء كائن المستند
Document doc = new Document();
// أضف صفحة إلى مجموعة صفحات من ملف PDF
Page page = doc.Pages.Add();
// إنشاء HtmlFragment مع محتويات HTML
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// تعيين معلومات الهامش السفلي
titel.Margin.Bottom = 10;
// تعيين معلومات الهامش العلوي
titel.Margin.Top = 200;
// أضف جزء HTML إلى مجموعة فقرات من الصفحة
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// احفظ ملف PDF
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## خاتمة
لقد نجحت في إضافة محتوى HTML باستخدام DOM في Aspose.PDF لـ .NET. يمكن الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.