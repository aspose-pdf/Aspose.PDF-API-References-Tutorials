---
title: استخدم البرنامج النصي لاتكس
linktitle: استخدم البرنامج النصي لاتكس
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام برنامج Latex النصي لإضافة تعبيرات أو صيغ رياضية في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 550
url: /ar/net/programming-with-text/use-latex-script/
---

يشرح هذا البرنامج التعليمي كيفية استخدام برنامج Latex النصي لإضافة تعبيرات أو صيغ رياضية في مستند PDF باستخدام Aspose.PDF لـ .NET. يوضح كود المصدر C # المقدم خطوات إنشاء مستند وإضافة جدول به خلية تحتوي على برنامج LaTeX النصي وحفظ المستند.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت Aspose.PDF لمكتبة .NET. يمكنك الحصول عليه من موقع Aspose أو استخدام NuGet لتثبيته في مشروعك.

## الخطوة 1: قم بإعداد المشروع

قم بإنشاء مشروع C # جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE) وأضف مرجعًا إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء الضرورية

أضف التعليمات التالية باستخدام التوجيهات في بداية ملف C # لاستيراد مساحات الأسماء المطلوبة:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Tables;
using Aspose.Pdf.Text;
```

## الخطوة 3: إنشاء المستند وتكوينه

 إنشاء ملف`Document` كائن وإضافة صفحة إليه:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## الخطوة 4: إنشاء الجدول وتكوينه

قم بإنشاء جدول وإضافة صف إليه:

```csharp
Table table = new Table();
Row row = table.Rows.Add();
```

## الخطوة 5: أضف خلية باستخدام برنامج LaTeX النصي

 قم بإنشاء خلية وإضافة ملف`LatexFragment` تحتوي على نص لاتكس:

```csharp
string latexText1 = "$123456789+\\sqrt{1}+\\int_a^b f(x)dx$";
Cell cell = row.Cells.Add();
LatexFragment ltext1 = new LatexFragment(latexText1, true);
cell.Paragraphs.Add(ltext1);
```

 نلاحظ أن`true` المعلمة في`LatexFragment` منشئ يزيل المسافات البادئة للفقرة اللاتكس.

## الخطوة 6: أضف الجدول إلى الصفحة

أضف الجدول إلى الصفحة:

```csharp
page.Paragraphs.Add(table);
```

## الخطوة 7: احفظ المستند

احفظ المستند في ملف PDF:

```csharp
doc.Save(dataDir + "LatextScriptInPdf_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لـ Use Latex Script باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// قم بإنشاء كائن مستند جديد
Document doc = new Document();
//أضف صفحة في مجموعة الصفحات
Page page = doc.Pages.Add();
// قم بإنشاء جدول
Table table = new Table();
// أضف صفًا إلى الجدول
Row row = table.Rows.Add();
// أضف خلية باستخدام برنامج Latex Script لإضافة تعبيرات / صيغ رياضية
string latexText1 = "$123456789+\\sqrt{1}+\\int_a^b f(x)dx$";
Cell cell = row.Cells.Add();
cell.Margin = new MarginInfo { Left = 20, Right = 20, Top = 20, Bottom = 20 };
// توفر المعلمة المنطقية لمنشئ LatexFragment الثانية إزالة المسافات البادئة للفقرة من LaTeX.
LatexFragment ltext1 = new LatexFragment(latexText1, true);
cell.Paragraphs.Add(ltext1);
// أضف الجدول داخل الصفحة
page.Paragraphs.Add(table);
// احفظ المستند
doc.Save(dataDir + "LatextScriptInPdf_out.pdf");
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية استخدام برنامج Latex النصي لإضافة تعبيرات أو صيغ رياضية في مستند PDF باستخدام Aspose.PDF لـ .NET. قدم هذا البرنامج التعليمي إرشادات خطوة بخطوة حول إنشاء مستند وإضافة جدول به خلية تحتوي على برنامج LaTeX النصي وحفظ المستند. يمكنك الآن دمج هذا الرمز في مشاريع C # الخاصة بك لإنشاء ملفات PDF ذات محتوى رياضي.