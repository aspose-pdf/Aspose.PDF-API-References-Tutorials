---
title: เพิ่มคำแนะนำเครื่องมือเป็นข้อความในไฟล์ PDF
linktitle: เพิ่มคำแนะนำเครื่องมือเป็นข้อความในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีเพิ่มคำแนะนำเครื่องมือให้กับข้อความในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 90
url: /th/net/programming-with-text/add-tooltip-to-text/
---
บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการเพิ่มคำแนะนำเครื่องมือให้กับข้อความในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ซอร์สโค้ด C# ที่ให้มาสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ที่ติดตั้งบนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose หรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการเพิ่มคำแนะนำเครื่องมือลงในข้อความ ให้เพิ่มคำสั่งต่อไปนี้โดยใช้คำสั่งที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเร็กทอรีเอกสาร
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่เก็บเอกสารของคุณ

## ขั้นตอนที่ 4: สร้างเอกสารตัวอย่างพร้อมข้อความ
 สร้างใหม่`Document` วัตถุและเพิ่มหน้าที่มีส่วนของข้อความ ในโค้ดที่ให้มา ส่วนของข้อความสองส่วนจะถูกเพิ่มลงในเอกสารพร้อมกับข้อความคำแนะนำเครื่องมือที่เกี่ยวข้อง

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## ขั้นตอนที่ 5: เปิดเอกสารและค้นหาส่วนของข้อความ
 โหลดเอกสารที่สร้างขึ้นโดยใช้`Document` Constructor และค้นหาส่วนของข้อความที่ต้องใช้คำแนะนำเครื่องมือ`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## ขั้นตอนที่ 6: เพิ่มคำแนะนำเครื่องมือให้กับส่วนของข้อความ
 วนซ้ำส่วนข้อความที่แยกออกมา และสร้างปุ่มที่มองไม่เห็นในตำแหน่งของมัน กำหนดข้อความคำแนะนำเครื่องมือที่ต้องการให้กับ`AlternateName` ทรัพย์สินของ`ButtonField`. เพิ่มฟิลด์ปุ่มลงในแบบฟอร์มของเอกสาร

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## ขั้นตอนที่ 7: ทำซ้ำสำหรับส่วนข้อความเพิ่มเติมพร้อมคำแนะนำเครื่องมือแบบยาว
ทำซ้ำขั้นตอนที่ 5 และ 6 สำหรับส่วนของข้อความที่มีคำแนะนำเครื่องมือแบบยาว แก้ไขเกณฑ์การค้นหาและข้อความคำแนะนำเครื่องมือตามลำดับ

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
 บันทึกเอกสาร PDF ที่แก้ไขโดยใช้ไฟล์`Save` วิธีการของ`Document` วัตถุ.

```csharp
document. Save(outputFile);
```

### ตัวอย่างซอร์สโค้ดสำหรับเพิ่มคำแนะนำเครื่องมือลงในข้อความโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// สร้างเอกสารตัวอย่างพร้อมข้อความ
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// เปิดเอกสารพร้อมข้อความ
Document document = new Document(outputFile);
// สร้างวัตถุ TextAbsorber เพื่อค้นหาวลีทั้งหมดที่ตรงกับนิพจน์ทั่วไป
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// ยอมรับตัวดูดซับสำหรับหน้าเอกสาร
document.Pages.Accept(absorber);
// รับส่วนของข้อความที่แยกออกมา
TextFragmentCollection textFragments = absorber.TextFragments;
// วนผ่านชิ้นส่วน
foreach (TextFragment fragment in textFragments)
{
	// สร้างปุ่มที่มองไม่เห็นในตำแหน่งส่วนของข้อความ
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// ค่า AlternateName จะแสดงเป็นคำแนะนำเครื่องมือโดยแอปพลิเคชันตัวแสดง
	field.AlternateName = "Tooltip for text.";
	// เพิ่มช่องปุ่มลงในเอกสาร
	document.Form.Add(field);
}
// ถัดไปจะเป็นตัวอย่างคำแนะนำเครื่องมือที่ยาวมาก
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
คุณได้เพิ่มคำแนะนำเครื่องมือลงในข้อความในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว ขณะนี้ไฟล์ PDF ที่เป็นผลลัพธ์สามารถพบได้ที่เส้นทางไฟล์เอาต์พุตที่ระบุ

## คำถามที่พบบ่อย

#### ถาม: บทช่วยสอนนี้เน้นอะไร

ตอบ: บทช่วยสอนนี้เน้นที่การเพิ่มคำแนะนำเครื่องมือให้กับข้อความภายในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับไลบรารี .NET ซอร์สโค้ด C# ที่ให้มาสาธิตขั้นตอนที่จำเป็นเพื่อให้บรรลุเป้าหมายนี้

#### ถาม: เนมสเปซใดบ้างที่ต้องนำเข้าสำหรับบทช่วยสอนนี้

ตอบ: ในไฟล์โค้ดที่คุณต้องการเพิ่มคำแนะนำเครื่องมือลงในข้อความ ให้นำเข้าเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารได้อย่างไร

 ตอบ: ในโค้ด ให้ค้นหาบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะสร้างเอกสารตัวอย่างพร้อมข้อความได้อย่างไร

 ตอบ: ในขั้นตอนที่ 4 คุณจะสร้างใหม่`Document` วัตถุและเพิ่มหน้าที่มีส่วนของข้อความ รหัสที่ให้มาจะเพิ่มส่วนข้อความสองส่วนพร้อมข้อความคำแนะนำเครื่องมือตามลำดับ

#### ถาม: ฉันจะเปิดเอกสารและค้นหาส่วนของข้อความได้อย่างไร

 ตอบ: ในขั้นตอนที่ 5 คุณจะโหลดเอกสารที่สร้างขึ้นโดยใช้`Document` ตัวสร้างและค้นหาส่วนของข้อความที่ต้องการคำแนะนำเครื่องมือโดยใช้`TextFragmentAbsorber`.

#### ถาม: ฉันจะเพิ่มคำแนะนำเครื่องมือให้กับส่วนของข้อความได้อย่างไร

 ตอบ: ในขั้นตอนที่ 6 คุณจะวนซ้ำส่วนข้อความที่แยกออกมา และสร้างปุ่มที่มองไม่เห็นในตำแหน่งนั้น ข้อความคำแนะนำเครื่องมือถูกกำหนดให้กับ`AlternateName` ทรัพย์สินของ`ButtonField`ซึ่งเพิ่มลงในแบบฟอร์มของเอกสาร

#### ถาม: ฉันจะทำซ้ำขั้นตอนสำหรับส่วนย่อยของข้อความเพิ่มเติมที่มีคำแนะนำเครื่องมือขนาดยาวได้อย่างไร

ตอบ: สำหรับส่วนของข้อความที่มีคำแนะนำเครื่องมือยาว ให้ทำซ้ำขั้นตอนที่ 5 และ 6 แก้ไขเกณฑ์การค้นหาและข้อความคำแนะนำเครื่องมือตามลำดับ

#### ถาม: ฉันจะบันทึกเอกสารที่แก้ไขได้อย่างไร

 ตอบ: ในขั้นตอนที่ 8 คุณจะบันทึกเอกสาร PDF ที่แก้ไขแล้วโดยใช้นามสกุลไฟล์`Save` วิธีการของ`Document` วัตถุ.

#### ถาม: สิ่งสำคัญที่ได้รับจากบทช่วยสอนนี้คืออะไร

ตอบ: ด้วยการทำตามบทช่วยสอนนี้ คุณได้เรียนรู้วิธีปรับปรุงเอกสาร PDF ของคุณโดยการเพิ่มคำแนะนำเครื่องมือให้กับข้อความโดยใช้ Aspose.PDF สำหรับ .NET ข้อมูลนี้สามารถให้ข้อมูลเพิ่มเติมอันมีค่าแก่ผู้อ่านเมื่อพวกเขาโต้ตอบกับเนื้อหา PDF