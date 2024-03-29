---
title: ค้นหาข้อความและวาดรูปสี่เหลี่ยมผืนผ้า
linktitle: ค้นหาข้อความและวาดรูปสี่เหลี่ยมผืนผ้า
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีค้นหาข้อความใน PDF วาดรูปสี่เหลี่ยมรอบข้อความที่พบ และบันทึกเอกสารที่แก้ไขโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 460
url: /th/net/programming-with-text/search-text-and-draw-rectangle/
---
บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.PDF สำหรับ .NET เพื่อค้นหาข้อความเฉพาะในเอกสาร PDF วาดรูปสี่เหลี่ยมผืนผ้ารอบข้อความที่พบ และบันทึกเอกสารที่แก้ไข ซอร์สโค้ด C# ที่ให้มาสาธิตกระบวนการทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่จะดำเนินการบทแนะนำต่อ โปรดแน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้ง Aspose.PDF สำหรับไลบรารี .NET แล้ว คุณสามารถรับได้จากเว็บไซต์ Aspose หรือใช้ NuGet เพื่อติดตั้งในโครงการของคุณ

## ขั้นตอนที่ 1: ตั้งค่าโครงการ

เริ่มต้นด้วยการสร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบรวม (IDE) ที่คุณต้องการ และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น

เพิ่มคำสั่งต่อไปนี้ที่จุดเริ่มต้นของไฟล์ C# ของคุณเพื่อนำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## ขั้นตอนที่ 3: กำหนดเส้นทางไปยังไดเร็กทอรีเอกสาร

 กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณโดยใช้ไฟล์`dataDir` ตัวแปร:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 4: โหลดเอกสาร PDF

 โหลดเอกสาร PDF โดยใช้ไฟล์`Document` ระดับ:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 แทนที่`"SearchAndGetTextFromAll.pdf"` ด้วยชื่อจริงของไฟล์ PDF ของคุณ

## ขั้นตอนที่ 5: สร้าง TextFragmentAbsorber

 สร้างก`TextFragmentAbsorber` วัตถุเพื่อค้นหาทุกกรณีของวลีค้นหาอินพุต:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 แทนที่`@"[\S]+"` ด้วยรูปแบบนิพจน์ทั่วไปที่คุณต้องการ

## ขั้นตอนที่ 6: เปิดใช้งานการค้นหานิพจน์ทั่วไป

 เปิดใช้งานการค้นหานิพจน์ทั่วไปโดยการตั้งค่า`TextSearchOptions` คุณสมบัติตัวดูดซับ:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## ขั้นตอนที่ 7: ค้นหาในทุกหน้า

ยอมรับตัวดูดซับสำหรับทุกหน้าของเอกสาร:

```csharp
document.Pages.Accept(textAbsorber);
```

## ขั้นตอนที่ 8: วาดรูปสี่เหลี่ยมผืนผ้ารอบข้อความที่พบ

 สร้างก`PdfContentEditor` วัตถุและวนซ้ำส่วนข้อความที่ดึงมา วาดรูปสี่เหลี่ยมผืนผ้ารอบแต่ละส่วนของข้อความ:

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## ขั้นตอนที่ 9: บันทึกเอกสารที่แก้ไข

