---
title: الحفاظ على الحقوق
linktitle: الحفاظ على الحقوق
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: احتفظ بحقوق النموذج في مستندات PDF الخاصة بك باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 210
url: /ar/net/programming-with-forms/preserve-rights/
---
في هذا البرنامج التعليمي، سنوضح لك كيفية الحفاظ على حقوق النموذج في مستند PDF باستخدام Aspose.PDF لـ .NET. وسنشرح لك التعليمات البرمجية المصدرية بلغة C# خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة 1: التحضير

تأكد من أنك قمت باستيراد المكتبات الضرورية وقمت بتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: افتح المستند

 افتح مستند PDF المصدر باستخدام`FileStream` مع إذن القراءة والكتابة:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## الخطوة 3: تحرير حقول النموذج

قم بفحص جميع حقول النموذج في المستند وإجراء التغييرات اللازمة. في هذا المثال، نقوم بتغيير قيمة حقل نموذج يحتوي على "A1" في اسمه:

```csharp
foreach(Field formField in pdfDocument.Form)
{
if (formField.FullName.Contains("A1"))
{
TextBoxField textBoxField = formField as TextBoxField;
textBoxField.Value = "Testing";
}
}
```

## الخطوة 4: احفظ المستند المحدث

حفظ مستند PDF المعدل:

```csharp
pdfDocument.Save();
```

##  الخطوة 5: إغلاق`FileStream`

 لا تنسى إغلاق`FileStream` الكائن عندما تنتهي:

```csharp
fs. Close();
```

### عينة من كود المصدر لحفظ الحقوق باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// اقرأ نموذج PDF المصدر باستخدام FileAccess للقراءة والكتابة.
// نحن بحاجة إلى إذن ReadWrite لأنه بعد التعديل،
// نحن بحاجة إلى حفظ المحتويات المحدثة في نفس المستند/الملف.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// إنشاء مثيل مستند
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// الحصول على القيم من جميع الحقول
foreach (Field formField in pdfDocument.Form)
{
	// إذا كان الاسم الكامل للحقل يحتوي على A1، قم بإجراء العملية
	if (formField.FullName.Contains("A1"))
	{
		// تحويل حقل النموذج إلى مربع نص
		TextBoxField textBoxField = formField as TextBoxField;
		// تعديل قيمة الحقل
		textBoxField.Value = "Testing";
	}
}
// احفظ المستند المحدث في FileStream المحفوظ
pdfDocument.Save();
// إغلاق كائن تدفق الملف
fs.Close();
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية الحفاظ على حقوق نموذج في مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات، يمكنك الوصول بسهولة إلى حقول النموذج وإجراء تغييرات معينة مع الحفاظ على أذونات الوصول والكتابة.


### الأسئلة الشائعة

#### س: هل يمكنني الحفاظ على حقوق حقول نموذج معينة دون التأثير على الحقوق الأخرى في مستند PDF؟

 ج: نعم، عن طريق استخدام`FullName` من خلال إدارة خصائص حقول النماذج، يمكنك استهداف حقول نماذج محددة للحفاظ عليها مع ترك الحقول الأخرى دون التأثير عليها.

#### س: هل يمكنني الحفاظ على حقوق النموذج في مستند PDF محمي بكلمة مرور؟

ج: نعم، يسمح لك Aspose.PDF for .NET بالحفاظ على حقوق النموذج حتى في مستندات PDF المحمية بكلمة مرور، طالما قمت بتوفير كلمة المرور الصحيحة للوصول إلى الملف وتعديله.

#### س: ماذا يحدث إذا حاولت تعديل حقول النموذج دون الحصول على حقوق الوصول المناسبة؟

ج: إذا حاولت تعديل حقول النموذج دون الحصول على حقوق الوصول المناسبة، فلن يتم حفظ التغييرات في مستند PDF، وقد تتلقى استثناءً أو رسالة خطأ.

#### س: هل Aspose.PDF for .NET متوافق مع كافة إصدارات .NET Framework؟

ج: نعم، يعد Aspose.PDF لـ .NET متوافقًا مع جميع إصدارات .NET Framework، بما في ذلك .NET Core و.NET Standard.

#### س: هل يمكنني الحفاظ على حقوق النموذج في مستند PDF برمجيًا بلغات برمجة أخرى إلى جانب C#؟

ج: نعم، يدعم Aspose.PDF for .NET لغات البرمجة المختلفة، مثل VB.NET وASP.NET، بالإضافة إلى C#.