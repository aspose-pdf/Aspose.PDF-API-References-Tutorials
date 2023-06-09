---
title: عناصر الوصول للأطفال
linktitle: عناصر الوصول للأطفال
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة للوصول إلى العناصر الفرعية من مستند PDF وتحريرها باستخدام Aspose.PDF for .NET. إضفاء الطابع الشخصي على محتوى PDF الخاص بك.
type: docs
weight: 10
url: /ar/net/programming-with-tagged-pdf/access-children-elements/
---
في هذا البرنامج التعليمي ، سنزودك بدليل تفصيلي حول الوصول إلى العناصر الفرعية لمستند PDF باستخدام Aspose.PDF for .NET. Aspose.PDF هي مكتبة قوية تسمح لك بإنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. باستخدام ميزات بنية المحتوى المحددة في Aspose.PDF ، يمكنك الوصول إلى خصائص العناصر المهيكلة وتعديلها في مستند PDF.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من توفر المتطلبات الأساسية التالية:

1. Visual Studio مثبت مع .NET framework.
2. مكتبة Aspose.PDF لـ .NET.

## الخطوة 1: إعداد المشروع

للبدء ، أنشئ مشروعًا جديدًا في Visual Studio وأضف مرجعًا إلى Aspose.PDF لمكتبة .NET. يمكنك تنزيل المكتبة من موقع Aspose الرسمي وتثبيتها على جهازك.

## الخطوة 2: استيراد مساحات الأسماء الضرورية

في ملف كود C # الخاص بك ، قم باستيراد مساحات الأسماء المطلوبة للوصول إلى الفئات والطرق التي يوفرها Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## الخطوة 3: تحميل مستند PDF والوصول إلى العناصر الفرعية

استخدم الكود التالي لتحميل مستند PDF والوصول إلى العناصر الفرعية:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document(dataDir + "StructureElementsTree.pdf");
ITaggedContent taggedContent = document.TaggedContent;
ElementList elementList = taggedContent.StructTreeRootElement.ChildElements;

foreach(Element element in elementList)
{
if (element is StructureElement)
{
StructureElement structureElement = element as StructureElement;
// الوصول إلى خصائص العنصر
string title = structureElement.Title;
string language = structureElement.Language;
string actualText = structureElement.ActualText;
string expansionText = structureElement.ExpansionText;
string alternativeText = structureElement.AlternativeText;
}
}
```

يتيح لك هذا الرمز الوصول إلى العناصر الفرعية لجذر بنية مستند PDF والحصول على خصائص كل عنصر.

## الخطوة 4: الوصول إلى Root Element Children وتغيير الخصائص

استخدم الكود التالي للوصول إلى العناصر الأبناء للعنصر الجذر وتعديل الخصائص:

```csharp
elementList = taggedContent.RootElement.ChildElements[1].ChildElements;

foreach(Element element in elementList)
{
if (element is StructureElement)
{
StructureElement structureElement = element as StructureElement;
// تعديل خصائص العنصر
structureElement.Title = "title";
structureElement.Language = "fr-FR";
structureElement.ActualText = "actual text";
structureElement.ExpansionText = "exp";
structureElement.AlternativeText = "alt";
}
}
```

يسمح لك هذا الرمز بالوصول إلى العناصر الأبناء للعنصر الأول من العنصر الجذر وتعديل خصائص كل عنصر.


### عينة من التعليمات البرمجية المصدر لـ Access Children Elements باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح مستند PDF
Document document = new Document(dataDir + "StructureElementsTree.pdf");
// الحصول على محتوى للعمل مع TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// الوصول إلى عنصر (عناصر) الجذر
ElementList elementList = taggedContent.StructTreeRootElement.ChildElements;
foreach (Element element in elementList)
{
	if (element is StructureElement)
	{
		StructureElement structureElement = element as StructureElement;
		// احصل على الخصائص
		string title = structureElement.Title;
		string language = structureElement.Language;
		string actualText = structureElement.ActualText;
		string expansionText = structureElement.ExpansionText;
		string alternativeText = structureElement.AlternativeText;
	}
}
// الوصول إلى عناصر الأطفال من العنصر الأول في عنصر الجذر
elementList = taggedContent.RootElement.ChildElements[1].ChildElements;
foreach (Element element in elementList)
{
	if (element is StructureElement)
	{
		StructureElement structureElement = element as StructureElement;
		// تعيين الخصائص
		structureElement.Title = "title";
		structureElement.Language = "fr-FR";
		structureElement.ActualText = "actual text";
		structureElement.ExpansionText = "exp";
		structureElement.AlternativeText = "alt";
	}
}
// حفظ وثيقة PDF الموسومة
document.Save(dataDir + "AccessChildrenElements.pdf");
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية الوصول إلى العناصر الفرعية لمستند PDF وكيفية تعديل خصائص العنصر باستخدام Aspose.PDF لـ .NET. يتيح لك ذلك تخصيص العناصر المهيكلة ومعالجتها في مستند PDF وفقًا لاحتياجاتك.