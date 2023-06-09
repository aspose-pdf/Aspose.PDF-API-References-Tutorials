---
title: أضف حد النص
linktitle: أضف حد النص
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة حد نصي إلى مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 70
url: /ar/net/programming-with-text/add-text-border/
---

سيرشدك هذا البرنامج التعليمي خلال عملية إضافة حد النص باستخدام Aspose.PDF for .NET. يوضح كود المصدر C # المقدم الخطوات الضرورية.

## متطلبات
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C # آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: قم بإعداد المشروع
1. قم بإنشاء مشروع C # جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية حيث تريد إضافة حد النص ، أضف ما يلي باستخدام التوجيه في أعلى الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود ، حدد موقع السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: إنشاء كائن مستند جديد
 تجسيد ملف`Document` عن طريق إضافة السطر التالي من التعليمات البرمجية:

```csharp
Document pdfDocument = new Document();
```

## الخطوة 5: أضف صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام ملف`Add` طريقة`Pages` مجموعة. في الكود المقدم ، يتم تخصيص الصفحة الجديدة للمتغير`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## الخطوة 6: قم بإنشاء جزء نصي
 إنشاء`TextFragment` الكائن وتقديم النص المطلوب. اضبط موضع جزء النص باستخدام امتداد`Position` ملكية. في الكود المقدم ، يتم تعيين النص على "النص الرئيسي" وموضعه عند (100 ، 600) على الصفحة.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## الخطوة 7: تعيين خصائص النص
تخصيص خصائص النص مثل حجم الخط ونوع الخط ولون الخلفية ولون المقدمة وما إلى ذلك في التعليمات البرمجية المتوفرة ، يتم تعيين خصائص مثل حجم الخط والخط ولون الخلفية ولون المقدمة ولون التمسيد لجزء النص.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## الخطوة 8: تفعيل حدود النص
 لتمكين حد النص ، اضبط ملف`DrawTextRectangleBorder` خاصية جزء النص`TextState` ل`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## الخطوة 9: أضف جزء النص إلى الصفحة
 استخدم ال`TextBuilder` فئة لإضافة`TextFragment` تعترض على الصفحة.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## الخطوة 10: احفظ مستند PDF
 احفظ مستند PDF باستخدام ملف`Save` طريقة`Document` هدف. حدد مسار ملف الإخراج الذي قمت بتعيينه في الخطوة 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لـ Add Text Border باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء كائن مستند جديد
Document pdfDocument = new Document();
// احصل على صفحة معينة
Page pdfPage = (Page)pdfDocument.Pages.Add();
// إنشاء جزء من النص
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// تعيين خصائص النص
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// قم بتعيين خاصية StrokingColor لرسم الحدود (التمسيد) حول مستطيل النص
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// قم بتعيين قيمة الخاصية DrawTextRectangleBorder إلى true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// احفظ المستند
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## خاتمة
لقد نجحت في إضافة حد نصي إلى مستند PDF الخاص بك باستخدام Aspose.PDF for .NET. يمكن الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.