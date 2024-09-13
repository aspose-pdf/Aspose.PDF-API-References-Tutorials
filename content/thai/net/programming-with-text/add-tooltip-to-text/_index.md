---
title: เพิ่มคำอธิบายเครื่องมือลงในข้อความในไฟล์ PDF
linktitle: เพิ่มคำอธิบายเครื่องมือลงในข้อความในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการเพิ่มคำอธิบายเครื่องมือลงในข้อความในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 90
url: /th/net/programming-with-text/add-tooltip-to-text/
---
บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับขั้นตอนการเพิ่มคำอธิบายเครื่องมือลงในข้อความในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ติดตั้งอยู่บนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose อย่างเป็นทางการหรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโครงการ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการเพิ่มคำอธิบายเครื่องมือลงในข้อความ ให้เพิ่มคำสั่ง using ต่อไปนี้ที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเรกทอรีเอกสาร
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่คุณเก็บเอกสารไว้

## ขั้นตอนที่ 4: สร้างเอกสารตัวอย่างด้วยข้อความ
 สร้างใหม่`Document`วัตถุและเพิ่มหน้าที่มีข้อความแยกส่วน ในโค้ดที่ให้มา จะมีการเพิ่มข้อความแยกส่วนสองส่วนลงในเอกสารพร้อมข้อความคำอธิบายที่เกี่ยวข้อง

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## ขั้นตอนที่ 5: เปิดเอกสารและค้นหาชิ้นส่วนข้อความ
 โหลดเอกสารที่สร้างขึ้นโดยใช้`Document` ผู้สร้างและค้นหาชิ้นส่วนข้อความที่ต้องการคำแนะนำโดยใช้`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## ขั้นตอนที่ 6: เพิ่มคำอธิบายเครื่องมือลงในชิ้นส่วนข้อความ
 วนซ้ำผ่านชิ้นส่วนข้อความที่แยกออกมาและสร้างปุ่มที่มองไม่เห็นในตำแหน่งของปุ่มเหล่านั้น กำหนดข้อความคำอธิบายเครื่องมือที่ต้องการให้กับ`AlternateName` ทรัพย์สินของ`ButtonField`. เพิ่มช่องปุ่มลงในแบบฟอร์มของเอกสาร

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## ขั้นตอนที่ 7: ทำซ้ำสำหรับข้อความเพิ่มเติมที่มีคำแนะนำยาว
ทำซ้ำขั้นตอนที่ 5 และ 6 สำหรับข้อความที่มีคำอธิบายยาว แก้ไขเกณฑ์การค้นหาและข้อความคำอธิบายให้เหมาะสม

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## ขั้นตอนที่ 8: บันทึกเอกสารที่แก้ไข
 บันทึกเอกสาร PDF ที่แก้ไขแล้วโดยใช้`Save` วิธีการของ`Document` วัตถุ.

```csharp
document. Save(outputFile);
```

### ตัวอย่างโค้ดที่มาสำหรับการเพิ่มคำอธิบายเครื่องมือลงในข้อความโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// สร้างเอกสารตัวอย่างด้วยข้อความ
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// เปิดเอกสารที่มีข้อความ
Document document = new Document(outputFile);
//สร้างวัตถุ TextAbsorber เพื่อค้นหาวลีทั้งหมดที่ตรงกับนิพจน์ทั่วไป
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// รับตัวดูดซับหน้าเอกสาร
document.Pages.Accept(absorber);
// รับชิ้นส่วนข้อความที่แยกออกมา
TextFragmentCollection textFragments = absorber.TextFragments;
// วนผ่านชิ้นส่วน
foreach (TextFragment fragment in textFragments)
{
	// สร้างปุ่มที่มองไม่เห็นบนตำแหน่งของชิ้นส่วนข้อความ
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// ค่า AlternateName จะแสดงเป็นคำแนะนำโดยแอปพลิเคชันตัวแสดง
	field.AlternateName = "Tooltip for text.";
	// เพิ่มช่องปุ่มลงในเอกสาร
	document.Form.Add(field);
}
// ต่อไปจะเป็นตัวอย่างของ tooltip ที่ยาวมาก
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// ตั้งข้อความยาวมาก
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
// บันทึกเอกสาร
document.Save(outputFile);
```