บันทึกเอกสารที่แก้ไข:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"SearchTextAndDrawRectangle_out.pdf"` ด้วยชื่อไฟล์เอาต์พุตที่ต้องการ

### ตัวอย่างซอร์สโค้ดสำหรับค้นหาข้อความและวาดรูปสี่เหลี่ยมผืนผ้าโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// สร้างวัตถุ TextAbsorber เพื่อค้นหาวลีทั้งหมดที่ตรงกับนิพจน์ทั่วไป
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีค้นหาข้อความที่ต้องการในเอกสาร PDF, วาดรูปสี่เหลี่ยมผืนผ้ารอบๆ ข้อความที่พบ และบันทึกเอกสารที่แก้ไขโดยใช้ Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอน ตั้งแต่การตั้งค่าโปรเจ็กต์ไปจนถึงการดำเนินการที่จำเป็น ตอนนี้คุณสามารถรวมโค้ดนี้เข้ากับโปรเจ็กต์ C# ของคุณเองเพื่อจัดการข้อความและวาดรูปสี่เหลี่ยมในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "ค้นหาข้อความและวาดรูปสี่เหลี่ยมผืนผ้า" คืออะไร

ตอบ: บทช่วยสอน "ค้นหาข้อความและวาดรูปสี่เหลี่ยมผืนผ้า" มีวัตถุประสงค์เพื่อแนะนำผู้ใช้ตลอดกระบวนการใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อค้นหาข้อความเฉพาะภายในเอกสาร PDF วาดรูปสี่เหลี่ยมรอบๆ ส่วนข้อความที่พบ และบันทึกข้อความที่แก้ไข เอกสาร. บทช่วยสอนให้คำแนะนำโดยละเอียดและตัวอย่างโค้ด C# เพื่อแสดงแต่ละขั้นตอนของกระบวนการ

#### ถาม: บทช่วยสอนนี้ช่วยในการวาดรูปสี่เหลี่ยมรอบข้อความเฉพาะในเอกสาร PDF อย่างไร

ตอบ: บทช่วยสอนนี้ให้คำแนะนำที่ครอบคลุมเกี่ยวกับวิธีค้นหาและวาดรูปสี่เหลี่ยมรอบๆ ส่วนข้อความเฉพาะภายในเอกสาร PDF โดยสาธิตกระบวนการตั้งค่าโปรเจ็กต์ การโหลดเอกสาร PDF การเปิดใช้งานการค้นหานิพจน์ทั่วไป การวาดรูปสี่เหลี่ยมรอบๆ ส่วนข้อความที่พบ และการบันทึก PDF ที่แก้ไข

#### ถาม: ข้อกำหนดเบื้องต้นใดบ้างที่จำเป็นในการปฏิบัติตามบทช่วยสอนนี้

ตอบ: ก่อนที่จะเริ่มบทช่วยสอน คุณควรมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# นอกจากนี้ คุณต้องติดตั้งไลบรารี Aspose.PDF สำหรับ .NET ด้วย คุณสามารถรับได้จากเว็บไซต์ Aspose หรือติดตั้งในโครงการของคุณโดยใช้ NuGet

#### ถาม: ฉันจะตั้งค่าโปรเจ็กต์ให้ปฏิบัติตามบทช่วยสอนนี้ได้อย่างไร

ตอบ: เริ่มต้นด้วยการสร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบรวม (IDE) ที่คุณต้องการ จากนั้น เพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET ให้กับโปรเจ็กต์ของคุณ ซึ่งจะทำให้คุณสามารถใช้ฟังก์ชันการทำงานของไลบรารีเพื่อจัดการเอกสาร PDF ได้

#### ถาม: ฉันสามารถวาดรูปสี่เหลี่ยมรอบข้อความที่ต้องการโดยใช้บทช่วยสอนนี้ได้หรือไม่

ตอบ: ใช่ บทช่วยสอนนี้เน้นที่การวาดสี่เหลี่ยมรอบๆ ส่วนข้อความเฉพาะภายในเอกสาร PDF โดยจะสาธิตวิธีการค้นหาข้อความที่ต้องการโดยใช้นิพจน์ทั่วไป สร้างสี่เหลี่ยมรอบส่วนของข้อความที่ระบุ และบันทึก PDF ที่แก้ไขแล้ว

#### ถาม: ฉันจะระบุข้อความที่ต้องการค้นหาและวาดรูปสี่เหลี่ยมรอบๆ ได้อย่างไร

 ตอบ: หากต้องการระบุข้อความที่คุณต้องการค้นหาและวาดรูปสี่เหลี่ยมรอบๆ ให้สร้าง`TextFragmentAbsorber` วัตถุและกำหนดรูปแบบโดยใช้`Text` พารามิเตอร์. แทนที่รูปแบบเริ่มต้น`@"[\S]+"` ในโค้ดของบทช่วยสอนด้วยรูปแบบนิพจน์ทั่วไปที่คุณต้องการ

#### ถาม: ฉันจะเปิดใช้งานการค้นหาข้อความด้วยนิพจน์ทั่วไปได้อย่างไร

 ตอบ: การค้นหานิพจน์ทั่วไปเปิดใช้งานได้โดยการสร้าง`TextSearchOptions` วัตถุและตั้งค่าเป็น`true` . กำหนดวัตถุนี้ให้กับ`TextSearchOptions` ทรัพย์สินของ`TextFragmentAbsorber` ตัวอย่าง. เพื่อให้แน่ใจว่ามีการใช้รูปแบบนิพจน์ทั่วไปในระหว่างการค้นหาข้อความ

#### ถาม: ฉันจะวาดรูปสี่เหลี่ยมรอบๆ ข้อความที่พบได้อย่างไร

 ตอบ: หลังจากระบุส่วนของข้อความโดยใช้`TextFragmentAbsorber` บทช่วยสอนจะให้การวนซ้ำเพื่อวนซ้ำส่วนต่างๆ เหล่านี้ สำหรับแต่ละส่วนของข้อความ บทช่วยสอนจะสาธิตวิธีสร้างสี่เหลี่ยมรอบๆ ข้อความโดยใช้`DrawBox` วิธีการและระบุลักษณะของสี่เหลี่ยม

#### ถาม: ขั้นตอนในการบันทึก PDF ที่แก้ไขด้วยสี่เหลี่ยมที่วาดคืออะไร

ตอบ: หลังจากวาดรูปสี่เหลี่ยมรอบๆ ส่วนข้อความที่ต้องการแล้ว ให้ใช้`Document` ชั้นเรียน`Save` วิธีการบันทึกเอกสารที่แก้ไข โค้ดตัวอย่างของบทช่วยสอนจะแสดงวิธีบันทึก PDF ที่แก้ไขแล้วและแสดงข้อความแสดงความสำเร็จ

#### ถาม: ฉันสามารถปรับแต่งลักษณะของสี่เหลี่ยมที่วาดออกมาได้หรือไม่

 ตอบ: ได้ คุณสามารถปรับแต่งลักษณะของสี่เหลี่ยมที่วาดได้ ในโค้ดตัวอย่างของบทช่วยสอน`DrawBox` วิธีการใช้ในการสร้างสี่เหลี่ยม คุณสามารถแก้ไขคุณสมบัติ เช่น สี สไตล์ และความหนา เพื่อปรับแต่งลักษณะของสี่เหลี่ยมที่วาดได้