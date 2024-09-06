---
title: ตั้งค่าคำอธิบายปุ่มตัวเลือก
linktitle: ตั้งค่าคำอธิบายปุ่มตัวเลือก
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อตั้งค่าคำอธิบายสำหรับปุ่มตัวเลือกในแบบฟอร์ม PDF
type: docs
weight: 280
url: /th/net/programming-with-forms/set-radio-button-caption/
---
ในคู่มือนี้ เราจะอธิบายทีละขั้นตอนถึงวิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อกำหนดคำบรรยายของปุ่มตัวเลือกในแบบฟอร์ม PDF เราจะแสดงวิธีการเข้าถึงฟิลด์ปุ่มตัวเลือก สร้างตัวเลือกปุ่มตัวเลือกใหม่ และปรับแต่งคำบรรยายของปุ่ม

## ขั้นตอนที่ 1: การกำหนดค่าไดเรกทอรีเอกสาร

 ขั้นตอนแรกคือการกำหนดค่าไดเรกทอรีเอกสารที่ฟอร์ม PDF ที่คุณต้องการทำงานอยู่ คุณสามารถใช้`dataDir` ตัวแปรสำหรับระบุเส้นทางไดเร็กทอรี

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 อย่าลืมเปลี่ยน`"YOUR DOCUMENTS DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 2: โหลดแบบฟอร์ม PDF ต้นฉบับ

 ในขั้นตอนนี้เราจะโหลดแบบฟอร์ม PDF ต้นฉบับโดยใช้`Aspose.Pdf.Facades.Form` ชั้นเรียนของ Aspose.PDF

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

ตรวจสอบให้แน่ใจว่าไฟล์ PDF ที่มีแบบฟอร์มนั้นมีอยู่ในไดเร็กทอรีเอกสารที่ระบุ

## ขั้นตอนที่ 3: การแก้ไขคำอธิบายปุ่มตัวเลือก

เราจะวนซ้ำผ่านชื่อฟิลด์ฟอร์มและค้นหาฟิลด์ปุ่มตัวเลือก หากพบฟิลด์ที่ตรงกัน เราจะสร้างตัวเลือกปุ่มตัวเลือกใหม่พร้อมคำอธิบายแบบกำหนดเอง และเพิ่มลงในฟิลด์ที่มีอยู่

```csharp
foreach(var item in form1.FieldNames)
{
if (item.Contains("radio1"))
{
Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
fieldoption.OptionName = "Yes";
fieldoption.PartialName = "Yesname";
var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
updatedFragment.TextState.FontSize = 10;
updatedFragment.TextState.LineSpacing = 6.32f;
// สร้างวัตถุ TextParagraph
TextParagraph par = new TextParagraph();
// ตั้งค่าตำแหน่งย่อหน้า
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// ระบุโหมดการห่อคำ
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// เพิ่ม TextFragment ใหม่ลงในย่อหน้า
par.AppendLine(updatedFragment);
// เพิ่ม TextParagraph โดยใช้ TextBuilder
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

ปรับแต่งปุ่มตัวเลือกคำบรรยายและการตั้งค่าอื่น ๆ ตามต้องการ

## ขั้นตอนที่ 4: บันทึก PDF ที่ได้

 ตอนนี้เราได้แก้ไขคำอธิบายปุ่มตัวเลือกเสร็จแล้ว เราสามารถบันทึก PDF ที่ได้โดยใช้`Save` วิธีการของ`Document` ระดับ.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

อย่าลืมระบุเส้นทางเต็มและชื่อไฟล์สำหรับ PDF ที่ได้

### ตัวอย่างโค้ดที่มาสำหรับการตั้งค่าคำบรรยายปุ่มตัวเลือกโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// โหลดซอร์สฟอร์ม PDF
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
foreach (var item in form1.FieldNames)
{
	Console.WriteLine(item.ToString());
	Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
	if (item.Contains("radio1"))
	{
		Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
		Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
		fieldoption.OptionName = "Yes";
		fieldoption.PartialName = "Yesname";
		var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
		updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
		updatedFragment.TextState.FontSize = 10;
		updatedFragment.TextState.LineSpacing = 6.32f;
		// สร้างวัตถุ TextParagraph
		TextParagraph par = new TextParagraph();
		// ตั้งค่าตำแหน่งย่อหน้า
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// ระบุโหมดการห่อคำ
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// เพิ่ม TextFragment ใหม่ลงในย่อหน้า
		par.AppendLine(updatedFragment);
		// เพิ่ม TextParagraph โดยใช้ TextBuilder
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## บทสรุป

ในคู่มือนี้ เราได้เรียนรู้วิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อตั้งค่าคำบรรยายสำหรับปุ่มตัวเลือกในแบบฟอร์ม PDF โดยทำตามขั้นตอนที่อธิบายไว้ คุณสามารถปรับแต่งตัวเลือกปุ่มตัวเลือกและเปลี่ยนคำบรรยายตามต้องการได้ อย่าลังเลที่จะสำรวจคุณสมบัติของ Aspose.PDF สำหรับ .NET เพิ่มเติมเพื่อขยายความเป็นไปได้ในการจัดการไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: ฉันสามารถใช้ Aspose.PDF สำหรับ .NET เพื่อตั้งค่าคำบรรยายสำหรับปุ่มตัวเลือกในแบบฟอร์ม PDF ได้หรือไม่

A: ใช่ คุณสามารถใช้ Aspose.PDF สำหรับ .NET เพื่อตั้งค่าคำบรรยายสำหรับปุ่มตัวเลือกในแบบฟอร์ม PDF ได้ โค้ดต้นฉบับตัวอย่างที่ให้มาจะสาธิตวิธีการเข้าถึงฟิลด์ปุ่มตัวเลือก สร้างตัวเลือกปุ่มตัวเลือกใหม่พร้อมคำบรรยายแบบกำหนดเอง และอัปเดตฟิลด์ที่มีอยู่

#### ถาม: ฉันจะปรับแต่งลักษณะที่ปรากฏของคำอธิบายปุ่มตัวเลือก เช่น ขนาดตัวอักษรและสี ได้อย่างไร

 A: คุณสามารถปรับแต่งลักษณะของคำอธิบายปุ่มตัวเลือกได้โดยการปรับคุณสมบัติของ`TextFragment` ใช้สำหรับคำบรรยาย เช่น คุณสามารถตั้งค่าแบบอักษร ขนาดแบบอักษร สี ระยะห่างระหว่างบรรทัด และตัวเลือกการจัดรูปแบบข้อความอื่น ๆ

#### ถาม: เป็นไปได้ไหมที่จะเพิ่มตัวเลือกปุ่มตัวเลือกหลายปุ่มพร้อมคำอธิบายที่แตกต่างกันลงในกลุ่มปุ่มตัวเลือกเดียว?

A: ใช่ คุณสามารถเพิ่มตัวเลือกปุ่มตัวเลือกหลายรายการพร้อมคำอธิบายที่แตกต่างกันลงในกลุ่มปุ่มตัวเลือกเดียวได้ แต่ละตัวเลือกจะแสดงถึงทางเลือกที่แตกต่างกัน และผู้ใช้สามารถเลือกได้เพียงหนึ่งตัวเลือกจากกลุ่มนั้น

#### ถาม: ฉันสามารถใช้ Aspose.PDF สำหรับ .NET เพื่อปรับเปลี่ยนฟิลด์ฟอร์มอื่นๆ ในเอกสาร PDF ได้หรือไม่

A: ใช่ Aspose.PDF สำหรับ .NET มีชุดฟีเจอร์ที่ครอบคลุมสำหรับจัดการฟิลด์ฟอร์มต่างๆ ในเอกสาร PDF เช่น ฟิลด์ข้อความ ช่องกาเครื่องหมาย รายการดร็อปดาวน์ และอื่นๆ คุณสามารถใช้ไลบรารีเพื่อตั้งค่า แก้ไขรูปลักษณ์ และเพิ่มการโต้ตอบให้กับฟิลด์ฟอร์มได้

#### ถาม: Aspose.PDF สำหรับ .NET รองรับการทำงานกับ PDF ที่สร้างจากแหล่งอื่น เช่น เอกสารที่สแกน หรือไม่

A: ใช่ Aspose.PDF สำหรับ .NET รองรับการทำงานกับ PDF ที่สร้างจากแหล่งต่างๆ รวมถึงเอกสารที่สแกน ไลบรารีนี้มีฟีเจอร์ OCR (Optical Character Recognition) เพื่อแยกข้อความจาก PDF ที่สแกนและจัดการเนื้อหาด้วยโปรแกรม