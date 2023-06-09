---
title: التلاعب بالجدول
linktitle: التلاعب بالجدول
second_title: Aspose.PDF لمرجع .NET API
description: تعامل بسهولة مع الجداول في مستندات PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 130
url: /ar/net/programming-with-tables/manipulate-table/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لمعالجة الجداول في مستند PDF باستخدام Aspose.PDF for .NET. تعد الجداول عنصرًا شائعًا في مستندات PDF ، ويمكن أن تكون القدرة على تعديل محتواها برمجيًا مفيدة للغاية في العديد من السيناريوهات. سنستخدم الكود المصدري C # المقدم لشرح العملية.

## متطلبات

قبل أن نبدأ ، تأكد من توفر لديك ما يلي:

- Visual Studio أو أي بيئة تطوير C # أخرى مثبتة.
- تمت إضافة Aspose.PDF لمكتبة .NET كمرجع لمشروعك.

الآن ، دعنا نتعمق في الخطوات المطلوبة لمعالجة الجداول في مستند PDF باستخدام Aspose.PDF لـ .NET.

## الخطوة 1: تحميل مستند PDF

تتمثل الخطوة الأولى في تحميل مستند PDF الحالي في تطبيق C # الخاص بك. تحتاج إلى توفير المسار إلى الدليل حيث يوجد المستند الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "input.pdf");
```

استبدل "دليل المستند" بالمسار الفعلي للدليل حيث يوجد مستند PDF الخاص بك.

## الخطوة 2: البحث عن الجداول في المستند

لمعالجة الجداول ، نحتاج إلى العثور عليها داخل مستند PDF. يوفر Aspose.PDF for .NET فئة TableAbsorber التي تسمح لنا باستخراج الجداول من المستند. سنقوم بإنشاء مثيل لفئة TableAbsorber وزيارة الصفحة المطلوبة من المستند.

```csharp
TableAbsorber absorber = new TableAbsorber();
absorb.Visit(pdfDocument.Pages[1]);
```

في هذا المثال ، نزور الصفحة الأولى من المستند. يمكنك تغيير رقم الصفحة حسب متطلباتك.

## الخطوة 3: الوصول إلى خلايا الجدول وأجزاء النص

بمجرد أن نحصل على الجداول ، يمكننا الوصول إلى خلاياها وأجزاء النص للتلاعب بها. في الكود المصدري المقدم ، نقوم بالوصول إلى الجدول الأول ، والخلية الأولى من صفها الأول ، والجزء النصي الثاني داخل تلك الخلية.

```csharp
TextFragment fragment = absorb.TableList[0].RowList[0].CellList[0].TextFragments[1];
```

يمكنك تعديل التعليمات البرمجية لاستهداف جداول أو خلايا أو أجزاء نصية مختلفة بناءً على احتياجاتك الخاصة.

## الخطوة 4: معالجة نص الجدول

مع الوصول إلى جزء النص ، يمكننا الآن تعديل محتواه. في المثال المعطى ، نقوم بتغيير النص إلى "hi world".

```csharp
fragment.Text = "hi world";
```

لا تتردد في استبدال "hi world" بالنص الذي تريده.

## الخطوة 5: حفظ المستند المعدل

بمجرد إجراء التعديلات المطلوبة ، نحتاج إلى حفظ مستند PDF المعدل.

```csharp
dataDir = dataDir + "ManipulateTable_out.pdf";
pdfDocument.Save(dataDir);
```

تأكد من توفير المسار واسم الملف للمستند المعدل.


### مثال على التعليمات البرمجية المصدر لـ Manipulate Table باستخدام Aspose.PDF لـ .NET

```csharp
try
{
	
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// قم بتحميل ملف PDF موجود
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// قم بإنشاء كائن TableAbsorber للعثور على الجداول
	TableAbsorber absorber = new TableAbsorber();

	// زيارة الصفحة الأولى مع الماص
	absorber.Visit(pdfDocument.Pages[1]);

	// احصل على حق الوصول إلى الجدول الأول على الصفحة ، والخلية الأولى والأجزاء النصية فيه
	TextFragment fragment = absorber.TableList[0].RowList[0].CellList[0].TextFragments[1];

	// تغيير نص الجزء الأول من النص في الخلية
	fragment.Text = "hi world";
	dataDir = dataDir + "ManipulateTable_out.pdf";
	pdfDocument.Save(dataDir);
	
	Console.WriteLine("\nTable manipulated successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية التعامل مع الجداول في مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع الدليل المفصل خطوة بخطوة ، يمكنك بسهولة تحميل مستند PDF والعثور على الجداول والوصول إلى الخلايا وأجزاء النص وتعديل محتوى الجدول وحفظ المستند المعدل. يوفر هذا الأسلوب المرونة والكفاءة عند التعامل مع معالجة الجدول في مستندات PDF.