## บทสรุป
คุณได้เพิ่มคำอธิบายเครื่องมือลงในข้อความในเอกสาร PDF สำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้สามารถพบไฟล์ PDF ที่ได้ในเส้นทางไฟล์เอาต์พุตที่ระบุ

## คำถามที่พบบ่อย

#### ถาม: บทช่วยสอนนี้เน้นอะไร?

A: บทช่วยสอนนี้มุ่งเน้นที่การเพิ่มคำอธิบายเครื่องมือลงในข้อความภายในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนที่จำเป็นในการบรรลุผลดังกล่าว

#### ถาม: จำเป็นต้องนำเข้าเนมสเปซใดสำหรับบทช่วยสอนนี้

ก: ในไฟล์โค้ดที่คุณต้องการเพิ่มคำอธิบายลงในข้อความ นำเข้าเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารได้อย่างไร?

 ก: ในโค้ด ให้หาบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะสร้างเอกสารตัวอย่างที่มีข้อความได้อย่างไร

 A: ในขั้นตอนที่ 4 คุณจะสร้างใหม่`Document` วัตถุและเพิ่มหน้าที่มีข้อความแยกส่วน รหัสที่ให้มาจะเพิ่มข้อความแยกส่วนสองส่วนพร้อมข้อความคำอธิบายที่เกี่ยวข้อง

#### ถาม: ฉันจะเปิดเอกสารและค้นหาชิ้นส่วนข้อความได้อย่างไร

 ก: ในขั้นตอนที่ 5 คุณจะโหลดเอกสารที่สร้างขึ้นโดยใช้`Document` ผู้สร้างและค้นหาชิ้นส่วนข้อความที่ต้องการคำแนะนำโดยใช้`TextFragmentAbsorber`.

#### ถาม: ฉันจะเพิ่มคำแนะนำลงในชิ้นส่วนข้อความได้อย่างไร

 A: ในขั้นตอนที่ 6 คุณจะวนซ้ำผ่านชิ้นส่วนข้อความที่แยกออกมาและสร้างปุ่มที่มองไม่เห็นในตำแหน่งของปุ่มเหล่านั้น ข้อความคำอธิบายเครื่องมือจะถูกกำหนดให้กับ`AlternateName` ทรัพย์สินของ`ButtonField`ซึ่งจะถูกเพิ่มเข้าในแบบเอกสาร

#### ถาม: ฉันจะทำซ้ำขั้นตอนสำหรับส่วนข้อความเพิ่มเติมที่มีคำแนะนำยาวได้อย่างไร

A: สำหรับชิ้นส่วนข้อความที่มีคำแนะนำยาว ให้ทำซ้ำขั้นตอนที่ 5 และ 6 แก้ไขเกณฑ์การค้นหาและข้อความคำแนะนำให้เหมาะสม

#### ถาม: ฉันจะบันทึกเอกสารที่แก้ไขได้อย่างไร

 ก: ในขั้นตอนที่ 8 คุณจะบันทึกเอกสาร PDF ที่แก้ไขแล้วโดยใช้`Save` วิธีการของ`Document` วัตถุ.

#### ถาม: สิ่งสำคัญที่สุดที่ได้จากบทช่วยสอนนี้คืออะไร?

A: เมื่อทำตามบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีปรับปรุงเอกสาร PDF ของคุณโดยการเพิ่มคำอธิบายเครื่องมือลงในข้อความโดยใช้ Aspose.PDF สำหรับ .NET ซึ่งสามารถให้ข้อมูลเพิ่มเติมอันมีค่าแก่ผู้อ่านเมื่อพวกเขาโต้ตอบกับเนื้อหา PDF