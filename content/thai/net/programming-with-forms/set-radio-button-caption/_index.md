---
title: ตั้งค่าคำบรรยายปุ่มตัวเลือก
linktitle: ตั้งค่าคำบรรยายปุ่มตัวเลือก
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อตั้งค่าคำบรรยายสำหรับปุ่มตัวเลือกในรูปแบบ PDF
type: docs
weight: 280
url: /th/net/programming-with-forms/set-radio-button-caption/
---
ในคู่มือนี้ เราจะอธิบายทีละขั้นตอนวิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อกำหนดคำอธิบายภาพของปุ่มตัวเลือกในรูปแบบ PDF เราจะแสดงวิธีการเข้าถึงฟิลด์ปุ่มตัวเลือก สร้างตัวเลือกปุ่มตัวเลือกใหม่ และปรับแต่งคำอธิบายภาพของปุ่ม

## ขั้นตอนที่ 1: การกำหนดค่าไดเร็กทอรีเอกสาร

 ขั้นตอนแรกคือการกำหนดค่าไดเร็กทอรีเอกสารซึ่งมีแบบฟอร์ม PDF ที่คุณต้องการใช้งาน คุณสามารถใช้`dataDir` ตัวแปรเพื่อระบุเส้นทางไดเรกทอรี

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 อย่าลืมเปลี่ยน`"YOUR DOCUMENTS DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 2: กำลังโหลดแบบฟอร์ม PDF ต้นฉบับ

 ในขั้นตอนนี้ เราจะโหลดแบบฟอร์ม PDF ต้นฉบับโดยใช้ไฟล์`Aspose.Pdf.Facades.Form` คลาสของ Aspose.PDF

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

ตรวจสอบให้แน่ใจว่าไฟล์ PDF ที่มีแบบฟอร์มนั้นมีอยู่ในไดเร็กทอรีเอกสารที่ระบุ

## ขั้นตอนที่ 3: การแก้ไขคำอธิบายปุ่มตัวเลือก

เราจะวนซ้ำชื่อฟิลด์ของฟอร์มและค้นหาฟิลด์ปุ่มตัวเลือก หากพบฟิลด์ที่ตรงกัน เราจะสร้างตัวเลือกปุ่มตัวเลือกใหม่พร้อมคำอธิบายภาพที่กำหนดเอง และเพิ่มลงในฟิลด์ที่มีอยู่

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
// กำหนดตำแหน่งย่อหน้า
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// ระบุโหมดการตัดคำ
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

ปรับแต่งปุ่มตัวเลือกคำอธิบายภาพและการตั้งค่าอื่นๆ ตามต้องการ

## ขั้นตอนที่ 4: บันทึก PDF ที่ได้

 ตอนนี้เราแก้ไขคำอธิบายปุ่มตัวเลือกเสร็จแล้ว เราสามารถบันทึกไฟล์ PDF ที่ได้โดยใช้`Save` วิธีการของ`Document` ระดับ.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

อย่าลืมระบุเส้นทางแบบเต็มและชื่อไฟล์สำหรับ PDF ที่ได้

### ตัวอย่างซอร์สโค้ดสำหรับตั้งค่าคำบรรยายปุ่มตัวเลือกโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// โหลดแบบฟอร์ม PDF แหล่งที่มา
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
		// กำหนดตำแหน่งย่อหน้า
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// ระบุโหมดการตัดคำ
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

ในคู่มือนี้ เราได้เรียนรู้วิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อตั้งค่าคำบรรยายสำหรับปุ่มตัวเลือกในรูปแบบ PDF ด้วยการทำตามขั้นตอนที่อธิบายไว้ คุณสามารถปรับแต่งตัวเลือกปุ่มตัวเลือกและเปลี่ยนคำอธิบายภาพได้ตามต้องการ สำรวจฟีเจอร์ของ Aspose.PDF สำหรับ .NET เพิ่มเติมได้ตามสบาย เพื่อขยายความเป็นไปได้ในการจัดการไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: ฉันสามารถใช้ Aspose.PDF สำหรับ .NET เพื่อตั้งค่าคำบรรยายสำหรับปุ่มตัวเลือกในรูปแบบ PDF ได้หรือไม่

ตอบ: ได้ คุณสามารถใช้ Aspose.PDF สำหรับ .NET เพื่อตั้งค่าคำบรรยายสำหรับปุ่มตัวเลือกในรูปแบบ PDF ซอร์สโค้ดตัวอย่างที่ให้มาสาธิตวิธีการเข้าถึงฟิลด์ปุ่มตัวเลือก สร้างตัวเลือกปุ่มตัวเลือกใหม่พร้อมคำบรรยายที่กำหนดเอง และอัปเดตฟิลด์ที่มีอยู่

#### ถาม: ฉันจะปรับแต่งลักษณะที่ปรากฏของคำอธิบายปุ่มตัวเลือก เช่น ขนาดตัวอักษรและสีได้อย่างไร

 ตอบ: คุณสามารถปรับแต่งลักษณะที่ปรากฏของคำอธิบายปุ่มตัวเลือกได้โดยการปรับคุณสมบัติของ`TextFragment` ใช้สำหรับคำบรรยายภาพ ตัวอย่างเช่น คุณสามารถตั้งค่าแบบอักษร ขนาดแบบอักษร สี ระยะห่างบรรทัด และตัวเลือกการจัดรูปแบบข้อความอื่นๆ ได้

#### ถาม: เป็นไปได้ไหมที่จะเพิ่มตัวเลือกปุ่มตัวเลือกหลายปุ่มพร้อมคำบรรยายที่แตกต่างกันในกลุ่มปุ่มตัวเลือกเดียว

ตอบ: ได้ คุณสามารถเพิ่มตัวเลือกปุ่มตัวเลือกได้หลายตัวเลือกพร้อมคำอธิบายภาพที่แตกต่างกันในกลุ่มปุ่มตัวเลือกเดียว แต่ละตัวเลือกจะแสดงตัวเลือกที่แตกต่างกัน และผู้ใช้สามารถเลือกได้เพียงตัวเลือกเดียวจากกลุ่ม

#### ถาม: ฉันสามารถใช้ Aspose.PDF สำหรับ .NET เพื่อแก้ไขฟิลด์แบบฟอร์มอื่นๆ ในเอกสาร PDF ได้หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET มีชุดคุณสมบัติที่ครอบคลุมเพื่อจัดการฟิลด์แบบฟอร์มต่างๆ ในเอกสาร PDF เช่น ฟิลด์ข้อความ กล่องกาเครื่องหมาย รายการดรอปดาวน์ และอื่นๆ คุณสามารถใช้ไลบรารีเพื่อตั้งค่า ปรับเปลี่ยนลักษณะที่ปรากฏ และเพิ่มการโต้ตอบลงในฟิลด์ของแบบฟอร์มได้

#### ถาม: Aspose.PDF สำหรับ .NET รองรับการทำงานกับ PDF ที่สร้างจากแหล่งอื่น เช่น เอกสารที่สแกนหรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET รองรับการทำงานกับ PDF ที่สร้างจากแหล่งต่างๆ รวมถึงเอกสารที่สแกนด้วย ไลบรารีมีความสามารถ OCR (Optical Character Recognition) เพื่อแยกข้อความจาก PDF ที่สแกนและจัดการเนื้อหาโดยทางโปรแกรม